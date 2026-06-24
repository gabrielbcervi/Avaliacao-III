# Regras de Negócio

## Listagem das Regras

| ID | Regra de Negócio |
|---|---|
| RN01 | Apenas professores podem criar turmas e publicar atividades |
| RN02 | Um estudante só pode acessar o conteúdo de uma turma após realizar a matrícula |
| RN03 | Atividades possuem prazo de entrega; entregas após o prazo são marcadas como "atrasadas" |
| RN04 | Apenas o professor responsável pela turma pode corrigir e atribuir notas às entregas |
| RN05 | Um estudante não pode entregar uma atividade que já foi por ele entregue anteriormente, salvo se o professor reabrir a entrega |
| RN06 | A nota atribuída a uma entrega deve estar dentro do intervalo definido pelo professor no momento da criação da atividade |
| RN07 | O sistema deve enviar notificações automáticas para estudantes quando uma nova atividade for publicada |
| RN08 | Um professor não pode matricular estudantes em turmas de outros professores sem permissão do administrador |

---

## Impacto das Regras na Solução

### RN01 – Apenas professores podem criar turmas e publicar atividades

**Descrição:** O perfil "Professor" é o único com permissão para criar turmas e publicar atividades. Estudantes e coordenadores não possuem esse acesso.

**Impactos:**

- **User Story:** US01 – Como professor, desejo criar uma turma para organizar meus estudantes e publicar atividades.
- **Caso de Uso:** UC01 – Criar Turma; UC03 – Publicar Atividade.
- **BPMN:** A criação de turma e publicação de atividade são tarefas executadas exclusivamente na raia do Professor.
- **Arquitetura:** Exige controle de autorização baseado em perfis (RBAC – Role-Based Access Control). O módulo de autenticação deve retornar o perfil do usuário para que a API valide as permissões antes de executar operações restritas.
- **Requisito Não Funcional:** Segurança – controle de acesso por perfil de usuário.

---

### RN03 – Atividades possuem prazo de entrega; entregas após o prazo são marcadas como "atrasadas"

**Descrição:** Ao criar uma atividade, o professor define uma data e horário limite para entrega. O sistema deve comparar o momento da entrega com o prazo definido e registrar automaticamente se a entrega é pontual ou atrasada.

**Impactos:**

- **User Story:** US05 – Como estudante, desejo entregar uma atividade dentro do prazo para que minha entrega seja registrada como pontual.
- **Caso de Uso:** UC05 – Entregar Atividade.
- **BPMN:** No processo de entrega de atividade, há um gateway exclusivo que verifica se o prazo foi respeitado; em caso negativo, o sistema registra a entrega como "atrasada" e pode enviar notificação ao professor.
- **Arquitetura:** O serviço de entregas deve consultar o atributo `deadline` da atividade e registrar o status `on_time` ou `late` no momento da entrega. Um job agendado (scheduler) pode complementar essa lógica para bloquear ou sinalizar entregas após o prazo.
- **Decisão Arquitetural:** Necessidade de um serviço de agendamento (scheduler/cron job) para gerenciar prazos de forma automatizada.
