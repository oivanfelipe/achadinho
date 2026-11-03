# Automação do Achei Promo: especificação técnica

> Complementa `estrategia/plano-lancamento-12-12.md`.
> Legenda de confiança: ✅ verificado em código/fonte lida · ⚠️ vem de fonte secundária ou de memória, validar antes de depender · 🛠️ decisão de design minha.

---

## 1. Objetivo e princípios

Entregar 5 a 7 ofertas por dia, em horários fixos, sem que a operação vire um trabalho em tempo integral. Meta de esforço: **30 a 45 minutos por dia** (revisar e aprovar), contra as 4 a 6 horas que as fontes citam para o processo manual.

Princípios de design 🛠️:

1. **Telegram primeiro, WhatsApp depois.** Telegram tem API oficial de bots. O pipeline é testado ali, sem risco de ban, e só então ganha o destino WhatsApp.
2. **Humano no meio.** Fila → aprovação com 1 clique → agendamento. O sistema sugere, você decide.
3. **Rastreio em tudo.** Cada link carrega subIds (canal, grupo, categoria, horário). Sem isso não há otimização.
4. **Falha segura.** Se o gateway de WhatsApp cair ou o número for restrito, o resto continua (Telegram, Canal).
5. **Nada de segredo no repositório.** Credenciais em variáveis de ambiente do Vercel/Supabase.

---

## 2. Arquitetura

```
 FONTES                 PROCESSAMENTO                       SAÍDAS
 ------                 -------------                       ------
 Shopee Open API  ──┐
 (productOfferV2)   │
 Painel ML (manual) ├─► coleta ─► normaliza ─► filtro/score ─► gera link ─► copy (LLM)
 Amazon (manual)    │    (cron)    (Supabase)   (regras)       (API/painel)   │
 Radar: Promobit,   │                                                         ▼
 Telegram, Pelando ─┘                                                  FILA (status: draft)
 (só inspiração,                                                              │
  sem copiar texto)                                                           ▼
                                                              Bot de Telegram do dono
                                                              [Aprovar] [Editar] [Pular]
                                                                              │
                                                                              ▼
                                                              AGENDADOR (Vercel Cron / n8n)
                                                          ┌───────────────────┼────────────────────┐
                                                          ▼                   ▼                    ▼
                                                  Canal Telegram      WhatsApp (gateway)    Canal WhatsApp
                                                  (Bot API oficial)   número dedicado       (manual / ⚠️)
                                                                              │
                                                                              ▼
                                                              TRACKING: conversionReport + subIds
                                                              ─► Supabase ─► dashboard (planilha/Vercel)
```

---

## 3. Fontes de oferta

| Fonte | Como usar | Automatizável? | Cuidado |
|---|---|---|---|
| Shopee Open Platform | Ofertas ordenadas por comissão/vendas | Sim (API) | Exige conta de afiliado aprovada e credenciais |
| Mercado Livre | Painel de afiliados | **Manual** (nenhuma fonte citou API de link) | Gerar link por canal; verificar parâmetro de rastreio sobrevivendo ao encurtador |
| Amazon | SiteStripe / painel | Manual | PA-API foi substituída pela Creators API; as fontes citam exigências de vendas para ter acesso ⚠️ |
| Promobit, Pelando, Hardmob, canais de Telegram | **Radar de produto** | Não copiar texto nem imagem | Termos de uso e direitos autorais. Use para descobrir *o que* está em alta, depois monte a oferta do zero |
| Páginas "Ofertas do dia" dos marketplaces | Descoberta | Parcial | Respeitar robots.txt e termos; preferir API quando existir |

Telegram como *fonte*: o README lista 5 canais. Para ler canais públicos de forma automatizada você precisaria de uma conta de usuário (MTProto), não de bot, e isso é um risco de conta. Recomendo **ler manualmente 10 minutos por dia** como radar e deixar a coleta automática só na API da Shopee.

---

## 4. Shopee Affiliate Open API

### 4.1 O que está verificado

Fonte: wrapper Python `snja/shopee-affiliate-openapi` (arquivado em 19/10/2024, sem licença, **usa o endpoint da Indonésia**). Li o código inteiro.

