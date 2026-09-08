# Aula 6: Organização Profissional no GitHub

## Git e GitHub na Prática

### Carga horária

4 horas

### Tema da aula

Planejamento e acompanhamento do trabalho com GitHub Issues, labels, responsáveis, milestones, GitHub Projects, listas de tarefas, templates e arquivos de orientação para colaboradores.

## 1. Apresentação da aula

Nas aulas anteriores, eu ensinei você a controlar versões, criar branches, abrir Pull Requests, revisar alterações, realizar merges, resolver conflitos e recuperar trabalhos.

Até este momento, nosso fluxo técnico já permite desenvolver e integrar funcionalidades.

Porém, uma equipe profissional precisa responder outras perguntas:

1. O que precisa ser feito?

2. Por que essa tarefa é necessária?

3. Quem será responsável?

4. Qual é a prioridade?

5. Quando a tarefa deverá ser concluída?

6. Quais tarefas dependem de outras?

7. O que está pendente?

8. O que está em desenvolvimento?

9. O que está em revisão?

10. O que já foi concluído?

Nesta aula, vamos utilizar os recursos do GitHub para transformar o repositório em um ambiente de planejamento e colaboração.

O fluxo principal será:

```text
Identificar uma necessidade

        ↓

Criar uma Issue

        ↓

Descrever o resultado esperado

        ↓

Adicionar critérios de conclusão

        ↓

Aplicar labels

        ↓

Definir responsável

        ↓

Associar a um milestone

        ↓

Adicionar ao GitHub Project

        ↓

Criar uma branch

        ↓

Desenvolver a tarefa

        ↓

Abrir um Pull Request

        ↓

Revisar e integrar

        ↓

Encerrar a Issue
```

Durante a prática, continuaremos utilizando o projeto:

```text
portal_da_turma
```

## 2. Objetivos da aula

Nesta aula, eu vou ensinar você a:

1. Entender o papel do GitHub Issues.

2. Diferenciar Issue, Pull Request e Discussion.

3. Criar uma Issue com título específico.

4. Escrever uma descrição compreensível.

5. Definir critérios de conclusão.

6. Criar listas de tarefas.

7. Dividir uma tarefa grande em partes menores.

8. Atribuir responsáveis.

9. Criar e aplicar labels.

10. Utilizar labels para tipo, prioridade e área.

11. Criar milestones.

12. Associar Issues e Pull Requests a uma entrega.

13. Acompanhar o progresso de um milestone.

14. Criar um GitHub Project.

15. Utilizar visualização em tabela.

16. Utilizar visualização em quadro.

17. Criar campos personalizados.

18. Organizar tarefas por status e prioridade.

19. Relacionar Issues com branches e Pull Requests.

20. Encerrar uma Issue automaticamente por meio do Pull Request.

21. Criar templates de Issues.

22. Criar template de Pull Request.

23. Criar um arquivo `CONTRIBUTING.md`.

24. Compreender a função do `CODE_OF_CONDUCT.md`.

25. Atualizar o README com orientações de colaboração.

26. Realizar triagem de tarefas.

27. Organizar um ciclo de trabalho colaborativo.

## 3. Resultados esperados

Ao final da aula, você deverá conseguir organizar uma entrega do projeto com:

```text
Issues bem descritas

Labels padronizadas

Responsáveis definidos

Milestone da versão

GitHub Project atualizado

Branches relacionadas às tarefas

Pull Requests vinculados

Documentação para colaboradores
```

Também deverá compreender a diferença entre:

```text
Issue

Registra, discute e acompanha um trabalho.
```

```text
Pull Request

Propõe e revisa alterações em arquivos.
```

```text
Project

Organiza e acompanha diversos itens de trabalho.
```

```text
Milestone

Agrupa Issues e Pull Requests relacionados a uma entrega.
```

## 4. Conhecimentos necessários

Para acompanhar esta aula, você deverá conhecer:

1. Repositório local e remoto.

2. Commits.

3. Branches.

4. Pull Requests.

5. Merge.

6. Revisão de código.

7. Markdown básico.

8. `git status`.

9. `git switch`.

10. `git pull`.

11. `git add`.

12. `git commit`.

13. `git push`.

## 5. Recursos necessários

1. Computador conectado à internet.

2. Conta no GitHub.

3. Repositório `portal_da_turma`.

4. Permissão para criar Issues.

5. Permissão para administrar labels e milestones, conforme a função do aluno.

6. Visual Studio Code.

7. Git instalado.

8. Equipes de três a cinco alunos.

## 6. Organização das quatro horas

### Primeiro momento: 30 minutos

Revisão do fluxo colaborativo e apresentação do GitHub Issues.

### Segundo momento: 35 minutos

Criação de Issues, listas de tarefas, responsáveis e labels.

### Terceiro momento: 30 minutos

Criação de milestones e planejamento de uma versão.

### Quarto momento: 35 minutos

Criação e configuração de um GitHub Project.

### Intervalo: 15 minutos

### Quinto momento: 35 minutos

Relacionamento entre Issue, branch, commit e Pull Request.

### Sexto momento: 30 minutos

Criação de templates e arquivos de contribuição.

### Sétimo momento: 25 minutos

Atividade colaborativa de planejamento e triagem.

### Oitavo momento: 20 minutos

Exercícios, desafios, avaliação e encerramento.

# Parte 1: Por que organizar o trabalho?

## 7. O problema de trabalhar apenas por mensagens

Imagine uma equipe que organiza o projeto somente por mensagens de chat.

Uma conversa poderá conter:

```text
Precisamos criar a página de contato.

Também falta corrigir o menu.

Alguém precisa atualizar o README.

A lista de alunos ainda não está pronta.

Quem ficou responsável pelos estilos?
```

Depois de alguns dias, a equipe poderá não saber:

1. Qual tarefa ainda está pendente.

2. Quem ficou responsável.

3. Qual foi a decisão final.

4. Qual branch pertence à tarefa.

5. Se a alteração já foi revisada.

6. Se o trabalho faz parte da próxima entrega.

7. Se existe alguma dependência.

## 8. Registro permanente

No GitHub, eu transformo essas necessidades em itens acompanháveis.

Exemplo:

```text
Issue 12

Criar a página de contato
```

A Issue pode registrar:

1. Objetivo.

2. Contexto.

3. Critérios de conclusão.

4. Responsável.

5. Labels.

6. Milestone.

7. Projeto.

8. Discussões.

9. Links para commits.

10. Pull Request relacionado.

## 9. Organização não é burocracia vazia

Eu não crio uma Issue apenas para aumentar a quantidade de itens.

A organização deve ajudar a equipe a:

1. Tomar decisões.

2. Dividir responsabilidades.

3. Reduzir dúvidas.

4. Acompanhar progresso.

