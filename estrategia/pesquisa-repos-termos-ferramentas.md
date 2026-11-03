# Pesquisa de referência: repositórios, termos oficiais e ferramentas

> Rodada 2 da pesquisa, em 03/11/2026. Complementa `plano-lancamento-12-12.md` e `automacao-tecnica.md`.
> Legenda: ✅ lido no texto oficial ou no código · 🔎 relatado por fonte secundária · ⚠️ validar.

---

## 1. Termos oficiais do Programa de Afiliados da Shopee (BR)

Fonte ✅: [Termos e Condições](https://help.shopee.com.br/portal/10/article/124094-Programa-de-Afiliados-Shopee-Termos-e-Condi%C3%A7%C3%B5es), "última atualização 09 de setembro de 2026". Li o texto completo (seções 1 a 17). A numeração e as remissões do próprio documento são inconsistentes; se for usar juridicamente, cite o texto original. Não é parecer jurídico.

### O que decide o plano

| Tema | O que o texto diz | Seção | Impacto |
|---|---|---|---|
| Atribuição | **7 dias, último clique vence**. Comissão vai para o afiliado cujo link foi o último usado antes da compra | 3.11 | Cookie confirmado. Quem clica no seu link e depois em outro afiliado perde a comissão para o outro. Poste o link e crie urgência legítima para a compra no mesmo dia |
| Cálculo | Menor valor entre o orçamento confirmado e o valor líquido da compra × taxa. Valor líquido exclui descontos, frete, taxa de cupom e Moedas Shopee | 3.2, 1.7 | O desconto de cupom reduz a base da comissão. Planeje no piso |
| Compra válida | Não pode ser comprador robô, nem "campos pré-populados", e não pode ser cancelada, devolvida ou fraudulenta | 1.6, 3.6 | Comissão é estornada em devolução |
| Autocompra | Não há proibição própria, mas é motivo de estorno ("comprado Produtos através de Links de Afiliados") | 3.6(c) | **Não compre seus produtos de teste pelo seu link.** Compre sem link |
| Pagamento | Mensal; precisa atingir valor mínimo (o valor **não consta** no texto); paga em até **60 dias** depois da aprovação do sistema | 3.3, 3.4 | Fluxo de caixa lento. Reforça a regra de não depender de comissão para pagar mídia |
| Conta de recebimento | Texto diz conta corrente vinculada a CNPJ (3.8), mas outra seção cita pagamento de pessoa física via "conta Maree" ou Shopee Pay (3.7, 12.4) | 3.7, 3.8, 12.4 | ⚠️ Inconsistente. Perguntar ao suporte como PF recebe. Para PJ, nota fiscal de serviço é condição de pagamento (3.4.1, 3.4.3) |
| Comissão Extra | Marca ou loja pode pagar extra por venda via seu link; Shopee pode descontar taxa de serviço | 11 | Priorize produtos com selo de comissão extra |
| Anúncios pagos | **Permitidos em redes sociais** (Instagram Ads, Facebook Ads, TikTok Ads, Pinterest Ads), só pela conta registrada. **Proibidos** em busca e shopping (Google Ads, Bing Ads) com links de afiliado | 2.3(b), 4.3(i), 13.3 | Meta Ads e TikTok Ads do plano estão dentro da regra. Nada de Google Ads para link de afiliado |
| Marca Shopee | A mídia social aprovada não deve conter marcas, nomes ou logotipos da Shopee. Facebook só via página de fãs, não pessoal | 2.3(a) | **Não use "Shopee" no nome do perfil, do grupo ou no avatar.** Revise se capturas de tela do app têm risco. ⚠️ Perguntar ao suporte |
| Mídia pública | A mídia de afiliado precisa estar **publicamente disponível** | 2.3 | Declare Instagram/TikTok públicos como mídia. ⚠️ Perguntar se divulgar link em grupo de WhatsApp está coberto |
| Cupons | Cupons nominais são exclusivos para o afiliado compartilhar com seus seguidores; compartilhar cupom nominal de terceiros é violação | 13.1, 13.1.1 | Só publicar cupom que a Shopee entregou a você ou cupom público da plataforma. Informar as condições do cupom (13.2) |
| Cookies | Só com link visível e clique voluntário. Proíbe pop-up, iFrame, redirecionamento automático, queda de cookie, instalação forçada do app | 4.4 | **Cuidado com a landing:** o rodízio de grupos não pode redirecionar para link de afiliado sem clique do usuário. A landing leva ao grupo, não à Shopee |
| Informação | Proíbe informação falsa, enganosa ou não verificada | 4.3(j), 8.2(c) | Reforça a regra de não inventar uso do produto e de não inflar "de/por" |
| Raspagem | Proíbe meios automatizados de extração de dados para coletar propriedade intelectual/visuais da Shopee | 4.3(d) | Use a API para ler ofertas. Não raspe o site |
| Divulgar mídia pela Shopee | Proibido anunciar sua mídia de afiliado nos canais sociais da própria Shopee | 4.3(f) | Não comentar o link do grupo em posts da Shopee |
| Shopee Vídeo | Vídeos estáticos podem ser excluídos e levar a banimento | 14.4 | Se postar lá, só vídeo de verdade |
| Encerramento | A Shopee pode encerrar a qualquer momento, com ou sem motivo | 7.2 | Risco de plataforma: não dependa só de Shopee |

### O que o texto NÃO diz

- Nada sobre **WhatsApp, Telegram, grupos, adicionar pessoas, mensagens não solicitadas** (só e-mail publicitário sem consentimento, 4.3(a)).
- Nada sobre **bots/automação** além de comprador robô e raspagem.
- Nada sobre **API/Open Platform** (os termos de uso da API não estão nesse documento).
- Nada sobre **identificação de publicidade** ou exibição de preço.
- Valor mínimo de pagamento e prazo de validação em dias.

Conclusão: o uso de grupo e de bot não é proibido por esse texto, mas também não é autorizado de forma expressa. Quem bloqueia na prática é o WhatsApp, não a Shopee.

Programa Indique e Ganhe de afiliados ✅ (12.1 e 12.2): R$ 20 por afiliado indicado que fizer ao menos 5 compras concluídas em 30 dias. Irrelevante para o grupo, mas pode virar receita lateral se você ensinar outros.

---

## 2. Repositórios open source de bots de ofertas (leitura de código)

Nenhum tem muita tração (0 a 22 estrelas) e **só um tem licença permissiva**. Use como referência de design, não copie código sem licença.

| Repo | Stack | WhatsApp | Licença | O que vale aprender |
|---|---|---|---|---|
| [wntuto/disparador-afiliados](https://github.com/wntuto/disparador-afiliados) | Node 22 + TypeScript, Fastify, SQLite, node-cron | **ZapsterAPI** (hospedada, QR) via `POST /v1/wa/messages` com `recipient="group:<id>"` | Nenhuma | Painel web com campanhas agendadas; busca `productOfferV2` com `sortType`; ML por parâmetros `matt_word`/`matt_tool` no link; dedupe de 7 dias; `SEND_DELAY_MS` entre grupos |
| [gustavohenrique-d/bot-ofertas-afiliados](https://github.com/gustavohenrique-d/bot-ofertas-afiliados) | Python 3.10, SQLite, cron | Ponte local baseada em Baileys (não oficial) + **Telegram Bot API** | "Todos os direitos reservados" (só leitura) | **O melhor desenho de operação** (ver 2.1) |
| [SaulloGabryel/BlueBot](https://github.com/SaulloGabryel/BlueBot) | Python (Telethon, Selenium) + Node (whatsapp-web.js) | whatsapp-web.js por QR | MIT | **Evitar:** monitora grupo de Telegram de terceiros e republica (copia o trabalho alheio); o módulo Shopee não usa a API (só reescreve parâmetros e encurta com TinyURL); sem anti-ban |
| [Mateus0790/botafiliado](https://github.com/Mateus0790/botafiliado) | Node, Docker | **Padrão: manda o "kit" da oferta no seu Telegram privado para você postar manualmente.** Opcional: Baileys por QR com aviso explícito de risco de ban | Nenhuma | Human-in-the-loop como padrão; Instagram pela Graph API oficial (comentário dispara DM com o link); retries com backoff; dedupe só depois de envio com sucesso |
| [vs-machado/offers-bot-automation](https://github.com/vs-machado/offers-bot-automation) | Next.js, FastAPI, Postgres, Redis, Celery | **WAHA** | Nenhuma | Plataforma multiusuário madura (250 commits). Extração por IA a partir de fontes do Telegram (replica conteúdo de terceiros) |
| [Maths9/shopee-telegram-affiliate-bot](https://github.com/Maths9/shopee-telegram-affiliate-bot) | Python/Flask | Nenhum | Nenhuma | Fluxo simples: você cola o link no bot, ele posta no canal de Telegram com foto, preço e botão |

### 2.1 O que adotar do melhor desenho (bot-ofertas-afiliados), sem copiar código

- **Rechecar antes de publicar:** buscar a oferta de novo na API; pular se sumiu ou se o preço subiu.
- **Falha segura:** não repetir tentativa em erro 503/rede do WhatsApp (evita post duplicado); continuar no Telegram; parar o slot após 3 falhas seguidas em todos os destinos.
- **Pausa aleatória** de 20 a 40 s entre posts.
- **Dedupe de 7 dias** em SQLite; para ML, por título (o mesmo produto com outro link é pego).
- **Filtros configuráveis:** desconto mínimo, comissão mínima, faixa de preço, nota mínima, vendas mínimas, palavras bloqueadas e preferidas, limite por palavra-chave.
- **Fila manual para ML** (CSV), porque o Mercado Livre não tem API de link.

### 2.2 Fatos do Mercado Livre vindos do código

- Não há API de geração de link de afiliado. Um repo anexa os parâmetros **`matt_word` e `matt_tool`** ao link; outro usa um link `meli.la` gerado pelo Linkbuilder do painel com sessão de navegador não oficial. ⚠️ Confirme no painel de afiliados qual forma é válida e se o parâmetro sobrevive ao encurtador.
- A busca pública `/sites/MLB/search` bloqueia tokens de aplicativo; catálogo e destaques por categoria funcionam. Sem dados de comissão nem nota nessa rota.

---

## 3. API de afiliados da Shopee: verificado no código

Verificado em 4 repositórios (nenhum é documentação oficial). Os nomes de campo vieram de código, não do painel.

- **Endpoint BR ✅:** `https://open-api.affiliate.shopee.com.br/graphql` (3 repositórios). Um deles recomenda copiar a URL do painel, pois pode variar por conta/região.
- **Assinatura ✅ (idêntica em todos):** `SHA256(AppId + Timestamp + CorpoJSON + Secret)` em hex. O corpo assinado é exatamente o enviado (`JSON.stringify({query})`, sem espaços extras).
- **Header ✅:** `Authorization: SHA256 Credential={appId}, Timestamp={ts}, Signature={sig}`. Um repo usa a ordem `Signature` antes de `Timestamp`; testar a que o seu painel aceitar.
- **Erro 10035 ✅ (README de um repo):** conta ainda sem acesso à Open API. É o sintoma de "credencial pedida, ainda não liberada".

### productOfferV2

```graphql
{
  productOfferV2(keyword: "serum vitamina c", sortType: 2, page: 1, limit: 20) {
    nodes {
      itemId shopId productName
      priceMin priceMax priceDiscountRate
      commissionRate sales ratingStar
      imageUrl shopName productLink offerLink
    }
    pageInfo { page limit hasNextPage }
  }
}
```

- `sortType`: 1 relevância, 2 mais vendidos, 3 maior preço, 4 menor preço, **5 maior comissão**.
- Busca por item: `productOfferV2(itemId: N, shopId: N)`.
- `offerLink` já é um link de afiliado; `generateShortLink` encurta e aceita `subIds`.
- Nenhum cliente trata limite de requisições. Implemente você mesmo.

### shopeeOfferV2 (campanhas)

```graphql
{ shopeeOfferV2(sortType: 1, page: 1, limit: 20) {
    nodes { offerName offerLink originalLink imageUrl periodStartTime periodEndTime } } }
```

Lista campanhas com período. **É a forma programática de descobrir a campanha 12.12 e suas datas.** ⚠️ Rodar assim que as credenciais saírem.

### generateShortLink

```graphql
mutation { generateShortLink(input: { originUrl: "https://shopee.com.br/...", subIds: ["wpp","g1","beleza","h1215","bf"] }) { shortLink } }
```

Escape o `originUrl` (um repo interpola sem escapar). Se falhar, o padrão dos repos é cair para o `offerLink`.

---

## 4. WhatsApp: ferramentas e capacidades

### 4.1 WAHA (HTTP API autohospedada, não oficial) ✅ doc oficial lida

| Ação | Chamada |
|---|---|
| Listar grupos | `GET /api/{session}/groups` (ids terminam em `@g.us`) |
| Criar grupo | `POST /api/{session}/groups` `{"name":"...","participants":[{"id":"55...@c.us"}]}` |
| Enviar texto ao grupo | `POST /api/sendText` `{"session":"default","chatId":"...@g.us","text":"..."}` |
| Enviar imagem | `POST /api/sendImage` (suportado nos 4 motores; corpo não verificado) |
| Link de convite | `GET /api/{session}/groups/{id}/invite-code` → `https://chat.whatsapp.com/{code}`; revogar: `POST .../invite-code/revoke` |
| **Só admins enviam** | `PUT /api/{session}/groups/{id}/settings/security/messages-admin-only` `{"adminsOnly":true}` |
| Só admins editam info | `PUT .../settings/security/info-admin-only` |
| **Aprovar entradas** | `PUT .../settings/security/membership-approval` `{"newMembersApprovalRequired":true}`; pedidos em `GET .../participants/join-requests`, aprovar em `POST .../join-requests/approve` |
| Histórico para novos | `PUT .../settings/security/member-share-history-mode` |

- Motores: WEBJS e WPP usam navegador real (Puppeteer); NOWEB e GOWS falam direto por WebSocket. O padrão é WEBJS.
- **Avisos do próprio WAHA:** "WhatsApp does not allow bots or unofficial clients on their platform, so this shouldn't be considered totally safe". Conselho: o bot **só responde**, nunca inicia conversa. Erros `463` (timelock de contato novo) e `475` (limite de mensagens): não reiniciar nem reconectar a sessão. 🔎 Valores de "5 a 10 denúncias de spam = ban" são folclore do fornecedor.
- Desde a versão 2026.6.1 os recursos que eram do plano Plus passaram para o Core gratuito (anúncio do próprio site). Há só um plano de apoio de US$ 5/mês sem benefícios. ⚠️ Confirmar.

### 4.2 Evolution API 🔎 (só fontes secundárias)

Baseada em Baileys; também aceita a API oficial (Cloud API). Criar instância `POST /instance/create` com `"integration":"WHATSAPP-BAILEYS"`. Duas chaves: global e da instância. Grupo é identificado pelo JID (`...@g.us`). ⚠️ Rotas e campos mudam entre versões; ler a doc oficial antes.

### 4.3 Canais do WhatsApp

- 🔎 **Não há API oficial para publicar em Canal.** O repositório botafiliado manda a oferta para o seu Telegram para você colar manualmente.
- Serviços de terceiros (Wassenger, artigo de abril/2024) postam em Canal por `POST https://api.wassenger.com/v1/messages` com `{"channel":"...@newsletter","message":"..."}`, só texto e imagem, um pedido por canal. É conexão não oficial, com o mesmo risco de ban do número.
- Canal só aceita a mesma mensagem para todos, sem segmentação, e a única métrica é reação com emoji. Descoberta é pela busca na aba Atualizações.
- **Decisão:** Canal entra como **espelho manual** (colar o que já foi aprovado), não como destino automatizado.

### 4.4 Recursos de grupo úteis (2026)

- 🔎 MacMagazine (19/02/2026): ao entrar, novos membros podem receber as últimas 25, 50, 75 ou 100 mensagens se alguém desbloquear; admins podem desabilitar o compartilhamento de histórico pelos demais. Reduz o problema de "cheguei e vi um grupo vazio". Mas lembre: histórico mostrando promoção vencida estraga a primeira impressão. Prefira **desabilitar para membros** e usar a mensagem fixa.
- Configurações de grupo confirmadas por imprensa: restringir envio a admins (Permissões do grupo → Enviar mensagens) e **aprovar novos participantes** (opcional, pode ser ativado depois). Com aprovação ligada, o link pode circular livremente, mas cada pedido precisa de aceite (fricção real). Recomendação: **ligada só se aparecer abuso**.
- Limite de membros: imprensa diverge (512 em matérias antigas, 1.024 em outras). ⚠️ Conferir no app.

---

## 5. Instagram: limites de uma conta nova

🔎 Estimativas da comunidade, sem número oficial da Meta:

- Seguir: cerca de 20 por hora e 300 a 500 por dia em conta madura; **conta nova tem limites bem menores**. Alta atividade logo após a criação, sem aquecimento, é sinal de risco.
- Postar: 2 a 3 publicações por dia é prática recomendada por terceiros.
- Padrão de seguir/deixar de seguir em horários regulares é detectável. Login de IPs e dispositivos diferentes aumenta o risco. Ferramentas de automação são gatilho comum de "ação bloqueada" (24 a 72 h em geral, às vezes semanas).
- Nenhuma fonte tratou de link de afiliado na bio.

**Consequência para o plano:** manter 10 a 15 seguidas/dia, comentários reais, mesmo dispositivo e rede, zero ferramenta de automação de follow.

Tática com API oficial: o botafiliado usa a **Graph API oficial** para responder comentário com DM contendo o link. Funil de "comente QUERO" → DM com o link do grupo é viável e legítimo, desde que a conta seja profissional e dentro das regras de mensagens da Meta. ⚠️ Conferir janelas e políticas atuais.

---

## 6. Mercado: o que dá para dizer com honestidade

- Busca de relatos reais de renda: **não encontrei nenhum** independente (sem print de ganho verificável, sem avaliação isenta). Toda promessa de "ganhos reais" vem de quem vende bot ou curso.
- Diretórios de grupos mostram que quase todos os grupos de "achadinhos" são de afiliados e que **o volume de mensagens de Shopee é o maior**. Isso indica mercado saturado, o que reforça a importância de nicho claro (beleza + casa até R$ 50), prova de velocidade e confiança, não só preço.
- Várias entradas de diretório têm audiência minúscula. Crescer é lento e a maioria não passa de centenas.

---

## 7. Lacunas que continuam abertas

- Tabelas oficiais de comissão (Shopee, ML, Amazon) e valor mínimo de pagamento.
- Como pessoa física recebe da Shopee (inconsistência 3.7/3.8) e se divulgar em grupo de WhatsApp está coberto pela "mídia de afiliado".
- Regras da Meta para anúncio com destino em convite de grupo.
- Limite atual de grupo e de Comunidade no WhatsApp.
- Termos de uso da Open API da Shopee.
- Datas e comissões extras da campanha 12.12 (consultar `shopeeOfferV2` e a Central do Afiliado).
- Contrato da Amazon Associados (exibição de preço, locais de link).
- Texto integral do Guia CONAR 2026.
