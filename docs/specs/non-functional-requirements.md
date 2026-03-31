# Non-Functional Requirements

## Segurança
- autenticação quando aplicável
- autorização por perfil quando aplicável
- validação de entrada
- tratamento de erro sem exposição indevida

## Qualidade
- código legível
- modularização adequada
- baixo acoplamento
- documentação mínima de execução
- testes unitários obrigatórios para regras de negócio, contratos HTTP e autenticação
- testes gerados junto com o código, nunca como etapa posterior

## Observabilidade
- logs em pontos críticos
- mensagens claras de falha
- rastreabilidade de operações importantes

## Performance
- modelagem adequada de banco
- endpoints claros
- evitar complexidade desnecessária em aplicação pequena

## Usabilidade
- foco em fluxo operacional
- linguagem simples na interface
- consistência visual mínima
