# Plano de Lançamento Achei Promo: 12/12

> Escrito em 03/11/2026. Faltam 39 dias para 12/12 (sábado).
> Documento técnico da automação: `estrategia/automacao-tecnica.md`.
> Personas, bios e prompts já existentes continuam valendo, com os ajustes apontados na seção 2.

---

## 0. Resumo executivo

**O que é o negócio.** Grupo de ofertas no WhatsApp (beleza, cosméticos, casa) monetizado por links de afiliado (Shopee, Mercado Livre, Amazon). Instagram e TikTok entram como topo de funil. O grupo é o ativo.

**Realidade dos números (sem romantizar).** Com as premissas ilustrativas que as próprias fontes usam, um grupo de 1.000 membros rende algo na casa de R$ 250 a R$ 330 por mês em comissão. As comissões levam 30 a 60 dias para cair. Quem paga mídia para encher o grupo só empata depois de uns 3 meses. Isso não invalida o projeto, mas define a regra do jogo: **o grupo precisa ser barato de encher, barato de operar (automação) e ter retenção alta**. Escala vem de várias frentes (mais grupos, Canal, Telegram), não de um grupo só.

**Cinco decisões estratégicas que eu recomendo:**

1. **Não depender só do WhatsApp.** Monte em paralelo um Canal do WhatsApp e um canal de Telegram espelho. Telegram tem API oficial de bots, então é onde a automação nasce sem risco de ban. WhatsApp recebe a automação só depois de testada.
2. **Automação com humano no meio.** Pipeline automático até a fila, aprovação em 1 clique (bot de Telegram), disparo agendado. Nada de despejar 40 links por dia.
3. **Conteúdo próprio ou transformado de verdade.** O Instagram passou a limitar recomendação de contas agregadoras e de reposts de baixo esforço. O fluxo atual do repositório (baixar vídeo de canal do Telegram, flip, zoom, áudio novo) cai exatamente nisso. Detalhes na seção 2.
4. **Soft launch na Black Friday (27/11), grande lançamento em 12/12.** Faltam 15 dias entre as duas datas e BF é a melhor janela do ano para provar o grupo, testar horários e começar a gerar comissão.
5. **Compliance desde o dia 1.** Guia do CONAR 2026 trata link de afiliado como publicidade. Copy com "tô usando faz 30 dias" só pode ser dita se for verdade.

**Metas propostas para 12/12 (hipóteses minhas, ajuste ao orçamento):**

| Marco | Meta |
|---|---|
| 24/11 | 80 a 150 membros (rede próxima + primeiros orgânicos) |
| 30/11 (BF/Cyber) | 250 a 400 |
| 11/12 | 500 a 700 |
| 12/12 | Lançamento oficial com grupo 1 acima de 500 membros ativos |
| 31/12 | Grupo 1 cheio (1.024) e grupo 2 aberto |

---

## 1. O que a pesquisa mostrou (e o quanto confiar)

Quase tudo que existe na internet sobre o tema vem de **vendedores de ferramenta de automação** (Achadinhos Pro, AutoLinks, Growify, DivulgaNinja, Z-API, Devzapp, Grupodewhatsapp). Os números são ilustrativos ou da própria experiência do autor, sem amostra. Regra deste documento: **toda cifra marcada com ⚠️ precisa ser validada por você no painel oficial antes de virar decisão.**

### 1.1 Comissões: as fontes se contradizem

| Plataforma | Beleza | Casa | Observação |
|---|---|---|---|
| Shopee | 8% a 12% em uma fonte, 20% a 30% em duas | 8% a 12% / 10% a 18% | Também aparece "3% a 15%" geral. ⚠️ Planeje no piso. Existe "Comissão Extra" por produto/campanha, que passa de 20% em alguns casos |
| Mercado Livre | 6% a 8% em uma fonte, até 16% em outra | 4% a 8% | O "16%" é teto de categoria premium. ⚠️ Cookie e prazo de pagamento divergem (30 a 60 dias para liberar) |
| Amazon | 8% a 10% (alguns citam até 15% para moda/beleza) | n/d | Regra repetida por várias fontes: **3 vendas qualificadas em 180 dias**, senão a conta é desativada. ⚠️ |

**Como usar isso:** no modelo financeiro use o piso (Shopee 8%, ML 6%, Amazon 8%). Se a realidade for maior, é lucro.
**Ação:** na semana 1, tire print das tabelas oficiais dos três painéis e salve em `estrategia/` (assim o plano passa a ter número real).

### 1.2 O que as fontes concordam em torno de grupos que funcionam

- Promessa clara no nome ("Achadinhos até R$ 50") vence nome genérico.
- 5 a 10 ofertas boas por dia, sempre nos mesmos horários, espaçadas. Rajada de links treina o grupo a silenciar.
- O erro que mais esvazia grupo: **admin que some**.
- Comprar membro, adicionar contato sem pedir e correntes de "adicione 10 grupos" derrubam leitura e aumentam risco de bloqueio.
- Mostrar a oferta antes de pedir a entrada converte melhor que "entra no grupo".
- Custo por membro com anúncio: R$ 0,60 a R$ 1,80 (autor do blog Devzapp, experiência própria) e 2 a 3 entradas a cada 10 cliques. ⚠️ É um dado, não um benchmark.

