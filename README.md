# Academy IA Factory

Ambiente de engenharia assistida por IA para transformar uma história de negócio em uma aplicação moderna,
usando GitHub Copilot Pro, memória explícita, regras, agentes e prompts de ação.

## Objetivo
Demonstrar, em aula, que a qualidade do resultado de IA depende da qualidade do ambiente preparado.

## Stack-alvo
- Backend: Java 17+, Spring Boot, Spring Data JPA, Flyway, Spring Security, OpenAPI/Swagger
- Frontend: React, TypeScript, Vite
- Banco de dados: PostgreSQL
- Processos: BPMN 2.0 para Camunda
- Diagramas: Mermaid e draw.io
- Assistência de IA: GitHub Copilot Pro

## Fluxo recomendado da aula
1. Apresentação do problema
2. Exibição do ambiente e explicação de cada arquivo
3. Colagem da história em `input/application-story.md`
4. Execução do prompt de protótipo
5. Execução do prompt de especificação
6. Execução do prompt de backend
7. Execução do prompt de frontend
8. Revisão técnica

## Estrutura principal
- `input/` → insumos de negócio
- `docs/memory-bank/` → memória explícita do projeto
- `.github/` → regras, agentes, prompts e skills do Copilot
- `backend/` → base backend Java
- `frontend/` → base frontend React
- `database/` → convenções e scripts
- `docs/diagrams/` → modelos Mermaid, BPMN e draw.io

## Ponto-chave pedagógico
Não começamos pedindo código.
Primeiro preparamos contexto, regras, especificação e papéis.
Depois pedimos implementação.

## Observações
- Todos os arquivos estão salvos em UTF-8.
- O ambiente foi escrito em português do Brasil.
- O conteúdo foi preparado para ser didático, profissional e reaproveitável.
