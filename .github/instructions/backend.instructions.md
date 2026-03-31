---
applyTo: "backend/**"
---

# Instruções para Backend

## Stack obrigatória
- Java 17+
- Spring Boot
- Spring Web
- Spring Data JPA
- Spring Security
- Flyway
- PostgreSQL
- OpenAPI / Swagger

## Diretrizes
- Usar arquitetura em camadas.
- Não misturar regra de negócio com camada HTTP.
- Preferir DTOs para entrada e saída.
- Validar entradas com Bean Validation.
- Criar tratamento global de exceções.
- Usar logs estruturados com contexto.
- Preparar código para testes unitários e de integração.
- Manter controllers finos e services claros.
- Repositories devem ser simples e focados em persistência.
- Entidades devem refletir o domínio e o banco relacional.

## Convenções
- `controller` para endpoints
- `service` para orquestração de negócio
- `repository` para persistência
- `domain` para entidades e enums
- `dto` para contratos
- `config` para configuração
- `exception` para erros
- `security` para autenticação e autorização

## Segurança
- Preparar autenticação baseada em JWT.
- Definir perfis e papéis com clareza.
- Proteger endpoints privados.
- Evitar exposição de dados sensíveis.

## Banco
- Toda mudança estrutural deve gerar migration Flyway.
- Garantir integridade relacional.
- Respeitar nomenclatura consistente.