### 1.3 Pontos onde o material do repositório conflita com a pesquisa

| Tema | O que o repo diz | O que a pesquisa mostra | Ajuste |
|---|---|---|---|
| Fonte de vídeo | Baixar de 5 canais do Telegram e "transformar" com flip + zoom + áudio novo | Instagram (30/04/2026) tira "agregadoras" de Explorar e sugestões e trata como baixo esforço: marca d'água, mudar velocidade, print de post alheio. TikTok não recomenda no Para Você conteúdo não original que reaproveita material de outros | Seção 2.3 |
| Copy | Exemplos tipo "Esse creme eu comprei por R$39 e em 3 semanas minha pele mudou" | Depoimento falso de uso é publicidade enganosa (CDC) e fere o guia CONAR 2026 | Só afirmar uso se você de fato usou. Seção 9 |
| Anúncio | "Meta Ads: Click-to-WhatsApp ativo" | Click-to-WhatsApp abre **conversa 1:1** com o número, não entra em grupo | Funil de duas etapas ou landing page. Seção 6.4 |
| Link na legenda | "Link nunca na legenda, sempre na bio" | Ok no Instagram. Mas aqui também precisa de identificação de publicidade visível | Seção 9 |
| Nome do grupo | "Achei Promo 🛍️ \| Ofertas reais todo dia" | Nome que vende é específico e promete uma coisa | Seção 4.1 |
| Aquecimento 21 dias | Fases de 7 dias | Você tem 39 dias, e BF cai no meio | Seção 5 estica as fases |

---

## 2. Conteúdo: o que postar, de onde tirar, o que evitar

### 2.1 Princípio

Instagram e TikTok são **vitrine do grupo**, não o negócio. O trabalho deles é fazer a pessoa pensar "quero ver essas ofertas todo dia". Isso se consegue com conteúdo que prova valor (preço real, comparação, achado), não com volume de repost.

### 2.2 Sete pilares de conteúdo (rotação semanal)

| # | Pilar | Exemplo | Persona | Frequência |
|---|---|---|---|---|
| 1 | Achado do dia | "Sérum de R$ 28 com 4,8 estrelas e 12 mil avaliações. Peguei hoje." (tela do produto, preço, avaliações) | Larissa | 3x/semana |
| 2 | Comparativo | 3 protetores solares do mesmo valor, com notas e preço por ml | Cida | 1x/semana |
| 3 | Antes e depois de verdade | Organização de gaveta com produtos de até R$ 30 | Cida | 1x/semana |
| 4 | Radar da semana | Carrossel "5 coisas que baixaram de preço" | Ambas | 1x/semana |
| 5 | Teste honesto | Unboxing real de produto comprado | Larissa | 1x/semana |
| 6 | Bastidor do grupo | Print de oferta que esgotou, horário em que foi enviada ("mandei 8h47, acabou 9h07") | Ambas | 2x/semana |
| 7 | Educação | "Como saber se o desconto é verdadeiro", "como achar cupom na Shopee" | Cida | 1x/semana |

O pilar 6 é o seu argumento de entrada mais forte: **prova de velocidade**.

### 2.3 Fontes de conteúdo: o que é seguro, o que é risco

**Seguro (prioridade):**

1. **Captura de tela e gravação da própria tela** do produto (preço, avaliações, frete) com sua narração ou legenda. É o formato mais barato e é conteúdo seu.
2. **Produtos comprados de verdade.** Reserve R$ 250 a R$ 400 para comprar 6 a 10 produtos baratos da própria vitrine. Eles viram unboxing, teste, comparativo. Conteúdo original, copy honesta, e resolve o problema do "tô usando".
3. **Vídeos gerados por IA para conteúdo sem produto** (fase 1), já cobertos em `conteudo/prompts-aquecimento-flow.md`. Conteúdo gerado ou modificado por IA segue as mesmas regras de identificação do guia CONAR 2026.
4. **Material que a própria plataforma disponibiliza a afiliados** (criativos, vídeos de campanha). ⚠️ Confirmar no painel de cada programa o que é permitido reusar e em que formato.
5. **Autorização direta.** Fale com 5 a 10 microcriadores de beleza e casa. Proponha dividir comissão por Reels com produtos. Conteúdo licenciado não é penalizado.

**Com cuidado (uso complementar, não base):**

- **Os 5 canais de Telegram do README.** Use como **radar de produto**: o produto e o preço não são de ninguém. O **vídeo** pode ser de terceiro. Se quiser usar um clipe, a regra do Instagram é que a transformação seja significativa (comentário, comparação, voz sua, preço e avaliação sobrepostos, corte para mostrar algo que o original não mostra). Flip, zoom e troca de áudio sozinhos são justamente edição de baixo esforço, e **não vou recomendar o truque de "burlar detecção"**: além de não funcionar de forma estável, expõe sua conta principal. Limite sugerido (minha heurística): no máximo 1 em cada 5 posts com clipe de terceiro, sempre com contribuição sua visível.
- Uma fonte cita que contas com mais de 10 reposts de terceiros em 30 dias ficam fora das recomendações, outra fala em mais de 50% do conteúdo. ⚠️ Números não confirmados, mas a direção é clara.