5. Evitar trabalho duplicado.

6. Registrar o que foi combinado.

7. Manter o foco da entrega.

# Parte 2: O que é uma Issue?

## 10. Conceito

Uma Issue é um item utilizado para registrar, discutir e acompanhar um trabalho.

Ela pode representar:

1. Uma funcionalidade.

2. Uma correção.

3. Uma melhoria.

4. Uma tarefa de documentação.

5. Uma dúvida técnica que precisa de decisão.

6. Uma atividade de pesquisa.

7. Uma proposta de alteração.

8. Um problema identificado por um usuário.

## 11. Exemplos de Issues

```text
Criar a página de contato
```

```text
Corrigir o link da página de projetos
```

```text
Atualizar as instruções de execução
```

```text
Melhorar a visualização em celulares
```

```text
Adicionar informações sobre o curso
```

## 12. Issue não é necessariamente um erro

A palavra Issue pode ser traduzida como questão, item ou ocorrência.

Por isso, uma Issue não representa apenas um defeito.

Ela pode acompanhar qualquer trabalho que a equipe precise planejar ou discutir.

# Parte 3: Issue, Pull Request e Discussion

## 13. Issue

Eu utilizo uma Issue quando preciso acompanhar um trabalho.

Exemplo:

```text
Criar uma página de projetos com três cartões.
```

## 14. Pull Request

Eu utilizo um Pull Request quando uma branch contém alterações que deverão ser revisadas e integradas.

Exemplo:

```text
A branch feature/pagina_projetos implementa a Issue 8.
```

## 15. Discussion

Eu utilizo uma Discussion quando o objetivo principal é manter uma conversa aberta, fazer perguntas, compartilhar ideias ou publicar um comunicado.

Exemplo:

```text
Qual tema visual devemos utilizar na próxima versão do portal?
```

## 16. Escolha prática

```text
Existe uma tarefa concreta que precisa ser concluída?

Issue
```

```text
Existem arquivos alterados que precisam ser revisados?

Pull Request
```

```text
Existe uma conversa ampla sem uma entrega definida?

Discussion
```

# Parte 4: Criando uma Issue

## 17. Acessando a área

Na página do repositório, acesso:

```text
Issues
```

Depois, seleciono a opção para criar uma nova Issue.

A apresentação da interface poderá variar com atualizações da plataforma e com as configurações do repositório.

## 18. Título da Issue

O título deve explicar o resultado esperado.

Exemplo adequado:

```text
Criar a página de contato
```

Exemplos inadequados:

```text
Página
```

```text
Nova tarefa
```

```text
Fazer contato
```

```text
Trabalho
```

## 19. Regra simples para títulos

Eu procuro utilizar:

```text
Verbo mais objeto da ação
```

Exemplos:

```text
Criar a página de projetos
```

```text
Corrigir o link do menu principal
```

```text
Atualizar a documentação de instalação
```

```text
Melhorar a responsividade da página inicial
```

# Parte 5: Escrevendo uma descrição completa

## 20. Estrutura recomendada

Uma boa Issue deverá responder:

1. Qual é o objetivo?

2. Por que essa tarefa é necessária?

3. O que deverá ser feito?

4. Como saberemos que a tarefa terminou?

5. Existem limitações ou decisões importantes?

## 21. Exemplo completo

```md
## Objetivo

Criar uma página de contato para apresentar os canais oficiais da turma.

## Contexto

O portal ainda não possui uma área que informe como visitantes podem entrar em contato com a equipe.

## Requisitos

1. Criar o arquivo contato.html.
2. Adicionar o link Contato ao menu principal.
3. Criar campos de nome, email e mensagem.
4. Não realizar envio real dos dados nesta versão.
5. Reutilizar o estilo visual das outras páginas.

## Critérios de conclusão

1. A página abre sem erro.
2. O link do menu funciona.
3. Os campos possuem rótulos.
4. O formulário funciona visualmente em telas menores.
5. O README informa que o formulário é demonstrativo.

## Observações

Não incluir senhas, tokens ou serviços externos nesta tarefa.
```

## 22. Contexto

A seção de contexto explica por que a tarefa existe.

Sem contexto, um aluno poderá executar tecnicamente a tarefa, mas tomar decisões diferentes do esperado.

## 23. Requisitos

Os requisitos informam o que deverá ser implementado.

Eles ajudam a limitar o trabalho.

## 24. Critérios de conclusão

Os critérios de conclusão informam como a equipe verificará que a tarefa terminou.

Eu evito critérios vagos como:

```text
Ficar bonito.
```

Prefiro critérios verificáveis:

```text
O menu deve funcionar em todas as páginas.
```

```text
A página deve permanecer legível em largura de 375 pixels.
```

```text
O README deve conter instruções de execução.
```

# Parte 6: Listas de tarefas

## 25. Sintaxe

Em Markdown, uma lista de tarefas pode ser escrita assim:

```md
1. [ ] Criar o arquivo contato.html.
2. [ ] Adicionar o link ao menu.
3. [ ] Criar os campos do formulário.
4. [ ] Adicionar estilos.
5. [ ] Testar a página.
```

## 26. Marcando uma tarefa concluída

```md
1. [x] Criar o arquivo contato.html.
2. [ ] Adicionar o link ao menu.
```

## 27. Quando utilizar

Eu utilizo uma lista de tarefas quando a Issue possui etapas pequenas que pertencem ao mesmo objetivo.

## 28. Quando criar Issues separadas

Se uma etapa:

1. Precisa de outro responsável.

2. Possui discussão própria.

3. Tem prazo diferente.

4. Pode ser concluída independentemente.

5. Precisa de acompanhamento detalhado.

ela poderá se tornar uma Issue separada ou uma subissue, conforme os recursos disponíveis no repositório.

# Parte 7: Dividindo tarefas grandes

## 29. Exemplo de tarefa ampla

```text
Melhorar o portal
```

Esse título é amplo demais.

Ele poderá esconder diversos trabalhos:

1. Corrigir o menu.

2. Criar página de contato.

3. Melhorar responsividade.

4. Atualizar README.

5. Adicionar área de projetos.

## 30. Divisão recomendada

```text
Issue 15

Corrigir a navegação do menu
```

```text
Issue 16

Criar a página de contato
```

```text
Issue 17

Melhorar a responsividade da página inicial
```

```text
Issue 18

Atualizar a documentação da versão
```

## 31. Benefício

Com tarefas menores, eu consigo:

1. Distribuir responsáveis.

2. Estimar melhor o trabalho.

3. Revisar separadamente.

4. Criar branches específicas.

5. Encerrar itens concluídos.

# Parte 8: Responsáveis

## 32. O que é um assignee?

Assignee é a pessoa atribuída a uma Issue ou Pull Request.

