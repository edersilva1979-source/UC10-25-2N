# Aula 4: Merge, Pull Request e Revisão de Código

## Git e GitHub na Prática

### Carga horária

4 horas

### Tema da aula

Integração de branches, criação e revisão de Pull Requests, aprovação de alterações e conclusão segura de funcionalidades no GitHub.

## 1. Apresentação da aula

Nas aulas anteriores, eu ensinei você a criar repositórios, registrar commits, sincronizar projetos e desenvolver funcionalidades em branches separadas.

Na Aula 3, cada integrante da equipe trabalhou em uma branch própria.

Exemplos:

```text
feature/pagina_sobre

feature/lista_alunos

feature/pagina_projetos

feature/pagina_contato

docs/atualiza_readme
```

Essas branches foram publicadas no GitHub, mas ainda não foram integradas à branch principal.

Nesta aula, vamos aprender como levar uma funcionalidade concluída para a `main`.

Primeiro, eu mostrarei o merge local.

Depois, utilizaremos o fluxo mais adequado para o trabalho colaborativo no GitHub:

```text
Criar uma branch

Desenvolver a tarefa

Criar commits

Publicar a branch

Abrir um Pull Request

Revisar as alterações

Solicitar correções quando necessário

Aprovar o trabalho

Realizar o merge

Atualizar o projeto local

Excluir a branch concluída
```

O objetivo não é apenas aprender a clicar no botão de merge.

Eu quero que você entenda:

1. Qual branch recebe as alterações.

2. Qual branch fornece as alterações.

3. O que um Pull Request realmente propõe.

4. Como analisar arquivos e commits antes da integração.

5. Como comunicar uma correção ao autor.

6. Como proteger a `main` de mudanças não revisadas.

## 2. Objetivos da aula

Nesta aula, eu vou ensinar você a:

1. Entender o conceito de merge.

2. Identificar a branch de destino.

3. Identificar a branch de origem.

4. Realizar um merge local.

5. Verificar o histórico depois de uma integração.

6. Cancelar um merge quando necessário.

7. Entender o que é um Pull Request.

8. Identificar a base branch.

9. Identificar a compare branch.

10. Criar um Pull Request.

11. Escrever um título objetivo.

12. Criar uma descrição completa.

13. Utilizar Pull Request em modo rascunho.

14. Analisar commits e arquivos modificados.

15. Escrever comentários de revisão.

16. Solicitar alterações.

17. Aprovar um Pull Request.

18. Compreender os principais métodos de merge do GitHub.

19. Realizar o merge de um Pull Request.

20. Excluir uma branch concluída.

21. Atualizar o repositório local depois do merge.

22. Compreender o GitHub Flow.

23. Proteger a branch principal.

24. Trabalhar com responsabilidade em uma revisão colaborativa.

## 3. Resultados esperados

Ao final da aula, você deverá conseguir executar este processo:

```text
Branch de funcionalidade concluída

        ↓

Publicação no GitHub

        ↓

Criação do Pull Request

        ↓

Revisão dos commits

        ↓

Revisão dos arquivos

        ↓

Comentários e correções

        ↓

Aprovação

        ↓

Merge na main

        ↓

Atualização local

        ↓

Exclusão da branch concluída
```

Os principais comandos utilizados serão:

```bash
git status

git branch

git checkout main

git pull origin main

git merge feature/pagina_sobre

git log --oneline --all --graph --decorate

git push origin main

git merge --abort

git fetch origin

git branch -d feature/pagina_sobre

git push origin --delete feature/pagina_sobre
```

## 4. Conhecimentos necessários

Para acompanhar esta aula, você deverá conhecer:

1. Repositório local.

2. Repositório remoto.

3. Branch `main`.

4. Branch de funcionalidade.

5. Commits.

6. `git status`.

7. `git add`.

8. `git commit`.

9. `git push`.

10. `git pull`.

11. `git fetch`.

12. `git branch`.

13. `git switch`.

14. `git diff`.

15. Publicação de branches.

## 5. Recursos necessários

1. Computador conectado à internet.

2. Git instalado.

3. Visual Studio Code.

4. Conta no GitHub.

5. Repositório `portal_da_turma`.

6. Branch `main` publicada.

7. Pelo menos uma branch de funcionalidade publicada.

8. Pelo menos dois alunos por equipe.

9. Permissão para criar e revisar Pull Requests no repositório.

## 6. Organização das quatro horas

### Primeiro momento: 25 minutos

Revisão das branches criadas na Aula 3.

### Segundo momento: 35 minutos

Explicação sobre merge, branch de origem e branch de destino.

### Terceiro momento: 35 minutos

Prática guiada de merge local.

### Quarto momento: 30 minutos

Introdução ao Pull Request e ao GitHub Flow.

### Intervalo: 15 minutos

### Quinto momento: 45 minutos

Criação de Pull Request no projeto da turma.

### Sexto momento: 35 minutos

Revisão, comentários, solicitação de mudanças e aprovação.

### Sétimo momento: 20 minutos

Merge pelo GitHub, exclusão da branch e atualização local.

### Oitavo momento: 15 minutos

Exercícios, desafios e encerramento.

# Parte 1: Revisão das branches

## 7. Situação atual do projeto

Ao final da Aula 3, poderemos ter um histórico semelhante a este:

```text
main

feature/pagina_sobre

feature/lista_alunos

feature/pagina_projetos

docs/atualiza_readme
```

Cada branch possui commits diferentes.

Exemplo:

```text
main

A → B → C
```

```text
feature/pagina_sobre

A → B → C → D → E
```

```text
feature/lista_alunos

A → B → C → F → G
```

A `main` ainda aponta para o commit C.

A página sobre foi desenvolvida nos commits D e E.

A lista de alunos foi desenvolvida nos commits F e G.

## 8. Verificando as branches locais

Dentro do projeto, executo:

```bash
git branch
```

Um resultado possível será:

```text
  feature/lista_alunos
* feature/pagina_sobre
  main
```

O asterisco indica a branch atual.

## 9. Verificando todas as branches

Primeiro, atualizo as referências remotas:

```bash
git fetch origin
```

Depois:

```bash
git branch -a
```

Resultado possível:

```text
  feature/lista_alunos
* feature/pagina_sobre
  main
  remotes/origin/feature/lista_alunos
  remotes/origin/feature/pagina_sobre
  remotes/origin/main
```

## 10. Verificando o histórico

```bash
git log --oneline --all --graph --decorate
```

Um exemplo seria:

```text
* 4e82a31 (HEAD -> feature/pagina_sobre) Adiciona estilos da página sobre
* 8c45d20 Cria a página sobre a turma
| * 51f01c2 (origin/feature/lista_alunos) Adiciona estilos da lista de alunos
| * a20d314 Cria a página de alunos
|/
* b10fc18 (origin/main, main) Atualiza a página inicial
```

Esse gráfico mostra que duas funcionalidades foram desenvolvidas separadamente.

# Parte 2: O que é merge?

## 11. Conceito de merge

Merge significa integrar linhas de desenvolvimento.

Quando eu realizo um merge, peço ao Git que incorpore as alterações de uma branch em outra.

Exemplo:

```text
main

A → B → C
```

```text
feature/pagina_sobre

A → B → C → D → E
```

Depois da integração:

```text
main

A → B → C → D → E
```