**Evitar:** marca d'água de outra plataforma, print de post alheio como conteúdo, texto de anúncio de outro afiliado, qualquer coisa que prometa resultado de saúde ("elimina manchas", "colágeno cura"). Produtos anti-idade e suplementos têm limite regulatório (ANVISA).

### 2.4 Fábrica de conteúdo semanal (processo, não inspiração)

```
Domingo 14h: batch semanal (3 horas)
  1. Puxar da fila do sistema os 20 melhores produtos da semana (score da automação)
  2. Escolher 7 para Reels, 3 para carrossel, 10 para Stories
  3. Gravar tela + voz (1h), editar no CapCut com template fixo (1h), legenda e CTA (30 min)
  4. Agendar no Meta Business Suite (IG + Facebook) e TikTok (programação nativa)
Seg a Sáb: 20 min/dia respondendo comentário e DM, 5 a 10 stories ao vivo
```

Template fixo de Reels de 15 a 25 segundos:

| Segundos | Elemento |
|---|---|
| 0 a 2 | Gancho com preço na tela ("R$ 28") |
| 2 a 8 | Produto em uso/tela, avaliação, motivo de valer |
| 8 a 15 | Prova (nota, nº de avaliações, comparativo) |
| 15 a 20 | CTA do grupo, sem "corre" nem "últimas unidades" |

CTA aprovados (do `marca/bio-e-copy.md`): "No grupo WPP eu aviso quando acho mais. Link na bio." e variações.

---

## 3. Estrutura de contas e ativos

| Ativo | Para quê | Observação |
|---|---|---|
| Instagram @acheipromo (conta única, profissional) | Reels, Stories, bio com link | Link da bio aponta para a landing (seção 6.3) |
| TikTok | Alcance barato e frio | Ligar o botão de conteúdo comercial ao postar produto com link. Sem isso o vídeo perde elegibilidade para o Para Você |
| Facebook Page | Persona Cida usa Facebook | Reels do Instagram podem ser compartilhados para a Page. Custo quase zero |
| Número WhatsApp dedicado (chip novo, WhatsApp Business) | Admin do grupo e do bot | Nunca use seu número pessoal como único admin |
| Segundo admin humano (outro número real) | Seguro contra ban do número da automação | Se a automação cair, o grupo continua seu |
| Grupo WhatsApp 1 | Ativo principal | Limite de 1.024 pessoas (⚠️ confirmar no app) |
| Canal do WhatsApp | Topo de funil sem limite, sem expor telefone dos membros | Não existe limite de seguidores |
| Canal de Telegram | Espelho com automação oficial | Fácil de automatizar sem risco de ban |
| Landing de link (Vercel) | Link único, medição e rodízio de grupos | Detalhe em `automacao-tecnica.md` |
| Planilha/Supabase de métricas | Dashboard | Seção 10 |

**Domínio:** registre algo curto (`acheipromo.com.br` ou parecido) para a landing. Isso permite trocar o destino sem trocar a bio e dá credibilidade.

---

## 4. Configuração do grupo (passo a passo)

### 4.1 Nome, foto, descrição

Nome (sugestão, testar contra o atual):

```
Achei Promo | Beleza e Casa até R$ 50
```

Foto: fundo claro, texto grande legível em miniatura de 1 cm (duas palavras, alto contraste). Ex.: "ACHEI PROMO".

Descrição (cumpre CONAR e LGPD, sem exclamação):

```
Ofertas de beleza, cosméticos e casa, achadas todo dia em Shopee, Mercado Livre e Amazon.
Horários: 8h30 · 12h15 · 16h30 · 19h30 · 21h
Aqui não tem corrente nem conversa paralela. Só oferta.
Os links são de afiliado: se você comprar, eu ganho uma comissão e o preço não muda para você.
Para sair, é só sair do grupo. Para silenciar, use "Silenciar notificações".
```

### 4.2 Configurações

1. **Só admins enviam mensagens** (fundamental: nada de spam de membro, nada de conversa).
2. Só admins editam dados do grupo.
3. Ativar aprovação de novos participantes só se houver abuso (cria atrito). ⚠️ Confirmar no app.
4. Mensagens temporárias desligadas.
5. Fixar mensagem de boas-vindas (o que o grupo entrega e os horários), reenviar nos fixos a cada 2 semanas.
6. Habilitar Comunidade só quando tiver grupo 2 (ver 7).

### 4.3 Mensagem fixa de boas-vindas

```
Bem-vinda ao Achei Promo.
Aqui eu mando 5 a 7 achados por dia, nos horários da descrição.
Toda oferta tem preço, nota do produto e o motivo de valer.
Prefere menos mensagens? Silencie e abra só no horário que combinar com você.
Se algum produto não for o que eu disse que era, me chama no privado que eu corrijo ou removo.
```