O responsável indica quem está conduzindo o trabalho.

## 33. Responsabilidade não significa trabalhar sozinho

Uma Issue pode ter colaboração de outras pessoas.

O responsável principal deverá:

1. Acompanhar a tarefa.

2. Comunicar impedimentos.

3. Atualizar o status.

4. Criar ou acompanhar a branch.

5. Solicitar revisão.

6. Confirmar os critérios de conclusão.

## 34. Atribuindo uma pessoa

Na lateral da Issue, localizo a área de responsáveis e seleciono o integrante.

A opção disponível dependerá das permissões do repositório e da relação do usuário com o projeto.

## 35. Evitando tarefas sem responsável

Uma Issue sem responsável pode permanecer aberta sem que ninguém saiba quem deverá agir.

Durante a triagem, eu verifico:

```text
Toda tarefa pronta para começar possui responsável?
```

# Parte 9: Labels

## 36. O que são labels?

Labels são rótulos utilizados para categorizar Issues, Pull Requests e, conforme os recursos disponíveis, outras conversas do repositório.

Elas facilitam filtros e identificação visual.

## 37. Categorias de labels

Eu posso organizar labels por três dimensões:

1. Tipo.

2. Prioridade.

3. Área.

## 38. Labels de tipo

```text
feature
```

Nova funcionalidade.

```text
bug
```

Problema ou comportamento incorreto.

```text
documentation
```

Documentação.

```text
improvement
```

Melhoria de algo existente.

```text
question
```

Dúvida que precisa de resposta.

## 39. Labels de prioridade

```text
priority: high
```

Trabalho urgente ou bloqueador.

```text
priority: medium
```

Trabalho importante para o ciclo atual.

```text
priority: low
```

Trabalho que pode esperar.

## 40. Labels de área

```text
area: html
```

```text
area: css
```

```text
area: documentation
```

```text
area: accessibility
```

```text
area: github
```

## 41. Labels de fluxo

Algumas equipes também utilizam:

```text
needs review
```

```text
blocked
```

```text
ready
```

```text
good first issue
```

## 42. Não criar labels demais

Uma lista muito extensa pode dificultar a escolha.

Eu crio labels que tenham uso real no fluxo da equipe.

## 43. Padrão sugerido para o curso

```text
Tipo

feature
bug
documentation
improvement
```

```text
Prioridade

priority: high
priority: medium
priority: low
```

```text
Área

area: html
area: css
area: github
area: documentation
```

```text
Situação especial

blocked
good first issue
```

# Parte 10: Criando e editando labels

## 44. Acessando labels

Na área de Issues, acesso o gerenciamento de labels.

Dependendo das permissões, posso:

1. Criar.

2. Editar.

3. Excluir.

4. Alterar cor.

5. Alterar descrição.

## 45. Exemplo

```text
Nome

priority: high
```

```text
Descrição

Tarefa urgente ou que impede outras atividades.
```

## 46. A descrição é importante

A descrição reduz interpretações diferentes.

Exemplo inadequado:

```text
Nome: importante

Descrição: importante
```

Exemplo melhor:

```text
Nome: priority: high

Descrição: Deve ser concluída antes das demais tarefas da entrega.
```

# Parte 11: Milestones

## 47. O que é um milestone?

Milestone é um marco utilizado para acompanhar um grupo de Issues e Pull Requests relacionados a uma entrega ou objetivo.

Exemplos:

```text
Versão 1.0
```

```text
Entrega do módulo de contato
```

```text
Apresentação final da turma
```

```text
Correções de agosto
```

## 48. O que um milestone pode conter?

1. Título.

2. Descrição.

3. Data de conclusão.

4. Issues associadas.

5. Pull Requests associados.

6. Progresso da entrega.

## 49. Exemplo da aula

```text
Título

Portal da Turma 1.0
```

```text
Descrição

Primeira versão pública do Portal da Turma, com páginas principais, documentação e revisão do layout.
```

```text
Data

Data definida pelo professor para a apresentação.
```

## 50. Issues do milestone

```text
Criar a página de contato

Criar a página de projetos

Corrigir a navegação

Melhorar a responsividade

Atualizar o README
```

## 51. Milestone não substitui Project

O milestone agrupa itens relacionados a uma entrega.

O Project oferece visualizações e campos para acompanhar o fluxo de trabalho.

# Parte 12: Planejando uma versão

## 52. Lista inicial

Para a versão 1.0, a equipe identifica:

```text
Funcionalidades obrigatórias

Correções obrigatórias

Documentação obrigatória

Melhorias opcionais
```

## 53. Priorização

Exemplo:

```text
Prioridade alta

Corrigir links quebrados
Criar página de contato
Atualizar instruções de execução
```

```text
Prioridade média

Melhorar responsividade
Adicionar cartões de projetos
```

```text
Prioridade baixa

Adicionar animações visuais
Criar uma segunda opção de tema
```

## 54. Escopo

Eu evito adicionar tarefas indefinidamente ao milestone.

Quando uma tarefa não é necessária para a entrega, posso movê la para um milestone posterior ou mantê la sem marco.

# Parte 13: GitHub Projects

## 55. Conceito

GitHub Projects é uma ferramenta de planejamento e acompanhamento que pode reunir Issues, Pull Requests e itens de planejamento.

Um Project pode ser visualizado e personalizado conforme o processo da equipe.

## 56. Visualizações comuns

### Tabela

Útil para observar muitos campos ao mesmo tempo.

Exemplo:

| Tarefa | Status | Prioridade | Responsável | Milestone |
|---|---|---|---|---|
| Criar contato | Em andamento | Alta | Aluno 1 | Versão 1.0 |
| Atualizar README | Pendente | Média | Aluno 2 | Versão 1.0 |

### Quadro

Útil para visualizar o fluxo por colunas.

Exemplo:

```text
Pendente

Em andamento

Em revisão

Concluído
```

### Roteiro

Útil para acompanhar trabalho em uma linha do tempo, quando datas e planejamento temporal são relevantes.

## 57. Project não impõe uma metodologia

A equipe pode adaptar o Project ao próprio processo.

Para o curso, utilizaremos um quadro simples.

# Parte 14: Criando o Project da turma

## 58. Nome

```text
Portal da Turma: Versão 1.0
```

## 59. Descrição

```text
Planejamento e acompanhamento das tarefas necessárias para publicar a primeira versão do Portal da Turma.
```

## 60. Campos sugeridos

```text
Status
```

Valores:

```text
Pendente

Pronto para iniciar

Em andamento

Em revisão

Concluído
```

```text
Prioridade
```

Valores:

```text
Alta

Média

Baixa
```

```text
Área
```

Valores:

```text
HTML

CSS

Documentação

GitHub
```