- Autenticação ✅: SHA-256 de `appId + timestamp + corpo JSON + secret`.
- Header ✅: `Authorization: SHA256 Credential={appId}, Signature={hash}, Timestamp={ts}`.
- Mutation de link curto ✅ (aceita `subIds`):

```graphql
mutation {
  generateShortLink(input: { originUrl: "https://shopee.com.br/produto-i.123.456", subIds: ["wpp","g1","beleza","h1215",""] }) {
    shortLink
  }
}
```

- Relatório de conversões ✅ (paginado por `scrollId`):

```graphql
{
  conversionReport(purchaseTimeStart: 1760000000, purchaseTimeEnd: 1760086399, scrollId: "", limit: 500, orderStatus: ALL) {
    nodes { estimatedTotalCommission grossCommission cappedCommission totalBrandCommission checkoutId purchaseTime }
    pageInfo { scrollId hasNextPage }
  }
}
```

### 4.2 Verificado em código de terceiros e o que continua pendente

> **Atualização (rodada 2):** o endpoint do Brasil e os campos de `productOfferV2` agora estão verificados **em código de 4 repositórios** (ver `pesquisa-repos-termos-ferramentas.md`, seção 3). Continuam não sendo documentação oficial: confirme no painel quando as credenciais saírem.

- ✅ **Endpoint do Brasil:** `https://open-api.affiliate.shopee.com.br/graphql` (3 repositórios). Um deles manda copiar a URL do painel, pois pode variar por conta.
- ✅ **`productOfferV2`:** argumentos `keyword, itemId, shopId, sortType, page, limit`; campos `itemId shopId productName priceMin priceMax priceDiscountRate commissionRate sales ratingStar imageUrl shopName productLink offerLink` e `pageInfo { page limit hasNextPage }`. `sortType`: 1 relevância, 2 mais vendidos, 3 maior preço, 4 menor preço, **5 maior comissão**.
- ✅ **`shopeeOfferV2`:** lista campanhas (`offerName offerLink originalLink imageUrl periodStartTime periodEndTime`). Use para descobrir a campanha 12.12 e as datas.
- ✅ **Erro 10035:** conta sem acesso à Open API ainda. Os códigos 10020 e 10030 vieram de fonte secundária ⚠️. Nenhum cliente existente trata limite de requisições; implemente backoff exponencial.
- ⚠️ Tempo de aprovação da API: uma fonte fala 5 a 15 dias, outra fala 24 a 48 horas para a conta de afiliado (são aprovações diferentes). **Peça as credenciais agora.**

### 4.3 Cliente mínimo (Node 20, sem dependência) 🛠️

```js
import crypto from "node:crypto";

const ENDPOINT = process.env.SHOPEE_ENDPOINT
  ?? "https://open-api.affiliate.shopee.com.br/graphql"; // confirmar no painel
const APP_ID = process.env.SHOPEE_APP_ID;
const SECRET = process.env.SHOPEE_SECRET;

export async function shopeeGql(query) {
  const ts = Math.floor(Date.now() / 1000);
  const body = JSON.stringify({ query });
  const sig = crypto.createHash("sha256")
    .update(APP_ID + ts + body + SECRET).digest("hex");
  const res = await fetch(ENDPOINT, {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      Authorization: `SHA256 Credential=${APP_ID}, Signature=${sig}, Timestamp=${ts}`,
    },
    body, // o MESMO string usado na assinatura
  });
  const json = await res.json();
  if (json.errors) throw new Error(JSON.stringify(json.errors));
  return json.data;
}
```

Armadilha ✅: o corpo enviado precisa ser byte a byte o mesmo que foi assinado.

### 4.4 Esquema de subIds 🛠️ (até 5 posições)

| Posição | Conteúdo | Exemplo |
|---|---|---|
| 1 | Canal | `wpp`, `tg`, `ig`, `tt` |
| 2 | Grupo | `g1`, `g2`, `canal` |
| 3 | Categoria | `beleza`, `casa` |
| 4 | Horário/slot | `h0830`, `h1215` |
| 5 | Tipo/experimento | `a`, `b`, `bf`, `1212` |

Isso responde "qual horário e categoria faz mais clique" direto no relatório.

---