### 4.4 Capacidade e redundância

- Limite de 1.024 por grupo ⚠️. Planeje 3 grupos até março.
- Uma Comunidade pode agrupar os grupos, e o aviso de Comunidade chega a todos. Números de capacidade de Comunidade variam muito entre fontes (de 2.000 a 5.000). ⚠️ Confirmar na Central de Ajuda do WhatsApp.
- **Link de convite sempre passa pela landing**, nunca direto. Quando o grupo enche, você troca o destino em um lugar só.

---

## 5. Cronograma dia a dia (03/11 a 12/12)

Legenda: 🧱 fundação · 🎥 conteúdo · 👥 aquisição · 🤖 automação · ⚖️ compliance · 📊 métricas

### Semana 1: 03/11 a 09/11, Fundação (sem postar oferta)

| Data | Tarefa |
|---|---|
| Ter 03 | ⚖️ Pedir aprovação **hoje**: Shopee Afiliados, Mercado Livre Afiliados, Amazon Associados. A Amazon exige 3 vendas em 180 dias, então comece cedo |
| Qua 04 | 🧱 Criar Instagram, TikTok, Facebook Page. Bios do `marca/bio-e-copy.md`. Primeiro post fase 1 |
| Qua 04 | 🧱 Comprar chip novo, ativar WhatsApp Business, iniciar aquecimento do número (item 5.4) |
| Qui 05 | 🧱 Registrar domínio, subir landing no Vercel com link provisório |
| Sex 06 | 🧱 Criar o grupo (privado, sem divulgar), configurar como seção 4. Criar Canal do WhatsApp e canal Telegram |
| Sáb 07 | 🤖 Pedir credenciais da API Shopee Open Platform (AppId + Secret). Começar o esqueleto da automação |
| Dom 08 | 🎥 Primeiro batch de conteúdo (7 posts). Comprar 6 a 10 produtos para teste |
| Seg 09 | 📊 Montar planilha de métricas e tabela real de comissões (prints dos painéis) |

### Semana 2: 10/11 a 16/11, Confiança + Autoridade (aquecimento)

Instagram/TikTok: 1 Reel por dia, 3 a 5 Stories. Foco em conteúdo de valor sem link.

- Qua 11: **Shopee 11.11**. Não vai ser seu lançamento, mas é radar. Registre quais produtos e faixas de preço bombaram, quais cupons foram usados e o que os concorrentes (grupos públicos de achadinhos) postaram. Salve tudo, vira insumo de pauta.
- Seguir 15 contas do nicho por dia (regra do repo). Comentar em 10 posts por dia com valor, não spam.
- 🤖 Entregar o MVP da automação em Telegram (seção 6 do doc técnico): seleção de produto, geração de link, mensagem, aprovação, disparo agendado no canal de Telegram.
- Sáb 14: primeiro teste de sourcing manual: montar fila de 30 ofertas.

### Semana 3: 17/11 a 23/11, Autoridade + Teaser

- 🎥 Reviews reais com os produtos comprados. Carrossel de "melhores achados". Stories com enquete e caixinha.
- 👥 **Semear o grupo com 50 a 100 pessoas conhecidas** que realmente querem receber ofertas (peça, não adicione; só link de convite). Sem isso o grupo parece vazio para quem chegar do anúncio.
- 🤖 Conectar a automação ao WhatsApp **do número dedicado** com poucos envios por dia (item 5.4). Postar manualmente os 2 primeiros dias.
- Seg 23: Stories "semana que vem entra no ar".

### Semana 4: 24/11 a 30/11, SOFT LAUNCH (Black Friday e Cyber Monday)

- Ter 24: abrir o link público do grupo e começar divulgação. Tudo a partir daqui leva ao grupo.
- Qua 25 a Qui 26: ofertas de aquecimento, 3 a 4 por dia, para manter o grupo vivo e provar a promessa.
- **Sex 27 (Black Friday): 6 a 8 ofertas, de 8h às 23h**, avisar com um dia de antecedência (modelo: "Amanhã é dia de Black Friday. O grupo vai ter mais oferta que o normal. Quem preferir, silencia hoje e volta no domingo").
- Seg 30 (Cyber Monday): 5 a 7 ofertas.
- 👥 Ads de teste a partir de 24/11 (seção 6.4): R$ 25/dia.
- 📊 Revisão no domingo: CPL, entrada/saída, cliques por post, melhores horários.

### Semana 5: 01/12 a 07/12, Enchimento acelerado

- Escalar o que funcionou em Ads (teto de R$ 40/dia se CPL ≤ R$ 2,00 e retenção em 7 dias ≥ 70%, heurísticas minhas).
- Parcerias com 5 a 10 microcriadores e donos de grupos não concorrentes (por conversa privada, nunca colando link no grupo dos outros).
- Postar 1 Reel por dia no pilar 6 (prova de velocidade) e 1 Reel de "o que rolou no grupo hoje".
- 🤖 Rodar 5 dias seguidos o ciclo completo sem intervenção, só aprovação.
- Sáb 05: segunda edição de "mensagem de reativação" para quem estava em silêncio.