A funcionalidade criada na branch passa a fazer parte da `main`.

## 12. A pergunta mais importante

Antes de executar um merge, eu faço duas perguntas:

1. Qual branch receberá as alterações?

2. Qual branch fornecerá as alterações?

No nosso exemplo:

```text
Branch de destino

main
```

```text
Branch de origem

feature/pagina_sobre
```

A `main` receberá a página sobre.

## 13. Regra prática

Eu entro primeiro na branch que deverá receber as alterações.

Depois, executo `git merge` informando a branch que fornecerá as alterações.

```bash
git checkout main

git merge feature/pagina_sobre
```

Eu posso ler esses comandos assim:

```text
Entre na main.

Traga para a main as alterações da feature/pagina_sobre.
```

## 14. Erro de raciocínio comum

Observe:

```bash
git checkout feature/pagina_sobre

git merge main
```

Nesse caso, estou levando a `main` para a branch de funcionalidade.

Não estou integrando a funcionalidade na `main`.

Esse fluxo pode ser útil em outra situação, mas não realiza o objetivo atual.

Por isso, eu sempre confirmo a branch de destino antes do merge.

## 15. Branch de destino

A branch de destino é aquela que receberá os commits e alterações.

No fluxo do curso:

```text
main
```

## 16. Branch de origem

A branch de origem é aquela que contém o trabalho que será integrado.

Exemplo:

```text
feature/pagina_sobre
```

# Parte 3: Preparação antes do merge

## 17. Verificar alterações pendentes

Antes de trocar de branch ou realizar um merge, executo:

```bash
git status
```

O resultado esperado será:

```text
nothing to commit, working tree clean
```

Eu evito começar uma integração com arquivos ainda não registrados.

## 18. Publicar os commits da funcionalidade

Na branch de funcionalidade:

```bash
git checkout feature/pagina_sobre
```

Verifico:

```bash
git status
```

Depois:

```bash
git push
```

Assim, confirmo que a branch publicada possui os commits mais recentes.

## 19. Atualizar a main

Agora entro na `main`:

```bash
git checkout main
```

Depois, atualizo:

```bash
git pull origin main
```

Eu não integro uma funcionalidade em uma `main` desatualizada.

## 20. Comparar antes de integrar

Posso verificar os arquivos que serão alterados:

```bash
git diff --name-only main..feature/pagina_sobre
```

Resultado possível:

```text
css/estilo.css

index.html

sobre.html
```

Também posso verificar os commits exclusivos:

```bash
git log main..feature/pagina_sobre --oneline
```

Resultado:

```text
4e82a31 Adiciona estilos da página sobre

8c45d20 Cria a página sobre a turma
```

## 21. Checklist antes do merge

Antes de continuar, eu verifico:

1. Estou na `main`.

2. A `main` está atualizada.

3. A área de trabalho está limpa.

4. A branch de funcionalidade foi publicada.

5. Os commits possuem mensagens adequadas.

6. Os arquivos modificados correspondem à tarefa.

7. O projeto foi testado.

# Parte 4: Merge local

## 22. Executando o merge

Estando na `main`, executo:

```bash
git merge feature/pagina_sobre
```

Um resultado possível será:

```text
Updating b10fc18..4e82a31

Fast forward

css/estilo.css | 20 ++++++++++++++++++++

index.html     |  2 ++

sobre.html     | 45 +++++++++++++++++++++++++++++++++++++++++++++

3 files changed
```

## 23. O que significa fast forward?

Quando a `main` não recebeu novos commits depois da criação da branch, o Git poderá apenas avançar o ponteiro da `main`.

Antes:

```text
A → B → C
          ↑
          main
           \
            D → E
                ↑
                feature/pagina_sobre
```

Depois:

```text
A → B → C → D → E
                  ↑
                  main
                  feature/pagina_sobre
```

Nesse caso, não é necessário criar um commit extra de merge.

## 24. Verificando o histórico

```bash
git log --oneline --all --graph --decorate
```

Resultado possível:

```text
* 4e82a31 (HEAD -> main, feature/pagina_sobre) Adiciona estilos da página sobre
* 8c45d20 Cria a página sobre a turma
* b10fc18 (origin/main) Atualiza a página inicial
```

A `main` local agora possui a funcionalidade.

O GitHub ainda não recebeu essa atualização.

## 25. Testando o projeto

Antes de publicar a integração, eu abro:

```text
index.html
```

Depois, testo:

1. O link para a página sobre.

2. O carregamento dos estilos.

3. A navegação de volta para a página inicial.

4. A exibição em diferentes tamanhos de tela.

5. A ausência de arquivos quebrados.

## 26. Publicando a main

Se tudo estiver correto:

```bash
git push origin main
```

Agora a `main` remota também possui a funcionalidade.

## 27. Merge com commit de integração

Quando as branches possuem desenvolvimentos diferentes, o Git poderá criar um commit de merge.

Exemplo inicial:

```text
          D → E feature/pagina_sobre
         /
A → B → C → F → G main
```

Depois do merge:

```text
          D → E
         /     \
A → B → C → F → G → M main
```

O commit M registra a união das linhas de desenvolvimento.

## 28. Forçando um commit de merge para fins didáticos

Existe a opção:

```bash
git merge --no-ff feature/pagina_sobre
```

Essa opção cria um commit de merge mesmo quando um avanço direto seria possível.

Ela pode ajudar a manter visível no histórico o momento em que a funcionalidade foi integrada.

> ⚠️ A equipe deve definir uma estratégia de histórico. Não utilizo uma opção apenas porque ela existe.

## 29. Mensagem do commit de merge

Quando o Git abre o editor para confirmar a mensagem, poderá sugerir algo semelhante a:

```text
Merge branch 'feature/pagina_sobre'
```

A equipe poderá manter ou adaptar a mensagem conforme o padrão adotado.

# Parte 5: Cancelando um merge

## 30. Quando cancelar?

Durante um merge, posso perceber que:

1. Escolhi a branch errada.

2. O projeto apresentou conflitos.

3. A integração não deveria ocorrer naquele momento.

4. A área de trabalho não estava preparada.

5. Preciso revisar melhor os arquivos.

## 31. Cancelando uma integração em andamento

Quando o merge ainda não foi concluído, posso utilizar:

```bash
git merge --abort
```

Esse comando tenta retornar ao estado anterior ao início do merge.

## 32. Verificação obrigatória

Depois:

```bash
git status
```

Também verifico:

```bash
git log --oneline --all --graph --decorate
```

## 33. Cuidado

`git merge --abort` não deve ser utilizado como substituto da compreensão do problema.

Antes de qualquer ação, eu leio a mensagem apresentada pelo Git.

A resolução detalhada de conflitos será estudada na Aula 5.

# Parte 6: O que é um Pull Request?

## 34. Conceito

Pull Request é uma proposta de integração.

Quando eu abro um Pull Request, estou dizendo:

```text
Eu concluí uma alteração nesta branch.

Quero que a equipe analise o trabalho.

Depois da revisão, proponho integrar essas alterações à branch principal.
```

O Pull Request não é apenas um botão de merge.

Ele é um espaço para:

1. Explicar a alteração.

2. Mostrar os commits.

3. Mostrar os arquivos modificados.

4. Fazer perguntas.

5. Comentar trechos específicos.

6. Solicitar correções.

7. Aprovar o trabalho.