## 5. Mercado Livre e Amazon (operação semiautomática)

- **ML:** não existe API de link. Um repositório anexa `matt_word` e `matt_tool` ao link do produto; outro usa `meli.la` gerado no Linkbuilder do painel. ⚠️ Confirme no painel qual formato é válido. Um link por canal gerado no painel; relatório separa cliques e vendas por link ✅(fonte). Fluxo: 1 vez por semana (domingo) gerar 20 a 30 links, colar em uma tabela do Supabase com título, preço, nota. A automação só lê a tabela.
- **Amazon:** SiteStripe no produto, mesmo fluxo. ⚠️ Ler o contrato sobre exibição de preço e lugares onde o link pode aparecer.
- Meta de mix de volume 🛠️: Shopee 60%, ML 30%, Amazon 10% (ajuste por EPC real).

---

## 6. Roadmap de build (MVP em 3 marcos)

| Marco | Data | Entrega | Critério de aceite |
|---|---|---|---|
| M1 Telegram MVP | até 14/11 | Coleta Shopee, filtro, link, copy, bot de aprovação, disparo agendado no **canal de Telegram** | 5 dias rodando sem tocar no código |
| M2 WhatsApp | até 21/11 | Gateway do número dedicado enviando ao **grupo**, com limites de volume | 3 dias consecutivos sem restrição |
| M3 Tracking + dashboard | até 26/11 | `conversionReport` diário, tabela por subId, alertas | Relatório pronto antes da Black Friday |

Fallback se a API Shopee atrasar: o gerador de links do painel + tabela manual alimentando a mesma fila.

---

## 7. Filtro e score de oferta 🛠️

Saída: `score` de 0 a 100 e `motivo` legível.

| Critério | Regra de corte | Peso |
|---|---|---|
| Nota | ≥ 4,6 | 20 |
| Avaliações | ≥ 200 | 15 |
| Desconto real | preço atual ≤ 70% da mediana dos 30 dias (histórico próprio no Supabase, pois não há preço histórico oficial) | 25 |
| Comissão | ≥ piso da plataforma | 15 |
| Faixa de preço | ≤ R$ 50 (ou lista premium) | 10 |
| Vendas recentes | proxy de procura | 10 |
| Frete/entrega | prazo ≤ 7 dias para SP | 5 |

Lista de bloqueio: palavras de promessa de saúde ("cura", "emagrece", "elimina"), marcas com reclamação recorrente, itens proibidos de cada programa.

**Dedupe:** não repetir o mesmo produto em 14 dias, nem mais de 2 vezes por mês. Importante: a mesma oferta três vezes leva ao silenciamento.

**Histórico de preço:** a automação grava cada preço visto. Em 3 semanas você tem base própria; até lá, depende de extensões e conferência manual.

---

## 8. Geração de copy (LLM) 🛠️

Use a API do Claude com *system prompt* que carrega `marca/bio-e-copy.md` e as personas. Regras duras que devem entrar no prompt e também numa validação pós-geração:

- Sem exclamação, sem travessão (— e –), sem as palavras banidas ("incrível", "perfeito", "curadoria", "exclusivo").
- Preço específico e nota sempre presentes.
- **Proibido inventar experiência de uso.** O modelo só pode usar fatos do cadastro do produto (preço, nota, nº avaliações, prazo). Frases em primeira pessoa ("testei", "tô usando") só entram se o campo `uso_real = true` for marcado por você.
- Sem promessa de saúde ou resultado.
- 3 variações por oferta (necessário também para evitar mensagens idênticas no WhatsApp).

Validador (função simples): reprova a mensagem se contiver `!`, `—`, `–`, palavra banida ou ausência de `R$`. Se reprovar, regenera uma vez; se falhar de novo, cai para o template fixo.

Saída por oferta: `{ titulo, mensagem_wpp, mensagem_telegram, legenda_story }`.

---

## 9. Gateway de WhatsApp: decisão e risco

### 9.1 Opções