```text
Estimativa
```

Valores possíveis:

```text
Pequena

Média

Grande
```

## 61. Não duplicar informações desnecessariamente

Se uma informação já existe em labels, assignees ou milestones, a equipe deverá decidir se também precisa de um campo personalizado.

Duplicação sem finalidade aumenta a manutenção.

# Parte 15: Criando uma visualização em quadro

## 62. Agrupamento

Configuro a visualização para agrupar pelo campo:

```text
Status
```

## 63. Colunas

```text
Pendente
```

Tarefas identificadas, mas ainda não preparadas.

```text
Pronto para iniciar
```

Tarefas com descrição, prioridade e responsável definidos.

```text
Em andamento
```

Trabalho sendo executado em uma branch.

```text
Em revisão
```

Pull Request aberto.

```text
Concluído
```

Pull Request integrado e Issue encerrada.

## 64. Critérios para mover um item

### Pendente para Pronto para iniciar

1. A descrição está completa.

2. Os critérios de conclusão estão definidos.

3. A prioridade foi escolhida.

4. O responsável foi definido.

5. Não existem dependências bloqueadoras.

### Pronto para iniciar para Em andamento

1. A branch foi criada.

2. O responsável iniciou a tarefa.

### Em andamento para Em revisão

1. Os commits foram publicados.

2. O Pull Request foi aberto.

### Em revisão para Concluído

1. O Pull Request foi aprovado.

2. O merge foi realizado.

3. A Issue foi encerrada.

# Parte 16: Adicionando Issues ao Project

## 65. Métodos

Uma Issue pode ser adicionada ao Project durante sua criação ou depois, conforme as opções disponíveis na interface.

## 66. Verificação

Depois de adicionar, eu confirmo:

1. Status.

2. Prioridade.

3. Responsável.

4. Milestone.

5. Área.

## 67. Itens sem Issue

O Project também pode aceitar itens de planejamento que ainda não são Issues, dependendo do recurso utilizado.

Quando o trabalho precisa de discussão, responsável e histórico detalhado, eu converto ou crio uma Issue.

# Parte 17: Triagem

## 68. O que é triagem?

Triagem é o processo de analisar novos itens e decidir como deverão ser organizados.

## 69. Perguntas de triagem

Para cada Issue, eu pergunto:

1. O título está específico?

2. A descrição explica o objetivo?

3. Existe informação suficiente para começar?

4. O item é realmente uma tarefa?

5. Existe duplicação?

6. Qual é o tipo?

7. Qual é a prioridade?

8. Qual é a área?

9. Quem será responsável?

10. Faz parte de qual milestone?

11. Existe alguma dependência?

## 70. Issue duplicada

Se duas Issues representam o mesmo trabalho, eu mantenho uma como principal e encerro ou relaciono a duplicada conforme o processo da equipe.

## 71. Issue sem informações

Eu solicito os dados necessários antes de movê la para Pronto para iniciar.

Exemplo de comentário:

```text
Para que esta tarefa possa ser iniciada, inclua o comportamento esperado, os arquivos envolvidos e os critérios de conclusão.
```

# Parte 18: Relacionando Issue e branch

## 72. Nome da branch

A branch deverá indicar a tarefa.

Exemplo:

```text
Issue 21

Criar a página de contato
```

Branch:

```text
feature/21_pagina_contato
```

Outra convenção possível:

```text
feature/pagina_contato
```

A equipe deverá escolher e manter um padrão.

## 73. Comentário na Issue

Depois de criar a branch, posso registrar:

```text
Branch criada: feature/21_pagina_contato
```

## 74. Commits relacionados

Uma mensagem poderá mencionar a Issue:

```text
Cria estrutura da página de contato para a Issue 21
```

A forma de referência e automação depende do texto utilizado e da plataforma.

# Parte 19: Relacionando Issue e Pull Request

## 75. Descrição do Pull Request

Posso utilizar uma palavra de encerramento seguida do número da Issue.

Exemplo:

```text
Closes #21
```

Quando o Pull Request for integrado na branch padrão, a Issue relacionada poderá ser encerrada automaticamente.

## 76. Outras palavras aceitas

A plataforma reconhece determinadas palavras de encerramento em inglês, como:

```text
Closes

Fixes

Resolves
```

Para o curso, utilizaremos:

```text
Closes #NUMERO
```

## 77. Modelo de Pull Request relacionado

```md
## Objetivo

Implementar a página de contato descrita na Issue 21.

## Alterações

1. Criação de contato.html.
2. Adição do link ao menu.
3. Criação dos estilos do formulário.
4. Atualização do README.

## Como testar

1. Abrir index.html.
2. Selecionar Contato.
3. Verificar os campos.
4. Testar em tela menor.

Closes #21
```

# Parte 20: Atualizando o Project durante o desenvolvimento

## 78. Início da tarefa

Quando o aluno cria a branch:

```text
Status: Em andamento
```

## 79. Pull Request aberto

```text
Status: Em revisão
```

## 80. Correções solicitadas

O item permanece:

```text
Em revisão
```

ou poderá utilizar um campo adicional, conforme o processo da equipe.

## 81. Merge concluído

```text
Status: Concluído
```

## 82. Atualização deve refletir a realidade

Um quadro desatualizado deixa de ajudar.

Cada responsável deverá atualizar o item quando o estado mudar.

# Parte 21: Templates de Issues

## 83. Por que criar templates?

Templates padronizam as informações solicitadas.

Eles ajudam a evitar Issues com descrições como:

```text
Está dando erro.
```

ou:

```text
Criar uma página nova.
```

## 84. Estrutura de arquivos

Uma estrutura comum é:

```text
.github

    ISSUE_TEMPLATE

        funcionalidade.md

        erro.md
```

## 85. Template de funcionalidade

Arquivo:

```text
.github/ISSUE_TEMPLATE/funcionalidade.md
```

Conteúdo:

```md
---
name: Nova funcionalidade
about: Propor uma nova funcionalidade para o projeto
title: "Criar "
labels: feature
assignees: ""
---

## Objetivo

Descreva o resultado esperado.

## Contexto

Explique por que a funcionalidade é necessária.

## Requisitos

1.
2.
3.

## Critérios de conclusão

1. [ ]
2. [ ]
3. [ ]

## Observações

Informe limitações, dependências ou decisões importantes.
```

## 86. Template de erro

Arquivo:

```text
.github/ISSUE_TEMPLATE/erro.md
```

Conteúdo:

