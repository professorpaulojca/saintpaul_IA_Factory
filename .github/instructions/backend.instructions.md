---
applyTo: "backend/**"
---

# Backend Instructions

## Stack mandatória

- Java 21
- Spring Boot 3.x
- Spring Web
- Spring Data JPA
- Spring Validation
- Spring Security
- JWT
- Flyway
- PostgreSQL
- springdoc-openapi

## Padrões obrigatórios

- Arquitetura em camadas: controller, service, repository, domain, dto, config, security.
- Controllers finos.
- Regras de negócio nos services.
- Repositories somente para acesso a dados.
- DTOs para entrada e saída.
- Tratamento centralizado de exceções.
- Logs estruturados.
- Versionamento de banco via Flyway.

## Segurança

- Basear autorização em perfis/roles.
- Nunca expor dados sensíveis sem necessidade.
- Sempre prever autenticação JWT quando a história mencionar acesso autenticado.
- Adotar endpoints públicos apenas quando houver justificativa.

## Observabilidade

- Adicionar logs em pontos relevantes de operação.
- Usar correlation id quando fizer sentido.
- Documentar endpoints via OpenAPI.

## Testes unitários

- Stack: JUnit 5 + Mockito + AssertJ.
- Obrigatório para: services, controllers e security.
- Padrão Given-When-Then.
- Nomes descritivos: `should_[resultado]_when_[condição]`.
- Testes negativos obrigatórios (entrada inválida, entidade não encontrada, permissão negada).
- Testes são gerados junto com o código, nunca como etapa separada.
- Consultar `docs/architecture/testing-standards.md` para detalhes completos.