| Opção | Como funciona | Risco de ban | Custo | Quando usar |
|---|---|---|---|---|
| Manual com WhatsApp Business | Você cola a mensagem | Baixo | Seu tempo | Primeiros 2 dias; fallback |
| Gateway não oficial (Evolution API/Baileys, WAHA, Z-API etc., conexão por QR code) | Emula WhatsApp Web | **Alto**, segundo as fontes, que são vendedoras de API oficial. Nenhuma tem dado da Meta | VPS ou plano mensal | Opção prática para grupo, com mitigação |
| Ferramenta pronta (Achadinhos Pro, AutoLinks, Growify, Pai das Ofertas etc.) | Mesma conexão por sessão, hospedada por eles. Um deles admite que não é a API oficial | Mesmo risco | Planos como R$ 49,97/mês (preço citado por um deles, ⚠️) | Se quiser pular o desenvolvimento |
| API oficial (Cloud API) | Oficial | Baixo | Cobrança por conversa. Uma fonte cita grupo cobrado por pessoa que recebe, e a Groups API aparece limitada a 8 participantes em fórum de desenvolvedores ⚠️ | Inviável para grupo público de centenas de membros |

**Leitura honesta:** não existe caminho oficial e barato para postar automaticamente em grupo grande. Quem automatiza grupo de ofertas está, quase sempre, usando conexão por sessão. Ela viola os termos de uso (envio automatizado/não oficial é causa de bloqueio, segundo as fontes), portanto **você aceita o risco com mitigação**, não elimina.

### 9.1.1 Endpoints do WAHA (documentação oficial lida)

Para a implementação do `WhatsAppGatewaySender`, o WAHA expõe: `POST /api/sendText` (`session`, `chatId` terminado em `@g.us`, `text`), `POST /api/sendImage`, `GET /api/{session}/groups`, `GET .../groups/{id}/invite-code`, `PUT .../settings/security/messages-admin-only` (`{"adminsOnly":true}`) e `PUT .../settings/security/membership-approval`. Lista completa em `pesquisa-repos-termos-ferramentas.md`, seção 4. O próprio WAHA avisa que "WhatsApp does not allow bots or unofficial clients" e que o bot deve **só responder** mensagens, nunca iniciar conversa. Erros `463` e `475` significam timelock e limite de mensagens: **não reiniciar nem refazer o pareamento**, apenas pausar.

Padrões de operação aproveitados dos repositórios lidos (sem copiar código):

- Reconsultar a oferta na API imediatamente antes de publicar; pular se sumiu ou se o preço subiu.
- Não repetir envio após erro 503 ou de rede no WhatsApp (evita mensagem duplicada); seguir com o Telegram.
- Parar o slot após 3 falhas seguidas em todos os destinos.
- Pausa aleatória de 20 a 40 s entre posts.
- Dedupe de 7 dias gravado **só depois** de envio com sucesso.
- Modo padrão "kit para postar manualmente": o bot manda a oferta pronta para o seu Telegram privado; o envio automático ao grupo é opcional e desligável.

### 9.2 Mitigação 🛠️ (junto ao que o Z-API descreve ⚠️)

1. Número **dedicado**, nunca o pessoal.
2. Aquecimento de 7 a 14 dias usando como gente (item 5.4 do plano).
3. Conta humana como **segunda admin** do grupo.
4. Intervalo mínimo de 5 minutos entre envios, jitter aleatório de ±2 min.
5. Volume: começar com ≤10 envios ativos/dia, chegar a 7 ofertas por dia (cada oferta é 1 a 2 mensagens).
6. Texto variado (5+ variações por estrutura).
7. Nada de rajada: **disparo único por slot**, sem reenvio.
8. Sem envio de madrugada.
9. Backoff e kill-switch: ao receber qualquer sinal de restrição, o sistema para tudo e avisa o dono no Telegram.
10. **Backup de audiência:** espelho em Canal do WhatsApp e Telegram. Se o grupo cair, você tem para onde levar as pessoas.

### 9.3 Observação de design

O sistema não deve depender de um gateway específico. Defina uma interface `Sender` com implementações `TelegramSender`, `WhatsAppGatewaySender`, `ManualSender` (apenas copia para a área de transferência / envia para você). Trocar de gateway vira configuração.

---

## 10. Teste de carga e checklist de go-live

Rodar em 09/12 (ver plano):

