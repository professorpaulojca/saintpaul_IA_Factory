# Decisions Log

## DEC-001
Adotar Java 21 e Spring Boot 3 como padrão de backend.

Motivo: stack moderna, produtiva e amplamente reconhecida no mercado.

## DEC-002
Adotar React + TypeScript + Vite para frontend.

Motivo: produtividade, legibilidade e boa experiência para demonstração.

## DEC-003
Adotar Memory Bank explícito em arquivos, e não apenas memória implícita da ferramenta.

Motivo: versionamento, auditabilidade e demonstração pedagógica.

## DEC-004
Adotar geração em etapas.

Motivo: reduzir improviso e aumentar consistência entre artefatos.

## DEC-005
Não pré-criar pastas de código (backend, frontend, database).

Motivo: garantir que todo código nasce da história e das especificações, reforçando a premissa de que a IA gera a partir de contexto, não de templates pré-montados.

## DEC-006
Usar Docker apenas para o PostgreSQL via `docker-compose.yml`.

Motivo: elimina o pré-requisito de instalar PostgreSQL localmente, simplifica o setup e garante consistência entre ambientes. Backend e frontend continuam rodando nativamente para agilidade no desenvolvimento.

## DEC-007
Testes unitários são obrigatórios e gerados junto com o código.

Motivo: testes como etapa separada são esquecidos ou superficiais. Gerando junto, a IA produz testes que refletem o comportamento real implementado. Foco em regras de negócio e caminhos de erro, não em cobertura numérica.
