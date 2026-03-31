# Saint Paul AI Factory

Repositório de engenharia assistida por IA para transformar uma **história de negócio** em uma **aplicação completa** — protótipos, especificações, diagramas, backend Java, frontend React e banco PostgreSQL.

> **Filosofia:** não começar pelo código. Começar pelo contexto, regras e especificações. A IA gera tudo a partir da história.

---

## Pré-requisitos

| Ferramenta | Versão mínima |
|-----------|---------------|
| VS Code | Última estável |
| GitHub Copilot Pro | Ativo com extensão no VS Code |
| Docker Desktop | Para o PostgreSQL |
| JDK | 21 |
| Maven | 3.9+ |
| Node.js | 20+ |

---

## Quick Start

```bash
# 1. Clone o repositório
git clone https://github.com/professorpaulojca/saintpaul_IA_Factory.git
cd saintpaul_IA_Factory

# 2. Suba o banco de dados
docker compose up -d

# 3. Abra no VS Code
code .
```

4. Cole a história da aplicação em `input/application-story.md`
5. Rode os prompts no chat do Copilot (01 a 05, em ordem)
6. A IA cria tudo — pastas, código, dependências, build e testes

---

## Fluxo de Geração

```
História → Protótipos → Especificações → Backend → Frontend → Revisão
  (você)    (Prompt 01)   (Prompt 02)   (Prompt 03) (Prompt 04) (Prompt 05)
```

| Prompt | O que a IA faz | Validação automática |
|--------|---------------|---------------------|
| **01** | Gera protótipos HTML/CSS/JS em `docs/prototypes/` | — |
| **02** | Gera specs, diagramas Mermaid, BPMN, draw.io | — |
| **03** | Cria `backend/` com Java/Spring/Flyway/JWT/Swagger | `mvn clean compile` + `mvn test` |
| **04** | Cria `frontend/` com React/TypeScript/Vite | `npm install` + `npx tsc --noEmit` + `npx vitest run` |
| **05** | Revisa coerência geral entre todos os artefatos | Relatório em `docs/review/` |

---

## Estrutura do Repositório

```
├── .github/
│   ├── copilot-instructions.md    # Regras gerais para o Copilot
│   ├── agents/                    # Agentes: Architect, Specifier, Builder, Reviewer
│   ├── instructions/              # Regras por área (backend, frontend, database, docs)
│   ├── prompts/                   # Prompts de ação (01 a 05)
│   └── skills/                    # Skills reutilizáveis (ex: generate-crud)
├── docs/
│   ├── memory-bank/               # Memória explícita do projeto
│   ├── specs/                     # Especificações (preenchidas pelo Prompt 02)
│   ├── architecture/              # Padrões de engenharia, segurança e testes
│   ├── diagrams/                  # Mermaid, draw.io
│   └── processes/                 # BPMN Camunda
├── input/
│   └── application-story.md       # ← PONTO DE ENTRADA: cole a história aqui
├── scripts/
│   ├── copilot-chat-sequence.md   # Guia operacional passo a passo
│   └── environment-setup.md       # Pré-requisitos da máquina
├── docker-compose.yml             # PostgreSQL 16 via Docker
├── AGENTS.md                      # Princípios dos agentes
└── README.md
```

### Pastas geradas pela IA (não existem inicialmente)

| Pasta | Criada por | Stack |
|-------|-----------|-------|
| `backend/` | Prompt 03 | Java 21, Spring Boot 3, JPA, Flyway, JWT, Swagger |
| `frontend/` | Prompt 04 | React 18+, TypeScript, Vite, React Router |
| `database/` | Conforme necessidade | Scripts auxiliares PostgreSQL |
| `docs/prototypes/` | Prompt 01 | HTML/CSS/JS puro |

---

## Stack Tecnológica

### Backend
- Java 21 + Spring Boot 3
- Spring Data JPA + PostgreSQL 16
- Spring Security + JWT
- Flyway (migrations versionadas)
- OpenAPI / Swagger
- JUnit 5 + Mockito + AssertJ (testes)

### Frontend
- React 18+ + TypeScript
- Vite
- React Router
- Vitest + React Testing Library + MSW (testes)

### Infraestrutura
- Docker Compose (PostgreSQL)
- Pacote base: `com.saintpaul.academy`

---

## Rodar a Aplicação (após geração)

```bash
# Banco (se ainda não estiver rodando)
docker compose up -d

# Backend (terminal 1)
cd backend && mvn spring-boot:run

# Frontend (terminal 2)
cd frontend && npm run dev
```

---

## Princípios

- **Contexto primeiro, código depois** — tudo nasce da história
- **Testes junto com o código** — nunca como etapa separada
- **Segurança desde o início** — JWT, validação, tratamento de erros
- **Rastreabilidade** — memória explícita, decisões documentadas, specs versionadas
- **Clareza sobre sofisticação** — código legível e manutenível

---

## Licença

Uso educacional. Desenvolvido para demonstração em aula na Saint Paul Escola de Negócios.
