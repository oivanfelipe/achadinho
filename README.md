# Achei Promo

Grupo de ofertas no WhatsApp com conteúdo de beleza, cosméticos e casa.
Monetização via afiliados: Shopee, Mercado Livre e Amazon.

---

## Estrutura do Projeto

```
estrategia/
  personas.md              # Duas personas definidas (Dona Cida 50+ e Larissa padrão)
  plano-lancamento-12-12.md  # Plano completo 03/11 a 12/12: conteúdo, aquisição, cronograma, compliance
  foco-mercado-livre-jornada.md  # Foco ML: regras do programa, jornada até o grupo, links, curadoria, modelo
  como-o-mercado-opera.md  # Como operadores de grupos de ofertas captam membros hoje + protocolo de reconhecimento
  automacao-tecnica.md     # Arquitetura da automação, API Shopee, gateway WhatsApp, dados
  pesquisa-repos-termos-ferramentas.md  # Termos oficiais Shopee, repos open source lidos, WAHA, Canais, limites do Instagram

conteudo/
  roteiros-google-flow.md  # Roteiros de vídeo com produto (fases 2 e 3)
  prompts-aquecimento-flow.md  # Prompts sem produto para fase 1 (dias 1-14)
  plano-aquecimento-perfis.md  # Aquecimento dos perfis 04/11 a 24/11, gate para anúncio, triagem de vídeos

marca/
  bio-e-copy.md            # Bios dos perfis, fórmulas de copy e checklist
  persona-virtual.md       # Rosto da marca (personagem criada com IA): ficha, prompts, bios e regras
```

---

## Personas

**Dona Cida (50+)**
Mulher 55-68 anos. Facebook e WhatsApp. Compra anti-idade, casa e saúde.
Ticket médio R$180. Precisa de confiança antes de comprar.

**Larissa (Padrão)**
Mulher 28-40 anos. Instagram e TikTok. Compra skincare, beleza e decor.
Ticket médio R$65. Age por FOMO, alta frequência de recompra.

---

## Plataformas de Afiliado

| Plataforma | Comissão | Melhor para |
|---|---|---|
| Mercado Livre | 16% estável | Beleza, moda, esporte |
| Amazon | Carrinho inteiro | Eletrônicos, tech |
| Shopee | 3-5% | Volume, produtos virais |

---

## Fluxo de Conteúdo

**Dias 1-14 (Aquecimento)**
Conteúdo sem produto. Objetivo: engajamento, saves e comentários.
Usar prompts do `prompts-aquecimento-flow.md` no CapCut ou Kling AI.
Fontes: canais do Telegram abaixo, transformados no CapCut antes de postar.

**Dias 15-21 (Conversão)**
Conteúdo com produto. CTA para o grupo WPP.
Usar roteiros do `roteiros-google-flow.md`.

---

## Fontes de Vídeo (Telegram)

- t.me/videosparaafiliadosgratisbr
- t.me/videosdashopeegratis
- t.me/achadinhosshopeeb
- t.me/videosdeprodutosdashopeebr
- t.me/videosachadinhosshopeebr

**Regra:** sempre transformar no CapCut antes de postar (flip + zoom + áudio novo + texto).

---

## Regras de Copy

- Sem travessões
- Sem exclamação
- Sem jargão de marca ("curadoria", "exclusivo", "incrível")
- Preço sempre específico quando tiver
- Tom de amiga mandando mensagem, não de anúncio
- Link nunca na legenda, sempre na bio
- Bio aponta para o grupo WPP

---

## Bio dos Perfis

**Instagram**
```
Achei Promo ✨
Acho primeiro. Conto aqui. Você decide.
💄 Beleza · 🏠 Casa · ✨ Cosméticos
👇 Grupo WPP com achados todo dia
```

**TikTok**
```
Achei Promo ✨
Promoção boa eu não guardo só pra mim
💄 Beleza · Casa
📲 Grupo WPP no link ⬇️
```

---

## Fluxo Completo

```
Instagram/TikTok (conteúdo)
        ↓
    Bio com link do grupo WPP
        ↓
    Grupo WhatsApp
        ↓
    Oferta com link de afiliado
        ↓
    Comissão (Shopee / ML / Amazon)
```