### Semana 6: 08/12 a 11/12, Contagem regressiva

| Dia | Ação |
|---|---|
| Ter 08 | Stories e Reels: "Sábado, 12/12, é o dia". Mostrar bastidor das ofertas já enfileiradas |
| Qua 09 | Último teste de carga da automação (ver doc técnico, item 10) |
| Qui 10 | Preparar fila de 40 ofertas para 12 e 13/12. Confirmar na Central do Afiliado Shopee a campanha 12.12 ⚠️ e as comissões extras |
| Sex 11 | Stories "amanhã". Ads no teto planejado. Verificação final de links e rastreio |
| **Sáb 12** | **LANÇAMENTO** (seção 8) |

### 5.4 Aquecimento do número de WhatsApp (o chip)

Guia do fornecedor Z-API, único com números concretos (⚠️ orientação comercial, não política da Meta):

- Usar o número como uma pessoa usa: conversar, receber, entrar em grupos, mandar áudio e foto, por **7 a 14 dias** antes da automação.
- Começo com cerca de 10 envios ativos por dia, subindo com o tempo.
- Intervalo mínimo de 5 minutos entre envios, variar o texto (pelo menos 5 variações de estrutura).
- Não enviar mais mensagens do que o número costuma receber.
- Evitar madrugada.
- Mesmo cumprindo isso, **não existe garantia** de que não banirá. Por isso o número do bot não é o único admin.

---

## 6. Como encher o grupo (aquisição)

### 6.1 Princípios

- Mostrar a oferta e depois chamar para o grupo.
- Só entra por link (opt-in). Nunca adicionar contato.
- Qualidade importa mais que volume: 1.000 membros que leem valem mais que 3.000 que silenciaram.

### 6.2 Canais por ordem de custo-benefício

| # | Canal | Custo | Papel | Obs |
|---|---|---|---|---|
| 1 | Rede próxima (status, lista de transmissão pessoal) | R$ 0 | Semente de 50 a 100 | Postar um achado com preço no status, com "mando umas 5 dessas por dia no grupo" |
| 2 | Bio + Stories com figurinha de link | R$ 0 | Contínuo | Destaque fixo "Grupo" explicando o que entra |
| 3 | Reels de achado com CTA | Tempo | Alcance frio | Primeiros vídeos costumam render ~200 views, caminho de meses ⚠️ |
| 4 | Parcerias com microcriadores | % de comissão | Público parecido | Combinar por mensagem privada |
| 5 | Diretórios gratuitos de grupos | R$ 0 | Qualidade média/alta | Um site cita ser a fonte de melhor qualidade |
| 6 | Meta Ads (Stories/Reels → landing) | R$ 25 a 60/dia | Escala | Seção 6.4 |
| 7 | TikTok Ads | Teste só se Meta responder bem | Opcional | |
| 8 | Prova social (print de oferta esgotada) | R$ 0 | Conversão | Pilar 6 |

**Não fazer:** comprar membros, adicionar pessoas, correntes de "adicione 10 grupos", postar link em grupos de outras pessoas, "sorteio" sem checar legalidade (ver seção 9).

### 6.3 Landing de entrada (Vercel)

Uma página simples: título específico, 3 benefícios, prova (print de oferta esgotada), botão "Entrar no grupo". O botão:

1. Dispara evento de `Lead` no Pixel e na API de Conversões.
2. Registra clique com UTM (origem).
3. Redireciona para o grupo com vaga (rodízio).

Especificação em `automacao-tecnica.md`.

### 6.4 Anúncios

**Dois caminhos válidos:**

| Caminho | Como funciona | Quando |
|---|---|---|
| A. Landing + Pixel | Anúncio de Tráfego/Leads → landing → grupo | Padrão. Mede custo por entrada clicada e otimiza com evento |
| B. Click-to-WhatsApp em duas etapas | Anúncio → conversa com número Business → mensagem automática com link do grupo | Funil com filtro: só quem responde entra. Usar a mensagem de saudação do WhatsApp Business |

**Click-to-WhatsApp direto para grupo não existe**: ele abre chat 1:1. Não encontrei regra oficial da Meta sobre anúncios que levem a convite de grupo. ⚠️ Conferir as Políticas de Publicidade. Faça um primeiro teste de R$ 10 a 20 só para ver se a campanha é aprovada.

**Estrutura sugerida:**

- 1 campanha, 3 conjuntos (público amplo mulher 25 a 55 / interesse em beleza e skincare / interesse em decoração e organização).
- 3 criativos por conjunto: prova de velocidade, achado com preço, comparativo.
- Orçamento: R$ 25/dia de 24/11 a 30/11 (R$ 175), R$ 40/dia de 01/12 a 11/12 (R$ 440), R$ 60/dia de 12/12 a 18/12 (R$ 420). Total em torno de R$ 1.000 até uma semana após o lançamento.
- Regras de corte (heurísticas minhas): se, após R$ 100 gastos, o custo por entrada passar de R$ 2,50, trocar criativo e copy antes de aumentar orçamento; pausar conjunto com retenção de 7 dias abaixo de 60%.
- Referência de custo por membro das fontes: R$ 0,60 a R$ 1,80 ⚠️.

