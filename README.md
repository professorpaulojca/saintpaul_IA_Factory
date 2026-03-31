# Saint Paul — AI Factory

> **"A IA boa não começa no prompt. Ela começa no ambiente."**

Ambiente de engenharia assistida por IA para transformar uma história de negócio em uma aplicação moderna e completa — usando **GitHub Copilot**, memória explícita, agentes especializados e prompts de ação em sequência.

---

## O que é este projeto?

O **AI Factory** demonstra, na prática, que a qualidade do código gerado por IA depende diretamente da qualidade do ambiente preparado para ela.

Em vez de jogar um prompt solto e torcer pelo melhor resultado, este ambiente ensina a IA a trabalhar com:

- **História de negócio** como fonte primária
- **Memória explícita** do projeto (memory bank)
- **Regras e padrões** técnicos definidos previamente
- **Agentes especializados** para cada papel no processo
- **Prompts de ação sequenciais** que guiam a geração passo a passo

O resultado: uma aplicação full-stack coerente, rastreável e pronta para revisão técnica.

---

## Stack gerada

| Camada | Tecnologia |
|--------|-----------|
| Backend | Java 17+, Spring Boot, Spring Data JPA, Spring Security + JWT, Flyway, OpenAPI/Swagger |
| Frontend | React 18, TypeScript, Vite, React Router, Axios |
| Banco de dados | PostgreSQL 15+ |
| Diagramas | Mermaid, draw.io, BPMN 2.0 (Camunda) |
| IA | GitHub Copilot Pro |

---

## Estrutura do repositório

```
saint-paul-ia-factory/
│
├── input/
│   └── application-story.md        ← COLE A HISTÓRIA AQUI
│
├── .github/
│   ├── copilot-instructions.md     ← regras globais do Copilot
│   ├── agents/                     ← agentes especializados
│   │   ├── analyst.agent.md        ← analista de negócio
│   │   ├── architect.agent.md      ← arquiteto de solução
│   │   ├── builder.agent.md        ← gerador de código
│   │   ├── reviewer.agent.md       ← revisor técnico
│   │   └── specifier.agent.md      ← gerador de especificações
│   ├── instructions/               ← padrões técnicos por camada
│   │   ├── backend.instructions.md
│   │   ├── frontend.instructions.md
│   │   ├── database.instructions.md
│   │   └── docs.instructions.md
│   ├── prompts/                    ← prompts de ação (executar em ordem)
│   │   ├── 01-prototype.prompt.md
│   │   ├── 02-specification.prompt.md
│   │   ├── 03-backend.prompt.md
│   │   ├── 04-frontend.prompt.md
│   │   └── 05-review.prompt.md
│   └── skills/
│       └── create-endpoint/        ← skill reutilizável de endpoint
│
├── docs/
│   ├── memory-bank/                ← memória explícita do projeto
│   │   ├── architecture.md
│   │   ├── business-rules.md
│   │   ├── current-state.md
│   │   ├── decisions.md
│   │   ├── glossary.md
│   │   └── product.md
│   ├── specs/                      ← especificações geradas pelo Prompt 02
│   │   ├── functional-requirements.md
│   │   ├── business-rules.md
│   │   ├── non-functional-requirements.md
│   │   └── use-cases.md
│   ├── architecture/               ← padrões e visão técnica
│   │   ├── solution-overview.md
│   │   ├── backend-standards.md
│   │   ├── frontend-standards.md
│   │   ├── database.instructions.md
│   │   ├── security.md
│   │   └── observability.md
│   └── diagrams/                   ← diagramas gerados pelo Prompt 02
│       ├── domain-model.mmd        ← modelo de domínio (Mermaid)
│       ├── main-flow.mmd           ← fluxo principal (Mermaid)
│       ├── process.bpmn            ← processo de negócio (BPMN)
│       └── process.drawio          ← diagrama livre (draw.io)
│
├── scripts/
│   └── copilot-chat-sequence.md    ← roteiro de aula
│
└── docker-compose.yml              ← PostgreSQL local
```

> As pastas `backend/`, `frontend/`, `database/` e `prototypes/` são **geradas pelos prompts**. Não existem no repositório até a execução.

---

## Pré-requisitos