8. Registrar decisões.

9. Executar verificações automáticas.

10. Integrar a branch quando tudo estiver pronto.

## 35. Pull Request e trabalho profissional

Em uma equipe, é comum evitar alterações diretas na `main`.

O fluxo passa a ser:

```text
Branch

Commits

Push

Pull Request

Revisão

Aprovação

Merge
```

Esse processo cria uma oportunidade de revisão antes da integração.

## 36. GitHub Flow

O GitHub Flow é um fluxo baseado em branches.

Uma sequência simples será:

```text
Criar uma branch

Fazer alterações

Criar commits

Publicar a branch

Abrir um Pull Request

Discutir e revisar

Realizar o merge

Excluir a branch
```

Esse fluxo pode ser utilizado não apenas para código, mas também para documentação e outros tipos de arquivos.

# Parte 7: Base branch e compare branch

## 37. Base branch

A base branch é a branch que receberá as alterações.

No nosso projeto:

```text
main
```

## 38. Compare branch

A compare branch é a branch que contém as alterações propostas.

Exemplo:

```text
feature/pagina_sobre
```

## 39. Leitura da comparação

```text
base: main

compare: feature/pagina_sobre
```

Eu posso interpretar assim:

```text
Compare a feature/pagina_sobre com a main.

Proponha levar as diferenças para a main.
```

## 40. Erro comum

Se as branches forem invertidas:

```text
base: feature/pagina_sobre

compare: main
```

O Pull Request proporá levar a `main` para a branch de funcionalidade.

Isso não corresponde ao objetivo da integração final.

## 41. Verificação

Antes de criar o Pull Request, eu confirmo:

```text
Destino

main
```

```text
Origem

feature/pagina_sobre
```

# Parte 8: Criando um Pull Request

## 42. Preparação local

Na branch de funcionalidade:

```bash
git switch feature/pagina_sobre
```

Verifico:

```bash
git status
```

Depois:

```bash
git push
```

## 43. Acessando o GitHub

Na página do repositório, o GitHub poderá mostrar uma sugestão para comparar a branch publicada.

Também posso acessar a área:

```text
Pull requests
```

Depois, seleciono a opção para criar um novo Pull Request.

## 44. Escolhendo as branches

Configuro:

```text
base

main
```

```text
compare

feature/pagina_sobre
```

## 45. Conferindo antes de continuar

O GitHub apresentará:

1. Quantidade de commits.

2. Quantidade de arquivos modificados.

3. Linhas adicionadas.

4. Linhas removidas.

5. Possibilidade de integração automática.

Eu confiro se os números fazem sentido para a tarefa.

## 46. Título do Pull Request

O título deve explicar o resultado principal.

Exemplo adequado:

```text
Cria a página sobre a turma
```

Exemplos pouco informativos:

```text
Alterações

Nova página

Trabalho pronto

Atualização

Final
```

## 47. Descrição do Pull Request

A descrição deve ajudar o revisor a entender:

1. O objetivo.

2. O que foi alterado.

3. Como testar.

4. O que ainda precisa de atenção.

5. Qual tarefa está relacionada.

## 48. Modelo de descrição

```md
## Objetivo

Criar uma página para apresentar a turma e seus objetivos.

## Alterações realizadas

1. Criação do arquivo sobre.html.
2. Adição do link Sobre no menu principal.
3. Inclusão de informações sobre a turma.
4. Criação de estilos para navegação e seções.

## Como testar

1. Abrir o arquivo index.html.
2. Selecionar o link Sobre.
3. Verificar o carregamento da página.
4. Testar o retorno para a página inicial.
5. Verificar a exibição em diferentes tamanhos de tela.

## Evidências

A página abre corretamente e os links de navegação funcionam.

## Observações

Não foram alteradas outras páginas do projeto.
```

## 49. Relacionando uma tarefa

Quando o projeto utiliza Issues, a descrição poderá conter:

```text
Closes #3
```

Quando o Pull Request for integrado, a Issue relacionada poderá ser encerrada automaticamente.

O uso de Issues será aprofundado na Aula 6.

## 50. Criando o Pull Request

Depois de revisar o título e a descrição, confirmo a criação.

A partir desse momento, a equipe poderá discutir e revisar a proposta.

# Parte 9: Pull Request em rascunho

## 51. O que é um rascunho?

Um Pull Request em rascunho indica que o trabalho ainda não está pronto para integração.

Ele pode ser utilizado quando:

1. Quero mostrar o progresso.

2. Preciso de uma opinião antecipada.

3. A funcionalidade ainda está incompleta.

4. Os testes ainda não foram concluídos.

5. Existem decisões em aberto.

## 52. Quando não utilizar

Não transformo todo Pull Request em rascunho sem necessidade.

Se a tarefa está pronta para revisão, crio um Pull Request normal.

## 53. Exemplo de descrição de rascunho

```md
## Situação

Trabalho em andamento.

## Já concluído

1. Estrutura da página.
2. Menu de navegação.
3. Conteúdo principal.

## Pendente

1. Ajustar responsividade.
2. Revisar cores.
3. Testar os links.
```

## 54. Convertendo para pronto

Quando concluir a tarefa, utilizo a opção para marcar o Pull Request como pronto para revisão.

# Parte 10: Estrutura de um Pull Request

## 55. Conversation

Na área de conversa, encontramos:

1. Título.

2. Descrição.

3. Comentários.

4. Eventos do histórico.

5. Solicitações de revisão.

6. Aprovações.

7. Atualizações da branch.

8. Resultado das verificações.

## 56. Commits

A área de commits mostra os registros incluídos na branch.

Eu verifico:

1. Quantidade de commits.

2. Ordem das alterações.

3. Mensagens.

4. Autores.

5. Possíveis commits desnecessários.

## 57. Files changed

A área de arquivos modificados mostra o que será integrado.

Essa é uma das partes mais importantes da revisão.

Eu verifico:

1. Arquivos novos.

2. Arquivos modificados.

3. Linhas adicionadas.

4. Linhas removidas.

5. Código duplicado.

6. Nomes inadequados.

7. Erros de digitação.

8. Alterações fora do objetivo.

9. Credenciais expostas.

10. Arquivos que não deveriam estar no repositório.

## 58. Checks

A área de verificações poderá mostrar testes e automações.

Na Aula 8, criaremos uma automação com GitHub Actions.

Mesmo antes disso, eu apresento aos alunos a ideia de que um Pull Request pode ser verificado automaticamente antes do merge.

# Parte 11: Revisando um Pull Request

## 59. Objetivo da revisão

A revisão não serve para procurar culpados.

Ela serve para melhorar o projeto antes da integração.

Uma boa revisão deve ser:

1. Respeitosa.

2. Específica.

3. Relacionada à tarefa.

4. Tecnicamente justificável.

5. Fácil de compreender.

6. Orientada para uma ação.

## 60. O que revisar primeiro?

Eu começo pela descrição.

Pergunto:

1. O objetivo está explicado?

2. As alterações correspondem ao objetivo?

3. O procedimento de teste foi informado?

4. Existem pendências declaradas?

## 61. Revisando os commits

Na área de commits, verifico:

1. As mensagens são específicas?

2. Os commits estão relacionados à tarefa?

3. Existe algum commit chamado teste ou atualização?

4. O histórico ajuda a compreender o desenvolvimento?

