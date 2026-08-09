# Repo projeto-alphractal Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [x]`) syntax for tracking.

**Goal:** Criar e publicar o repositório público `InteliBlockchain-IBC/projeto-alphractal` — landing page do primeiro projeto do clube com um parceiro externo, com README curto, TAP versionado e licença MIT.

**Architecture:** Repositório git único (sem framework, sem build). Um `README.md` estático como página inicial, um PDF versionado em `docs/`, um asset de imagem em `assets/`, licença MIT na raiz. Não há código de aplicação nesta fase — o código do MVP entra neste mesmo repo em um ciclo futuro, fora deste plano.

**Tech Stack:** Git, GitHub (`gh` CLI), Markdown. Nenhuma dependência de runtime.

## Global Constraints

- Repositório: `InteliBlockchain-IBC/projeto-alphractal`, **público**, branch padrão `main`.
- Licença: **MIT**, titular do copyright "Inteli Blockchain", ano 2026 — exigida pelo TAP (seção 5, Propriedade Intelectual).
- Nome da empresa parceira em qualquer texto novo: **Alphractal** (o arquivo PDF original tem o typo "Alphactral" — não repita o erro em conteúdo novo).
- Sem `CLAUDE.md` neste repo e sem alterar o `CLAUDE.md` raiz do workspace (decisão do spec).
- Todo commit em português, conventional commits (`docs:`, `chore:`), seguindo o padrão já usado nos outros repos do clube (`aulas`, `docs3`).
- Repositório local já existe e está inicializado em `/home/messiasolivindo/Documentos/github/inteli_blockchain/projetos/projeto-alphractal/`, branch `main`, com 1 commit (`docs: adiciona design do repo projeto-alphractal`). Todos os comandos abaixo assumem esse diretório como cwd, salvo indicação contrária.

---

### Task 1: Licença MIT

**Files:**
- Create: `LICENSE`

**Interfaces:**
- Produces: arquivo `LICENSE` na raiz — sem dependência de outros arquivos.

- [x] **Step 1: Criar o arquivo `LICENSE`**

Conteúdo exato (texto padrão MIT):

