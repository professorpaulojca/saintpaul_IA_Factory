# AGENTS.md

Este repositório adota uma abordagem de engenharia assistida por IA.

## Princípios

- Não implementar funcionalidades sem antes compreender a história do produto.
- Toda geração deve respeitar memória, especificações, segurança, observabilidade e arquitetura.
- O objetivo não é apenas gerar código, mas gerar uma aplicação coerente, segura, rastreável e evolutiva.
- As pastas de código (`backend/`, `frontend/`, `database/`) são criadas durante a execução dos prompts, não existem previamente.

## Fontes obrigatórias de contexto

Antes de gerar qualquer artefato, ler:

- `input/application-story.md`
- `docs/memory-bank/product.md`
- `docs/memory-bank/business-rules.md`
- `docs/memory-bank/architecture.md`
- `docs/memory-bank/decisions.md`
- `docs/specs/non-functional-requirements.md`
- `docs/architecture/engineering-standards.md`

## Ordem preferencial de trabalho

1. História
2. Protótipo funcional
3. Especificação funcional e técnica
4. Diagramas e BPMN
5. Banco de dados
6. Backend
7. Frontend
8. Revisão completa
