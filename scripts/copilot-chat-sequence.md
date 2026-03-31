# Sequência Operacional da Aula

## 1. Mostrar a estrutura
Explique que a IA não começa do zero, mas também não começa pelo código. Ela começa com contexto, regras, agentes e prompts de ação. As pastas `backend/`, `frontend/` e `database/` **não existem** — serão geradas nos passos seguintes.

## 2. Subir o banco
Executar na raiz do projeto:
```bash
docker compose up -d
```

## 3. Colar a história
Arquivo: `input/application-story.md`

## 4. Rodar Prompt 01
Arquivo: `.github/prompts/01-prototipo-funcional.prompt.md`

Objetivo: gerar protótipos HTML/CSS/JS em `docs/prototypes/`.

## 5. Rodar Prompt 02
Arquivo: `.github/prompts/02-especificacoes-e-fluxos.prompt.md`

Objetivo: gerar especificações, Mermaid, BPMN e draw.io.

## 6. Rodar Prompt 03
Arquivo: `.github/prompts/03-backend-java.prompt.md`

Objetivo: criar `backend/`, gerar todo o código Java/Spring/Postgres/Flyway/Security/Swagger, compilar e validar o build automaticamente.

## 7. Rodar Prompt 04
Arquivo: `.github/prompts/04-frontend-react.prompt.md`

Objetivo: criar `frontend/`, gerar todo o código React/TS/Vite, instalar dependências e validar TypeScript automaticamente.

## 8. Rodar Prompt 05
Arquivo: `.github/prompts/05-revisao-geral.prompt.md`

Objetivo: revisar coerência geral e consolidar qualidade.

## Resultado

Ao final dos 5 prompts, você terá:
- Protótipos visuais
- Especificações e diagramas completos
- Backend compilado e pronto para rodar
- Frontend com dependências instaladas e pronto para rodar
- Relatório de revisão

Para subir a aplicação:
```bash
# Banco (se ainda não estiver rodando)
docker compose up -d

# Backend (em um terminal)
cd backend && mvn spring-boot:run

# Frontend (em outro terminal)
cd frontend && npm run dev
```
