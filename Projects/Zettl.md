# Stacks & Deploy

- **Frontend** 
	- Stack: Angular
	- Deploy: Netlify/Vercel
- **Backend**
	- Stack: Java + Spring Boot
	- Deploy: Render
- **Database**
	- Stack: PostgreSQL
	- Deploy: Railway

# 1) Objetivos do projeto (resultados que você precisa ter)

- MVP funcional: criar/abrir um vault (pasta com notas e subpastas), listar árvore de arquivos, abrir/editar/salvar notas em Markdown no backend, persistência em PostgreSQL, frontend Angular consumindo API Java.
    
- Infra mínima para deploy (Render/Netlify ou similar).
    
- Testes básicos (unit + integração) e CI simples.
    
- Documentação mínima (README, endpoints, como rodar local).
    

# 2) Entregáveis / checkpoints (modo 42: obrigatório vs bonus)

**Obrigatórios (MVP)**

1. Backend Spring Boot com endpoints REST para: criar vault, upload `.zip`, extrair/normalizar, listar arquivos (árvore), ler nota, criar/editar/deletar nota.
    
2. PostgreSQL com esquema relacional (users, vaults, notes).
    
3. Frontend Angular: tela de login (ou modo “demo”), lista em árvore, editor Markdown com preview (salvar para backend).
    
4. Deploy mínimo: frontend em Netlify/Vercel/GH Pages, backend em Render (free tier).
    
5. README com instruções para rodar local e deploy.
    
6. Testes: JUnit (backend) cobrindo endpoints críticos; testes unitários básicos do frontend.
    
7. CI (GitHub Actions): build + tests para backend e frontend.
    

**Bonus (extra crédito)**

- Upload de `.zip` e importação automática para tabela notes.
    
- Histórico de versões das notas (versioning simples).
    
- Busca full-text nas notas.
    
- PWA/offline básico.
    
- Exportar vault como `.zip`.
    
- Autenticação por JWT + refresh tokens.
    
- E2E com Cypress.
    

# 3) Roadmap por sprints (4 semanas — ajustável)

Cada sprint = 1 semana (ou 2 se preferir ritmo mais lento). Vou propor 4 semanas.

**Sprint 0 — Preparação (1–2 dias)**

- Criar repo (GitHub), configurar branches (main, develop, feature/*).
    
- Inicializar projeto Spring Boot (Maven/Gradle), Angular (Angular CLI).
    
- Escolher versões: Java 17+, Spring Boot 3.x, Node 18+, Angular 16+.
    
- Criar README com checklist.
    

**Sprint 1 — Backend básico + DB (7 dias)**

- Modelagem DB + migrations (Flyway/Liquibase opcional).
    
- Implementar entidades JPA: User, Vault, Note.
    
- Endpoints CRUD básicos (ver lista abaixo).
    
- Configurar dev DB (docker-compose postgres ou local).
    
- Unit tests JUnit para repositórios e serviços.
    
- Documentar API (Springdoc / Swagger).
    

**Sprint 2 — Frontend básico + integração mock**

- Criar interface Angular: layout, login-demo, listagem de arquivos (tree component), editor Markdown (usar ngx-markdown, or ngx-md, ou integrate simple textarea+marked).
    
- Implementar serviços Angular com mock JSON (para testar UI sem backend).
    
- Salvar localmente (localStorage) como fallback para demo.
    
- Testes unitários (Karma/Jasmine).
    

**Sprint 3 — Conectar frontend ↔ backend + upload .zip**

- Implementar integração HTTP real (Angular HttpClient).
    
- Implementar endpoint de upload `.zip` e extração (backend).
    
- Fluxo completo: criar vault → listar → abrir → editar → salvar.
    
- Deploy do frontend (Netlify) e backend (Render free).
    
- CI básico (build/test + deploy manual).
    

**Sprint 4 — Polimento, testes, docs e bônus**

- Cobrir casos de ponta (paths com /, encoding).
    
- Adicionar testes de integração (SpringBootTest para endpoints).
    
- Implementar pelo menos 1 feature bonus (ex.: export zip ou histórico simples).
    
- Preparar demo / checklist de avaliação.
    

# 4) Modelo de dados (SQL) — esquema mínimo