## 62. Revisando os arquivos

Na área de arquivos, verifico:

1. O arquivo correto foi alterado?

2. Existem arquivos extras?

3. O código está organizado?

4. Os nomes são compreensíveis?

5. A indentação está consistente?

6. Os links funcionam?

7. O conteúdo está correto?

8. Existe informação confidencial?

9. O projeto continua funcionando?

## 63. Testando localmente

Para uma revisão mais completa, posso baixar a branch.

Primeiro:

```bash
git fetch origin
```

Depois:

```bash
git checkout --track origin/feature/pagina_sobre
```

Se a branch local já existir:

```bash
git checkout feature/pagina_sobre
```

Depois:

```bash
git pull
```

Agora posso abrir e testar o projeto no computador.

## 64. Não alterar a branch sem autorização

Durante a revisão, eu não modifico diretamente o trabalho de outro aluno sem combinar com a equipe.

Normalmente, registro comentários e permito que o autor faça as correções.

# Parte 12: Tipos de comentário

## 65. Comentário geral

Utilizo quando a observação se refere ao Pull Request como um todo.

Exemplo:

```text
A estrutura da página está organizada e a navegação funcionou corretamente. Antes da aprovação, revise o título da seção Objetivos da turma, pois há uma palavra repetida.
```

## 66. Comentário em uma linha

Na área de arquivos modificados, posso selecionar uma linha específica.

Exemplo:

```text
Este endereço aponta para contato.htm, mas o arquivo criado se chama contato.html. Ajuste o valor do href para evitar um link quebrado.
```

## 67. Sugestão de alteração

Quando a plataforma permite, posso propor uma substituição específica.

Exemplo:

```html
<a href="contato.html">Contato</a>
```

A sugestão deve ser pequena e objetiva.

## 68. Pergunta de revisão

Nem toda observação precisa assumir que existe um erro.

Exemplo:

```text
Esta classe será reutilizada nas outras páginas ou pertence somente à página sobre?
```

Perguntas ajudam a compreender a decisão do autor.

# Parte 13: Como escrever bons comentários

## 69. Comentário inadequado

```text
Está errado.
```

Problemas:

1. Não informa onde está o erro.

2. Não explica a consequência.

3. Não orienta a correção.

## 70. Comentário melhor

```text
O link Sobre aponta para pagina_sobre.html, mas o arquivo criado se chama sobre.html. Ajuste o href para que a navegação funcione.
```

Esse comentário informa:

1. O local.

2. O problema.

3. A consequência.

4. A correção esperada.

## 71. Comentário inadequado

```text
Não gostei.
```

Esse comentário apresenta uma preferência sem critério técnico.

## 72. Comentário melhor

```text
A cor do texto possui pouco contraste com o fundo. Ajuste a combinação para facilitar a leitura.
```

## 73. Comentário inadequado

```text
Refaça tudo.
```

## 74. Comentário melhor

```text
A página atende ao objetivo principal. Antes da aprovação, separe o menu e o conteúdo principal com elementos semânticos e corrija os dois links indicados nos comentários.
```

# Parte 14: Opções da revisão

## 75. Comment

Utilizo quando quero enviar comentários sem aprovar ou bloquear a proposta.

É adequado para:

1. Perguntas.

2. Observações opcionais.

3. Elogios.

4. Sugestões não obrigatórias.

## 76. Approve

Utilizo quando considero que o Pull Request pode ser integrado.

Antes de aprovar, verifico:

1. O objetivo foi cumprido.

2. O projeto funciona.

3. Os comentários obrigatórios foram resolvidos.

4. Não existem arquivos indevidos.

5. A branch está atualizada quando necessário.

## 77. Request changes

Utilizo quando existem correções obrigatórias antes do merge.

Exemplos:

1. Link quebrado.

2. Erro de funcionamento.

3. Senha publicada.

4. Arquivo incorreto.

5. Alteração fora do objetivo.

6. Requisito não atendido.

> ⚠️ A capacidade de impedir efetivamente o merge depende das regras e proteções configuradas no repositório.

# Parte 15: Solicitando alterações

## 78. Situação prática

Durante a revisão, encontro este código:

```html
<a href="sobre_turma.html">Sobre</a>
```

Mas o arquivo criado é:

```text
sobre.html
```

## 79. Comentário do revisor

```text
O link aponta para sobre_turma.html, mas o arquivo criado se chama sobre.html. Corrija o href e teste a navegação antes de solicitar uma nova revisão.
```

## 80. Enviando a revisão

Seleciono:

```text
Request changes
```

Depois, envio um resumo:

```text
A estrutura da página está correta. Solicitei apenas a correção do link do menu e um novo teste de navegação.
```

## 81. O autor recebe o retorno

O autor volta à branch:

```bash
git checkout feature/pagina_sobre
```

Atualiza:

```bash
git pull
```

Corrige o arquivo.

Depois:

```bash
git status

git diff

git add index.html

git commit -m "Corrige o link da página sobre"

git push
```

## 82. O Pull Request é atualizado automaticamente

O autor não precisa criar outro Pull Request.

Quando novos commits são enviados para a mesma branch, eles aparecem na proposta existente.

## 83. Respondendo ao comentário

O autor poderá responder:

```text
Link corrigido e navegação testada na página inicial e na página sobre.
```

Depois, marca a conversa como resolvida quando apropriado.

# Parte 16: Nova revisão e aprovação

## 84. Revisor verifica a correção

O revisor atualiza a página do Pull Request.

Depois, confere:

1. Novo commit.

2. Linha corrigida.

3. Link funcionando.

4. Ausência de novos problemas.

## 85. Aprovando

Seleciona:

```text
Approve
```

Pode escrever:

```text
Correção verificada. A página e os links funcionaram corretamente. Pull Request aprovado.
```

## 86. Aprovação não substitui o teste

Eu não aprovo apenas porque o autor informou que corrigiu.

Eu verifico a alteração.

# Parte 17: Métodos de merge no GitHub

## 87. Merge commit

Esse método mantém os commits da branch e cria um commit de integração.

Representação:

```text
          D → E
         /     \
A → B → C       M main
```

Vantagens:

1. Mantém visível a branch no histórico.

2. Preserva os commits individuais.

3. Registra o momento da integração.

Possível desvantagem:

1. O histórico poderá possuir muitos commits de merge.

## 88. Squash and merge

Esse método reúne os commits da branch em um único commit antes da integração.

Antes:

```text
D Cria a página

E Adiciona estilos

F Corrige o link
```

Depois:

```text
S Cria a página sobre a turma
```

Vantagens:

1. Histórico principal mais compacto.

2. Útil quando a branch possui muitos commits pequenos.

Possível desvantagem:

1. Os commits individuais não aparecem separadamente na `main`.

## 89. Rebase and merge

Esse método reaplica os commits da branch sobre o final da base branch, criando um histórico linear.

Representação:

```text
A → B → C → D → E
```

Vantagens:

1. Histórico linear.

2. Evita um commit de merge.

Possível desvantagem:

1. Exige compreensão maior do histórico.

## 90. Qual método utilizaremos?

Para a primeira prática, utilizaremos:

```text
Create a merge commit
```

Assim, os alunos conseguirão visualizar claramente a integração no gráfico do histórico.

O professor poderá demonstrar os outros métodos em um repositório de teste.

## 91. Estratégia da equipe

