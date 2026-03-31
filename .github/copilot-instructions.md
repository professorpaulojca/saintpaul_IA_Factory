# Instruções Gerais do Repositório

Você está trabalhando em um ambiente de engenharia assistida por IA, voltado para transformar uma história de negócio em uma aplicação moderna, segura e sustentável.

## Objetivo do repositório
Ajudar a produzir, com alta qualidade:
- protótipos funcionais;
- especificações;
- diagramas;
- BPMN;
- backend Java;
- frontend React;
- scripts de banco;
- documentação técnica.

## Fontes obrigatórias de contexto
Antes de qualquer implementação, consulte:
1. `input/application-story.md`
2. `docs/memory-bank/`
3. `docs/specs/`
4. `docs/architecture/`
5. `docs/diagrams/`

## Regras obrigatórias
- Nunca inventar requisitos sem deixar isso explícito.
- Sempre priorizar clareza, simplicidade e manutenção.
- Sempre explicar brevemente o porquê das decisões técnicas.
- Respeitar separação de responsabilidades.
- Evitar acoplamento desnecessário.
- Gerar código coerente com Java/Spring no backend e React/TypeScript no frontend.
- Preferir nomes claros em português do domínio e inglês técnico quando fizer sentido no código.
- Sempre propor testes mínimos e logs úteis.
- Sempre considerar segurança, auditoria e observabilidade.
- Toda decisão relevante deve ser compatível com `docs/memory-bank/decisions.md`.

## Estilo de resposta esperado
- Seja objetivo.
- Estruture por etapas.
- Primeiro explique o porquê.
- Depois proponha o como.
- Quando houver risco, limitação ou suposição, deixe explícito.

## Definição de qualidade
Uma entrega de qualidade:
- atende à história;
- respeita as regras de negócio;
- é legível;
- é evolutiva;
- é consistente entre backend, frontend e banco;
- evita “mágicas” desnecessárias;
- é forte o suficiente para revisão técnica exigente.