```md
---
name: Relatar erro
about: Registrar um comportamento incorreto
title: "Corrigir "
labels: bug
assignees: ""
---

## Descrição do problema

Explique o comportamento observado.

## Resultado esperado

Explique o que deveria acontecer.

## Passos para reproduzir

1.
2.
3.

## Evidências

Inclua mensagens, capturas ou exemplos sem expor informações confidenciais.

## Ambiente

1. Navegador:
2. Sistema operacional:
3. Versão do projeto:

## Critérios de conclusão

1. [ ] O erro não ocorre mais.
2. [ ] A correção foi testada.
3. [ ] Não houve quebra de outras funcionalidades.
```


## 87. Formulários de Issue

O GitHub também oferece formulários estruturados em arquivos de configuração YAML.

Eles permitem campos obrigatórios, menus, caixas de seleção e validação de entrada.

Para uma primeira aula, utilizaremos templates em Markdown.

# Parte 22: Template de Pull Request

## 88. Caminho

```text
.github/PULL_REQUEST_TEMPLATE.md
```

## 89. Conteúdo

```md
## Objetivo

Descreva o resultado principal deste Pull Request.

## Issue relacionada

Closes #NUMERO

## Alterações realizadas

1.
2.
3.

## Como testar

1.
2.
3.

## Checklist

1. [ ] Estou na branch correta.
2. [ ] Revisei os arquivos alterados.
3. [ ] Testei a funcionalidade.
4. [ ] Não adicionei credenciais.
5. [ ] Atualizei a documentação quando necessário.
6. [ ] Os commits possuem mensagens específicas.

## Observações

Informe riscos, limitações ou decisões importantes.
```

## 90. Benefício

O autor recebe uma estrutura pronta e lembra de informar os dados necessários à revisão.

# Parte 23: CONTRIBUTING.md

## 91. Função

O arquivo `CONTRIBUTING.md` explica como uma pessoa deve contribuir com o projeto.

Ele pode informar:

1. Como preparar o ambiente.

2. Como escolher uma Issue.

3. Como criar uma branch.

4. Como escrever commits.

5. Como abrir um Pull Request.

6. Como solicitar revisão.

7. Quais padrões devem ser seguidos.

8. Como comunicar problemas.

## 92. Exemplo

````md
# Como contribuir

## 1. Escolha uma tarefa

Selecione uma Issue que esteja marcada como pronta para iniciar e confirme o responsável.

## 2. Atualize a branch principal

```bash
git switch main

git pull origin main
```

## 3. Crie uma branch

```bash
git switch -c feature/numero_descricao
```

## 4. Desenvolva a tarefa

Realize apenas as alterações relacionadas à Issue.

## 5. Crie commits específicos

```bash
git add .

git commit -m "Descrição da alteração"
```

## 6. Publique a branch

```bash
git push -u origin NOME_DA_BRANCH
```

## 7. Abra um Pull Request

Preencha o template, relacione a Issue e informe como testar.

## 8. Responda à revisão

Corrija os pontos obrigatórios e envie novos commits para a mesma branch.
````

## 93. Local do arquivo

O GitHub reconhece diretrizes de contribuição em locais como:

```text
Raiz do repositório

docs

.github
```

Para o curso, utilizaremos a raiz:

```text
CONTRIBUTING.md
```

# Parte 24: CODE_OF_CONDUCT.md

## 94. Função

Um código de conduta define padrões de comportamento e orienta como a comunidade deverá tratar situações inadequadas.

Ele é especialmente importante em projetos abertos à participação de outras pessoas.

## 95. O que pode abordar

1. Respeito entre participantes.

2. Comunicação profissional.

3. Inclusão.

4. Comportamentos não aceitos.

5. Forma de relatar problemas.

6. Responsabilidade dos mantenedores.

## 96. Projeto de sala de aula

Mesmo em um projeto educacional, eu reforço:

1. Comentários devem ser técnicos e respeitosos.

2. Revisões não devem atacar pessoas.

3. Dúvidas devem ser tratadas com paciência.

4. Erros fazem parte do aprendizado.

5. Informações pessoais não devem ser publicadas sem autorização.

# Parte 25: Atualizando o README

## 97. Seção de contribuição

No README, adiciono:

```md
## Como contribuir

1. Leia o arquivo CONTRIBUTING.md.
2. Escolha uma Issue pronta para iniciar.
3. Confirme o responsável.
4. Crie uma branch específica.
5. Desenvolva a tarefa.
6. Abra um Pull Request.
7. Aguarde a revisão antes do merge.
```

## 98. Seção de planejamento

```md
## Planejamento

As tarefas são organizadas por meio de GitHub Issues e acompanhadas no Project da versão atual.
```

## 99. Seção de segurança

```md
## Segurança

Não publique senhas, tokens, chaves privadas, dados pessoais ou credenciais de serviços externos.
```

# Parte 26: Projeto prático da aula

## 100. Objetivo

Organizar a entrega:

```text
Portal da Turma 1.0
```

## 101. Criar o milestone

```text
Portal da Turma 1.0
```

Descrição:

```text
Primeira versão pública do portal, contendo páginas principais, documentação, navegação revisada e layout responsivo.
```

## 102. Criar labels

```text
feature

bug

documentation

improvement

priority: high

priority: medium

priority: low

area: html

area: css

area: github

blocked
```

## 103. Criar Issues

### Issue 1

```text
Criar a página de contato
```

### Issue 2

```text
Criar a página de projetos
```

### Issue 3

```text
Corrigir os links do menu principal
```

### Issue 4

```text
Melhorar a responsividade da página inicial
```

### Issue 5

```text
Atualizar o README para a versão 1.0
```

## 104. Atribuir responsáveis

Cada Issue deverá possuir um responsável principal.

## 105. Associar ao milestone

Todas as cinco Issues pertencem a:

```text
Portal da Turma 1.0
```

## 106. Criar o Project

Nome:

```text
Portal da Turma: Versão 1.0
```

## 107. Configurar o quadro

```text
Pendente

Pronto para iniciar

Em andamento

Em revisão

Concluído
```

## 108. Adicionar os itens

Cada Issue deverá aparecer no quadro.

## 109. Definir prioridade

Exemplo:

```text
Corrigir links

Alta
```

```text
Criar página de contato

Alta
```

```text
Atualizar README

Média
```

```text
Melhorar responsividade

Média
```

```text
Criar página de projetos

Baixa ou média, conforme a entrega
```

# Parte 27: Executando uma Issue do início ao fim

## 110. Issue escolhida

```text
Criar a página de contato
```

Número de exemplo:

```text
21
```

## 111. Confirmar preparação

A Issue deverá possuir:

1. Descrição.

2. Critérios de conclusão.

3. Label `feature`.

4. Label `priority: high`.

5. Label `area: html`.

6. Responsável.

7. Milestone.

8. Project.

9. Status Pronto para iniciar.

## 112. Atualizar a main

```bash
git switch main

git pull origin main
```

## 113. Criar a branch

```bash
git switch -c feature/21_pagina_contato
```