Não existe uma única estratégia adequada para todos os projetos.

A equipe deverá definir:

1. Qual histórico deseja manter.

2. Se commits pequenos serão preservados.

3. Se Pull Requests serão reunidos em um commit.

4. Se commits de merge serão utilizados.

5. Qual método é permitido no repositório.

# Parte 18: Realizando o merge do Pull Request

## 92. Verificações antes do merge

Antes de confirmar, verifico:

1. O Pull Request não está em rascunho.

2. As alterações foram revisadas.

3. A aprovação foi registrada.

4. As conversas obrigatórias foram resolvidas.

5. Os testes foram realizados.

6. As verificações automáticas foram concluídas, quando existirem.

7. Não existem conflitos.

8. A base branch está correta.

9. A compare branch está correta.

## 93. Confirmando o merge

Seleciono o método definido pela equipe.

Depois, confirmo o merge.

O GitHub registrará a integração na `main`.

## 94. Mensagem de integração

Uma mensagem possível será:

```text
Merge pull request #4 from turma/feature/pagina_sobre
```

O número dependerá da ordem dos Pull Requests no repositório.

## 95. Pull Request concluído

Depois do merge, o Pull Request será marcado como integrado.

O histórico de conversas, revisões e decisões continuará disponível.

# Parte 19: Excluindo a branch concluída

## 96. Por que excluir?

Depois da integração, a branch de funcionalidade normalmente não precisa continuar ativa.

A exclusão ajuda a:

1. Reduzir branches antigas.

2. Evitar reutilização acidental.

3. Indicar que a tarefa foi concluída.

4. Facilitar a navegação no repositório.

## 97. Excluindo no GitHub

Depois do merge, o GitHub poderá oferecer a opção:

```text
Delete branch
```

Confirmo somente depois de verificar que a integração foi concluída.

## 98. A exclusão remove a funcionalidade?

Não.

Os commits integrados continuam na `main`.

A branch era uma referência para aquela linha de desenvolvimento.

## 99. Excluindo localmente

Primeiro, volto para a `main`:

```bash
git checkout main
```

Depois, atualizo:

```bash
git pull origin main
```

Agora excluo a branch local:

```bash
git branch -d feature/pagina_sobre
```

## 100. Atualizando referências remotas

```bash
git fetch --prune origin
```

Depois:

```bash
git branch -a
```

A branch concluída não deverá mais aparecer como ativa.

# Parte 20: Atualizando o projeto local depois do merge

## 101. Situação

O merge foi realizado no GitHub.

O computador do aluno ainda poderá estar com uma `main` antiga.

## 102. Atualização

```bash
git checkout main

git pull origin main
```

## 103. Conferindo o histórico

```bash
git log --oneline --all --graph --decorate
```

## 104. Conferindo os arquivos

```bash
git status
```

Depois, testo o projeto.

## 105. Fluxo obrigatório

Depois de um merge realizado no GitHub, eu não continuo trabalhando sobre uma `main` antiga.

Eu atualizo antes de criar a próxima branch.

# Parte 21: Proteção da branch principal

## 106. O problema de alterações diretas

Mesmo utilizando Pull Requests, um colaborador poderá executar:

```bash
git checkout main

git commit

git push
```

Se o repositório permitir, isso levará alterações diretamente para a `main`.

## 107. Branch protegida

O GitHub permite criar regras para proteger branches importantes.

Uma regra poderá exigir:

1. Pull Request antes da integração.

2. Quantidade mínima de aprovações.

3. Resolução das conversas.

4. Verificações automáticas aprovadas.

5. Branch atualizada antes do merge.

6. Restrições de envio direto.

7. Histórico linear.

8. Commits assinados.

A disponibilidade e as opções poderão variar conforme o tipo de repositório, permissões e plano utilizado.

## 108. Configuração didática sugerida

Para o projeto da turma, o professor poderá proteger:

```text
main
```

E exigir:

1. Pull Request.

2. Uma aprovação.

3. Resolução das conversas.

4. Bloqueio de alteração direta.

## 109. Objetivo da proteção

A proteção não existe porque a equipe desconfia dos integrantes.

Ela existe para garantir que todos sigam o mesmo processo.

# Parte 22: Revisão responsável

## 110. O revisor também é responsável

A pessoa que aprova assume responsabilidade pela análise realizada.

A aprovação não deve ser automática.

## 111. O autor também é responsável

O autor deve:

1. Testar antes de solicitar revisão.

2. Explicar a alteração.

3. Responder aos comentários.

4. Corrigir os problemas.

5. Evitar alterações extras.

6. Atualizar a branch quando necessário.

## 112. Responsabilidade compartilhada

Um Pull Request bem conduzido possui:

```text
Autor preparado

Revisor atento

Comentários específicos

Correções verificadas

Integração consciente
```

# Parte 23: Erros comuns

## 113. Merge realizado na branch errada

Antes do comando, verifico:

```bash
git branch --show-current
```

Se o objetivo é integrar na `main`, o resultado deve ser:

```text
main
```

## 114. Main desatualizada

Antes do merge local:

```bash
git switch main

git pull origin main
```

## 115. Arquivos não registrados

Antes da integração:

```bash
git status
```

Eu resolvo as alterações pendentes antes de continuar.

## 116. Pull Request com base invertida

Configuração correta:

```text
base: main

compare: feature/nome_da_tarefa
```

## 117. Título genérico

Evito:

```text
Atualização
```

Prefiro:

```text
Cria a página de contato
```

## 118. Descrição vazia

Uma descrição vazia obriga o revisor a descobrir sozinho o objetivo e o modo de teste.

Eu informo:

1. Objetivo.

2. Alterações.

3. Teste.

4. Observações.

## 119. Aprovar sem testar

Eu não aprovo somente olhando o título.

Analiso os commits, arquivos e funcionamento.

## 120. Comentário sem orientação

Evito:

```text
Errado.
```

Escrevo:

```text
O link aponta para um arquivo que não existe. Ajuste o href para projetos.html e teste a navegação.
```

## 121. Merge com conversas pendentes

Antes do merge, verifico se os comentários obrigatórios foram resolvidos.

## 122. Excluir a branch antes do merge

Eu confirmo a integração antes da exclusão.

## 123. Continuar em uma main antiga

Depois do merge no GitHub:

```bash
git switch main

git pull origin main
```

## 124. Conflito durante o merge

Se houver conflito, não escolho alterações aleatoriamente.

Executo:

```bash
git status
```

Analiso os arquivos indicados.

Se precisar interromper:

```bash
git merge --abort
```

A resolução completa será estudada na Aula 5.

# Parte 24: Prática guiada de merge local

## 125. Etapa 1: Verificar a funcionalidade

```bash
git switch feature/pagina_sobre

git status

git log --oneline
```

## 126. Etapa 2: Publicar os últimos commits

```bash
git push
```

## 127. Etapa 3: Voltar para a main

```bash
git switch main
```

## 128. Etapa 4: Atualizar

```bash
git pull origin main
```

## 129. Etapa 5: Comparar

```bash
git diff --name-only main..feature/pagina_sobre

git log main..feature/pagina_sobre --oneline
```

## 130. Etapa 6: Integrar

```bash
git merge feature/pagina_sobre
```

## 131. Etapa 7: Verificar

```bash
git status

git log --oneline --all --graph --decorate
```