**Projeção de membros (modelo simples):**

| Fonte | Membros até 12/12 |
|---|---|
| Rede própria + status | 80 a 120 |
| Orgânico Instagram/TikTok (conta nova, 5 semanas) | 40 a 100 |
| Parcerias e diretórios | 30 a 80 |
| Ads (R$ 615 até 11/12 ÷ R$ 1,20 por entrada) | cerca de 500 |
| **Total** | **650 a 800** (cenário base), 400 no cenário ruim |

### 6.5 Retenção (mais importante que aquisição)

- Cadência fixa: mesmos horários todos os dias.
- Ofertas boas: filtro de preço real (seção 7), nota e nº de avaliações.
- Pesquisa a cada 2 semanas por reação: "qual categoria vocês querem mais?".
- Nunca repetir o mesmo produto 3 vezes.
- Avisar antes de mudar o ritmo (BF, Natal).
- Responder pelo privado quem reclama; nunca discutir no grupo.
- Medir **cliques por oferta**, não total de membros.

---

## 7. Operação diária (depois do lançamento)

### 7.1 Horários base (hipóteses para testar, não verdades)

| Horário | Tipo | Persona |
|---|---|---|
| 08h30 | Necessidade (casa, cozinha, organização) | Cida |
| 12h15 | Melhor oferta do dia (com prazo) | Ambas |
| 16h30 | Cupom ou frete grátis | Larissa |
| 19h30 | Beleza e desejo | Larissa |
| 21h00 | Achado "viral" | Larissa |

Teste: uma categoria, três horários, um horário por dia, 2 semanas, registrar cliques por post. Dias do mês importam: dia 5 vende mais que dia 27 por causa do pagamento (hipótese de uma fonte).

### 7.2 Filtro de qualidade de oferta (score; implementar na automação)

Produto só entra na fila se:

- Nota ≥ 4,6 e ≥ 200 avaliações (Cida desconfia de pouco volume).
- Desconto real: preço atual ≤ 70% da mediana dos últimos 30 dias (detecta "de/por" inflado).
- Vendedor com boa reputação e frete aceitável.
- Dentro da faixa de preço (até R$ 50 como padrão, exceções por tabela de "premium").
- Comissão acima do piso da plataforma.
- Fora da lista de bloqueio (saúde com promessa, produto com histórico de reclamação).

Isso é regra minha, não vem das fontes. Calibre com dados reais.

### 7.3 Formato da mensagem (respeitando o `bio-e-copy.md`: sem exclamação, sem travessão, sem jargão de marca)

```
Sérum vitamina C 30 ml
De R$ 79 por R$ 28
Nota 4,8 com 12 mil avaliações
Chega em 4 dias para SP
Link: {link}
```

Com opinião (só quando for verdade):

```
Testei esse protetor solar faz 3 semanas. Não pesa e não deixa a pele branca.
R$ 34 no Mercado Livre, nota 4,7.
Link: {link}
```

Para a Cida:

```
Organizador de gaveta, kit com 6. R$ 22.
4,8 estrelas, 3 mil avaliações. Muita gente da minha idade comprou e comentou que serve para cozinha.
Link: {link}
```

> Atenção à última linha: "muita gente da minha idade" é só se for verdade. Prefira fato verificável ("3 mil avaliações, muitas citam cozinha").

### 7.4 Rotina semanal

| Dia | Tarefa | Tempo |
|---|---|---|
| Dom | Batch de conteúdo + revisão da fila da semana + relatório | 3h |
| Seg | Ajustar horários e filtros conforme dados | 30 min |
| Ter a Sáb | Aprovar fila (manhã), responder DM e comentários | 30 min/dia |
| Sex | Parceria e prospecção de microcriadores | 45 min |

---

## 8. Dia do lançamento: sábado, 12/12

Premissa: o grupo já tem 500+ pessoas. O que muda é a **densidade de ofertas e a quantidade de gente nova chegando**.

| Hora | Ação |
|---|---|
| 07h00 | Checagem de links e do bot, verificar painel Shopee (campanha 12.12 ⚠️) |
| 08h00 | Stories "hoje é o dia" + mensagem no grupo avisando a agenda do dia |
| 08h30 | Oferta 1 (casa) |
| 10h00 | Oferta 2 (beleza) |
| 12h15 | Destaque do dia (melhor comissão + melhor preço) |
| 14h00 | Oferta 4 |
| 16h30 | Oferta 5 (cupom) |
| 19h30 | Oferta 6 (beleza) |
| 21h00 | Oferta 7 (viral) e resumo "o que esgotou hoje" |
| Dia todo | Ads no teto, 1 Reel de prova de velocidade a cada 3 horas, responder tudo |

Mensagem de agenda (modelo):

```
Hoje é 12/12 e tem mais oferta que o normal, das 8h30 às 21h.
Vou avisar cada achado com preço e nota.
Quem preferir silenciar e abrir só no fim do dia, tudo bem. As melhores ficam registradas aqui.
```