## 114. Atualizar o Project

```text
Status: Em andamento
```

## 115. Desenvolver

Criar e alterar os arquivos definidos na Issue.

## 116. Criar commits

```bash
git add contato.html index.html

git commit -m "Cria a estrutura da página de contato"
```

Depois:

```bash
git add css/estilo.css README.md

git commit -m "Adiciona estilos e documentação da página de contato"
```

## 117. Publicar

```bash
git push -u origin feature/21_pagina_contato
```

## 118. Abrir Pull Request

Na descrição:

```text
Closes #21
```

## 119. Atualizar o Project

```text
Status: Em revisão
```

## 120. Revisar e integrar

Depois da aprovação e do merge, a Issue será encerrada conforme a relação criada.

## 121. Atualizar o Project

```text
Status: Concluído
```

# Parte 28: Dependências e bloqueios

## 122. Situação

A página de contato depende do menu atualizado.

Se o menu ainda não estiver pronto, a Issue poderá ser marcada:

```text
blocked
```

## 123. Comentário

```text
Esta tarefa depende da conclusão da Issue 19, responsável pela atualização do menu principal.
```

## 124. Evitando trabalho impedido

Antes de atribuir uma tarefa, eu verifico se todas as dependências necessárias estão disponíveis.

# Parte 29: Comunicação nas Issues

## 125. Comentário de início

```text
Iniciei a tarefa na branch feature/21_pagina_contato.
```

## 126. Comentário de impedimento

```text
A tarefa está bloqueada porque o componente de navegação ainda não foi integrado. Aguardo a conclusão da Issue 19.
```

## 127. Comentário de decisão

```text
A equipe decidiu manter o formulário apenas como demonstração visual nesta versão. O envio real será planejado para uma versão posterior.
```

## 128. Comentário de conclusão

```text
Implementação concluída no Pull Request 27. Os critérios foram testados e o item está pronto para revisão.
```

## 129. Evitando comentários vazios

Evito:

```text
Estou fazendo.
```

Prefiro:

```text
Concluí a estrutura HTML e iniciarei os estilos. Ainda falta testar o menu em tela menor.
```

# Parte 30: Erros comuns

## 130. Título genérico

```text
Erro
```

Melhor:

```text
Corrigir o link da página de projetos no menu
```

## 131. Issue sem critérios

Sem critérios, o responsável não sabe exatamente quando terminar.

## 132. Muitas tarefas na mesma Issue

Uma Issue muito ampla dificulta responsável, revisão e encerramento.

## 133. Label sem significado definido

Rótulos como:

```text
importante
```

podem ser interpretados de formas diferentes.

## 134. Toda tarefa marcada como prioridade alta

Se tudo é urgente, a prioridade deixa de orientar.

## 135. Milestone sem escopo

Um milestone com todas as ideias do projeto nunca termina.

## 136. Quadro desatualizado

O Project deve representar a situação real.

## 137. Encerrar Issue antes do merge

Eu encerro quando o resultado foi entregue e aceito, conforme o fluxo definido.

## 138. Branch sem relação com a tarefa

Nomes genéricos dificultam identificar qual Issue está sendo implementada.

## 139. Pull Request sem referência

Sem a relação, o histórico fica fragmentado.

## 140. Template excessivamente longo

Um template deve pedir informações úteis, não transformar cada contribuição em um formulário desnecessariamente complexo.

# Parte 31: Prática guiada completa

## 141. Etapa 1: Criar labels

Criar os rótulos definidos para o curso.

## 142. Etapa 2: Criar milestone

```text
Portal da Turma 1.0
```

## 143. Etapa 3: Criar cinco Issues

Cada uma deverá possuir:

1. Título.

2. Objetivo.

3. Contexto.

4. Requisitos.

5. Critérios de conclusão.

## 144. Etapa 4: Aplicar metadados

1. Labels.

2. Responsável.

3. Milestone.

## 145. Etapa 5: Criar Project

```text
Portal da Turma: Versão 1.0
```

## 146. Etapa 6: Configurar campos

1. Status.

2. Prioridade.

3. Área.

4. Estimativa.

## 147. Etapa 7: Criar quadro

Agrupar por status.

## 148. Etapa 8: Adicionar Issues

Conferir todos os campos.

## 149. Etapa 9: Escolher uma Issue

Mover para Pronto para iniciar.

## 150. Etapa 10: Criar branch

```bash
git switch main

git pull origin main

git switch -c feature/NUMERO_descricao
```

## 151. Etapa 11: Atualizar status

```text
Em andamento
```

## 152. Etapa 12: Desenvolver e publicar

```bash
git add .

git commit -m "Descrição específica"

git push -u origin NOME_DA_BRANCH
```

## 153. Etapa 13: Criar Pull Request

Adicionar:

```text
Closes #NUMERO
```

## 154. Etapa 14: Atualizar status

```text
Em revisão
```

## 155. Etapa 15: Revisar e integrar

Depois do merge, confirmar o encerramento da Issue.

## 156. Etapa 16: Concluir

```text
Status: Concluído
```

# Parte 32: Atividade colaborativa

## 157. Organização da equipe

Cada equipe terá:

1. Responsável pela triagem.

2. Responsável pelo Project.

3. Responsáveis pelas Issues.

4. Revisores.

As funções serão alternadas.

## 158. Fase 1: planejamento

A equipe deverá criar uma entrega com seis Issues.

Tipos obrigatórios:

1. Duas funcionalidades.

2. Uma correção.

3. Uma melhoria.

4. Uma tarefa de documentação.

5. Uma tarefa de organização no GitHub.

## 159. Fase 2: triagem

Cada Issue deverá receber:

1. Tipo.

2. Prioridade.

3. Área.

4. Responsável.

5. Milestone.

6. Status.

## 160. Fase 3: execução

Cada integrante escolhe uma Issue pronta.

## 161. Fase 4: acompanhamento

A equipe deverá atualizar o quadro durante o trabalho.

## 162. Fase 5: apresentação

A equipe deverá explicar:

1. Como definiu prioridades.

2. Como dividiu as tarefas.

3. Como escolheu os responsáveis.

4. Como acompanhou o trabalho.

5. Como relacionou Issues e Pull Requests.

# Parte 33: Exercícios de fixação

## 163. Exercício 1: conceitos

Responda com suas palavras.

1. O que é uma Issue?

2. Uma Issue representa somente um erro?

3. Qual é a diferença entre Issue e Pull Request?

4. Para que servem labels?

5. Qual é a função de um responsável?

6. O que é um milestone?

7. Para que serve um Project?

8. Qual é a diferença entre milestone e Project?

9. Para que servem critérios de conclusão?

10. Por que utilizar templates?

11. Qual é a função do `CONTRIBUTING.md`?

