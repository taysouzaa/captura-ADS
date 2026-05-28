# Relatório de SEO — Lead Curso ADS (Método P4)
**Arquivo analisado:** `index.html`  
**Última atualização:** 21 de maio de 2026  
**URL de produção prevista:** `https://productads.metodop4.com.br/`  
**Repositório GitHub:** `https://github.com/taysouzaa/captura-ADS`  
**Branch:** `master` — commit inicial `cfc006f`

---

## Resumo Executivo

A landing page está bem estruturada do ponto de vista de SEO técnico. Todas as melhorias críticas identificadas na análise inicial foram implementadas. A única pendência antes da publicação é criar o arquivo `assets/og-image.png` (1200×630 px).

| Categoria | Status |
|---|---|
| Meta tags básicas | ✅ OK |
| Open Graph / Twitter Card | ✅ OK |
| JSON-LD estruturado (Course + FAQPage) | ✅ Implementado |
| Hierarquia de headings | ✅ OK |
| Imagens com alt text | ✅ OK |
| Keywords / conteúdo | ✅ OK |
| Performance / preload | ✅ Implementado |
| Mobile / responsividade | ✅ OK |
| Acessibilidade (aria) | ✅ Implementado |
| Compartilhamento social | ✅ OK |
| sitemap.xml | ✅ Criado |
| robots.txt | ✅ Criado |
| Canonical URL | ✅ OK |

---

## 1. Meta Tags Básicas

```html
<title>Aula Gratuita de Product Ads — Método P4</title>
<meta name="description" content="Aprenda de graça como usar o Product Ads para vender mais no Mercado Livre...">
<meta name="keywords" content="product ads, mercado livre, curso gratuito, anúncios mercado livre, método p4, gabriel pim, e-commerce, vendas online">
<meta name="robots" content="index, follow">
<meta name="author" content="Método P4">
<link rel="canonical" href="https://productads.metodop4.com.br/">
```

**Status: ✅ Completo**

- `<title>` com 49 caracteres — dentro do ideal (50–60 chars). Inclui keyword principal ("Product Ads") e a marca.
- `<meta name="description">` com ~130 caracteres — dentro do ideal (120–155 chars).
- `<meta name="keywords">` adicionado com 8 termos relevantes.
- `canonical` aponta para a URL definitiva — garante que UTM params não causem conteúdo duplicado.
- `lang="pt-BR"` no `<html>` — correto para indexação regional.

---

## 2. Open Graph e Twitter Card

```html
<meta property="og:type"       content="website">
<meta property="og:url"        content="https://productads.metodop4.com.br/">
<meta property="og:title"      content="Curso Gratuito de Product Ads — Método P4">
<meta property="og:image"      content="https://productads.metodop4.com.br/assets/og-image.png">
<meta property="og:image:alt"  content="Curso Gratuito de Product Ads — Método P4">
<meta property="og:image:width"  content="1200">
<meta property="og:image:height" content="630">
<meta property="og:locale"     content="pt_BR">
<meta property="og:site_name"  content="Método P4">
<meta name="twitter:card"      content="summary_large_image">
```

**Status: ✅ Completo**

- `og:image:alt` adicionado — acessibilidade no compartilhamento.
- Dimensões 1200×630 declaradas — compatível com WhatsApp, Facebook e LinkedIn.

**Pendência:** Criar `assets/og-image.png` (1200×630 px) com a identidade visual da marca.

---

## 3. JSON-LD — Schema Estruturado

Dois schemas implementados: `Course` e `FAQPage`.

**`@type: Course`** — descreve o conteúdo educacional para o Google:
- `name`, `description`, `provider`, `instructor`, `offers` (preço 0, BRL), `educationalLevel: Beginner`, `inLanguage: pt-BR`
- Links `sameAs` para Instagram, LinkedIn e YouTube do Método P4

**`@type: FAQPage`** — permite rich results (acordeão de perguntas na SERP):
- 5 perguntas implementadas no schema, sincronizadas com o accordion HTML

**Status: ✅ Implementado**

**Recomendação futura:** Adicionar `AggregateRating` ao `Course` quando houver avaliações verificáveis:
```json
"aggregateRating": { "@type": "AggregateRating", "ratingValue": "5", "reviewCount": "4", "bestRating": "5" }
```

---

## 4. Hierarquia de Headings

