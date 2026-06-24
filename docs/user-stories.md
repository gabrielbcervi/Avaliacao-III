# User Stories

## US01 – Criar Turma

**Como** professor,  
**desejo** criar uma turma na plataforma,  
**para que** eu possa organizar meus estudantes e publicar conteúdos e atividades de forma centralizada.

**Critérios de Aceitação:**
- O professor deve estar autenticado com perfil "Professor".
- O sistema deve solicitar: nome da turma, disciplina, descrição e código de acesso.
- Após a criação, o sistema deve gerar um código único de ingresso para a turma.
- A turma deve aparecer na lista de turmas do professor imediatamente após a criação.

---

## US02 – Matricular-se em Turma

**Como** estudante,  
**desejo** me matricular em uma turma utilizando um código de acesso,  
**para que** eu possa visualizar as atividades e materiais disponibilizados pelo professor.

**Critérios de Aceitação:**
- O estudante deve estar autenticado com perfil "Estudante".
- O sistema deve aceitar o código de acesso e vincular o estudante à turma correspondente.
- Caso o código seja inválido, o sistema deve exibir uma mensagem de erro clara.
- Após a matrícula, a turma deve aparecer na lista de turmas do estudante.

---

## US03 – Publicar Atividade

**Como** professor,  
**desejo** publicar uma atividade em uma turma com prazo de entrega,  
**para que** os estudantes possam visualizá-la e realizar a entrega dentro do prazo.

**Critérios de Aceitação:**
- Apenas professores da turma podem publicar atividades.
- O professor deve informar: título, descrição, data de entrega, valor máximo da nota e se aceita entrega após o prazo.
- Após a publicação, os estudantes da turma devem receber uma notificação.
- A atividade deve aparecer na lista de atividades da turma com status "Aberta".

---

## US04 – Visualizar Atividades da Turma

**Como** estudante,  
**desejo** visualizar todas as atividades publicadas em uma turma,  
**para que** eu possa me organizar e cumprir os prazos estabelecidos.

**Critérios de Aceitação:**
- O estudante deve estar matriculado na turma para visualizar suas atividades.
- O sistema deve exibir: título, descrição, prazo de entrega e status (aberta, encerrada, entregue).
- Atividades com prazo vencido devem ser destacadas visualmente.

---

## US05 – Entregar Atividade

**Como** estudante,  
**desejo** realizar a entrega de uma atividade enviando um arquivo ou texto,  
**para que** o professor possa corrigir e atribuir uma nota.

**Critérios de Aceitação:**
- O estudante deve estar matriculado na turma e a atividade deve estar com status "Aberta".
- O sistema deve aceitar upload de arquivos (PDF, DOCX, imagens) ou resposta em texto.
- Entregas realizadas após o prazo devem ser registradas com status "Atrasada".
- O estudante não pode realizar uma segunda entrega sem que o professor reabra a atividade.
- Após a entrega, o sistema deve confirmar o recebimento com data e horário.

---

## US06 – Corrigir e Atribuir Nota

**Como** professor,  
**desejo** corrigir a entrega de um estudante e atribuir uma nota,  
**para que** o estudante receba feedback sobre seu desempenho.

**Critérios de Aceitação:**
- Apenas o professor responsável pela turma pode corrigir entregas.
- A nota deve estar dentro do intervalo definido na criação da atividade.
- O professor pode incluir um comentário textual de feedback.
- Após a correção, o estudante deve receber uma notificação informando que sua entrega foi avaliada.

---

## US07 – Receber Notificações

**Como** estudante,  
**desejo** receber notificações quando uma nova atividade for publicada ou minha entrega for corrigida,  
**para que** eu me mantenha atualizado sem precisar verificar a plataforma constantemente.

**Critérios de Aceitação:**
- O sistema deve enviar notificação ao estudante sempre que uma nova atividade for publicada na turma.
- O sistema deve enviar notificação ao estudante quando sua entrega for avaliada.
- O estudante deve poder configurar suas preferências de notificação (e-mail ou in-app).

---

## US08 – Acompanhar Desempenho da Turma

**Como** coordenador,  
**desejo** visualizar um painel com o desempenho geral de uma turma,  
**para que** eu possa identificar estudantes em dificuldades e apoiar intervenções pedagógicas.

**Critérios de Aceitação:**
- O coordenador deve ter acesso a um painel com: média de notas por turma, taxa de entrega de atividades e listagem de estudantes com baixo desempenho.
- Os dados devem ser atualizados em tempo real.
- O coordenador não deve ter acesso a dados individuais de forma invasiva; apenas indicadores agregados por padrão.

---

## US09 – Gerenciar Usuários

**Como** administrador,  
**desejo** criar, editar e desativar contas de usuários na plataforma,  
**para que** apenas pessoas autorizadas tenham acesso ao sistema.

**Critérios de Aceitação:**
- O administrador deve poder criar contas atribuindo perfil (Estudante, Professor, Coordenador).
- O administrador deve poder desativar contas sem excluir o histórico de atividades.
- Contas desativadas não devem conseguir realizar login.

---

## US10 – Publicar Material de Apoio

**Como** professor,  
**desejo** publicar materiais de apoio (PDFs, links, vídeos) em uma turma,  
**para que** os estudantes tenham acesso a conteúdos complementares às aulas.

**Critérios de Aceitação:**
- O professor deve poder fazer upload de arquivos ou inserir links externos.
- Os materiais devem ficar disponíveis para todos os estudantes matriculados na turma.
- O professor deve poder organizar os materiais por tema ou data.
