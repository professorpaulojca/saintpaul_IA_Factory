---
agent: agent
description: Transforma a história de negócio em especificações, diagramas Mermaid, BPMN e modelo de domínio.
tools:
  - search/codebase
  - read/readFile
  - edit/editFiles
---

# Prompt 02 — Gerar Especificações, Diagramas e Fluxos

Leia:
- `input/application-story.md`
- `docs/memory-bank/`

Objetivo:
Transformar a história em documentação de engenharia.

## Gere
1. Requisitos funcionais
2. Requisitos não funcionais
3. Regras de negócio
4. Casos de uso
5. Entidades e relacionamentos
6. Fluxos principais
7. Modelo conceitual de banco
8. Diagramas Mermaid
9. BPMN em XML para Camunda
10. Versão draw.io em XML simplificado

## Saída esperada
Gerar ou atualizar:
- `docs/specs/functional-requirements.md`
- `docs/specs/non-functional-requirements.md`
- `docs/specs/use-cases.md`
- `docs/specs/business-rules.md`
- `docs/diagrams/domain-model.mmd`
- `docs/diagrams/main-flow.mmd`
- `docs/diagrams/process.bpmn`
- `docs/diagrams/process.drawio`

## Qualidade exigida
- Clareza
- Rastreabilidade
- Coerência com a história
- Premissas explicitadas
