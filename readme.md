# Auto Email Base

## Быстрый старт

```bash
cd /Users/nikolay.bulgakov/Documents/Work/new-base/old/bf_v2
nvm use
npm i
chmod +x ./mail
```

## Основные команды

```bash
./mail dev X_IQ rfm-311
./mail build-min X_IQ rfm-311
./mail build-pretty X_IQ rfm-311
./mail clean
```

- `dev` — watch + локальный сервер
- `build-min` — minify head (по умолчанию)
- `build-pretty` — без минификации, + `index.pretty.html`
- `clean` — удаляет `dist/` (в git не попадает)

## Где результат

```
dist/<CATEGORY>/mail-<MAIL>/<LOCALE>/index.html
```

`index.pretty.html` создаётся только через `build-pretty` или флаг `--pretty`.

## Полезные флаги

- `--pretty` — дополнительно создать `index.pretty.html`
- `--no-trimCss` — отключить трим неиспользуемых правил
- `--minifyHtml` — минимизировать HTML (осторожно)
- `--minifyAll` — минимизировать HTML + head CSS + inline CSS
- `--locales en,es` — собрать только выбранные локали

## Как сделать новое письмо

```
X_IQ/mail-rfm-311  ->  X_IQ/mail-rfm-999
```

И запустить:

```bash
./mail dev X_IQ rfm-999
```