## 132. Etapa 8: Testar

Abrir e testar o projeto.

## 133. Etapa 9: Publicar a main

```bash
git push origin main
```

## 134. Etapa 10: Excluir a branch

```bash
git branch -d feature/pagina_sobre

git push origin --delete feature/pagina_sobre
```

# Parte 25: Prática guiada de Pull Request

## 135. Tarefa escolhida

Utilizaremos:

```text
feature/lista_alunos
```

## 136. Etapa 1: Atualizar a branch

```bash
git switch feature/lista_alunos

git status

git push
```

## 137. Etapa 2: Criar o Pull Request

No GitHub:

```text
base: main

compare: feature/lista_alunos
```

## 138. Etapa 3: Título

```text
Cria a página de alunos
```

## 139. Etapa 4: Descrição

```md
## Objetivo

Criar uma página para apresentar os alunos da turma.

## Alterações realizadas

1. Criação do arquivo alunos.html.
2. Adição do link Alunos no menu.
3. Criação de uma tabela com dados fictícios.
4. Inclusão dos estilos da tabela.

## Como testar

1. Abrir index.html.
2. Selecionar Alunos.
3. Verificar o carregamento da página.
4. Testar os links do menu.
5. Conferir a tabela em tela menor.

## Observações

Os dados utilizados são fictícios.
```

## 140. Etapa 5: Solicitar revisão

Selecionar um colega como revisor, conforme as permissões disponíveis.

## 141. Etapa 6: Revisar

O revisor verifica:

1. Descrição.

2. Commits.

3. Arquivos.

4. Links.

5. Conteúdo.

6. Segurança.

7. Funcionamento.

## 142. Etapa 7: Solicitar correção

Comentário de exemplo:

```text
O link Alunos da página inicial aponta para aluno.html, mas o arquivo criado se chama alunos.html. Ajuste o href e teste novamente.
```

Depois:

```text
Request changes
```

## 143. Etapa 8: Corrigir

O autor executa:

```bash
git switch feature/lista_alunos

git pull
```

Corrige o arquivo.

Depois:

```bash
git add index.html

git commit -m "Corrige o link da página de alunos"

git push
```

## 144. Etapa 9: Aprovar

O revisor verifica e seleciona:

```text
Approve
```

## 145. Etapa 10: Realizar o merge

Utilizar o método definido pelo professor.

Para esta aula:

```text
Create a merge commit
```

## 146. Etapa 11: Excluir a branch remota

Selecionar:

```text
Delete branch
```

## 147. Etapa 12: Atualizar localmente

```bash
git switch main

git pull origin main

git fetch --prune origin

git branch -d feature/lista_alunos
```

# Parte 26: Atividade colaborativa

## 148. Organização da equipe

Cada equipe terá:

1. Um autor.

2. Um revisor principal.

3. Um segundo observador, quando possível.

4. Um responsável pelo merge.

As funções deverão mudar na atividade seguinte.

## 149. Tarefas sugeridas

### Tarefa 1

```text
feature/pagina_projetos
```

### Tarefa 2

```text
feature/pagina_contato
```

### Tarefa 3

```text
docs/atualiza_readme
```

### Tarefa 4

```text
fix/correcao_menu
```

## 150. Etapas da atividade

1. Autor verifica a branch.

2. Autor publica os commits.

3. Autor cria o Pull Request.

4. Autor descreve o objetivo e o teste.

5. Revisor analisa os commits.

6. Revisor analisa os arquivos.

7. Revisor testa o projeto.

8. Revisor registra pelo menos um comentário útil.

9. Autor responde.

10. Autor corrige quando necessário.

11. Revisor verifica novamente.

12. Revisor aprova.

13. Responsável realiza o merge.

14. Equipe exclui a branch concluída.

15. Todos atualizam a `main`.

## 151. Regra da atividade

Nenhum Pull Request poderá ser integrado sem uma revisão registrada.

## 152. Registro da equipe

Cada grupo deverá apresentar:

```text
Título do Pull Request

Autor

Revisor

Branch de origem

Branch de destino

Commits incluídos

Arquivos modificados

Comentário realizado

Correção solicitada

Resultado da revisão

Método de merge

Situação da branch depois do merge
```

# Parte 27: Modelo de Pull Request

## 153. Arquivo de modelo

Em projetos profissionais, podemos criar um arquivo de modelo.

Local sugerido:

```text
.github/PULL_REQUEST_TEMPLATE.md
```

Conteúdo:

```md
## Objetivo

Descreva o resultado esperado.

## Alterações realizadas

1.
2.
3.

## Como testar

1.
2.
3.

## Checklist

1. Revisei os arquivos alterados.
2. Testei a funcionalidade.
3. Não adicionei credenciais.
4. Atualizei a documentação quando necessário.
5. Utilizei mensagens de commit específicas.

## Observações

Informe riscos, limitações ou decisões importantes.
```

O uso de templates será aprofundado na Aula 6.

# Parte 28: Checklist do autor

## 154. Antes de abrir o Pull Request

1. Estou na branch correta.

2. Minha `main` estava atualizada quando comecei.

3. A tarefa está concluída.

4. O projeto foi testado.

5. Os commits foram criados.

6. As mensagens são específicas.

7. A branch foi publicada.

8. Não existem credenciais.

9. Não existem arquivos temporários.

10. A documentação foi atualizada quando necessário.

## 155. Antes de solicitar nova revisão

1. Li todos os comentários.

2. Corrigi os pontos obrigatórios.

3. Testei novamente.

4. Criei um commit específico.

5. Enviei a branch.

6. Respondi ao revisor.

# Parte 29: Checklist do revisor

## 156. Durante a revisão

1. Entendi o objetivo.

2. Verifiquei as branches.

3. Li os commits.

4. Analisei os arquivos.

5. Testei o projeto.

6. Procurei arquivos indevidos.

7. Verifiquei links.

8. Verifiquei nomes.

9. Verifiquei a documentação.

10. Escrevi comentários específicos.

## 157. Antes de aprovar

1. Os problemas obrigatórios foram corrigidos.

2. As conversas foram resolvidas.

3. O projeto funciona.

4. A proposta não possui alterações fora do objetivo.

5. A branch pode ser integrada.

# Parte 30: Exercícios de fixação

## 158. Exercício 1: Conceitos

Responda com suas palavras.

1. O que é merge?

2. O que é branch de destino?

3. O que é branch de origem?

4. Por que devemos entrar na branch de destino antes de executar `git merge`?

5. O que é um Pull Request?

6. O que significa base branch?

7. O que significa compare branch?

8. Qual é a função da revisão?

9. Qual é a diferença entre Comment, Approve e Request changes?

10. Publicar uma branch é o mesmo que realizar merge?

11. Por que excluir uma branch depois da integração?

12. Por que atualizar a `main` depois de um merge no GitHub?

## 159. Exercício 2: Relacione os conceitos

### Conceitos

```text
A. Merge

B. Pull Request

C. Base branch

D. Compare branch

E. Approve

F. Request changes

G. Delete branch

H. Branch protection
```

### Definições

```text
1. Branch que receberá as alterações.

2. Aprovação da proposta.

3. Integração de linhas de desenvolvimento.

4. Solicitação de correções obrigatórias.

5. Regra que protege uma branch importante.

6. Proposta de integração e espaço de revisão.

7. Remoção de uma branch concluída.

8. Branch que contém as alterações propostas.
```

