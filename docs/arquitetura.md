# Arquitetura de Software

## Estilo Arquitetural Escolhido: Em Camadas (Layered Architecture) com elementos de Publish-Subscribe para notificações

---

## Justificativa

O sistema **EduClass**, em sua versão MVP, apresenta as seguintes características que guiaram a escolha arquitetural:

- **Escopo bem definido:** o sistema tem fronteiras claras entre interface, lógica de negócio e persistência;
- **Equipe pequena:** grupos reduzidos se beneficiam de uma arquitetura mais simples, com menor overhead de infraestrutura;
- **Prazos curtos:** a arquitetura em camadas permite desenvolvimento mais ágil, com separação de responsabilidades sem a complexidade de microserviços;
- **Regras de negócio centralizadas:** as RNs do EduClass (controle de prazo, permissões por perfil, ciclo de correção) são melhor gerenciadas em uma camada de serviço centralizada;
- **Notificações assíncronas:** a necessidade de enviar notificações (RN07) sem impactar o fluxo principal justifica a adoção de Publish-Subscribe neste ponto específico.

A arquitetura de **Microserviços** foi descartada por adicionar complexidade desnecessária para o porte do projeto e tamanho da equipe neste estágio.

---

## Visão Geral das Camadas

```
┌────────────────────────────────────────┐
│           Camada de Apresentação       │  → Frontend Web (React)
├────────────────────────────────────────┤
│           Camada de API (REST)         │  → Controllers / Rotas
├────────────────────────────────────────┤
│        Camada de Serviços (Negócio)    │  → Regras de Negócio / Use Cases
├────────────────────────────────────────┤
│        Camada de Repositório (Dados)   │  → Acesso ao banco de dados
├────────────────────────────────────────┤
│           Banco de Dados               │  → PostgreSQL
└────────────────────────────────────────┘
                    ↕ (assíncrono)
┌────────────────────────────────────────┐
│       Serviço de Notificações          │  → Pub/Sub via message broker
└────────────────────────────────────────┘
```

---

## Decisões Arquiteturais

### DA01 – Adoção da Arquitetura em Camadas

**Decisão:** Utilizar arquitetura em camadas como padrão principal da aplicação backend.

**Contexto:** O sistema possui requisitos funcionais bem definidos e uma equipe de desenvolvimento pequena.

**Justificativa:** A separação em camadas (Apresentação → API → Serviço → Repositório → Dados) facilita a manutenção, testabilidade e evolução do sistema sem a complexidade de uma arquitetura distribuída.

**Consequências:** Acoplamento entre camadas é tolerado; escalabilidade horizontal exige atenção futura.

---

### DA02 – Autenticação via JWT (JSON Web Token)

**Decisão:** Utilizar autenticação stateless com tokens JWT.

**Contexto:** O sistema precisa distinguir perfis de usuário (Professor, Estudante, Coordenador, Administrador) e restringir funcionalidades conforme o perfil (RN01, RN04, RN08).

**Justificativa:** JWT permite validação de permissões sem consulta ao banco a cada requisição, é amplamente suportado e facilita futuras integrações. O payload do token armazenará o perfil do usuário para uso no controle de autorização (RBAC).

**Consequências:** Necessidade de estratégia de revogação de tokens (blacklist ou refresh tokens de curta duração).

---

### DA03 – Publish-Subscribe para Notificações

**Decisão:** Utilizar o padrão Publish-Subscribe (via message broker simples, ex: Redis Pub/Sub) para o envio de notificações.

**Contexto:** As notificações (RN07) devem ser enviadas de forma assíncrona sem bloquear as operações principais (publicação de atividade, correção de entrega).

**Justificativa:** Desacoplar o fluxo principal do sistema do serviço de notificações garante melhor performance e facilita a extensão futura para múltiplos canais (in-app, e-mail, SMS).

**Consequências:** Necessidade de gerenciar um broker de mensagens na infraestrutura; eventual consistência nas notificações (pode haver pequeno atraso).

---

### DA04 – Banco de Dados Relacional (PostgreSQL)

**Decisão:** Utilizar PostgreSQL como banco de dados principal.

**Contexto:** O sistema possui relacionamentos complexos entre entidades (Turma ↔ Estudante ↔ Atividade ↔ Entrega ↔ Nota) e exige consistência transacional.

**Justificativa:** Bancos relacionais são a escolha natural para domínios com forte estrutura de dados e regras de integridade referencial. PostgreSQL oferece recursos avançados (JSONB, full-text search) que podem ser úteis em fases futuras.

**Consequências:** Menor flexibilidade para dados não estruturados; escalabilidade horizontal de banco exige estratégias adicionais (replicação, sharding) no futuro.

---

## Stack Tecnológica

| Camada | Tecnologia |
|---|---|
| Frontend | React + TypeScript |
| Backend (API) | Node.js + Express (ou NestJS) |
| Banco de Dados | PostgreSQL |
| Autenticação | JWT + bcrypt |
| Notificações | Redis Pub/Sub |
| Armazenamento de Arquivos | Amazon S3 (ou MinIO para on-premise) |
| Containerização | Docker + Docker Compose |
| Controle de Versão | Git + GitHub |
