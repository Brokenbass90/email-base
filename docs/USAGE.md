# Auto Email Base — Usage

## Requirements

- Node.js **20.18.1** (see `.nvmrc`)
- npm

## Install

```bash
nvm use
npm i
```

## Build ONE email

Build **all locales** that exist in `vendor/data/<locale>/`:

```bash
npm run build -- --category X_IQ --mail rfm-311
```

Build **only selected locales**:

```bash
npm run build -- --category X_IQ --mail rfm-311 --locales en,ru
```

Output:

- `dist/<CATEGORY>/mail-<MAIL>/<LOCALE>/index.html` — compact
- `dist/<CATEGORY>/mail-<MAIL>/<LOCALE>/index.pretty.html` — readable

## Dev (watch + server + auto-open)

```bash
npm run dev -- --category X_IQ --mail rfm-311
```

- Serves `dist/` on `http://127.0.0.1:3001/`
- Opens **pretty** by default
- Live reload on changes

Example URL:

`http://127.0.0.1:3001/X_IQ/mail-rfm-311/en/`

## Create a new email

1) Copy an existing mail folder:

```bash
cp -R X_IQ/mail-rfm-311 X_IQ/mail-my-new-mail
```

2) Edit:

- `X_IQ/mail-my-new-mail/app/templates/index.pug` (preferred)
- `X_IQ/mail-my-new-mail/app/styles/main.styl`

3) Optional head-extra (goes to head and inline):

- `X_IQ/mail-my-new-mail/app/styles/head-extra.styl`

4) Run dev:

```bash
npm run dev -- --category X_IQ --mail my-new-mail
```

## Locales & missing keys

Locales = folders in `vendor/data/`.

If a key is missing, it stays as the key/placeholder (good for development).
