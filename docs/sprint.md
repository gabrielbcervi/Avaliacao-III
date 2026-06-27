# Diário de Sprint

## Informações Gerais

**Projeto:** EduClass – Sistema de Gestão de Sala de Aula Online  
**Sprint:** Sprint 1 (Concepção e Modelagem)  
**Duração:** 2 aulas (6 horas no total)  
**Integrantes:** Gabriel Cervi, Matheus Stroher, Andrey Moraes, João Henrique Marcks

---

## Divisão de Responsabilidades

| Integrante | Responsabilidade Principal |
|---|---|
| Matheus Stroher  | Visão do Produto, Stakeholders, MVP e coordenação geral |
| Gabriel Cervi | Regras de Negócio, User Stories e Backlog |
| João Marcks | BPMN (processo de entrega de atividade) e Diagrama de Casos de Uso (UML) |
| Andrey Moraes | Arquitetura de Software, Modelo C4 (Contexto e Containers) e Decisões Arquiteturais |

> Todos os integrantes participaram das revisões e validações cruzadas dos artefatos.

---

## Aula 1 – Concepção da Solução

### Principais Atividades Realizadas
- Leitura e análise conjunta do enunciado da avaliação.
- Definição do nome e escopo do produto: **EduClass**.
- Identificação dos stakeholders e seus interesses.
- Definição de 8 regras de negócio relevantes para o domínio.
- Elaboração de 10 User Stories com critérios de aceitação.
- Definição do MVP com justificativa de priorização.
- Criação do repositório GitHub e da estrutura de pastas.
- Criação do quadro Kanban no GitHub Projects e distribuição das tarefas.

### Principais Decisões Tomadas
- Escolhemos o **GitHub Projects** como gestor de projetos por já estar integrado ao repositório.
- Definimos que o MVP cobriria o fluxo pedagógico completo: criar turma → matricular → publicar atividade → entregar → corrigir.
- Decidimos usar **nomes genéricos para os integrantes** nos artefatos para facilitar a reutilização.

### Dificuldades Encontradas
- Dificuldade inicial para definir o escopo do MVP sem incluir funcionalidades desnecessárias.
- Algumas regras de negócio levantadas eram muito técnicas (ex: validação de formato de arquivo); optamos por manter apenas as que têm impacto pedagógico ou de negócio.

### Soluções Adotadas
- Usamos o critério de "valor imediato ao usuário + viabilidade técnica" para filtrar o MVP.
- Separamos as regras com impacto em múltiplos artefatos para aprofundar a rastreabilidade.

---

## Aula 2 – Projeto da Solução

### Principais Atividades Realizadas
- Modelagem do processo BPMN: **Entrega de Atividade pelo Estudante**.
- Criação do Diagrama de Casos de Uso (UML) com os principais atores e funcionalidades.
- Definição da arquitetura em camadas com componente Pub/Sub para notificações.
- Criação do Modelo C4: Nível 1 (Contexto) e Nível 2 (Containers).
- Registro das 4 decisões arquiteturais com contexto e justificativa.
- Organização e revisão final de todos os artefatos.
- Montagem da apresentação.

### Principais Decisões Tomadas
- Optamos pela **arquitetura em camadas** no lugar de microserviços, pela simplicidade e adequação ao tamanho do projeto e da equipe.
- Escolhemos **PostgreSQL** pelo suporte nativo a relacionamentos complexos entre as entidades do sistema.
- Adotamos **JWT** para autenticação stateless, alinhado com a necessidade de controle de permissões por perfil (RBAC).
- Incluímos **Redis Pub/Sub** apenas para o módulo de notificações, mantendo o restante da arquitetura mais simples.

### Dificuldades Encontradas
- Dúvidas sobre o nível de detalhe adequado para o Modelo C4 (Nível 2).
- Dificuldade em representar corretamente o gateway condicional no BPMN para o caso de entrega após o prazo.

### Soluções Adotadas
- Consultamos exemplos de modelos C4 disponíveis em c4model.com para calibrar o nível de detalhe.
- Revisamos a notação BPMN e utilizamos um gateway exclusivo (XOR) para representar a verificação de prazo.

---

## Retrospectiva

**O que funcionou bem:**
- Divisão clara de responsabilidades desde o início.
- Uso do Kanban para acompanhar o progresso em tempo real.
- Revisão cruzada dos artefatos entre os integrantes.

**O que pode melhorar:**
- Melhor estimativa de tempo para cada artefato.
- Iniciar a modelagem BPMN antes das User Stories para garantir maior alinhamento.

**Aprendizados:**
- A rastreabilidade entre artefatos (Regra de Negócio → User Story → BPMN → Arquitetura) torna a solução mais coerente e defensável na banca.
- A definição clara do MVP no início evita retrabalho e mantém o foco da equipe.