```
MIT License

Copyright (c) 2026 Inteli Blockchain

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

- [x] **Step 2: Verificar**

Run: `test -f LICENSE && head -3 LICENSE`
Expected: imprime `MIT License` / linha em branco / `Copyright (c) 2026 Inteli Blockchain`.

- [x] **Step 3: Commit**

```bash
git add LICENSE
git commit -m "chore: adiciona licença MIT"
```

---

### Task 2: Banner do clube

**Files:**
- Create: `assets/banner_blockas.png` (copiado de `aulas/others/assets/banner_blockas.png`, no workspace pai, fora deste repo)

**Interfaces:**
- Produces: `assets/banner_blockas.png` — consumido pela tag `<img>` do `README.md` (Task 4).

- [x] **Step 1: Copiar o banner**

O arquivo de origem está fora deste repositório, em outro repositório do workspace. Caminho absoluto de origem (ajuste se o workspace estiver em outro local):
`/home/messiasolivindo/Documentos/github/inteli_blockchain/aulas/others/assets/banner_blockas.png`

```bash
mkdir -p assets
cp "/home/messiasolivindo/Documentos/github/inteli_blockchain/aulas/others/assets/banner_blockas.png" assets/banner_blockas.png
```

- [x] **Step 2: Verificar**

Run: `file assets/banner_blockas.png`
Expected: `assets/banner_blockas.png: PNG image data, ...` (arquivo binário válido, não vazio).

- [x] **Step 3: Commit**

```bash
git add assets/banner_blockas.png
git commit -m "chore: adiciona banner do clube"
```

---

### Task 3: TAP versionado

**Files:**
- Create: `docs/TAP-Alphractal.pdf` (copiado de `documentos_projetos/TAP - Inteli Blockchain e Alphactral.pdf`, no workspace pai)

**Interfaces:**
- Produces: `docs/TAP-Alphractal.pdf` — consumido pelo link da seção "Links" do `README.md` (Task 4).

- [x] **Step 1: Copiar e renomear o TAP**

Caminho absoluto de origem (ajuste se o workspace estiver em outro local):
`/home/messiasolivindo/Documentos/github/inteli_blockchain/documentos_projetos/TAP - Inteli Blockchain e Alphactral.pdf`

```bash
mkdir -p docs
cp "/home/messiasolivindo/Documentos/github/inteli_blockchain/documentos_projetos/TAP - Inteli Blockchain e Alphactral.pdf" "docs/TAP-Alphractal.pdf"
```

Note: o nome do arquivo de origem tem o typo "Alphactral" — o novo nome (`TAP-Alphractal.pdf`) já corrige isso. Não altere o conteúdo do PDF, só o nome do arquivo.

- [x] **Step 2: Verificar**

Run: `file "docs/TAP-Alphractal.pdf"`
Expected: `docs/TAP-Alphractal.pdf: PDF document, ...`

- [x] **Step 3: Commit**

```bash
git add "docs/TAP-Alphractal.pdf"
git commit -m "docs: adiciona TAP do projeto Alphractal"
```

---

### Task 4: README

**Files:**
- Create: `README.md`

**Interfaces:**
- Consumes: `assets/banner_blockas.png` (Task 2), `docs/TAP-Alphractal.pdf` (Task 3) — ambos já devem existir no repo antes deste task.
- Produces: `README.md` na raiz — landing page pública do repositório, sem dependentes dentro deste plano.

- [x] **Step 1: Criar o `README.md`**

Conteúdo exato:

````markdown
<p align="center">
  <img src="./assets/banner_blockas.png" alt="Banner Inteli Blockchain" width="700">
</p>

<h1 align="center">
  Projeto Alphractal — Monitoramento de Taxas em Tempo Real (Ethereum)
</h1>

<p align="center">
  <strong>Projeto do clube Inteli Blockchain em parceria com a Alphractal.</strong>
</p>

<p align="center">
  🔵 <strong>Status: Planejamento</strong> — kickoff em 18/08/26
</p>

---

## 🎯 Sobre o projeto

A Alphractal é uma plataforma de inteligência de mercado de nível institucional
focada no ecossistema Web3, desenvolvida pela Nortech Labs. Hoje, a aba "Fees" da
plataforma mostra apenas médias históricas estáticas de custo de transação na rede
Ethereum — um ponto cego para a volatilidade instantânea da mempool, que expõe
investidores institucionais a risco de execução e a custos imprevistos.

Este projeto vai desenvolver um módulo de monitoramento em tempo real (backend
Node.js + frontend React) que traduz dados brutos da blockchain em indicadores
financeiros instantâneos, dando previsibilidade de custo para operações
institucionais de alto volume.

---

## 🔗 Links

- 📄 [Termo de Abertura de Projeto (TAP)](./docs/TAP-Alphractal.pdf)

---

## 🗓️ Próximos passos

O código do MVP (backend + frontend) entra neste mesmo repositório conforme o
desenvolvimento avança, a partir do kickoff em 18/08/26. Este README será
atualizado com instruções de setup e instalação nesse momento.

---

<p align="center">
  Um projeto do <a href="https://github.com/InteliBlockchain-IBC">Inteli Blockchain</a>
</p>
````

- [x] **Step 2: Verificar renderização local**

Run: `grep -c "TAP-Alphractal.pdf" README.md`
Expected: `1` (o link para o TAP está presente e usa o caminho relativo correto).

- [x] **Step 3: Commit**

```bash
git add README.md
git commit -m "docs: adiciona README do projeto Alphractal"
```

---

### Task 5: Publicar no GitHub

**Files:** nenhum arquivo novo — apenas comandos de rede/git.

**Interfaces:**
- Consumes: todos os commits das Tasks 1–4 já devem existir na branch `main` local antes deste task.

- [x] **Step 1: Confirmar autenticação e branch**

```bash
gh auth status
git branch --show-current
git log --oneline
```

Expected: `gh auth status` mostra "Logged in to github.com" com escopo `repo`; branch atual é `main`; o log mostra os commits das Tasks 1–4 (mais o commit do spec já existente).

- [x] **Step 2: Criar o repositório remoto público e fazer o primeiro push**

```bash
gh repo create InteliBlockchain-IBC/projeto-alphractal \
  --public \
  --description "Sistema de monitoramento em tempo real de custos de taxa na rede Ethereum — projeto do Inteli Blockchain com a Alphractal." \
  --source=. \
  --remote=origin \
  --push
```

Expected: comando termina sem erro e imprime a URL `https://github.com/InteliBlockchain-IBC/projeto-alphractal`. Se der erro de permissão (sem acesso de criação de repo na org), crie o repo manualmente pela UI do GitHub em `InteliBlockchain-IBC` como público e então rode:

```bash
git remote add origin https://github.com/InteliBlockchain-IBC/projeto-alphractal.git
git push -u origin main
```

- [x] **Step 3: Verificar o repositório publicado**

```bash
gh repo view InteliBlockchain-IBC/projeto-alphractal --web
```

Expected: abre o repositório no navegador; confirmar visualmente que o README renderiza com o banner, o link do TAP funciona e abre o PDF, e que o repo está marcado como público.

- [x] **Step 4: Nenhum commit adicional necessário**

Este task não cria arquivos novos — apenas publica o que já foi commitado nas tasks anteriores.

---

## Verificação final (checklist do spec)

- [x] `README.md` renderiza corretamente no GitHub (banner aparece, link do TAP funciona).
- [x] `docs/TAP-Alphractal.pdf` abre e é idêntico ao PDF original em `documentos_projetos/`.
- [x] `LICENSE` é o texto padrão MIT, copyright "Inteli Blockchain".
- [x] Repositório criado como **público** na org `InteliBlockchain-IBC`, branch `main`, push feito com sucesso.