- [ ] 20 ofertas na fila, todas com link rastreável aberto manualmente (3 amostras clicadas e conferidas no painel).
- [ ] Mensagem passa no validador de copy (nenhuma exclamação, nenhum travessão, preço e nota presentes).
- [ ] Aprovação via Telegram funciona do celular.
- [ ] Agendador respeita fuso America/Sao_Paulo e janelas de horário.
- [ ] Kill-switch testado (simular restrição).
- [ ] Falha da API Shopee cai no modo manual sem derrubar o dia.
- [ ] `conversionReport` retorna dados e grava por subId.
- [ ] Alerta se uma oferta passar do horário sem ter sido enviada.
- [ ] Backup do banco e das variáveis.

---

## 11. Landing e rodízio de grupos (Vercel) 🛠️

Rota `GET /entrar`:

1. Lê `utm_source`, `utm_campaign`, `fbclid`.
2. Grava clique em `clicks` (Supabase).
3. Dispara evento `Lead` pelo Pixel (client) e pela API de Conversões (server), com deduplicação por `event_id`.
4. Escolhe o grupo com vaga: tabela `groups(id, invite_url, capacity, estimated_members, active)`; o primeiro `active = true` com `estimated_members < capacity - 30`.
5. `302` para o `invite_url`.

Estimativa de membros: você atualiza `estimated_members` manualmente 1 vez ao dia (o WhatsApp não expõe a lista por API). Troca de grupo vira edição de uma linha, sem mexer na bio.

Fricção importante: o tráfego de bio e de anúncios usa o mesmo domínio, e a UTM diz de onde veio, o que permite calcular o custo por entrada por origem.

---

## 12. Modelo de dados (Supabase) 🛠️

```sql
create table products (
  id uuid primary key default gen_random_uuid(),
  marketplace text not null,        -- shopee | ml | amazon
  external_id text not null,
  title text, category text,
  url text not null,
  rating numeric, rating_count int, sales int,
  commission_rate numeric,
  unique (marketplace, external_id)
);

create table price_history (
  product_id uuid references products(id),
  seen_at timestamptz default now(),
  price numeric not null
);

create table offers (
  id uuid primary key default gen_random_uuid(),
  product_id uuid references products(id),
  score int, reason text,
  affiliate_url text,
  sub_ids text[],
  copy jsonb,                       -- variações de mensagem
  uso_real boolean default false,   -- libera frase em 1ª pessoa
  status text default 'draft',      -- draft|approved|scheduled|sent|skipped
  scheduled_for timestamptz,
  sent_at timestamptz
);

create table sends (
  id uuid primary key default gen_random_uuid(),
  offer_id uuid references offers(id),
  channel text, group_id text,
  sent_at timestamptz default now(),
  ok boolean, error text
);

create table clicks (
  id uuid primary key default gen_random_uuid(),
  at timestamptz default now(),
  source text, campaign text, group_id uuid
);

create table commissions (
  checkout_id text primary key,
  purchase_time timestamptz,
  est_commission numeric,
  status text,
  sub_ids text[]
);
```

Ligue RLS em todas as tabelas; o painel e os cron jobs usam a chave de serviço no servidor.

---

## 13. Monitoramento e alertas

| Evento | Ação |
|---|---|
| Falha de envio ou sessão do WhatsApp caiu | Alerta imediato no Telegram do dono, pausa fila |
| Fila com menos de 10 ofertas aprovadas | Alerta às 18h do dia anterior |
| Queda de CTR > 40% na semana | Alerta no relatório de domingo |
| Pico de saídas do grupo (> 3% em um dia) | Alerta e revisão das últimas ofertas |
| Erros 10030 (limite de API) | Backoff e retry, registrar |

---

## 14. Próximos passos de build (se você aprovar)

1. Criar a estrutura `automacao/` no repositório (Node 20 + TypeScript).
2. Implementar M1 (Telegram MVP) com a interface `Sender` e o validador de copy.
3. Subir no Vercel (Cron) + Supabase.
4. Registrar o app no Open Platform da Shopee assim que a conta de afiliado for aprovada e validar os campos da seção 4.2.

Bloqueio atual: **credenciais da Shopee**. Sem elas, o M1 roda com ofertas carregadas manualmente e o restante do pipeline fica provado.
