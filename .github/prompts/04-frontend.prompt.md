---
agent: agent
description: Gera o frontend completo em React/TypeScript alinhado aos protótipos e à API do backend.
tools:
  - search/codebase
  - read/readFile
  - edit/editFiles
  - execute/runInTerminal
---

# Prompt 04 — Gerar Frontend React

## Leia antes de gerar

- `input/application-story.md` — história de negócio (fonte primária)
- `docs/specs/` — requisitos funcionais, casos de uso, fluxos
- `docs/diagrams/` — modelo de domínio, fluxo principal
- `prototypes/` — protótipos HTML/CSS gerados no Prompt 01 (referência visual)
- `backend/` — controllers, DTOs e types para alinhar contratos de API
- `frontend/README.md` — estrutura esperada de pastas e responsabilidades

## Objetivo

Gerar o frontend completo e coerente com os protótipos e com o backend, expandindo a base já existente em `frontend/`.

## Stack obrigatória

- React 18+
- TypeScript
- Vite
- React Router v6
- Axios
- Context API

## O que gerar

### Páginas
- Tela de login (já existe como base, ajustar se necessário)
- Dashboard inicial com visão geral do domínio
- Página de listagem para cada entidade principal (busca, filtro, tabela)
- Página de formulário para criação e edição de cada entidade
- Fluxos completos alinhados com os casos de uso das specs

### Componentes
- Componentes de UI reutilizáveis em `components/ui/` (Button, Input, Table, Modal, LoadingSpinner)
- Componentes específicos do domínio em `components/<Entidade>/`
- Layouts autenticado e público em `layouts/`

### Navegação
- Configuração de rotas em `routes/AppRoutes.tsx`
- Guard de autenticação em `routes/PrivateRoute.tsx`
- Redirecionamento automático para login quando não autenticado

### Serviços HTTP
- Instância Axios com interceptors de autenticação em `services/api.ts`
- Um service por entidade de negócio em `services/<entidade>Service.ts`
- Nenhuma chamada HTTP direta em componentes ou pages

### Estado e hooks
- `context/AuthContext.tsx` para estado de autenticação
- `hooks/useAuth.ts` para ações de auth
- Hooks customizados por entidade quando houver lógica de estado repetida

### Tipos TypeScript
- Interfaces alinhadas com os DTOs do backend em `types/<entidade>.ts`
- Sem uso de `any`; tipagem completa em todas as operações

## Saída esperada

Atualizar `frontend/` seguindo exatamente a estrutura definida em `frontend/README.md`.
O código deve:
- Executar com `npm run dev`
- Ter o fluxo login → dashboard → CRUD funcionando end-to-end
- Ser visualmente coerente com os protótipos de `prototypes/`
- Ter contratos TypeScript alinhados com os DTOs do backend

## Qualidade exigida

- Feedback visual obrigatório: loading, erro e estado vazio em todas as listagens
- Tipagem TypeScript sem `any`
- Sem lógica de negócio em componentes de UI
- Componentes pequenos e com responsabilidade única
- Organização modular que permita expansão fácil
- Clareza visual e código limpo para demonstração em aula
