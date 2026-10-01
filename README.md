# Caderno de Inglês

Aplicativo web para treinar inglês um pouco por dia. É um único arquivo (`index.html`), sem instalação: basta abrir no navegador.

## Exercícios

- **Cartões**: vocabulário com pronúncia (IPA e áudio) e repetição espaçada. Acertou, a palavra sobe de nível; errou, ela volta para o começo e aparece mais.
- **Quiz**: múltipla escolha nas duas direções (inglês → português e português → inglês).
- **Gramática**: complete a frase, com explicação em português de cada regra.
- **Ditado**: ouça uma frase e escreva o que entendeu. O app marca as palavras que faltaram.
- **Pronúncia**: pares mínimos (*ship* × *sheep*, *three* × *tree*) com dicas de como produzir cada som, sílaba tônica, e leitura em voz alta com correção por reconhecimento de voz (Chrome ou Edge, com microfone liberado). Onde o microfone não está disponível, você ouve o modelo, repete e se autoavalia.

Três níveis: **Iniciante** (A1–A2), **Intermediário** (B1–B2) e **Avançado** (C1). Cada nível tem vocabulário, gramática, ditado e pronúncia próprios, e a voz fica mais rápida nos níveis mais altos.

Meta diária de XP, sequência de dias e progresso ficam salvos no navegador (`localStorage`).

## Como usar

O app é um PWA: pode ser instalado na tela inicial do celular ou do computador e funciona sem internet.

### Publicar com o GitHub Pages (grátis)

1. No GitHub, abra o repositório e vá em **Settings → Pages**.
2. Em **Source**, escolha **Deploy from a branch**.
3. Selecione o branch com o app (por exemplo `main`) e a pasta **/ (root)**. Clique em **Save**.
4. Em um ou dois minutos o app fica disponível em `https://marcoszanchet.github.io/marcoszanchet/`.

### Instalar no aparelho

- **Android (Chrome)**: abra o endereço e toque em **Instalar** no fim da página, ou no menu ⋮ → **Instalar app**.
- **iPhone (Safari)**: toque em **Compartilhar** → **Adicionar à Tela de Início**.
- **Computador (Chrome ou Edge)**: clique no ícone de instalação na barra de endereço.

Depois da primeira abertura, o app funciona offline. A voz usa as vozes em inglês do próprio aparelho.

### Rodar localmente

```sh
python3 -m http.server 8000
```

Abra `http://localhost:8000`. Abrir o `index.html` direto também funciona, mas sem instalação nem modo offline.

### Publicar uma nova versão

Depois de mudar o app, troque o valor de `VERSION` em `sw.js` (por exemplo `caderno-v2`) para que os aparelhos baixem a versão nova.

Atalhos: `espaço` vira o cartão, `1`/`2` marcam erro/acerto, `1`–`4` escolhem a opção no quiz e na gramática.

## Como adicionar conteúdo

As palavras, frases de gramática e de ditado ficam no começo do `<script>`, nas constantes `CATS`, `GRAMMAR`, `DICTATION`, `PAIRS` e `STRESS`, separadas por nível.
