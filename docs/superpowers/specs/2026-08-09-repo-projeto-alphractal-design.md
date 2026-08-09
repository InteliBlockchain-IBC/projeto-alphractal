# Design: repo `projeto-alphractal`

**Data:** 2026-08-09
**Status:** Aprovado

## Contexto

Primeiro projeto do clube com um parceiro externo (empresa **Alphractal**, plataforma
de inteligência de mercado Web3 desenvolvida pela Nortech Labs). O TAP já existe em
PDF (`documentos_projetos/TAP - Inteli Blockchain e Alphactral.pdf`, nome do arquivo
com erro de digitação — nome correto da empresa é **Alphractal**).

Objetivo: um repositório que sirva de página inicial do projeto — descrição curta,
link pro TAP e materiais da empresa — consultável por membros do clube e por pessoas
de fora avaliando o trabalho entregue.

## Decisões

- **Um repo por projeto** (não um repo único "vitrine" com todos os projetos dentro).
  Um índice central que lista os repos de cada projeto é uma ideia futura, mas fica
  fora de escopo agora — só há um projeto até hoje, então não há o que indexar ainda.
- **Nome do repo:** `projeto-alphractal`, na org `InteliBlockchain-IBC`.
- **Visibilidade:** público. Confirmado seguro após revisão do conteúdo do TAP (sem
  valores, dados pessoais ou informação sensível). O próprio TAP (seção 5, Propriedade
  Intelectual) exige que o código do projeto seja público sob licença MIT — este repo
  também vai hospedar esse código quando o desenvolvimento começar.
- **Licença:** MIT (exigida pelo TAP).
- **Local:** clonado em `projetos/projeto-alphractal/` neste workspace, como os demais
  repos do clube — mas **sem `CLAUDE.md` próprio** (não é um projeto de contexto
  interno de desenvolvimento, é uma vitrine pública) e **sem registro no `CLAUDE.md`
  raiz** do workspace por ora.

## Estrutura

```
projeto-alphractal/
├── README.md
├── LICENSE                 (MIT)
├── assets/
│   └── banner_blockas.png  (copiado de aulas/others/assets/, banner padrão do clube)
└── docs/
    └── TAP-Alphractal.pdf  (TAP atual, copiado e renomeado — corrige o typo do nome original)
```

## Conteúdo do README

Curto, no mesmo estilo visual do README de `aulas/` (banner centralizado, título,
seções com emoji):

1. Banner do clube + título do projeto.
2. 2–3 frases: quem é a Alphractal, o problema (ponto cego de volatilidade da mempool
   Ethereum na aba "Fees"), status atual (`🔵 Planejamento — kickoff 18/08/26`).
3. Seção "Links" apontando para `docs/TAP-Alphractal.pdf`. Sem seção de "materiais
   adicionais" — não existe nenhum além do TAP hoje, e um link vazio/placeholder é
   pior que nenhuma seção.
4. Nota de que o código do MVP entra neste mesmo repo quando o desenvolvimento
   começar (após o kickoff).

## Fora de escopo

- Repositório índice/vitrine central listando todos os projetos do clube — criar
  quando existir um segundo projeto.
- Estrutura de código (backend/frontend) — só depois do kickoff (18/08/26).
- Registro deste repo no `CLAUDE.md` raiz do workspace.

## Verificação

Checklist manual (não há lógica de negócio/testável aqui, é criação de conteúdo):

- [ ] `README.md` renderiza corretamente no GitHub (banner aparece, links funcionam).
- [ ] `docs/TAP-Alphractal.pdf` abre e é idêntico ao PDF original.
- [ ] `LICENSE` é o texto padrão MIT.
- [ ] Repo criado como público na org `InteliBlockchain-IBC` e primeiro push feito.
