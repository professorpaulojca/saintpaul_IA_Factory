---
applyTo: "database/**"
---

# Instruções para Banco de Dados

## Banco-alvo
PostgreSQL

## Diretrizes
- Modelagem relacional clara.
- Chaves primárias simples, preferencialmente `bigserial` ou `uuid` conforme contexto.
- Chaves estrangeiras explícitas.
- Índices para campos de busca, autenticação e relacionamentos críticos.
- Uso de Flyway como mecanismo oficial de evolução.
- Scripts devem ser legíveis, reversíveis quando possível e bem nomeados.

## Convenções
- Tabelas em `snake_case`
- Colunas em `snake_case`
- Chaves estrangeiras com sufixo `_id`
- Timestamps de auditoria sempre que fizer sentido: `created_at`, `updated_at`

## Qualidade
- Evitar ambiguidade em nomes.
- Garantir aderência com entidades JPA.
- Evitar sobreengenharia.
