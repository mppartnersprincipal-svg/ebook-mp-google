# Método Balcão Cheio — Landing Page

Landing page de venda do e-book **Método Balcão Cheio** (M|P Assessoria Digital) —
guia de 7 passos para lojas de material de construção aparecerem no Google.

Página **100% estática** (HTML + CSS + JS puro, sem framework, sem build).
Renderiza instantaneamente e carrega em menos de 3 segundos.

---

## 🚀 Deploy na Vercel

Este repositório já está pronto pra Vercel — **não precisa de build**.

1. Acesse [vercel.com](https://vercel.com) e clique em **Add New → Project**.
2. Importe o repositório `mppartnersprincipal-svg/ebook-mp-google`.
3. Em *Framework Preset*, deixe **Other** (é site estático).
4. *Build Command* e *Output Directory*: **deixe em branco** (a Vercel serve a raiz).
5. Clique em **Deploy**.

Cada `git push` na branch `main` gera um novo deploy automático.

---

## ⚙️ O que preencher antes de rodar tráfego

Tudo está marcado dentro do `index.html` com o prefixo `>>>`. São 3 itens:

### 1. Domínio
As tags `canonical`, `og:url`, `og:image` e `twitter:image` usam
`https://ebook-mp-google.vercel.app/` como padrão. Se você usar um **domínio
próprio** na Vercel, substitua essa URL no `index.html`, no `robots.txt` e no `sitemap.xml`.

### 2. Imagem de compartilhamento (og:image)
Gere uma imagem **1200×630px** (capa do e-book / oferta) e salve como
`assets/og-image.jpg`. É a imagem que aparece ao compartilhar o link no
WhatsApp, Instagram e redes. Sem ela, o link compartilha sem prévia.

### 3. Pixels de rastreamento
No `<head>` do `index.html` há dois blocos comentados prontos:

- **Meta Pixel** (Facebook/Instagram Ads) → troque `SEU_PIXEL_ID` e descomente.
- **Google tag** (GA4 / Google Ads) → troque `G-XXXXXXX` / `AW-XXXXXXXXX` e descomente.

Os cliques nos botões de compra já disparam os eventos `InitiateCheckout`
(Meta) e `begin_checkout` (Google) automaticamente — só passam a registrar
quando os pixels estiverem instalados.

> **Importante:** para medir a **compra concluída**, o pixel também precisa
> estar na página de checkout/obrigado (`ggcheckout.app`). Esta LP mede apenas
> o início do checkout.

---

## 📁 Estrutura

```
index.html          Landing page completa (CSS e JS inline)
assets/             Logo M|P (SVG)
uploads/            Logos dos clientes (WebP)
vercel.json         Headers de cache e segurança
robots.txt          Indexação liberada
sitemap.xml         Mapa do site (1 página)
```

---

## 🎯 Checkout

O botão de compra aponta para:
`https://ggcheckout.app/checkout/v2/eUguTMM9upibnKAKUj0R`

Para trocar, faça um "localizar e substituir" dessa URL no `index.html`.

---

© M|P Assessoria Digital · [mppartners.com.br](https://mppartners.com.br)