12. O que significa relacionar um Pull Request a uma Issue?

## 164. Exercício 2: relacione os conceitos

### Conceitos

```text
A. Issue

B. Label

C. Assignee

D. Milestone

E. Project

F. Pull Request

G. CONTRIBUTING.md

H. CODE_OF_CONDUCT.md
```

### Definições

```text
1. Define padrões de comportamento da comunidade.

2. Organiza e acompanha vários itens em visualizações e campos.

3. Registra e acompanha uma tarefa, ideia ou problema.

4. Explica como contribuir com o projeto.

5. Identifica a pessoa responsável pelo trabalho.

6. Propõe e revisa alterações em arquivos.

7. Categoriza itens do repositório.

8. Agrupa Issues e Pull Requests relacionados a uma entrega.
```

## 165. Exercício 3: avalie títulos

Classifique como adequado ou inadequado.

```text
Criar a página de contato

Tarefa nova

Corrigir o link do menu principal

Erro

Atualizar as instruções de instalação

Fazer coisas no CSS

Melhorar a responsividade da página inicial

Projeto
```

Reescreva os títulos inadequados.

## 166. Exercício 4: critérios de conclusão

Para a Issue:

```text
Criar a página de projetos
```

escreva cinco critérios de conclusão verificáveis.

## 167. Exercício 5: escolha as labels

### Situação 1

Criar uma nova página urgente em HTML.

Resposta:

```text
Tipo:

Prioridade:

Área:
```

### Situação 2

Corrigir um problema visual de baixa prioridade no CSS.

Resposta:

```text
Tipo:

Prioridade:

Área:
```

### Situação 3

Atualizar o README para a próxima versão.

Resposta:

```text
Tipo:

Prioridade:

Área:
```

## 168. Exercício 6: organize o fluxo

Coloque na ordem correta:

```text
Abrir o Pull Request.

Criar a Issue.

Realizar o merge.

Definir responsável.

Criar a branch.

Aplicar labels.

Desenvolver a tarefa.

Adicionar ao milestone.

Encerrar a Issue.
```

## 169. Exercício 7: analise a Issue

Observe:

```md
# Melhorar o site

Deixar a página melhor.
```

Responda:

1. O título está específico?

2. Existe contexto?

3. Existem requisitos?

4. Existem critérios de conclusão?

5. Como você reescreveria a Issue?

## 170. Exercício 8: Project

Distribua as tarefas nas colunas adequadas.

```text
Issue criada, mas sem responsável.

Branch criada e trabalho iniciado.

Pull Request aberto.

Pull Request integrado.

Issue completa e pronta para começar.
```

Colunas:

```text
Pendente

Pronto para iniciar

Em andamento

Em revisão

Concluído
```

## 171. Exercício 9: template

Crie um template de Issue para:

```text
Solicitação de melhoria de acessibilidade
```

O template deverá pedir:

1. Página afetada.

2. Problema observado.

3. Resultado esperado.

4. Critérios de conclusão.

5. Evidências.

# Parte 34: Desafios

## 172. Desafio 1: backlog do portal

Crie dez Issues para melhorias futuras do Portal da Turma.

Requisitos:

1. Títulos específicos.

2. Descrições completas.

3. Critérios de conclusão.

4. Labels.

5. Prioridade.

## 173. Desafio 2: triagem profissional

Troque o backlog com outra equipe.

A equipe revisora deverá:

1. Identificar títulos vagos.

2. Identificar Issues duplicadas.

3. Sugerir divisão de tarefas grandes.

4. Aplicar ou sugerir labels.

5. Definir itens prontos para iniciar.

## 174. Desafio 3: milestone da versão 1.1

Crie:

```text
Portal da Turma 1.1
```

Associe pelo menos cinco Issues.

Defina:

1. Objetivo.

2. Data.

3. Escopo obrigatório.

4. Melhorias opcionais.

## 175. Desafio 4: Project com duas visualizações

Crie:

1. Uma visualização em tabela.

2. Uma visualização em quadro.

Na tabela, mostre:

1. Título.

2. Status.

3. Prioridade.

4. Responsável.

5. Milestone.

No quadro, agrupe por status.

## 176. Desafio 5: automação de encerramento

Crie uma Issue, uma branch e um Pull Request.

Na descrição do Pull Request, utilize:

```text
Closes #NUMERO
```

Depois do merge, verifique o estado da Issue.

## 177. Desafio 6: templates completos

Crie:

```text
.github/ISSUE_TEMPLATE/funcionalidade.md

.github/ISSUE_TEMPLATE/erro.md

.github/PULL_REQUEST_TEMPLATE.md
```

Teste a criação de uma nova Issue e de um novo Pull Request.

## 178. Desafio 7: guia de contribuição

Crie um `CONTRIBUTING.md` com:

1. Como escolher uma Issue.

2. Como atualizar a `main`.

3. Como criar branch.

4. Padrão de commits.

5. Como publicar.

6. Como abrir Pull Request.

7. Como responder à revisão.

8. Regras de segurança.

## 179. Desafio 8: código de conduta da turma

Crie um `CODE_OF_CONDUCT.md` apropriado ao ambiente educacional.

Inclua:

1. Respeito.

2. Comunicação técnica.

3. Inclusão.

4. Proteção de dados pessoais.

5. Procedimento para relatar problemas.

## 180. Desafio 9: dependências

Crie três Issues em sequência:

```text
Criar estrutura do menu

Adicionar links ao menu

Testar navegação completa
```

Explique a dependência entre elas e marque o trabalho bloqueado quando necessário.

## 181. Desafio 10: ciclo completo

Execute uma tarefa do início ao fim:

1. Issue.

2. Labels.

3. Responsável.

4. Milestone.

5. Project.

6. Branch.

7. Commits.

8. Pull Request.

9. Revisão.

10. Merge.

11. Issue encerrada.

12. Project concluído.

# Parte 35: Avaliação

## 182. Critérios

A atividade poderá valer 10 pontos.

### Issue: 2 pontos

Título, contexto, requisitos e critérios de conclusão.

### Labels: 1 ponto

Classificação adequada.

### Responsável: 1 ponto

Responsabilidade definida.

### Milestone: 1 ponto

Item associado à entrega correta.

### Project: 2 pontos

Campos e status atualizados.

### Relação com desenvolvimento: 2 pontos

Branch e Pull Request relacionados à Issue.

### Documentação: 1 ponto

Template ou diretriz de contribuição criado corretamente.

## 183. Evidências

O aluno deverá apresentar:

1. Issue criada.

2. Labels.

3. Responsável.

4. Milestone.

5. Project.

6. Branch.

7. Pull Request.

8. Relação de encerramento.

9. Arquivo de documentação.

# Parte 36: Gabarito

## 184. Gabarito do exercício 1

