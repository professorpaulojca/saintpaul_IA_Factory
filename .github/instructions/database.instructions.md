---
applyTo: "database/**,backend/src/main/resources/db/migration/**"
---

# Database Instructions

## Banco padrão

- PostgreSQL 16

## Regras obrigatórias

- Nomear tabelas e colunas de forma consistente.
- Incluir chaves primárias, estrangeiras e índices relevantes.
- Evitar modelagem ambígua.
- Declarar constraints para proteger integridade.
- Versionar mudanças por Flyway.

## Boas práticas

- Usar campos `created_at` e `updated_at` quando a entidade justificar rastreabilidade.
- Separar tabela transacional de tabela histórica quando houver trilha de evolução.
- Criar scripts claros e auditáveis.