## 160. Exercício 3: Complete os comandos

### Entrar na main

```bash
git __________ main
```

### Atualizar a main

```bash
git __________ origin main
```

### Integrar uma funcionalidade

```bash
git __________ feature/pagina_contato
```

### Cancelar um merge em andamento

```bash
git merge __________
```

### Visualizar o gráfico

```bash
git log __________ __________ __________ __________
```

### Excluir uma branch local

```bash
git branch __________ feature/pagina_contato
```

### Excluir uma branch remota

```bash
git push origin __________ feature/pagina_contato
```

## 161. Exercício 4: Identifique origem e destino

### Situação 1

A página de contato deve entrar na `main`.

Resposta:

```text
Destino:

Origem:
```

### Situação 2

A atualização do README deve entrar na `main`.

Resposta:

```text
Destino:

Origem:
```

### Situação 3

A `main` atualizada precisa ser levada para a branch de projetos.

Resposta:

```text
Destino:

Origem:
```

## 162. Exercício 5: Avalie títulos

Classifique os títulos como adequados ou inadequados.

```text
Atualização

Cria a página de contato

Final

Corrige o link do menu principal

Alterações do trabalho

Atualiza as instruções de instalação

Agora funciona

Adiciona estilos responsivos ao portal
```

Reescreva os títulos inadequados considerando uma alteração possível.

## 163. Exercício 6: Avalie comentários

### Comentário 1

```text
Está errado.
```

### Comentário 2

```text
O link aponta para contato.htm, mas o arquivo criado se chama contato.html. Ajuste o href e teste a navegação.
```

### Comentário 3

```text
Não gostei desta cor.
```

### Comentário 4

```text
O contraste entre texto e fundo dificulta a leitura. Ajuste as cores para aumentar a legibilidade.
```

Responda:

1. Quais comentários são adequados?

2. Quais são inadequados?

3. Como melhorar os comentários inadequados?

## 164. Exercício 7: Organize o fluxo

Coloque na ordem correta:

```text
Realizar o merge.

Criar a branch.

Aprovar o Pull Request.

Desenvolver a tarefa.

Abrir o Pull Request.

Criar commits.

Publicar a branch.

Revisar os arquivos.

Excluir a branch.
```

## 165. Exercício 8: Interprete o gráfico

Observe:

```text
*   9f220a1 (main) Merge pull request #5
|\
| * 98b73e1 Corrige o link da página de projetos
| * 7a109c3 Cria a página de projetos
|/
* 6d82a10 Atualiza a página inicial
```

Responda:

1. Qual commit representa o merge?

2. Quantos commits foram criados na branch de projetos?

3. Qual correção foi feita antes do merge?

4. A funcionalidade já está na `main`?

5. O histórico preservou os commits da branch?

# Parte 31: Desafios

## 166. Desafio 1: Merge local controlado

Crie a branch:

```text
feature/area_tecnologias
```

Adicione uma seção de tecnologias.

Crie dois commits.

Depois:

```bash
git switch main

git pull origin main

git diff --name-only main..feature/area_tecnologias

git merge feature/area_tecnologias

git log --oneline --all --graph --decorate
```

Teste e publique.

## 167. Desafio 2: Pull Request completo

Crie uma nova funcionalidade.

O Pull Request deverá possuir:

1. Título específico.

2. Objetivo.

3. Lista de alterações.

4. Procedimento de teste.

5. Pelo menos dois commits.

6. Pelo menos dois arquivos modificados.

7. Um revisor.

8. Um comentário em uma linha.

9. Uma aprovação.

10. Merge.

11. Exclusão da branch.

## 168. Desafio 3: Revisão com correção

O revisor deverá encontrar ou solicitar uma melhoria real.

O autor deverá:

1. Corrigir.

2. Criar um novo commit.

3. Enviar para a mesma branch.

4. Responder ao comentário.

5. Solicitar nova revisão.

O revisor deverá verificar novamente antes de aprovar.

## 169. Desafio 4: Pull Request em rascunho

Crie uma branch com uma funcionalidade incompleta.

Abra um Pull Request em rascunho.

Na descrição, informe:

1. O que já foi feito.

2. O que falta.

3. Qual opinião deseja receber.

Depois, conclua a tarefa e marque como pronto para revisão.

## 170. Desafio 5: Comparação dos métodos

Em repositórios de teste, faça três integrações:

1. Merge commit.

2. Squash and merge.

3. Rebase and merge.

Depois, execute em cada repositório:

```bash
git log --oneline --all --graph --decorate
```

Compare:

1. Quantidade de commits.

2. Presença de commit de merge.

3. Preservação dos commits individuais.

4. Formato do histórico.

## 171. Desafio 6: Modelo de Pull Request

Crie:

```text
.github/PULL_REQUEST_TEMPLATE.md
```

Inclua:

1. Objetivo.

2. Alterações.

3. Teste.

4. Checklist.

5. Observações.

Depois, crie um novo Pull Request e verifique se o modelo foi carregado.

## 172. Desafio 7: Proteção da main

Com orientação do professor e permissões adequadas:

1. Crie uma regra para a `main`.

2. Exija Pull Request.

3. Exija uma aprovação.

4. Exija resolução das conversas.

5. Tente realizar um envio direto.

6. Registre o comportamento apresentado.

## 173. Desafio 8: Auditoria de Pull Request

Escolha um Pull Request concluído.

Registre:

```text
Número do Pull Request

Título

Autor

Revisor

Branch de origem

Branch de destino

Quantidade de commits

Quantidade de arquivos

Comentários

Correções

Método de merge

Data da integração
```

## 174. Desafio 9: Projeto colaborativo

A equipe deverá integrar três funcionalidades diferentes.

Cada integrante deverá atuar pelo menos uma vez como:

1. Autor.

2. Revisor.

3. Responsável pela integração.

Ao final, apresente o gráfico:

```bash
git log --oneline --all --graph --decorate
```

# Parte 32: Avaliação

## 175. Critérios de avaliação

A atividade poderá valer 10 pontos.

### Preparação da branch: 1 ponto

A branch está atualizada e sem alterações pendentes.

### Pull Request: 2 pontos

Possui título e descrição adequados.

### Commits: 1 ponto

As mensagens explicam as alterações.

### Revisão: 2 pontos

O aluno analisou arquivos e escreveu comentários específicos.

### Correções: 1 ponto

O autor respondeu e corrigiu os pontos obrigatórios.

### Aprovação: 1 ponto

A aprovação foi realizada depois da verificação.

### Merge: 1 ponto

A integração ocorreu na branch correta.

### Encerramento: 1 ponto

A branch foi excluída e a `main` local foi atualizada.

## 176. Evidências de aprendizagem

O aluno deverá apresentar:

1. Link ou identificação do Pull Request.

2. Título.

3. Descrição.

4. Commits.

5. Arquivos modificados.

6. Comentário de revisão.

7. Correção realizada.

8. Aprovação.

9. Merge.

10. Histórico atualizado.

# Parte 33: Gabarito

## 177. Gabarito do exercício 1

### Questão 1

Merge é a integração das alterações de uma linha de desenvolvimento em outra.

### Questão 2

Branch de destino é aquela que receberá as alterações.

### Questão 3

Branch de origem é aquela que fornece as alterações.

