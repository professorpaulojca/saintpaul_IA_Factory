---
applyTo: "frontend/**"
---

# Frontend Instructions

## Stack mandatória

- React
- TypeScript
- Vite
- React Router
- CSS modular ou estrutura simples com arquivos separados

## Padrões obrigatórios

- Separar páginas, componentes, serviços, hooks e tipos.
- Centralizar chamadas HTTP em `src/services`.
- Implementar tratamento de loading, erro e estado vazio quando aplicável.
- Evitar lógica de negócio complexa dentro de componentes visuais.
- Preferir componentes pequenos, claros e reutilizáveis.

## Segurança e sessão

- Respeitar autenticação e autorização baseadas na especificação.
- Manter token e sessão com cuidado.
- Proteger rotas privadas.
- Nunca confiar apenas no frontend para validação.

## UX

- Interface simples, profissional e operacional.
- Priorizar clareza de fluxo.
- Foco em produtividade do usuário operacional.

## Testes unitários

- Stack: Vitest + React Testing Library + MSW.
- Obrigatório para: hooks customizados, serviços de API, componentes com lógica.
- Testar pelo comportamento do usuário, não pela implementação.
- Queries por acessibilidade (`getByRole`, `getByLabelText`, `getByText`).
- Interações via `userEvent`.
- Testes são gerados junto com o código, nunca como etapa separada.
- Consultar `docs/architecture/testing-standards.md` para detalhes completos.