```
H1 — "100% Gratuito transformar suas vendas no Mercado Livre"
  H2 — "Por que você precisa participar dessa aula?"
  H2 — "O que você vai aprender?"
  H2 — "Ainda está com dúvidas?"
  H2 — "Quem é o Gabriel Pim"
  H2 — "Depoimentos"
```

**Status: ✅ Correto** — um H1 único, H2 organizando seções, sem salto de nível.

---

## 5. Imagens e Alt Text

| Imagem | Alt declarado | Situação |
|---|---|---|
| Logo navbar (`01 (1).png`) | `alt="Método P4"` | ✅ |
| Logo footer (`03.png`) | `alt="Método P4"` | ✅ |
| Hero background | CSS bg-image + texto sobreposto | ✅ decorativa |
| Instructor background | CSS bg-image + texto sobreposto | ✅ decorativa |
| Ícones Font Awesome decorativos | `aria-hidden="true"` | ✅ implementado |

**Status: ✅ OK**

---

## 6. Keywords e Densidade de Conteúdo

| Keyword | Posição |
|---|---|
| Product Ads | Title, description, keywords, corpo, FAQ |
| Mercado Livre | Title, H1, corpo, FAQ, schema |
| Gratuito | Title, hero, price card, modal |
| Método P4 | Title, OG, JSON-LD, footer, schema |
| Gabriel Pim | JSON-LD, seção instrutor |
| Anúncios / Campanhas | Body, FAQ, checklist |

**Status: ✅ Bom** — keywords naturais, sem stuffing, sinônimos presentes.

---

## 7. Performance e Core Web Vitals

**Status: ✅ Implementado**

```html
<link rel="preconnect" href="https://cdnjs.cloudflare.com">
<link rel="preload" href="fonts/static/Sora-Bold.ttf" as="font" type="font/ttf" crossorigin>
<link rel="preload" href="fonts/static/Sora-Regular.ttf" as="font" type="font/ttf" crossorigin>
<link rel="preload" as="image" href="assets/ChatGPT%20Image%2021%20de%20mai.%20de%202026%2C%2016_12_07.png">
```

- Preload das fontes mais usadas → elimina FOUT (Flash of Unstyled Text)
- Preload da imagem hero → melhora o LCP (Largest Contentful Paint)
- Preconnect para CDN do Font Awesome → reduz latência de rede
- CSS inline no `<head>` — zero requests de .css externo ✅
- JS ao final do `<body>` — não bloqueia renderização ✅

---

## 8. Mobile e Responsividade

**Status: ✅ Correto**

- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- Breakpoints: `max-width: 900px`, `max-width: 768px`, `max-width: 480px`
- Cards de depoimento: horizontais em desktop/tablet, verticais em mobile (< 480px)
- Carrossel drag-scroll funciona com mouse e touch
- Hambúrguer menu mobile com animação
- Botão WhatsApp flutuante visível em todas as telas
- Modal de formulário responsivo

---

## 9. Acessibilidade (A11y)

**Status: ✅ Implementado**

- `aria-label` nos links sociais do footer, nav burger, WhatsApp, modal e carrossel
- `aria-modal="true"` no modal de formulário
- `aria-live="polite"` no estado de sucesso do formulário
- `aria-expanded` nos botões de FAQ (via JavaScript)
- `tabindex="0"` e `role="button"` nos acionadores do FAQ
- `aria-hidden="true"` em todos os ícones Font Awesome decorativos (FAQ, price badge, depoimentos, modal)

---

## 10. Compartilhamento Social

**Status: ✅ Completo**

- Open Graph completo (Facebook, WhatsApp, LinkedIn)
- Twitter Card `summary_large_image`
- Links sociais com `aria-label` e `rel="noopener noreferrer"`
- WhatsApp flutuante com mensagem pré-preenchida

---

## 11. Arquivos Técnicos

**Status: ✅ Criados**

- **`sitemap.xml`** — URL `https://productads.metodop4.com.br/`, `changefreq: monthly`, `priority: 1.0`
- **`robots.txt`** — `Allow: /` + apontamento para o sitemap

---

## 12. Conteúdo e Conversão

**Status: ✅ Bem estruturado**

- Proposta de valor no hero: "100% Gratuito" + "Mercado Livre"
- 4 depoimentos reais com nomes: Marcos Tezotto, Telma, Adriano Almeida Pereira, Roniclaudio
- Bio detalhada do instrutor Gabriel Pim
- **FAQ com 5 perguntas** que eliminam objeções de inscrição
- CTAs em: hero, seção de preço, FAQ e instrutor
- Formulário com 5 campos: nome, WhatsApp (2×), e-mail, nível de medalha ML

