# Architecture Memory

## Premissa

Nenhuma pasta de código (`backend/`, `frontend/`, `database/`) existe previamente. Elas serão criadas pela IA a partir das especificações e da stack tecnológica abaixo.

## Diretrizes arquiteturais

### Backend
- Java 21
- Spring Boot 3
- Pacote base: `com.saintpaul.academy`
- Arquitetura em camadas
- REST API
- JPA + PostgreSQL
- Flyway
- Spring Security com JWT
- OpenAPI

### Frontend
- React + TypeScript + Vite
- rotas protegidas quando necessário
- serviços centralizados
- componentes reutilizáveis

### Diagramas
- Mermaid para documentação rápida
- BPMN para processos em Camunda
- draw.io para visual formal quando necessário

## Infraestrutura

### Banco de dados (Docker)
- PostgreSQL 16 via `docker-compose.yml` na raiz do projeto
- Comando: `docker compose up -d`
- Banco: `academy_db`
- Credenciais: `postgres` / `postgres`
- Porta: `5432`

### Backend
- Roda local com `mvn spring-boot:run`
- Conecta ao PostgreSQL via Docker

### Frontend
- Roda local com `npm run dev`

## Princípios
- simplicidade pragmática
- separação de responsabilidades
- rastreabilidade
- segurança base
- legibilidade
