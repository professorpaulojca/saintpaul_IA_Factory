---
agent: agent
description: Gera o backend completo em Java/Spring Boot com entidades, services, controllers, segurança e migrations Flyway.
tools:
  - search/codebase
  - read/readFile
  - edit/editFiles
  - execute/runInTerminal
---

# Prompt 03 — Gerar Backend Java

## Leia antes de gerar

- `input/application-story.md` — história de negócio (fonte primária)
- `docs/specs/` — requisitos funcionais, regras de negócio, casos de uso
- `docs/architecture/` — padrões técnicos, segurança, observabilidade
- `docs/diagrams/` — modelo de domínio, fluxos, BPMN
- `backend/README.md` — estrutura esperada de pastas e responsabilidades de cada camada

## Objetivo

Gerar o backend completo da aplicação expandindo a base já existente em `backend/`.

## Stack obrigatória

- Java 17+
- Spring Boot
- Spring Web
- Spring Data JPA
- PostgreSQL
- Flyway
- Spring Security com JWT
- OpenAPI / Swagger
- Logs estruturados (SLF4J)

## O que gerar

### Domínio
- Entidades JPA para cada conceito identificado na história (`domain/`)
- Enums de status, tipos e perfis conforme regras de negócio

### Acesso a dados
- Repositories Spring Data JPA para cada entidade (`repository/`)
- Queries customizadas quando necessário

### Lógica de negócio
- Services com regras extraídas da história e especificações (`service/`)
- Um service por família de casos de uso

### Camada HTTP
- Controllers REST finos, apenas HTTP (`controller/`)
- DTOs separados de request e response (`dto/<entidade>/`)
- Validação Bean Validation nos DTOs de entrada

### Infraestrutura
- Migrations Flyway para todas as tabelas (`db/migration/`)
- Seguir convenções documentadas em `database/README.md`
- Configurações adicionais em `config/` se necessário
- Exceções de negócio em `exception/`

### Segurança
- Manter base JWT existente (`security/`)
- Definir endpoints públicos e protegidos no `SecurityConfig`
- Perfis/roles alinhados com os atores da história

### Testes
- Testes unitários para todos os services de negócio
- Testes de integração para controllers principais
- Padrão Given-When-Then com nomes descritivos

## Saída esperada

Atualizar `backend/` seguindo exatamente a estrutura definida em `backend/README.md`.
O código deve:
- Compilar e executar com `./mvnw spring-boot:run`
- Expor todos os endpoints no Swagger (`/swagger-ui.html`)
- Ter separação clara de camadas
- Refletir fielmente a história e as especificações

## Qualidade exigida

- Separação de camadas sem vazamento de lógica
- Validações nos DTOs de entrada
- Consistência entre entidades JPA e migrations Flyway
- Logs estruturados em operações importantes
- Nenhum stack trace exposto nas respostas de erro
- Clareza de código para demonstração em aula
