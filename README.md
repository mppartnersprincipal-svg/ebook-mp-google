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
✅ Configurado: **`https://ebook.mppartners.com.br/`** (canonical, OG, robots e sitemap).
Requer o domínio adicionado no projeto da Vercel (Settings → Domains) e o
CNAME `ebook → cname.vercel-dns.com` na zona DNS da Hostinger.

### 2. Imagem de compartilhamento (og:image)
✅ Pronta: `assets/og-image.jpg` (1200×630) — aparece ao compartilhar o link
no WhatsApp, Instagram e redes. Se atualizar a arte, mantenha o mesmo nome
de arquivo e use o [Sharing Debugger](https://developers.facebook.com/tools/debug/)
para limpar o cache da Meta.

### 3. Pixels de rastreamento
- **Meta Pixel** → ✅ **instalado e ativo** ("Pixel Ebook Google MP", ID `1584286433549777`).
  Dispara `PageView` no carregamento e `InitiateCheckout` no clique dos botões.
- **Google tag** (GA4 / Google Ads) → ainda comentado no `<head>`; troque
  `G-XXXXXXX` / `AW-XXXXXXXXX` e descomente quando for usar.

O mesmo Pixel ID deve estar configurado na GGCheckout (integração nativa,
de preferência com o token da API de Conversões) para registrar o `Purchase`.

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

O botão de compra aponta para o checkout no domínio próprio (GGCheckout):
`https://pay.mppartners.com.br/checkout/v4/eUguTMM9upibnKAKUj0R`

(CNAME `pay → pay.ggcheckout.app` na zona DNS da Hostinger. A URL antiga
`ggcheckout.app/checkout/v4/...` continua válida como fallback.)

Para trocar, faça um "localizar e substituir" dessa URL no `index.html`.

---

© M|P Assessoria Digital · [mppartners.com.br](https://mppartners.com.br)
