# Prompt 04 — Gerar Frontend React

Leia:

- `input/application-story.md`
- `docs/specs/*`
- protótipos gerados em `docs/prototypes/`
- contratos do backend gerado em `backend/`

## Objetivo
Criar a pasta `frontend/` e gerar o frontend completo a partir da especificação e dos contratos do backend.

A pasta `frontend/` **não existe previamente**. Deve ser criada nesta etapa com toda a estrutura necessária (package.json, vite.config.ts, tsconfig.json, src/, etc.).

## Stack obrigatória

- React
- TypeScript
- Vite
- React Router

## Gerar

1. estrutura de páginas
2. componentes reutilizáveis
3. serviços de API
4. autenticação e proteção de rotas quando aplicável
5. telas operacionais principais
6. feedback de loading e erro
7. **testes unitários** para hooks, serviços e componentes com lógica (conforme `docs/architecture/testing-standards.md`)

## Regras

- manter aderência visual ao protótipo
- manter aderência funcional à especificação
- priorizar clareza operacional
- evitar lógica de negócio excessiva no componente visual

## Pós-geração (executar automaticamente)

Após gerar todos os arquivos:

1. Executar `cd frontend && npm install` para instalar dependências
2. Executar `npx tsc --noEmit` para validar TypeScript
3. Executar `npx vitest run` para rodar os testes
4. Se houver erros, corrigir automaticamente e revalidar
5. Confirmar que build e testes passaram com sucesso antes de encerrar