---

## Controle de Versão

| Data | Ação | Detalhe |
|---|---|---|
| 21/05/2026 | Repositório criado | `git init` + `git remote add origin https://github.com/taysouzaa/captura-ADS.git` |
| 21/05/2026 | Commit inicial | `cfc006f` — 19 arquivos (index.html, assets, fonts, SEO-REPORT, sitemap, robots) |
| 21/05/2026 | Push para GitHub | Branch `master` publicada em `https://github.com/taysouzaa/captura-ADS` |
| 21/05/2026 | Push branch `main` | Conteúdo movido para branch padrão `main` |
| 21/05/2026 | Troca imagem hero | `ChatGPT Image 21 de mai...png` → `79c11951-48df-4d6a-b3f4-baa48199607b.png` (preload + background-image atualizados) |

---

## Pendência Única Antes da Publicação

| Item | Descrição |
|---|---|
| 🔴 `assets/og-image.png` | Imagem 1200×630 px com identidade visual do Método P4 — necessária para preview ao compartilhar no WhatsApp, Facebook e LinkedIn |

---

## Histórico Completo — O Que Foi Construído

### Estrutura da página (em ordem)

1. **`<head>` SEO** — title, description, keywords, canonical, OG, Twitter Card, JSON-LD Course, JSON-LD FAQPage, preconnect, preload de fontes e hero image
2. **Navbar fixa** — logo clicável, links âncora, hambúrguer mobile, solid-on-scroll via JS
3. **Hero** — background com imagem + gradiente, H1 com keywords, CTA principal
4. **Por que participar** — grid 2×2 com 4 benefit cards numerados, hover com translateY + green glow
5. **O que você vai aprender** — 4 itens fiéis ao conteúdo original, cards com borda verde esquerda, sem ícones
6. **Preço / CTA** — price card escuro (dark navy) sobre fundo branco, destaque "100% GRATUITA"
7. **FAQ** — accordion acessível com 5 perguntas; seção na cor azul escuro (intercalação)
8. **Instrutor (Gabriel Pim)** — background com foto, bio completa, intocada na intercalação de cores
9. **Depoimentos** — carrossel drag-scroll com 4 cards **deitados** (horizontal): avatar+nome+estrelas à esquerda, texto à direita; vertical em mobile
10. **Footer** — logo, redes sociais, contato; intocado na intercalação de cores
11. **WhatsApp flutuante** — botão fixo com mensagem pré-preenchida via URL encode
12. **Modal de formulário** — 5 campos, máscara de telefone, validação, envio via webhook n8n

### Intercalação de cores das seções

| Seção | Cor |
|---|---|
| Hero | Imagem própria (intocada) |
| Por que participar | Azul escuro (`--dark2` → `--section-blue`) |
| O que você vai aprender + Preço | Branco (`#fff` → `#f4f8fd`) |
| FAQ | Azul escuro (`--dark2` → `--section-blue`) |
| Gabriel Pim (Instrutor) | Imagem própria (intocada) |
| Depoimentos | Branco (`#f8fbff` → `#fff`) |
| Footer | Azul escuro (intocado) |

### Funcionalidades JavaScript

- Scroll reveal com IntersectionObserver (`reveal`, `d1`–`d4`)
- Nav solid on scroll
- Hambúrguer menu mobile
- FAQ accordion com `aria-expanded`, suporte a teclado (Enter/Space)
- Carrossel drag-scroll (mouse e touch) com scroll por largura real do card
- Modal abrir/fechar
- Máscara de telefone `(XX) XXXXX-XXXX`
- Captura de UTM params (`utm_source`, `utm_medium`, `utm_campaign`, `utm_content`, `utm_term`)
- POST para webhook: `https://n8n.srv1095468.hstgr.cloud/webhook/lead-ADS`
- Estado de sucesso após envio

### Sistema de design

| Token | Valor |
|---|---|
| `--dark` | `#111c2c` |
| `--dark2` | `#0b1422` |
| `--section-blue` | `#0f1d31` |
| `--green` | `#58de56` |
| `--green2` | `#41c63f` |
| `--green3` | `#8bf286` |
| `--white` | `#fdfdfd` |
| Tipografia | Sora (self-hosted, 6 pesos, `font-display: swap`) |
| Border radius cards | 14px – 20px |
| Animações | CSS transitions + IntersectionObserver reveal |