### Questão 1

Issue é um item utilizado para registrar, discutir e acompanhar um trabalho.

### Questão 2

Não. Ela pode representar funcionalidade, melhoria, documentação, ideia ou outro trabalho.

### Questão 3

Issue acompanha o trabalho. Pull Request propõe e revisa alterações em arquivos.

### Questão 4

Labels categorizam e facilitam filtros e identificação.

### Questão 5

Indicar quem conduz e acompanha a tarefa.

### Questão 6

Milestone agrupa Issues e Pull Requests relacionados a uma entrega.

### Questão 7

Project organiza e acompanha itens por visualizações, campos e status.

### Questão 8

Milestone representa uma entrega. Project acompanha o fluxo de vários itens.

### Questão 9

Definem como verificar que a tarefa terminou.

### Questão 10

Padronizar as informações necessárias.

### Questão 11

Explicar como contribuir com o projeto.

### Questão 12

Criar uma ligação entre a implementação e o item de trabalho.

## 185. Gabarito do exercício 2

```text
A corresponde a 3.

B corresponde a 7.

C corresponde a 5.

D corresponde a 8.

E corresponde a 2.

F corresponde a 6.

G corresponde a 4.

H corresponde a 1.
```

## 186. Gabarito do exercício 3

### Adequados

```text
Criar a página de contato

Corrigir o link do menu principal

Atualizar as instruções de instalação

Melhorar a responsividade da página inicial
```

### Inadequados

```text
Tarefa nova

Erro

Fazer coisas no CSS

Projeto
```

As reescritas deverão informar uma ação e um objeto específicos.

## 187. Gabarito do exercício 5

### Situação 1

```text
Tipo: feature

Prioridade: priority: high

Área: area: html
```

### Situação 2

```text
Tipo: bug

Prioridade: priority: low

Área: area: css
```

### Situação 3

```text
Tipo: documentation

Prioridade: priority: medium

Área: area: documentation
```

## 188. Gabarito do exercício 6

Ordem:

```text
Criar a Issue.

Aplicar labels.

Definir responsável.

Adicionar ao milestone.

Criar a branch.

Desenvolver a tarefa.

Abrir o Pull Request.

Realizar o merge.

Encerrar a Issue.
```

## 189. Gabarito do exercício 8

```text
Issue criada, mas sem responsável.

Pendente
```

```text
Issue completa e pronta para começar.

Pronto para iniciar
```

```text
Branch criada e trabalho iniciado.

Em andamento
```

```text
Pull Request aberto.

Em revisão
```

```text
Pull Request integrado.

Concluído
```

# Parte 37: Revisão oral

## 190. Perguntas

1. O que é uma Issue?

2. Qual é a diferença entre Issue e Pull Request?

3. Para que servem labels?

4. Quem é o assignee?

5. O que é milestone?

6. O que é GitHub Project?

7. Como uma tarefa entra em Em andamento?

8. Quando uma tarefa entra em Em revisão?

9. Para que servem critérios de conclusão?

10. Como relacionamos Pull Request e Issue?

11. Para que serve `CONTRIBUTING.md`?

12. Para que serve um template?

# Parte 38: Resumo dos arquivos

## 191. Template de funcionalidade

```text
.github/ISSUE_TEMPLATE/funcionalidade.md
```

## 192. Template de erro

```text
.github/ISSUE_TEMPLATE/erro.md
```

## 193. Template de Pull Request

```text
.github/PULL_REQUEST_TEMPLATE.md
```

## 194. Diretrizes de contribuição

```text
CONTRIBUTING.md
```

## 195. Código de conduta

```text
CODE_OF_CONDUCT.md
```

## 196. Apresentação do projeto

```text
README.md
```

# Parte 39: Fluxo completo da aula

## 197. Planejamento

```text
Criar Issue

Definir critérios

Aplicar labels

Definir responsável

Associar milestone

Adicionar ao Project
```

## 198. Desenvolvimento

```bash
git switch main

git pull origin main

git switch -c feature/NUMERO_descricao
```

Depois:

```bash
git add .

git commit -m "Descrição específica"

git push -u origin NOME_DA_BRANCH
```

## 199. Revisão

```text
Abrir Pull Request

Relacionar Issue

Atualizar Project

Solicitar revisão
```

## 200. Conclusão

```text
Aprovar

Realizar merge

Encerrar Issue

Mover para Concluído

Atualizar milestone
```

# Parte 40: Encerramento

## 201. O que aprendemos

Nesta aula, eu mostrei que um repositório profissional não contém apenas arquivos e commits.

Ele também registra o planejamento, as responsabilidades e as decisões da equipe.

Aprendemos que:

```text
Issues acompanham o trabalho.

Labels classificam.

Responsáveis definem quem conduz.

Milestones agrupam entregas.

Projects mostram o fluxo.

Templates padronizam informações.

CONTRIBUTING.md orienta colaboradores.
```

## 202. Preparação para a próxima aula

Na próxima aula, vamos transformar o trabalho concluído em uma versão oficial.

Aprenderemos:

1. Tags.

2. Tags leves e anotadas.

3. Versionamento semântico.

4. CHANGELOG.

5. Release notes.

6. Releases no GitHub.

7. Versões de teste.

## 203. Frase de encerramento

Uma equipe não se organiza apenas distribuindo tarefas.

Ela se organiza quando todos conseguem compreender o que precisa ser feito, quem está responsável, qual é a prioridade e o que significa concluir.

Quando Issues, Projects e documentação são utilizados com propósito, o GitHub deixa de ser apenas um local para armazenar código e passa a representar o processo completo de desenvolvimento.

# Referências

1. Documentação oficial do GitHub sobre Issues  
   https://docs.github.com/pt/issues/tracking-your-work-with-issues/learning-about-issues/about-issues

2. Início rápido para GitHub Issues  
   https://docs.github.com/pt/issues/tracking-your-work-with-issues/learning-about-issues/quickstart

3. Documentação sobre labels e milestones  
   https://docs.github.com/pt/issues/using-labels-and-milestones-to-track-work

4. Documentação oficial sobre Projects  
   https://docs.github.com/pt/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects

5. Guia de início rápido para Projects  
   https://docs.github.com/pt/issues/planning-and-tracking-with-projects/learning-about-projects/quickstart-for-projects

6. Diretrizes para contribuidores  
   https://docs.github.com/pt/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors

7. Configuração de contribuições saudáveis  
   https://docs.github.com/pt/communities/setting-up-your-project-for-healthy-contributions

8. Documentação sobre templates de Issues e Pull Requests  
   https://docs.github.com/pt/communities/using-templates-to-encourage-useful-issues-and-pull-requests

9. Documentação geral do GitHub  
   https://docs.github.com/pt