**Pós-lançamento (13 a 20/12):** Natal. Pico de presente 10 a 15 dias antes. Mudar linha editorial para "presentes até R$ 50".

---

## 9. Compliance e risco

### 9.1 Publicidade (CONAR)

O guia do CONAR para influenciadores (vigência 01/06/2026, segundo fontes secundárias ⚠️) trata remuneração por desempenho, como afiliado, como publicidade. Pede identificação ostensiva e imediata ("publicidade", "publi", ferramenta nativa de parceria paga). Conteúdo feito ou alterado por IA segue as mesmas regras. Aplicação prática:

- Em todo post com link de afiliado: "Publi" ou "contém link de afiliado" **no início**, não no fim da legenda.
- TikTok: ativar a configuração de conteúdo comercial.
- Descrição do grupo: aviso de afiliado (modelo na seção 4.1).
- Conferir o texto integral do guia no site do CONAR.

### 9.2 Consumidor (CDC)

- Nunca afirmar uso/experiência que não aconteceu.
- Preço sempre com data/hora e "pode mudar".
- Não inflar "de/por".
- Sem promessas de saúde/estética (ANVISA).

### 9.3 LGPD

- Só entra por link.
- Não coletar número para uso fora do grupo.
- Descrição explica como sair.

### 9.4 Sorteios

Sorteio com prêmio pode exigir autorização prévia (promoção comercial). Se não for ter consultoria jurídica, **não faça sorteio**. Use "acesso antecipado a cupom" e prova de velocidade como incentivo.

### 9.5 Regras de cada programa

- Amazon: contrato exige cadastro dos locais onde os links aparecem e regras de exibição de preço. ⚠️ Ler o Contrato de Operação antes de postar.
- Shopee e Mercado Livre: as fontes não trazem lista de práticas proibidas. ⚠️ Ler termos no painel (autocompra, uso de cupom, anúncio com link direto em buscador).
- Fiscal: Shopee mudou o modelo para PJ (NFS-e por marca para Comissão Extra, a partir de ago/2026, fonte única). ⚠️ Conversar com contador sobre MEI/CNPJ.

### 9.6 Matriz de risco

| Risco | Prob. | Impacto | Mitigação |
|---|---|---|---|
| Ban do número da automação | Média/alta | Alto | Segundo admin humano, aquecimento, volume baixo, espelho em Telegram e Canal |
| Instagram limitar alcance por repost | Alta se mantiver o fluxo atual | Médio | Seção 2.3 |
| Comissão menor que o planejado | Média | Médio | Modelo no piso, validar painéis na semana 1 |
| Ads com CPL alto | Média | Médio | Gates de decisão na seção 6.4 |
| Grupo silenciado em massa | Média | Alto | Cadência fixa, qualidade, aviso antes de mudar |
| API Shopee atrasar | Média | Médio | MVP em fluxo manual com gerador do painel |
| Reclamação de produto/oferta falsa | Média | Médio | Filtro de score, resposta no privado, retirar rápido |
| Link quebrado ou sem rastreio | Baixa | Médio | Teste diário de 3 links, painel de alertas |

---

## 10. Métricas e rituais

### 10.1 KPIs

| KPI | Definição | Meta de referência (a calibrar) |
|---|---|---|
| Membros | Total no grupo | Seção 0 |
| Custo por entrada | Gasto ÷ cliques com entrada estimada | ≤ R$ 1,80 |
| Retenção 7 dias | % que continua em 7 dias | ≥ 70% |
| Cliques por oferta | Do painel de afiliado, por subId | acompanhar tendência |
| CTR por horário | Cliques ÷ membros ativos | testar 3 horários |
| Comissão estimada/dia | Painéis | cresce semana a semana |
| Comissão confirmada | Após prazo da plataforma | |
| Incidentes | Bloqueios, reclamações | zero |

### 10.2 Rituais

- **Diário (10 min):** conferir links, cliques das 5 ofertas, saídas do grupo.
- **Semanal (domingo):** relatório, ajuste de horário e filtro, definição das 3 hipóteses da semana.
- **Quinzenal:** enquete no grupo; decisão de abrir grupo 2.

---

## 11. Orçamento

| Item | Estimativa (R$) |
|---|---|
| Chip + plano | 30 a 60 |
| Domínio | 40 a 60/ano |
| Vercel/Supabase (plano grátis no início) | 0 |
| Produtos de teste | 250 a 400 |
| Ads até 18/12 | cerca de 1.000 |
| Ferramentas de IA/vídeo | conforme assinatura atual |
| Reserva (parcerias, extras) | 200 |
| **Total até 18/12** | **R$ 1.600 a 1.800** |

Comissão esperada nos 3 primeiros meses é pequena e atrasada. Trate o investimento como CAC do ativo.

---

## 12. Decisões que dependem de você

