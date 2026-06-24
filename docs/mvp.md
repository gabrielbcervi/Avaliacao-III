# MVP – Minimum Viable Product

## Definição

O MVP do **EduClass** representa o conjunto mínimo de funcionalidades capazes de entregar valor real aos usuários principais (professores e estudantes), viabilizando o uso da plataforma desde o primeiro ciclo de desenvolvimento.

O objetivo é validar o fluxo central da plataforma: **criar turma → publicar atividade → entregar atividade → corrigir e dar feedback**.

---

## Funcionalidades do MVP

| Prioridade | Funcionalidade | User Story | Justificativa |
|---|---|---|---|
| 1 | Autenticação de usuários (login/logout) | — | Pré-requisito para todas as demais funcionalidades |
| 2 | Criar turma (professor) | US01 | Estrutura base para organização do sistema |
| 3 | Matricular-se em turma (estudante) | US02 | Permite que estudantes acessem o conteúdo |
| 4 | Publicar atividade com prazo | US03 | Funcionalidade central para professores |
| 5 | Visualizar atividades da turma | US04 | Permite ao estudante se organizar |
| 6 | Entregar atividade (upload de arquivo ou texto) | US05 | Concretiza o fluxo principal do sistema |
| 7 | Corrigir entrega e atribuir nota | US06 | Fecha o ciclo pedagógico de avaliação |
| 8 | Notificações básicas (in-app) | US07 | Garante que os usuários sejam informados de eventos relevantes |

---

## Funcionalidades Futuras (Pós-MVP)

| Funcionalidade | User Story | Fase Sugerida |
|---|---|---|
| Painel de desempenho da turma para coordenador | US08 | Fase 2 |
| Gerenciamento de usuários pelo administrador | US09 | Fase 2 |
| Publicação de materiais de apoio | US10 | Fase 2 |
| Notificações por e-mail | US07 (extensão) | Fase 2 |
| Fórum de discussão por turma | — | Fase 3 |
| Reabertura de entrega pelo professor | RN05 | Fase 2 |
| Relatórios e exportação de notas | — | Fase 3 |
| Integração com calendário externo | — | Fase 3 |
| App mobile nativo | — | Fase 4 |

---

## Justificativa da Priorização

As funcionalidades do MVP foram selecionadas com base nos seguintes critérios:

1. **Valor imediato ao usuário:** as funcionalidades escolhidas cobrem o fluxo pedagógico completo — da criação da turma até o feedback da avaliação — o que é suficiente para que professores e estudantes usem a plataforma de forma produtiva desde o início.

2. **Viabilidade técnica:** as funcionalidades do MVP utilizam recursos tecnológicos simples e bem estabelecidos (autenticação JWT, upload de arquivos, banco relacional), reduzindo o risco de desenvolvimento.

3. **Validação do produto:** o MVP permite coletar feedback real de professores e estudantes sobre usabilidade, fluxo de trabalho e necessidades não mapeadas, antes de investir em funcionalidades mais complexas.

4. **Regras de negócio críticas cobertas:** o MVP já implementa as RNs mais importantes (RN01, RN02, RN03, RN04), garantindo integridade dos dados e segurança do sistema desde a primeira versão.