### Questão 4

Porque `git merge` incorpora a branch informada na branch atual.

### Questão 5

Pull Request é uma proposta de integração e um espaço para discussão, revisão e aprovação.

### Questão 6

Base branch é a branch de destino.

### Questão 7

Compare branch é a branch que contém as alterações propostas.

### Questão 8

A revisão verifica se a alteração atende ao objetivo e pode ser integrada com segurança.

### Questão 9

Comment registra observações. Approve aprova. Request changes solicita correções antes da integração.

### Questão 10

Não. Publicar envia a branch. Merge integra as alterações.

### Questão 11

Para indicar conclusão e reduzir branches antigas ou reutilizadas por engano.

### Questão 12

Porque o merge realizado no GitHub ainda precisa ser recebido pelo repositório local.

## 178. Gabarito do exercício 2

```text
A corresponde a 3.

B corresponde a 6.

C corresponde a 1.

D corresponde a 8.

E corresponde a 2.

F corresponde a 4.

G corresponde a 7.

H corresponde a 5.
```

## 179. Gabarito do exercício 3

### Entrar na main

```bash
git switch main
```

### Atualizar a main

```bash
git pull origin main
```

### Integrar

```bash
git merge feature/pagina_contato
```

### Cancelar

```bash
git merge --abort
```

### Gráfico

```bash
git log --oneline --all --graph --decorate
```

### Excluir local

```bash
git branch -d feature/pagina_contato
```

### Excluir remota

```bash
git push origin --delete feature/pagina_contato
```

## 180. Gabarito do exercício 4

### Situação 1

```text
Destino: main

Origem: feature/pagina_contato
```

### Situação 2

```text
Destino: main

Origem: docs/atualiza_readme
```

### Situação 3

```text
Destino: feature/pagina_projetos

Origem: main
```

## 181. Gabarito do exercício 5

### Adequados

```text
Cria a página de contato

Corrige o link do menu principal

Atualiza as instruções de instalação

Adiciona estilos responsivos ao portal
```

### Inadequados

```text
Atualização

Final

Alterações do trabalho

Agora funciona
```

As reescritas dependem da alteração realizada.

## 182. Gabarito do exercício 6

Os comentários 2 e 4 são adequados.

Os comentários 1 e 3 são inadequados porque não explicam claramente o problema e a ação esperada.

## 183. Gabarito do exercício 7

Ordem correta:

```text
Criar a branch.

Desenvolver a tarefa.

Criar commits.

Publicar a branch.

Abrir o Pull Request.

Revisar os arquivos.

Aprovar o Pull Request.

Realizar o merge.

Excluir a branch.
```

## 184. Gabarito do exercício 8

1. O commit de merge é `9f220a1`.

2. Foram criados dois commits na branch.

3. Foi corrigido o link da página de projetos.

4. Sim. O merge está registrado na `main`.

5. Sim. Os commits aparecem separadamente no histórico.

# Parte 34: Revisão oral

## 185. Perguntas para a turma

1. O que é merge?

2. Qual branch deve estar ativa antes do merge?

3. O que é branch de destino?

4. O que é branch de origem?

5. O que é Pull Request?

6. O que significa base?

7. O que significa compare?

8. Qual é a função da revisão?

9. Quando utilizamos Request changes?

10. Quando utilizamos Approve?

11. Quais são os três métodos de merge apresentados?

12. Por que excluir uma branch concluída?

13. O que fazer depois de um merge realizado no GitHub?

14. Para que serve a proteção da `main`?

# Parte 35: Resumo dos comandos

## 186. Verificar a branch

```bash
git branch --show-current
```

## 187. Atualizar a main

```bash
git switch main

git pull origin main
```

## 188. Comparar branches

```bash
git diff --name-only main..feature/nome_da_tarefa

git log main..feature/nome_da_tarefa --oneline
```

## 189. Realizar merge

```bash
git merge feature/nome_da_tarefa
```

## 190. Criar commit de merge

```bash
git merge --no-ff feature/nome_da_tarefa
```

## 191. Cancelar merge

```bash
git merge --abort
```

## 192. Visualizar histórico

```bash
git log --oneline --all --graph --decorate
```

## 193. Publicar a main

```bash
git push origin main
```

## 194. Excluir branch local

```bash
git branch -d feature/nome_da_tarefa
```

## 195. Excluir branch remota

```bash
git push origin --delete feature/nome_da_tarefa
```

## 196. Atualizar referências

```bash
git fetch --prune origin
```

# Parte 36: Fluxo completo da aula

## 197. Autor

```bash
git switch feature/nome_da_tarefa

git status

git push
```

Depois, cria o Pull Request.

## 198. Revisor

Analisa:

```text
Descrição

Commits

Arquivos

Testes

Segurança
```

Depois, comenta, solicita correções ou aprova.

## 199. Autor corrige

```bash
git switch feature/nome_da_tarefa

git pull

git add .

git commit -m "Descrição da correção"

git push
```

## 200. Responsável integra

No GitHub:

```text
Approve

Merge

Delete branch
```

## 201. Equipe atualiza

```bash
git switch main

git pull origin main

git fetch --prune origin

git branch -d feature/nome_da_tarefa
```

# Parte 37: Encerramento

## 202. O que aprendemos

Nesta aula, eu mostrei que desenvolver uma funcionalidade é apenas uma parte do trabalho.

Antes de levar a alteração para a `main`, precisamos revisar, discutir, testar e aprovar.

Aprendemos que:

```text
Merge integra branches.

Pull Request propõe a integração.

Base é a branch de destino.

Compare é a branch de origem.

Comment registra uma observação.

Request changes solicita correções.

Approve autoriza a integração.

Branch protection ajuda a manter a main estável.
```

## 203. Preparação para a próxima aula

Na próxima aula, vamos provocar e resolver conflitos.

Aprenderemos:

1. Por que conflitos acontecem.

2. Como identificar os arquivos envolvidos.

3. Como interpretar os marcadores.

4. Como decidir qual conteúdo manter.

5. Como concluir a resolução.

6. Como cancelar um merge.

7. Como recuperar alterações com restore, revert, reset, stash e reflog.

## 204. Frase de encerramento

Uma boa integração não começa no botão de merge.

Ela começa em uma tarefa bem definida, continua em commits compreensíveis e termina com uma revisão responsável.

Quando a equipe utiliza Pull Requests corretamente, o histórico registra não apenas o código, mas também as decisões que permitiram melhorar o projeto.

# Referências

1. Documentação oficial do Git sobre merge  
   https://git-scm.com/docs/git-merge

2. Livro oficial Pro Git sobre branches e merge  
   https://git-scm.com/book/pt-br/v2/Branches-no-Git-Branches-e-Merges-B%C3%A1sicos

3. Documentação oficial do GitHub sobre Pull Requests  
   https://docs.github.com/pt/pull-requests

4. Documentação oficial do GitHub sobre revisão de Pull Requests  
   https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests

5. Documentação oficial do GitHub sobre merge de Pull Requests  
   https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request

6. Documentação oficial do GitHub sobre GitHub Flow  
   https://docs.github.com/pt/get-started/using-github/github-flow

7. Documentação oficial do GitHub sobre branches protegidas  
   https://docs.github.com/pt/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches

8. Referência oficial de comandos Git  
   https://git-scm.com/docs