1. **Orçamento total** que aceita investir até 18/12.
2. **Número do chip** e quem é o segundo admin humano.
3. Vai operar como **CPF, MEI ou CNPJ**? (impacta recebimento e nota fiscal da Shopee).
4. Aceita o **soft launch na Black Friday** ou prefere manter silêncio total até 12/12?
5. Quer que eu **construa a automação neste repositório**? (Recomendo: Node + Supabase + Vercel + bot de Telegram para aprovação.)
6. Confirmar quais **fontes do README** ainda serão usadas como radar e quais conteúdos próprios serão gravados.

---

## 13. Fontes consultadas

Pesquisa feita em 03/11/2026. Quase todas são páginas comerciais de ferramentas, então use como referência de prática, não como regra oficial.

**Grupos de ofertas e aquisição**
- [Nexo Afiliados: criar grupo de ofertas](https://nexoafiliados.com/blog/como-criar-grupo-de-ofertas-whatsapp)
- [Devzapp: grupos de achadinhos em 24h](https://blog.devzapp.com.br/post/estrategia-para-grupos-de-ofertas-whatsapp-24h)
- [Grupodewhatsapp: como conseguir membros](https://grupodewhatsapp.com/blog/como-conseguir-membros-grupo-promocoes)
- [DivulgaNinja: encher grupo de vendas](https://www.divulganinja.com.br/blog/como-encher-grupo-de-vendas-no-whatsapp-que-realmente-compra/)
- [Autolinks: automatizar grupos de afiliados](https://autolinks.pro/blog/como-automatizar-grupos-de-afiliados)
- [Pai das Ofertas: automatizar Shopee no WhatsApp](https://paidasofertas.com/blog/automatizar-shopee-whatsapp-tutorial)
- [Zenvia: Click to WhatsApp](https://zenvia.com/blog/como-usar-anuncios-click-to-whatsapp-no-seu-negocio/)

**Afiliados e comissões**
- [Rally de Vendas: comissão Shopee](https://rallydevendas.com.br/blog/comissao-afiliado-shopee-quanto-por-cento)
- [DivulgaNinja: Shopee e WhatsApp](https://www.divulganinja.com.br/blog/programa-afiliados-shopee-whatsapp-telegram-2026/)
- [DivulgaNinja: quanto o Mercado Livre paga](https://www.divulganinja.com.br/blog/quanto-mercado-livre-paga-afiliados-comissoes-2026)
- [DivulgaNinja: Mercado Livre 16%](https://www.divulganinja.com.br/blog/mercado-livre-afiliados-como-ganhar-16-porcento-requisitos-10k-seguidores)
- [DivulgaNinja: guia Amazon](https://www.divulganinja.com.br/blog/programa-associados-amazon-guia-afiliados-whatsapp-telegram/)
- [Actana: mudanças Shopee 2026](https://actana.com.br/blog/mudancas-na-shopee-em-2026)

**API**
- [snja/shopee-affiliate-openapi (arquivado)](https://github.com/snja/shopee-affiliate-openapi)
- [gregojoao/shopee-affiliate](https://github.com/gregojoao/shopee-affiliate) (a página retornou 404 na leitura)

**Plataformas e risco de WhatsApp**
- [Z-API: boas práticas](https://developer.z-api.io/tips/best-practices)
- [NexusAI: WhatsApp não oficial e banimento](https://nexusai.com.br/whatsapp-nao-oficial-banimento-2026/)
- [Fast Company Brasil: motivos de bloqueio](https://fastcompanybrasil.com/tech/whatsapp-veja-7-motivos-que-podem-causar-o-bloqueio-da-sua-conta/)
- [Comunidade Meta: Groups API limitada a 8 participantes](https://developers.facebook.com/community/threads/1084199161066371/)
- [Hardware.com.br: grupos de 1.024](https://www.hardware.com.br/noticias/whatsapp-comeca-a-liberar-grupos-com-1-024-pessoas/amp/)

**Instagram/TikTok/CONAR**
- [Olhar Digital: Instagram contra contas de repost](https://olhardigital.com.br/2026/04/30/internet-e-redes-sociais/instagram-aperta-o-cerco-contra-contas-de-repost-entenda-a-mudanca/)
- [Canaltech: Instagram prioriza original](https://canaltech.com.br/redes-sociais/instagram-vai-priorizar-conteudo-original-e-penalizar-repost-287469/)
- [TecMundo: regras do Para Você](https://www.tecmundo.com.br/software/286866-tiktok-entenda-regras-elegibilidade-conteudo-feed-para-voce.htm)
- [UAI: afiliado é publicidade para o Conar](https://www.uai.com.br/networking-e-negocios/2026/09/23/ganha-comissao-com-link-de-afiliado-para-o-conar-isso-ja-e-publicidade/)
- [Migalhas: Guia CONAR 2026](https://www.migalhas.com.br/depeso/456124/guia-conar-2026-o-que-todo-influenciador-precisa-saber-agora)

**Lacunas não resolvidas na pesquisa (você precisa verificar):** tabelas oficiais de comissão dos três programas; janela de cookie da Shopee e do ML; campanha oficial 12.12 da Shopee; limite atual de grupo/Comunidade na Central de Ajuda do WhatsApp; política da Meta para anúncio que leva a convite de grupo; texto integral do Guia CONAR; lista de práticas proibidas de Shopee e ML.