- [VS Code](https://code.visualstudio.com/) com extensão **GitHub Copilot** (plano Pro ou superior)
- [Docker](https://www.docker.com/) para o banco de dados local
- [Java 17+](https://adoptium.net/) e [Maven](https://maven.apache.org/) (para rodar o backend gerado)
- [Node.js 20+](https://nodejs.org/) (para rodar o frontend gerado)

---

## Como usar

### 1. Suba o banco de dados

```bash
docker-compose up -d
```

### 2. Cole a história de negócio

Abra o arquivo `input/application-story.md` e descreva o sistema a ser construído:

- Contexto do negócio
- Problemas que o sistema resolve
- Usuários e seus perfis
- Funcionalidades esperadas
- Regras de negócio
- Fluxos principais

---

### 3. Execute os prompts em sequência

Abra o **Copilot Chat** no VS Code (`Ctrl+Shift+I`) e execute cada prompt na ordem abaixo.

---

#### Prompt 01 — Protótipos Funcionais

Gera telas HTML/CSS/JS para visualizar o produto antes de qualquer código de produção.

```
@workspace #file:.github/prompts/01-prototype.prompt.md
```

**Saída:** pasta `prototypes/` com telas navegáveis do sistema.

---

#### Prompt 02 — Especificação Técnica

Transforma a história em engenharia: requisitos, regras, casos de uso e diagramas.

```
@workspace #file:.github/prompts/02-specification.prompt.md
```

**Saída:** `docs/specs/` preenchido + diagramas Mermaid e BPMN em `docs/diagrams/`.

---

#### Prompt 03 — Backend Java

Gera o backend completo com base nas especificações e no modelo de domínio.

```
@workspace #file:.github/prompts/03-backend.prompt.md
```

**Saída:** pasta `backend/` com aplicação Spring Boot compilável, endpoints documentados no Swagger e migrations Flyway.

Para rodar após geração:

```bash
cd backend
./mvnw spring-boot:run
```

Swagger disponível em: `http://localhost:8080/swagger-ui.html`

---

#### Prompt 04 — Frontend React

Gera o frontend alinhado aos protótipos e à API do backend.

```
@workspace #file:.github/prompts/04-frontend.prompt.md
```

**Saída:** pasta `frontend/` com aplicação React/TypeScript executável, fluxo de autenticação e páginas CRUD.

Para rodar após geração:

```bash
cd frontend
npm install
npm run dev
```

Aplicação disponível em: `http://localhost:5173`

---

#### Prompt 05 — Revisão Técnica

Submete toda a solução gerada a uma revisão técnica integrada.

```
@workspace #file:.github/prompts/05-review.prompt.md
```

**Saída:** relatório com pontos fortes, problemas encontrados, correções recomendadas e parecer final.

---

## Agentes especializados

Os agentes em `.github/agents/` podem ser ativados no Copilot Chat para papéis específicos:

| Agente | Quando usar |
|--------|------------|
| `analyst.agent.md` | Analisar e enriquecer a história de negócio |
| `architect.agent.md` | Decisões de arquitetura e estrutura da solução |
| `specifier.agent.md` | Gerar ou revisar especificações técnicas |
| `builder.agent.md` | Geração de código por camada |
| `reviewer.agent.md` | Revisão técnica de qualquer artefato |

Para ativar no Copilot Chat:

```
@workspace #file:.github/agents/architect.agent.md
```

---

## Fluxo completo

```
História de negócio
        │
        ▼
[Prompt 01] Protótipos HTML/CSS/JS
        │
        ▼
[Prompt 02] Especificações + Diagramas
        │
        ▼
[Prompt 03] Backend Java/Spring Boot
        │
        ▼
[Prompt 04] Frontend React/TypeScript
        │
        ▼
[Prompt 05] Revisão Técnica Integrada
```

---

## Ponto-chave pedagógico

A maioria das pessoas pede código assim:

> *"Crie um sistema de gestão de pedidos com Java e React."*

Neste ambiente, a IA recebe:

- A **história completa** do negócio
- A **memória** de decisões anteriores
- Os **padrões técnicos** de cada camada
- Os **agentes** certos para cada papel
- A **sequência** correta de geração

O resultado não é só mais código — é um sistema **rastreável**, **coerente** e **revisável**.

---

## Público-alvo

- Alunos em formação em engenharia de software
- Desenvolvedores iniciando com IA aplicada à engenharia
- Times que querem reduzir improviso e aumentar consistência na geração assistida por IA

---

## Observações

- Todos os arquivos estão em UTF-8
- O ambiente foi escrito em português do Brasil
- O conteúdo é didático, profissional e reutilizável para diferentes histórias de negócio
