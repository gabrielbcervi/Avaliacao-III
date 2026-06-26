# EduClass – Sistema de Gestão de Sala de Aula Online

## Sobre o Projeto

O **EduClass** é uma plataforma digital de gestão de sala de aula online desenvolvida como proposta de solução para uma instituição de ensino que deseja centralizar a comunicação entre professores e estudantes, o gerenciamento de atividades, avaliações e o acompanhamento pedagógico.

Este projeto foi desenvolvido como parte da **Avaliação Integradora** da disciplina de Modelagem e Projetos em Engenharia de Software.

---

## Estrutura do Repositório

```
classroom-project/
├── docs/
│   ├── visao-produto.md       # Problema, público-alvo, objetivos e benefícios
│   ├── stakeholders.md        # Mapeamento dos envolvidos no sistema
│   ├── regras-negocio.md      # Regras de negócio e seus impactos
│   ├── user-stories.md        # User Stories com critérios de aceitação
│   ├── mvp.md                 # MVP e funcionalidades futuras
│   ├── arquitetura.md         # Arquitetura e decisões arquiteturais
│   ├── sprint.md              # Diário de Sprint e colaboração da equipe
│   └── README.md              # Este arquivo
├── bpmn/
│   └── entrega-atividade.bpmn # Processo BPMN: Entrega de Atividade
├── uml/
│   └── casos-de-uso.png       # Diagrama de Casos de Uso
├── c4/
│   ├── contexto.png           # C4 Nível 1 – Contexto
│   └── containers.png         # C4 Nível 2 – Containers
└── apresentacao/
    └── apresentacao-final.pdf  # Apresentação da banca
```

---

## Integrantes

| Nome | GitHub |
|---|---|
| Matheus Stroher | @maghteil |
| Integrante B | @integranteB |
| João Henrique | @joaomarcks-hot |
| Andrey Moraes | @andreymoraes191-exe |

---

## Links

- **Repositório GitHub:** *(inserir link)*
- **Gestor de Projetos (GitHub Projects):** *(inserir link)*

---

## Tecnologias Utilizadas na Solução Proposta

| Camada | Tecnologia |
|---|---|
| Frontend | React + TypeScript |
| Backend | Node.js + Express |
| Banco de Dados | PostgreSQL |
| Autenticação | JWT |
| Notificações | Redis Pub/Sub |
| Armazenamento | Amazon S3 / MinIO |
| Infraestrutura | Docker + Docker Compose |

---

## Funcionalidade Inovadora

O EduClass propõe como funcionalidade inovadora um **Painel de Risco Acadêmico com Alertas Automáticos**: um módulo que analisa padrões de comportamento dos estudantes (entregas atrasadas, ausência de entregas, notas abaixo da média) e gera alertas automáticos para professores e coordenadores, permitindo intervenção pedagógica precoce antes que o estudante reprove ou abandone a disciplina.

---

## Como Navegar pela Documentação

Sugerimos a seguinte ordem de leitura:

1. [`visao-produto.md`](visao-produto.md) – entenda o problema e os objetivos
2. [`stakeholders.md`](stakeholders.md) – conheça os envolvidos
3. [`regras-negocio.md`](regras-negocio.md) – compreenda as restrições do domínio
4. [`user-stories.md`](user-stories.md) – veja os requisitos funcionais
5. [`mvp.md`](mvp.md) – entenda o que será entregue primeiro
6. [`arquitetura.md`](arquitetura.md) – conheça as decisões técnicas
7. [`sprint.md`](sprint.md) – acompanhe o processo de desenvolvimento
