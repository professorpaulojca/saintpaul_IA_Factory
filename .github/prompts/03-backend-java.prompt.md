# Prompt 03 — Gerar Backend Java

Leia:

- `input/application-story.md`
- `docs/specs/*`
- `docs/architecture/*`
- `docs/processes/*`

## Objetivo
Criar a pasta `backend/` e gerar o backend completo a partir da especificação, com padrão corporativo adequado a uma aplicação pequena.

A pasta `backend/` **não existe previamente**. Deve ser criada nesta etapa com toda a estrutura necessária (pom.xml, packages Java, migrations, application.yml, etc.).

## Pacote Java base
`com.saintpaul.academy`

## Stack obrigatória

- Java 21
- Spring Boot 3
- Spring Data JPA
- Spring Validation
- Spring Security com JWT
- Flyway
- PostgreSQL
- OpenAPI / Swagger
- Logs estruturados

## Gerar

1. entidades JPA
2. DTOs
3. repositories
4. services
5. controllers
6. tratamento global de exceções
7. configuração de segurança
8. migrations Flyway
9. documentação básica de execução
10. **testes unitários** para services, controllers e security (conforme `docs/architecture/testing-standards.md`)

## Regras

- arquitetura em camadas
- controllers finos
- services com regra de negócio
- consistência de nomes
- validações explícitas
- endpoint de autenticação se a história exigir login
- swagger funcional

## Pós-geração (executar automaticamente)

Após gerar todos os arquivos:

1. Garantir que o PostgreSQL está rodando (`docker compose up -d` na raiz do projeto)
2. O `application.yml` deve usar: host `localhost`, porta `5432`, banco `academy_db`, usuário `postgres`, senha `postgres`
3. Executar `mvn clean compile -f backend/pom.xml` para validar compilação
4. Se houver erros de compilação, corrigir automaticamente e recompilar
5. Executar `mvn test -f backend/pom.xml` para rodar os testes
6. Se houver testes falhando, corrigir e re-executar
7. Confirmar que build e testes passaram com sucesso antes de encerrar
