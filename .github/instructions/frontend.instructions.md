---
applyTo: "frontend/**"
---

# Instruções para Frontend

## Stack obrigatória
- React
- TypeScript
- Vite
- React Router
- Context API ou solução simples equivalente
- Consumo de API REST

## Diretrizes
- Interface clara e direta.
- Componentes pequenos e reutilizáveis.
- Separar componentes, páginas, serviços, hooks e tipos.
- Evitar lógica de negócio pesada na interface.
- Criar serviços de API centralizados.
- Tratar erros de forma visível e elegante.
- Preparar autenticação com controle de sessão.
- Priorizar acessibilidade, clareza e responsividade básica.

## Convenções
- `pages/` para páginas
- `components/` para componentes reaproveitáveis
- `services/` para chamadas HTTP
- `types/` para contratos TypeScript
- `hooks/` para lógica reutilizável
- `layouts/` para estrutura visual
- `routes/` para roteamento

## UX
- Dar feedback de carregamento.
- Mostrar mensagens claras de sucesso e erro.
- Respeitar protótipos e especificações geradas anteriormente.
