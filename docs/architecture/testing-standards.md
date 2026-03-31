# Testing Standards

## Filosofia

Testes não existem para cobrir linhas de código. Existem para **proteger comportamento de negócio**.

Um teste unitário eficaz:
- Valida um **comportamento**, não uma implementação
- Falha quando o **negócio quebra**, não quando refatoram o código
- Serve como **documentação viva** do que o sistema faz

## Backend (Java / Spring Boot)

### Stack de testes
- JUnit 5
- Mockito
- AssertJ
- Spring Boot Test (apenas para testes de integração pontuais)
- H2 (banco em memória para testes de repository, quando necessário)

### O que testar

| Camada | Obrigatório | Foco |
|--------|------------|------|
| Service | Sim | Regras de negócio, validações, fluxos condicionais |
| Controller | Sim | Contrato HTTP (status codes, formato de resposta, validação de input) |
| Repository | Quando houver queries customizadas | Comportamento de queries `@Query` ou derivadas complexas |
| Security | Sim | Acesso autorizado/negado por role, token inválido |
| DTOs / Mappers | Quando houver lógica | Conversão entre entidades e DTOs |

### O que NÃO testar isoladamente
- Getters e setters triviais
- Construtores gerados (records, Lombok)
- Código do framework (Spring, JPA)
- Configurações estáticas

### Padrões obrigatórios

1. **Given-When-Then** — todo teste segue essa estrutura:
   ```java
   @Test
   void should_reject_login_when_password_is_wrong() {
       // given
       var request = new LoginRequest("admin", "wrong");
       when(repository.findByUsername("admin")).thenReturn(Optional.of(user));
       when(encoder.matches("wrong", user.getPassword())).thenReturn(false);

       // when & then
       assertThatThrownBy(() -> authService.authenticate(request))
           .isInstanceOf(IllegalArgumentException.class)
           .hasMessage("Usuário ou senha inválidos.");
   }
   ```

2. **Nomes descritivos** — `should_[resultado]_when_[condição]`:
   - `should_return_token_when_credentials_are_valid`
   - `should_throw_exception_when_user_not_found`
   - `should_deny_access_when_role_is_insufficient`

3. **Um assert por comportamento** — cada teste valida uma única decisão de negócio.

4. **Mocks apenas nas fronteiras** — mockar dependências diretas do SUT (System Under Test), nunca mockar o próprio objeto testado.

5. **Dados de teste explícitos** — não usar dados aleatórios. Construir cenários claros e reprodutíveis.

6. **Testes negativos são obrigatórios** — para cada caminho feliz, testar ao menos:
   - Entrada inválida / ausente
   - Entidade não encontrada
   - Permissão negada (quando aplicável)

### Estrutura de diretórios

```
backend/src/test/java/com/saintpaul/academy/
├── service/
│   └── AuthServiceTest.java
├── controller/
│   └── AuthControllerTest.java
├── security/
│   └── JwtServiceTest.java
└── repository/
    └── (apenas se houver queries customizadas)
```

### Execução

```bash
mvn test -f backend/pom.xml
```

## Frontend (React / TypeScript)

### Stack de testes
- Vitest
- React Testing Library
- @testing-library/jest-dom
- MSW (Mock Service Worker) para mock de API quando necessário

### O que testar

| Tipo | Obrigatório | Foco |
|------|------------|------|
| Hooks customizados | Sim | Lógica de estado e efeitos colaterais |
| Serviços de API | Sim | Chamadas corretas, tratamento de erro |
| Componentes com lógica | Sim | Renderização condicional, eventos, feedback |
| Páginas | Cenários-chave | Fluxo completo de interação |
| Componentes puramente visuais | Não | Sem lógica para validar |

### Padrões obrigatórios

1. **Testar pelo comportamento do usuário**, não pela implementação:
   ```typescript
   // BOM — testa o que o usuário vê
   expect(screen.getByText('Usuário ou senha inválidos.')).toBeInTheDocument();

   // RUIM — testa implementação interna
   expect(component.state.error).toBe('Usuário ou senha inválidos.');
   ```

2. **Nomes descritivos em português ou inglês consistente**:
   - `should display error message when login fails`
   - `should redirect to dashboard after successful login`

3. **Interações via `userEvent`**, não `fireEvent`:
   ```typescript
   await userEvent.click(screen.getByRole('button', { name: /entrar/i }));
   ```

4. **Queries por acessibilidade**: preferir `getByRole`, `getByLabelText`, `getByText`. Evitar `getByTestId` exceto quando não houver alternativa semântica.

5. **Mock de API via MSW** para testes que dependem de backend — nunca mockar `fetch`/`axios` diretamente.

### Estrutura de diretórios

```
frontend/src/
├── services/
│   └── __tests__/
│       └── authService.test.ts
├── hooks/
│   └── __tests__/
│       └── useAuth.test.ts
├── pages/
│   └── __tests__/
│       └── LoginPage.test.tsx
└── components/
    └── __tests__/
        └── (quando houver lógica)
```

### Execução

```bash
cd frontend && npx vitest run
```

## Métricas de qualidade

Não perseguir cobertura numérica cega. Priorizar:

- **100%** das regras de negócio em services cobertos
- **100%** dos caminhos de erro tratados e testados
- **100%** dos controllers com validação de contrato
- Hooks e serviços de API com ao menos cenário feliz + erro

## Regra de geração

Sempre que a IA gerar código em `backend/` ou `frontend/`, deve gerar simultaneamente os testes unitários correspondentes. Testes não são uma etapa separada — são parte da entrega de cada funcionalidade.
