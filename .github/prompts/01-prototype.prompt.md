---
agent: agent
description: Gera protótipos HTML/CSS/JS a partir da história de negócio para visualizar o produto antes do backend.
tools:
  - search/codebase
  - read/readFile
  - edit/editFiles
---

# Prompt 01 — Criar Protótipos Funcionais

Leia:
- `input/application-story.md`
- `docs/memory-bank/`
- `docs/specs/`

Objetivo:
Criar protótipos funcionais iniciais usando HTML, CSS e JavaScript puro, com foco em fluxo e entendimento do produto.

## Instruções
- Identifique as telas principais.
- Gere protótipos simples, claros e funcionais.
- Não usar frameworks neste primeiro passo.
- Priorize navegação e fluxo de negócio.
- Crie uma pasta `prototypes/` com:
  - `index.html`
  - telas auxiliares conforme necessário
  - `styles.css`
  - `app.js`

## Saída esperada
- lista de telas;
- justificativa de cada tela;
- arquivos HTML/CSS/JS;
- breve explicação do fluxo entre telas.

## Restrições
- Não sofisticar design.
- Focar em entendimento do produto.
- Não gerar backend nesta etapa.
