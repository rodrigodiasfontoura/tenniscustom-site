# Tennis Custom — Site

Site oficial do app Tennis Custom. Hospedado no GitHub Pages com domínio customizado em `tenniscustom.app`.

## Estrutura

```
.
├── index.html              # Landing PT (default em /)
├── en/index.html           # Landing EN (em /en/)
├── privacidade.html        # Privacy PT
├── privacy.html            # Privacy EN
├── termos.html             # Terms PT
├── terms.html              # Terms EN
├── suporte.html            # Support PT
├── support.html            # Support EN
├── 404.html                # Página de erro bilíngue
├── legal.css               # CSS compartilhado das páginas legais
├── CNAME                   # Domínio customizado para GitHub Pages
└── README.md
```

## URLs públicas

- `https://tenniscustom.app/` — Landing PT
- `https://tenniscustom.app/en/` — Landing EN
- `https://tenniscustom.app/privacidade.html` — Política de Privacidade
- `https://tenniscustom.app/privacy.html` — Privacy Policy
- `https://tenniscustom.app/termos.html` — Termos de Uso
- `https://tenniscustom.app/terms.html` — Terms of Use
- `https://tenniscustom.app/suporte.html` — Suporte
- `https://tenniscustom.app/support.html` — Support

## Deploy — Passo a passo

### 1. Criar repositório no GitHub

1. Acesse [github.com/new](https://github.com/new)
2. Nome do repo: `tenniscustom-site` (ou qualquer outro)
3. Marque **Public** (obrigatório para GitHub Pages no plano grátis)
4. Não inicialize com README/license/gitignore
5. Clique em **Create repository**

### 2. Subir os arquivos

Pelo terminal, dentro da pasta do projeto:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/tenniscustom-site.git
git push -u origin main
```

### 3. Ativar GitHub Pages

1. No repositório, vá em **Settings → Pages**
2. Em **Source**, selecione `Deploy from a branch`
3. Branch: `main`, pasta: `/ (root)`
4. Clique em **Save**

Aguarde 1–2 minutos. Acesse `https://SEU-USUARIO.github.io/tenniscustom-site/` para verificar.

### 4. Configurar o domínio customizado no Namecheap

No painel do Namecheap, em **Domain List → Manage → Advanced DNS**, configure:

**Apague registros existentes (parking, etc.)** e adicione:

| Type | Host | Value | TTL |
|------|------|-------|-----|
| A Record | @ | 185.199.108.153 | Automatic |
| A Record | @ | 185.199.109.153 | Automatic |
| A Record | @ | 185.199.110.153 | Automatic |
| A Record | @ | 185.199.111.153 | Automatic |
| CNAME | www | SEU-USUARIO.github.io | Automatic |

Substitua `SEU-USUARIO` pelo seu username do GitHub.

### 5. Configurar o domínio no GitHub

1. No repositório, **Settings → Pages**
2. Em **Custom domain**, digite: `tenniscustom.app`
3. Clique em **Save**
4. Aguarde a verificação DNS (pode levar de 5min a 24h, geralmente é rápido)
5. Quando aparecer "DNS check successful", marque ✅ **Enforce HTTPS**

O arquivo `CNAME` no repo já tem o domínio. O GitHub vai emitir um certificado SSL Let's Encrypt automaticamente.

### 6. App Store Connect

No App Store Connect, atualize as URLs do app:
- **Privacy Policy URL:** `https://tenniscustom.app/privacy.html`
- **Support URL:** `https://tenniscustom.app/support.html`
- **Marketing URL** (opcional): `https://tenniscustom.app/en/`

Para a App Store em PT, use as URLs `/privacidade.html` e `/suporte.html`.

## Editar o site no futuro

Cada página é um arquivo HTML único, com CSS inline (landing) ou via `legal.css` (páginas legais). Não há build step.

Para editar:
1. Edite o arquivo HTML diretamente
2. `git add . && git commit -m "Update" && git push`
3. GitHub Pages atualiza em ~1 minuto

## Checklist quando publicar o app na App Store

- [ ] Trocar "Em breve na App Store" / "Coming soon" pelo botão real do App Store nas duas landing pages
- [ ] Adicionar screenshots reais do app na seção de features
- [ ] Atualizar Open Graph image com preview real
- [ ] Adicionar favicon (ícone do app em `/favicon.ico` e PNGs)
- [ ] Considerar Plausible/Umami para analytics privados (opcional)

## Stack

- HTML + CSS puro, sem build step
- Google Fonts (Fraunces + IBM Plex Sans + IBM Plex Mono)
- Hospedagem: GitHub Pages
- DNS: Namecheap
- SSL: Let's Encrypt (automático via GitHub)

## Autoria

Tennis Custom · © 2026 Rodrigo Fontoura
