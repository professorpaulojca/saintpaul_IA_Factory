# Copilot Repository Instructions

Você está atuando em um ambiente de geração assistida de software voltado a transformar uma história de negócio em uma aplicação moderna e segura.

## Objetivo do repositório

Preparar uma base de engenharia em alto nível técnico para que a IA consiga gerar:

- protótipos funcionais em HTML/CSS/JavaScript
- especificações funcionais e técnicas
- diagramas Mermaid e draw.io
- BPMN compatível com Camunda
- backend Java com Spring Boot
- frontend React com TypeScript
- scripts de banco PostgreSQL e migrations Flyway

## Premissa fundamental

As pastas `backend/`, `frontend/` e `database/` **não existem previamente**. Elas devem ser criadas pela IA durante a execução dos prompts correspondentes, a partir das especificações e da stack tecnológica definida. O pacote Java base é `com.saintpaul.academy`.

## Regras gerais obrigatórias

1. Sempre ler `input/application-story.md` antes de qualquer geração.
2. Sempre considerar os arquivos de `docs/memory-bank/` como fonte de verdade do contexto persistente.
3. Sempre produzir artefatos alinhados a:
   - Java 21
   - Spring Boot 3
   - Spring Data JPA
   - Flyway
   - Spring Security com JWT
   - PostgreSQL 16
   - React 18+
   - TypeScript
   - Vite
4. Sempre usar arquitetura em camadas no backend.
5. Sempre separar componentes, páginas, hooks, rotas e serviços no frontend.
6. Sempre explicar brevemente o porquê das decisões importantes.
7. Sempre priorizar clareza, manutenibilidade, rastreabilidade e segurança.
8. Nunca inventar requisito que contradiga a história.
9. Sempre sugerir validações, logs, tratamento de erros e testes mínimos.
10. Sempre gerar documentação técnica quando criar estruturas importantes.

## Diretrizes de qualidade

- Código legível antes de código sofisticado.
- Estrutura evolutiva antes de velocidade pontual.
- Segurança base desde o início.
- Logs estruturados e pontos de observabilidade.
- Contratos claros entre backend e frontend.
- Consistência entre protótipo, especificação e implementação.

## Sequência esperada

1. Ler história
2. Gerar protótipos funcionais iniciais
3. Gerar especificações e diagramas
4. Gerar backend (criar pasta, gerar código, compilar e validar)
5. Gerar frontend (criar pasta, gerar código, instalar dependências e validar)
6. Revisar consistência completa

## Regra de execução

Sempre que gerar código em `backend/` ou `frontend/`, executar automaticamente:
- **Backend**: `mvn clean compile` para validar compilação. `mvn test` para rodar testes. Corrigir erros e recompilar se necessário.
- **Frontend**: `npm install` seguido de `npx tsc --noEmit` para validar. `npx vitest run` para rodar testes. Corrigir erros e revalidar se necessário.

Testes unitários são parte da entrega de cada funcionalidade, nunca uma etapa separada. Consultar `docs/architecture/testing-standards.md` para padrões.

O objetivo é que cada etapa termine com artefatos validados, testados e prontos para uso.

## Formato de resposta preferido

- Seja direto e profissional.
- Explique primeiro o objetivo e depois a implementação.
- Ao criar arquivos, informe claramente onde cada um deve ficar.
- Ao revisar, aponte gaps concretos e correções objetivas.
