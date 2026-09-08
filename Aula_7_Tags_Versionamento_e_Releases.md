# Aula 7: Tags, Versionamento e Releases

## Git e GitHub na Prática

### Carga horária

4 horas

### Tema da aula

Criação e gerenciamento de tags, aplicação do Versionamento Semântico, manutenção do arquivo `CHANGELOG.md` e publicação de versões oficiais com GitHub Releases.

## 1. Apresentação da aula

Nas aulas anteriores, eu ensinei você a controlar alterações, trabalhar com branches, revisar Pull Requests, integrar funcionalidades, resolver conflitos e organizar tarefas no GitHub.

Agora nosso projeto possui um histórico completo de desenvolvimento.

Porém, ainda precisamos responder a algumas perguntas importantes:

1. Qual commit representa a primeira versão oficial?
2. Como identificar uma versão utilizada pelos usuários?
3. Como informar que uma versão recebeu uma correção?
4. Como diferenciar uma pequena melhoria de uma mudança incompatível?
5. Como apresentar ao usuário o que mudou em cada versão?
6. Como disponibilizar uma versão estável para consulta ou download?

Para responder a essas perguntas, vamos trabalhar com:

```text
Tags

Versionamento Semântico

CHANGELOG

Release notes

GitHub Releases
```

Uma tag marca um ponto específico do histórico.

Uma versão comunica o significado daquela entrega.

Uma Release apresenta a entrega para os usuários.

O fluxo principal desta aula será:

```text
Concluir as funcionalidades

        ↓

Atualizar a branch main

        ↓

Testar o projeto

        ↓

Atualizar o CHANGELOG

        ↓

Definir o número da versão

        ↓

Criar uma tag anotada

        ↓

Publicar a tag

        ↓

Criar uma Release no GitHub

        ↓

Comunicar as alterações
```

## 2. Objetivos da aula

Nesta aula, eu vou ensinar você a:

1. Entender o conceito de versão.
2. Compreender o que é uma tag.
3. Diferenciar tag, commit e branch.
4. Diferenciar tag e Release.
5. Criar uma tag leve.
6. Criar uma tag anotada.
7. Inspecionar informações de uma tag.
8. Criar uma tag em um commit específico.
9. Publicar uma tag no GitHub.
10. Publicar várias tags.
11. Excluir uma tag local.
12. Excluir uma tag remota.
13. Compreender os riscos de mover uma tag publicada.
14. Aplicar Versionamento Semântico.
15. Diferenciar versões Major, Minor e Patch.
16. Criar versões de pré lançamento.
17. Entender metadados de compilação.
18. Criar e manter um `CHANGELOG.md`.
19. Diferenciar changelog e release notes.
20. Preparar uma versão oficial.
21. Criar uma Release no GitHub.
22. Utilizar Releases em modo rascunho.
23. Identificar uma pré release.
24. Anexar arquivos a uma Release.
25. Gerar notas de versão automaticamente.
26. Criar uma versão de correção.
27. Organizar um fluxo de lançamento em equipe.

## 3. Resultados esperados

Ao final da aula, você deverá conseguir executar o seguinte processo:

```text
main estável

        ↓

CHANGELOG atualizado

        ↓

versão escolhida

        ↓

tag criada

        ↓

tag enviada ao GitHub

        ↓

Release publicada

        ↓

versão comunicada aos usuários
```

Os principais comandos serão:

```bash
git tag

git tag -a v1.0.0 -m "Primeira versão estável"

git show v1.0.0

git push origin v1.0.0

git push origin --tags

git tag -d v1.0.0

git push origin --delete v1.0.0

git describe --tags --always
```

## 4. Conhecimentos necessários

Para acompanhar esta aula, você deverá conhecer:

1. Repositório local.
2. Repositório remoto.
3. Branch `main`.
4. Commits.
5. Branches.
6. Merge.
7. Pull Request.
8. Issues.
9. Milestones.
10. `git status`.
11. `git add`.
12. `git commit`.
13. `git log`.
14. `git pull`.
15. `git push`.
16. `git switch`.
17. `git branch`.
18. Markdown.

## 5. Recursos necessários

1. Computador conectado à internet.
2. Git instalado.
3. Visual Studio Code.
4. Conta no GitHub.
5. Repositório `portal_da_turma`.
6. Branch `main` atualizada.
7. Permissão de escrita no repositório.
8. Funcionalidades concluídas e revisadas.
9. Pull Requests integrados.

## 6. Organização das quatro horas

### Primeiro momento: 25 minutos

Revisão do projeto e apresentação dos conceitos de tag, versão e Release.

### Segundo momento: 35 minutos

Criação, inspeção, publicação e exclusão de tags.

### Terceiro momento: 35 minutos

Versionamento Semântico e exercícios de decisão de versão.

### Quarto momento: 30 minutos

Criação e manutenção do `CHANGELOG.md`.

### Intervalo: 15 minutos

### Quinto momento: 45 minutos

Preparação e publicação da Release `v1.0.0`.

### Sexto momento: 30 minutos

Simulação de correção e publicação da versão `v1.0.1`.

### Sétimo momento: 25 minutos

Atividade colaborativa, exercícios, desafios e encerramento.

# Parte 1: O que é uma versão?

## 7. Conceito inicial

Uma versão identifica um estado específico de um projeto.

Exemplos:

```text
Versão 1.0.0

Primeira versão estável do Portal da Turma.
```

```text
Versão 1.0.1

Correção de um link quebrado.
```

```text
Versão 1.1.0

Adição de uma nova página de eventos.
```

```text
Versão 2.0.0

Reestruturação incompatível com a versão anterior.
```

## 8. Por que criar versões?

Versões ajudam a:

1. Identificar entregas estáveis.
2. Comunicar mudanças.
3. Reproduzir um estado do projeto.
4. Investigar problemas.
5. Organizar suporte.
6. Planejar atualizações.
7. Referenciar documentação.
8. Distribuir arquivos.
9. Comparar entregas.
10. Trabalhar com dependências.

## 9. Projeto sem versão

Imagine que um usuário informa:

```text
O site apresentou um problema.
```

Eu preciso perguntar:

1. Em qual versão?
2. Antes ou depois da correção do menu?
3. A página de projetos já existia?
4. Qual commit estava publicado?

Sem uma identificação de versão, a investigação fica mais difícil.

## 10. Projeto versionado

O usuário informa:

```text
O problema aconteceu na versão 1.0.0.
```

Agora posso localizar exatamente o estado correspondente.

# Parte 2: Commit, branch, tag e Release

## 11. Commit

Um commit registra uma alteração no histórico.

Exemplo:

```text
8a31f20 Corrige o link da página de projetos
```

O projeto pode possuir dezenas ou milhares de commits.

## 12. Branch

Uma branch é uma linha móvel de desenvolvimento.

Quando novos commits são criados, a branch avança.

```text
main

A → B → C → D
```

Depois de outro commit:

```text
main

A → B → C → D → E
```

## 13. Tag

Uma tag marca um ponto específico do histórico.

Ela normalmente permanece apontando para o mesmo commit.

```text
A → B → C → D → E
            ↑
          v1.0.0
```

Enquanto a `main` continua avançando, a tag `v1.0.0` continua identificando o commit D.

## 14. Release

Uma Release é uma publicação criada sobre uma tag.

Ela pode apresentar:

1. Nome da versão.
2. Descrição.
3. Notas de lançamento.
4. Lista de mudanças.
5. Links de comparação.
6. Arquivos anexados.
7. Código fonte compactado.
8. Indicação de pré lançamento.

## 15. Comparação resumida

| Elemento | Função principal | Avança com novos commits? |
|---|---|---:|
| Commit | Registrar uma alteração | Não |
| Branch | Representar uma linha de desenvolvimento | Sim |
| Tag | Marcar um ponto do histórico | Normalmente não |
| Release | Apresentar e distribuir uma versão | Não |

## 16. Uma comparação simples

Eu posso pensar assim:

```text
Commit

Uma página do diário do projeto.
```

```text
Branch

O marcador que acompanha a página atual.
```

```text
Tag

Um marcador permanente colocado em uma página importante.
```

```text
Release

Uma edição publicada com título, descrição e arquivos.
```

# Parte 3: Preparando o repositório

## 17. Entrando na main

```bash
git switch main
```

## 18. Atualizando

```bash
git pull origin main
```

## 19. Verificando alterações pendentes

```bash
git status
```

Resultado esperado:

```text
nothing to commit, working tree clean
```

## 20. Visualizando o histórico

```bash
git log --oneline --all --graph --decorate
```

## 21. Conferindo o projeto

Antes de criar uma versão, eu verifico:

1. Os Pull Requests foram integrados.
2. Não existem conflitos pendentes.
3. A documentação está atualizada.
4. O projeto foi testado.
5. Não existem credenciais.
6. As Issues previstas foram concluídas.
7. O milestone da versão pode ser encerrado.
8. O histórico está publicado.

## 22. Regra importante

Eu não crio uma tag de versão estável em um projeto que ainda não foi verificado.

A tag não corrige o projeto.

Ela apenas identifica o estado escolhido.

# Parte 4: Listando tags

## 23. Comando básico

```bash
git tag
```

Se ainda não existirem tags, o comando não exibirá resultados.

## 24. Listando com padrão

```bash
git tag --list "v1.*"
```

Esse comando mostra tags que começam com `v1.`.

## 25. Ordenando por versão

```bash
git tag --sort=-v:refname
```

A opção apresenta as versões mais altas primeiro, quando os nomes seguem um padrão compatível.

## 26. Tags remotas

```bash
git ls-remote --tags origin
```

Esse comando consulta as referências de tags existentes no remote.

# Parte 5: Tag leve

## 27. O que é uma tag leve?

Uma tag leve funciona como um nome apontando para um commit.

Ela não possui uma mensagem de anotação própria com as mesmas informações de uma tag anotada.

## 28. Criando

```bash
git tag v0.1.0
```

A tag será criada no commit atual.

## 29. Verificando

```bash
git tag
```

Resultado:

```text
v0.1.0
```

## 30. Quando utilizar?

Tags leves podem ser úteis para marcações temporárias ou particulares.

Para versões oficiais, eu prefiro tags anotadas.

# Parte 6: Tag anotada

## 31. O que é uma tag anotada?

Uma tag anotada cria um objeto próprio no Git.

Ela registra informações como:

1. Nome da tag.
2. Autor da tag.
3. Email.
4. Data.
5. Mensagem.
6. Commit marcado.
7. Assinatura, quando utilizada.

## 32. Criando a primeira versão oficial

```bash
git tag -a v1.0.0 -m "Primeira versão estável do Portal da Turma"
```

## 33. Entendendo o comando

```text
git tag

Trabalha com tags.
```

```text
-a

Cria uma tag anotada.
```

```text
v1.0.0

Define o nome da versão.
```

```text
-m

Permite informar a mensagem.
```

## 34. Inspecionando a tag

```bash
git show v1.0.0
```

O Git apresentará:

1. Informações da tag.
2. Mensagem.
3. Autor.
4. Data.
5. Commit associado.
6. Alterações daquele commit.

## 35. Visualizando no gráfico

```bash
git log --oneline --all --graph --decorate
```

Resultado possível:

```text
* 92f3b10 (HEAD -> main, tag: v1.0.0, origin/main) Atualiza o changelog da versão 1.0.0
* 78ac401 Adiciona página de projetos
* 04b28d3 Corrige o menu principal
```

# Parte 7: Criando tag em um commit específico

## 36. Situação

Eu deveria ter criado a tag no commit anterior.

Primeiro, localizo o código:

```bash
git log --oneline
```

Exemplo:

```text
92f3b10 Atualiza documentação futura

78ac401 Conclui a versão estável
```

## 37. Criando no commit escolhido

```bash
git tag -a v1.0.0 78ac401 -m "Primeira versão estável do Portal da Turma"
```

## 38. Verificando

```bash
git show v1.0.0
```

## 39. Regra

Antes de criar a tag, eu confirmo qual commit representa a versão.

# Parte 8: Publicando tags

## 40. Tag local não aparece automaticamente no GitHub

O comando:

```bash
git push
```

normalmente envia commits e branches acompanhadas, mas não publica automaticamente todas as tags locais.

## 41. Publicando uma tag específica

```bash
git push origin v1.0.0
```

## 42. Publicando todas as tags locais ausentes

```bash
git push origin --tags
```

## 43. Qual opção utilizar?

Para um lançamento controlado, eu prefiro enviar a tag específica:

```bash
git push origin v1.0.0
```

Assim, evito publicar marcações locais que ainda não deveriam ser compartilhadas.

## 44. Verificando no GitHub

Na página do repositório, acesso a área de tags ou Releases.

A tag deverá aparecer vinculada ao commit correto.

# Parte 9: Excluindo tags

## 45. Excluindo localmente

```bash
git tag -d v0.1.0
```

## 46. Excluindo no remote

```bash
git push origin --delete v0.1.0
```

## 47. Confirmando

```bash
git tag

git ls-remote --tags origin
```

## 48. Cuidado com tags oficiais

Excluir ou mover uma tag publicada pode confundir usuários, automações e integrantes da equipe.

Se a versão `v1.0.0` foi publicada com um problema, normalmente criamos uma nova versão de correção:

```text
v1.0.1
```

## 49. Tag criada no commit errado e ainda não publicada

Posso excluir localmente:

```bash
git tag -d v1.0.0
```

Depois, criar no commit correto:

```bash
git tag -a v1.0.0 CODIGO_CORRETO -m "Primeira versão estável"
```

## 50. Tag já publicada

Antes de alterar uma tag remota, eu comunico a equipe e verifico se alguém já utilizou aquela versão.

A prática mais segura costuma ser criar uma nova versão.

# Parte 10: Tags assinadas

## 51. Conceito

Uma tag pode ser assinada criptograficamente.

Isso ajuda a verificar a autoria e a integridade da marcação.

## 52. Exemplo

```bash
git tag -s v1.0.0 -m "Primeira versão estável"
```

A assinatura exige uma configuração compatível, como uma chave GPG ou outro método aceito pelo ambiente utilizado.

## 53. Verificação

```bash
git tag -v v1.0.0
```

## 54. Escopo da aula

Nesta aula, apresento tags assinadas como prática profissional adicional.

A configuração completa das chaves poderá ser realizada em uma atividade avançada.

# Parte 11: Versionamento Semântico

## 55. Estrutura

O Versionamento Semântico utiliza:

```text
MAJOR.MINOR.PATCH
```

Exemplo:

```text
2.4.3
```

Onde:

```text
2

MAJOR
```

```text
4

MINOR
```

```text
3

PATCH
```

## 56. Versão Major

A versão Major aumenta quando existe uma mudança incompatível com a versão anterior.

Exemplo:

```text
1.4.2 → 2.0.0
```

Situações possíveis:

1. Remoção de uma funcionalidade utilizada pelos usuários.
2. Alteração incompatível de uma API.
3. Mudança estrutural que exige adaptação.
4. Novo formato que não aceita dados anteriores.

## 57. Versão Minor

A versão Minor aumenta quando adicionamos funcionalidade compatível com a versão anterior.

Exemplo:

```text
1.4.2 → 1.5.0
```

Situações possíveis:

1. Nova página.
2. Novo filtro.
3. Novo relatório.
4. Nova opção de configuração.
5. Melhoria funcional que não quebra o uso anterior.

## 58. Versão Patch

A versão Patch aumenta quando corrigimos um problema sem quebrar compatibilidade.

Exemplo:

```text
1.4.2 → 1.4.3
```

Situações possíveis:

1. Correção de link.
2. Ajuste de cálculo.
3. Correção de texto.
4. Correção de estilo.
5. Correção de segurança compatível.

## 59. Regra resumida

```text
Quebrou compatibilidade?

MAJOR
```

```text
Adicionou funcionalidade compatível?

MINOR
```

```text
Corrigiu um problema compatível?

PATCH
```

## 60. Exemplo completo

Versão atual:

```text
1.2.4
```

### Correção de link

```text
1.2.5
```

### Nova página compatível

```text
1.3.0
```

### Mudança incompatível

```text
2.0.0
```

## 61. Reinício dos números menores

Quando aumento Minor, Patch volta para zero:

```text
1.2.4 → 1.3.0
```

Quando aumento Major, Minor e Patch voltam para zero:

```text
1.3.7 → 2.0.0
```

# Parte 12: Desenvolvimento inicial

## 62. Versões abaixo de 1.0.0

Projetos em desenvolvimento inicial podem utilizar:

```text
0.1.0

0.2.0

0.9.0
```

A versão `1.0.0` normalmente representa a definição da primeira interface pública estável do projeto.

## 63. Exemplo do curso

Poderíamos utilizar:

```text
v0.1.0

Estrutura inicial.
```

```text
v0.5.0

Funcionalidades principais em desenvolvimento.
```

```text
v1.0.0

Primeira versão estável apresentada ao usuário.
```

# Parte 13: Pré lançamentos

## 64. Estrutura

Uma versão de pré lançamento acrescenta um identificador depois de um hífen.

Exemplos:

```text
1.0.0-alpha.1

1.0.0-beta.1

1.0.0-rc.1
```

## 65. Alpha

Uma versão alpha representa um estágio inicial de testes.

Pode possuir funcionalidades incompletas ou instabilidade.

## 66. Beta

Uma versão beta está mais avançada, mas ainda passa por validação.

## 67. Release Candidate

`rc` significa candidato a lançamento.

Exemplo:

```text
1.0.0-rc.1
```

A equipe acredita que a versão pode se tornar estável caso nenhum problema importante seja encontrado.

## 68. Ordem conceitual

```text
1.0.0-alpha.1

        ↓

1.0.0-beta.1

        ↓

1.0.0-rc.1

        ↓

1.0.0
```

## 69. Criando uma tag de pré lançamento

```bash
git tag -a v1.0.0-rc.1 -m "Primeiro candidato da versão 1.0.0"

git push origin v1.0.0-rc.1
```

No GitHub, marco a Release como pré lançamento.

# Parte 14: Metadados de compilação

## 70. Estrutura

Metadados podem ser acrescentados depois de `+`.

Exemplo:

```text
1.0.0+20260804
```

```text
1.0.0+build.45
```

## 71. Finalidade

Metadados podem identificar:

1. Número de build.
2. Data.
3. Ambiente.
4. Processo de compilação.

Eles não alteram a precedência da versão segundo o Versionamento Semântico.

## 72. Escopo

No Portal da Turma, utilizaremos principalmente:

```text
MAJOR.MINOR.PATCH
```

Pré lançamentos serão utilizados em desafios.

# Parte 15: Decidindo a próxima versão

## 73. Cenário 1

Versão atual:

```text
1.0.0
```

Alteração:

```text
Corrige um erro no link da página de alunos.
```

Próxima versão:

```text
1.0.1
```

## 74. Cenário 2

Versão atual:

```text
1.0.1
```

Alteração:

```text
Adiciona uma nova página de eventos sem quebrar as páginas existentes.
```

Próxima versão:

```text
1.1.0
```

## 75. Cenário 3

Versão atual:

```text
1.4.3
```

Alteração:

```text
Remove o formato antigo de cadastro e exige um novo formato incompatível.
```

Próxima versão:

```text
2.0.0
```

## 76. Cenário 4

Versão atual:

```text
2.3.8
```

Alteração:

```text
Corrige uma falha de segurança sem alterar a interface pública.
```

Próxima versão:

```text
2.3.9
```

# Parte 16: O que é um changelog?

## 77. Conceito

Um changelog é um arquivo que registra mudanças relevantes de cada versão.

Nome comum:

```text
CHANGELOG.md
```

## 78. Objetivo

O changelog ajuda usuários e colaboradores a descobrir:

1. O que foi adicionado.
2. O que mudou.
3. O que foi corrigido.
4. O que foi removido.
5. O que foi descontinuado.
6. O que mudou em segurança.
7. Quando a versão foi publicada.

## 79. Changelog não é o git log

O histórico de commits pode conter mensagens técnicas e intermediárias.

Exemplo:

```text
Corrige indentação

Ajusta texto

Atualiza teste

Resolve comentário
```

O changelog reúne mudanças relevantes para quem usa ou acompanha o projeto.

## 80. Ordem cronológica inversa

As versões mais recentes aparecem primeiro.

Exemplo:

```text
2.0.0

1.1.0

1.0.1

1.0.0
```

# Parte 17: Estrutura do CHANGELOG

## 81. Criando o arquivo

Na raiz do projeto, crio:

```text
CHANGELOG.md
```

## 82. Modelo inicial

```md
# Changelog

Todas as mudanças relevantes deste projeto serão documentadas neste arquivo.

O formato está baseado no Keep a Changelog e o projeto utiliza Versionamento Semântico.

## [Não publicado]

### Adicionado

### Alterado

### Corrigido

### Removido

## [1.0.0] - 2026-08-04

### Adicionado

1. Página inicial do Portal da Turma.
2. Página de apresentação da turma.
3. Página de alunos.
4. Página de projetos.
5. Navegação entre as páginas.
6. Documentação inicial.
```

## 83. Seção Não publicado

A seção `Não publicado` reúne mudanças que ainda não pertencem a uma versão liberada.

Quando chega o momento do lançamento, movemos as entradas para a nova versão.

## 84. Categorias recomendadas

### Adicionado

Novas funcionalidades.

### Alterado

Mudanças em funcionalidades existentes.

### Descontinuado

Funcionalidades que serão removidas futuramente.

### Removido

Funcionalidades removidas.

### Corrigido

Correções de problemas.

### Segurança

Correções ou mudanças relacionadas à segurança.

## 85. Exemplo mais completo

```md
## [1.1.0] - 2026-08-18

### Adicionado

1. Página de eventos da turma.
2. Filtro de projetos por tecnologia.

### Alterado

1. Menu principal reorganizado para telas menores.

### Corrigido

1. Link da página de contato.
2. Contraste do texto no rodapé.
```

# Parte 18: Changelog com links de comparação

## 86. Referências no final do arquivo

Podemos criar links para comparar versões.

Exemplo:

```md
[Não publicado]: https://github.com/USUARIO/portal_da_turma/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/USUARIO/portal_da_turma/releases/tag/v1.0.0
```

## 87. Depois da versão 1.0.1

```md
[Não publicado]: https://github.com/USUARIO/portal_da_turma/compare/v1.0.1...HEAD
[1.0.1]: https://github.com/USUARIO/portal_da_turma/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/USUARIO/portal_da_turma/releases/tag/v1.0.0
```

> Substitua `USUARIO` e o nome do repositório pelos dados reais.

# Parte 19: Changelog e release notes

## 88. Changelog

É um documento contínuo dentro do repositório.

Ele reúne mudanças de várias versões.

## 89. Release notes

São as notas específicas de uma publicação.

Elas podem destacar:

1. Principais novidades.
2. Correções importantes.
3. Instruções de atualização.
4. Problemas conhecidos.
5. Colaboradores.
6. Links relacionados.

## 90. Relação entre os dois

O changelog pode servir como base para as release notes.

Porém, as notas de lançamento podem ser mais comunicativas e direcionadas ao usuário.

# Parte 20: Preparando a versão v1.0.0

## 91. Checklist de código

1. Todas as funcionalidades planejadas foram concluídas.
2. Os Pull Requests foram aprovados.
3. Não existem conflitos.
4. Os links funcionam.
5. O projeto foi testado.
6. Não existem credenciais.
7. A branch `main` está atualizada.

## 92. Checklist de gestão

1. Issues da versão foram concluídas.
2. O milestone foi revisado.
3. Pendências foram movidas para outra versão.
4. O Project representa a situação real.
5. Responsáveis confirmaram as entregas.

## 93. Checklist de documentação

1. README atualizado.
2. CHANGELOG atualizado.
3. Instruções de execução verificadas.
4. Versão informada quando necessário.
5. Licença revisada.

## 94. Atualizando o changelog

Crio ou edito:

```text
CHANGELOG.md
```

Depois:

```bash
git status

git diff

git add CHANGELOG.md

git commit -m "Documenta as mudanças da versão 1.0.0"

git push origin main
```

## 95. Confirmando a main

```bash
git switch main

git pull origin main

git status
```

## 96. Criando a tag

```bash
git tag -a v1.0.0 -m "Primeira versão estável do Portal da Turma"
```

## 97. Conferindo

```bash
git show v1.0.0
```

## 98. Publicando

```bash
git push origin v1.0.0
```

# Parte 21: Criando uma GitHub Release

## 99. Acessando a área de Releases

Na página do repositório, acesso a área de Releases.

Seleciono a opção para criar uma nova publicação.

A interface poderá mudar com o tempo, mas os elementos principais permanecem semelhantes.

## 100. Escolhendo a tag

Seleciono:

```text
v1.0.0
```

Se a tag ainda não existir, o GitHub também poderá permitir sua criação durante o processo.

Nesta aula, criamos e publicamos a tag pelo terminal antes da Release.

## 101. Definindo o título

Exemplo:

```text
Portal da Turma 1.0.0
```

## 102. Escrevendo as notas

```md
# Portal da Turma 1.0.0

Esta é a primeira versão estável do projeto desenvolvido durante o curso de Git e GitHub.

## Principais recursos

1. Página inicial.
2. Apresentação da turma.
3. Lista de alunos.
4. Página de projetos.
5. Navegação entre páginas.
6. Layout responsivo básico.
7. Documentação do projeto.

## Como executar

1. Baixe o código fonte ou clone o repositório.
2. Abra a pasta no Visual Studio Code.
3. Abra o arquivo index.html no navegador.

## Observações

Esta versão representa a conclusão das funcionalidades planejadas para a primeira entrega estável.
```

## 103. Rascunho

Uma Release em rascunho ainda não fica publicada como lançamento final.

Eu utilizo o rascunho para:

1. Revisar o texto.
2. Conferir a tag.
3. Anexar arquivos.
4. Solicitar validação.
5. Preparar uma publicação futura.

## 104. Pré release

Marco como pré release quando a versão ainda é experimental.

Exemplo:

```text
v1.1.0-beta.1
```

## 105. Última versão

Uma Release estável poderá ser indicada como a versão mais recente.

Pré releases normalmente não substituem a última versão estável para os usuários que procuram uma entrega final.

## 106. Publicando

Depois de revisar:

1. Tag correta.
2. Título.
3. Descrição.
4. Arquivos.
5. Indicação de estabilidade.

Confirmo a publicação.

# Parte 22: Arquivos da Release

## 107. Código fonte

O GitHub disponibiliza arquivos compactados do código correspondente à tag.

Normalmente aparecem opções de código fonte em formatos como ZIP e tarball.

## 108. Assets adicionais

Podemos anexar:

1. Executáveis.
2. Instaladores.
3. Documentos em PDF.
4. Arquivos compilados.
5. Pacotes.
6. Checksums.

## 109. Cuidado

Não anexo:

1. Senhas.
2. Chaves privadas.
3. Dados pessoais.
4. Configurações secretas.
5. Arquivos não verificados.

## 110. Projeto HTML

Para o Portal da Turma, a tag e o código fonte podem ser suficientes.

Em um projeto compilado, poderíamos anexar o resultado pronto para uso.

# Parte 23: Notas geradas automaticamente

## 111. Recurso do GitHub

O GitHub pode gerar uma proposta de notas de lançamento com base nas mudanças e nos Pull Requests incluídos desde a versão anterior.

## 112. Benefício

Esse recurso ajuda a:

1. Listar contribuições.
2. Identificar Pull Requests.
3. Criar links de comparação.
4. Acelerar a preparação das notas.

## 113. Revisão humana

Eu não publico o texto gerado sem revisar.

Verifico:

1. Se os títulos são compreensíveis.
2. Se alterações internas precisam aparecer.
3. Se existe informação importante ausente.
4. Se as categorias estão adequadas.
5. Se o texto atende ao usuário.

## 114. Configuração avançada

O comportamento das notas automáticas pode ser configurado por um arquivo como:

```text
.github/release.yml
```

Exemplo:

```yaml
changelog:
  categories:
    - title: Novidades
      labels:
        - enhancement
        - feature

    - title: Correções
      labels:
        - bug
        - fix

    - title: Documentação
      labels:
        - documentation
```

Essa configuração utiliza labels para organizar as alterações em categorias.

# Parte 24: Criando a versão de correção v1.0.1

## 115. Problema encontrado

Depois da publicação de `v1.0.0`, identificamos:

```text
O link Projetos aponta para projeto.html, mas o arquivo correto é projetos.html.
```

## 116. Criando a Issue

Título:

```text
Corrigir link da página de projetos
```

Label:

```text
bug
```

Milestone:

```text
v1.0.1
```

## 117. Criando a branch

```bash
git switch main

git pull origin main

git switch -c fix/link_pagina_projetos
```

## 118. Corrigindo

Alterar:

```html
<a href="projeto.html">Projetos</a>
```

Para:

```html
<a href="projetos.html">Projetos</a>
```

## 119. Registrando

```bash
git status

git diff

git add index.html

git commit -m "Corrige o link da página de projetos"

git push -u origin fix/link_pagina_projetos
```

## 120. Pull Request

Criar o Pull Request para:

```text
base: main

compare: fix/link_pagina_projetos
```

Depois:

1. Revisar.
2. Aprovar.
3. Realizar o merge.
4. Excluir a branch.

## 121. Atualizando o changelog

```md
## [Não publicado]

## [1.0.1] - 2026-08-11

### Corrigido

1. Link da página de projetos no menu principal.

## [1.0.0] - 2026-08-04

### Adicionado

1. Primeira versão estável do Portal da Turma.
```

## 122. Registrando o changelog

```bash
git switch main

git pull origin main

git add CHANGELOG.md

git commit -m "Documenta a correção da versão 1.0.1"

git push origin main
```

## 123. Criando a tag

```bash
git tag -a v1.0.1 -m "Corrige o link da página de projetos"
```

## 124. Publicando

```bash
git push origin v1.0.1
```

## 125. Criando a Release

Título:

```text
Portal da Turma 1.0.1
```

Notas:

```md
# Portal da Turma 1.0.1

## Correção

1. Corrigido o link da página de projetos no menu principal.

## Atualização

Usuários da versão 1.0.0 devem utilizar esta versão para receber a correção de navegação.
```

# Parte 25: Versão Minor v1.1.0

## 126. Nova funcionalidade

A equipe adiciona:

```text
Página de eventos da turma.
```

A mudança é compatível com a versão anterior.

Próxima versão:

```text
1.1.0
```

## 127. Changelog

```md
## [1.1.0] - 2026-09-01

### Adicionado

1. Página de eventos.
2. Calendário das próximas atividades.

### Alterado

1. Menu principal atualizado com o item Eventos.
```

## 128. Tag

```bash
git tag -a v1.1.0 -m "Adiciona a página de eventos"

git push origin v1.1.0
```

# Parte 26: Versão Major v2.0.0

## 129. Mudança incompatível

Imagine que a versão 2 remove as páginas HTML separadas e passa a utilizar uma estrutura completamente nova que exige atualização dos links e integrações externas.

A mudança não mantém compatibilidade com o uso anterior.

Próxima versão:

```text
2.0.0
```

## 130. Comunicação obrigatória

Uma versão Major precisa explicar claramente:

1. O que deixou de funcionar.
2. O que foi removido.
3. Como migrar.
4. Quais requisitos mudaram.
5. Quais alternativas existem.

## 131. Exemplo de notas

```md
# Portal da Turma 2.0.0

## Mudanças importantes

A estrutura de navegação foi reconstruída e não utiliza mais as páginas individuais da versão 1.

## Como migrar

1. Atualize links personalizados.
2. Revise integrações que apontavam para arquivos HTML específicos.
3. Utilize as novas rotas documentadas no README.
```

# Parte 27: Identificando a versão pelo terminal

## 132. Tag mais próxima

```bash
git describe --tags --always
```

Resultado possível:

```text
v1.0.1
```

Quando existem commits depois da tag, poderá aparecer uma descrição semelhante a:

```text
v1.0.1-3-g8ac42f1
```

## 133. Interpretação

```text
v1.0.1

Tag mais próxima.
```

```text
3

Quantidade de commits depois da tag.
```

```text
g8ac42f1

Identificador abreviado do commit atual.
```

## 134. Utilidade

Esse comando pode ajudar a identificar builds de desenvolvimento entre versões oficiais.

# Parte 28: Comparando versões

## 135. Commits entre duas tags

```bash
git log v1.0.0..v1.0.1 --oneline
```

## 136. Diferenças de conteúdo

```bash
git diff v1.0.0..v1.0.1
```

## 137. Arquivos modificados

```bash
git diff --name-only v1.0.0..v1.0.1
```

## 138. Estatísticas

```bash
git diff --stat v1.0.0..v1.0.1
```

## 139. Uso profissional

Antes de escrever as notas, eu comparo as tags para confirmar o que realmente mudou.

# Parte 29: Fluxo profissional de lançamento

## 140. Planejamento

1. Definir escopo da versão.
2. Criar milestone.
3. Relacionar Issues.
4. Definir responsáveis.
5. Acompanhar no Project.

## 141. Desenvolvimento

1. Criar branches.
2. Desenvolver.
3. Criar commits.
4. Abrir Pull Requests.
5. Revisar.
6. Integrar.

## 142. Preparação

1. Atualizar `main`.
2. Testar.
3. Revisar segurança.
4. Atualizar README.
5. Atualizar CHANGELOG.
6. Confirmar número da versão.

## 143. Publicação

1. Criar tag anotada.
2. Inspecionar tag.
3. Publicar tag.
4. Criar Release em rascunho.
5. Revisar notas.
6. Anexar arquivos.
7. Publicar Release.

## 144. Depois do lançamento

1. Comunicar a equipe.
2. Encerrar milestone.
3. Verificar downloads ou feedback.
4. Criar Issues para problemas encontrados.
5. Preparar a próxima versão.

# Parte 30: Papéis da equipe

## 145. Responsável pela versão

1. Confirma o escopo.
2. Verifica o status das Issues.
3. Coordena a preparação.
4. Confirma a versão.

## 146. Desenvolvedores

1. Concluem as tarefas.
2. Testam as alterações.
3. Atualizam documentação.
4. Respondem revisões.

## 147. Revisores

1. Verificam Pull Requests.
2. Testam funcionalidades.
3. Validam correções.
4. Confirmam critérios.

## 148. Responsável pela publicação

1. Atualiza o changelog.
2. Cria a tag.
3. Confere o commit.
4. Cria as notas.
5. Publica a Release.

## 149. Responsabilidade compartilhada

Uma Release não deve depender de uma única pessoa sem revisão.

A equipe confirma coletivamente que o estado marcado pode ser apresentado aos usuários.

# Parte 31: Erros comuns

## 150. Criar tag na branch errada

Antes:

```bash
git branch --show-current

git status

git log -1 --oneline
```

## 151. Criar tag antes do commit do changelog

Se a tag for criada antes da atualização do changelog, a versão marcada não conterá a documentação final.

Primeiro, crio o commit.

Depois, crio a tag.

## 152. Esquecer de publicar a tag

A tag existe localmente, mas não aparece no GitHub.

Solução:

```bash
git push origin NOME_DA_TAG
```

## 153. Utilizar somente git push

O envio normal da branch pode não publicar a tag.

Envio a tag explicitamente.

## 154. Alterar uma versão publicada

Evito mover `v1.0.0` para outro commit.

Crio `v1.0.1` ou outra versão apropriada.

## 155. Escolher versão pelo tamanho do trabalho

Versionamento Semântico não depende apenas da quantidade de linhas modificadas.

Depende do impacto e da compatibilidade.

Uma correção grande ainda pode ser Patch.

Uma pequena remoção incompatível pode exigir Major.

## 156. Changelog com todos os commits

O changelog deve apresentar mudanças relevantes, não copiar o histórico sem curadoria.

## 157. Release sem instruções

Uma Release precisa ajudar o usuário a compreender e utilizar a versão.

## 158. Marcar versão estável como pré release

Confiro as opções antes da publicação.

## 159. Publicar segredo como asset

Reviso todos os arquivos anexados.

## 160. Criar versão sem teste

A tag identifica o estado existente. Ela não garante qualidade.

# Parte 32: Prática guiada completa

## 161. Etapa 1: Atualizar a main

```bash
git switch main

git pull origin main

git status
```

## 162. Etapa 2: Testar

Verificar:

```text
Página inicial

Menu

Página sobre

Página de alunos

Página de projetos

Documentação
```

## 163. Etapa 3: Atualizar o changelog

Criar ou atualizar:

```text
CHANGELOG.md
```

## 164. Etapa 4: Registrar

```bash
git add CHANGELOG.md

git commit -m "Documenta as mudanças da versão 1.0.0"

git push origin main
```

## 165. Etapa 5: Criar a tag

```bash
git tag -a v1.0.0 -m "Primeira versão estável do Portal da Turma"
```

## 166. Etapa 6: Inspecionar

```bash
git show v1.0.0
```

## 167. Etapa 7: Publicar

```bash
git push origin v1.0.0
```

## 168. Etapa 8: Criar Release em rascunho

Configurar:

```text
Tag: v1.0.0

Título: Portal da Turma 1.0.0
```

## 169. Etapa 9: Revisar notas

Conferir:

1. Recursos.
2. Correções.
3. Instruções.
4. Arquivos.
5. Links.

## 170. Etapa 10: Publicar

Publicar a Release estável.

## 171. Etapa 11: Conferir

1. Tag visível.
2. Release visível.
3. Código fonte disponível.
4. Notas corretas.
5. Link do changelog funcionando.

# Parte 33: Atividade colaborativa

## 172. Objetivo

Cada equipe preparará uma versão simulada do Portal da Turma.

## 173. Equipes

Cada grupo terá:

1. Responsável pela versão.
2. Responsável pelo changelog.
3. Responsável pelos testes.
4. Responsável pela tag.
5. Responsável pelas release notes.

Em equipes menores, um aluno poderá assumir mais de um papel.

## 174. Cenário

Versão atual:

```text
1.0.0
```

Mudanças realizadas:

1. Nova página de eventos.
2. Correção de dois links.
3. Melhoria do menu responsivo.
4. Atualização do README.

## 175. Pergunta

Qual deve ser a próxima versão?

Resposta esperada:

```text
1.1.0
```

A nova funcionalidade compatível exige incremento Minor.

## 176. Entrega da equipe

1. Número escolhido.
2. Justificativa.
3. Seção do changelog.
4. Mensagem da tag.
5. Release notes.
6. Checklist de testes.
7. Evidência da tag.
8. Evidência da Release em rascunho.

## 177. Regra

A Release não será publicada até que outro grupo revise o material.

# Parte 34: Exercícios de fixação

## 178. Exercício 1: Conceitos

Responda com suas palavras.

1. O que é uma tag?
2. Qual é a diferença entre branch e tag?
3. Qual é a diferença entre tag e Release?
4. O que é uma tag anotada?
5. Por que tags anotadas são adequadas para versões oficiais?
6. Para que serve o Versionamento Semântico?
7. O que representa Major?
8. O que representa Minor?
9. O que representa Patch?
10. O que é uma pré release?
11. Para que serve o changelog?
12. Qual é a diferença entre changelog e release notes?

## 179. Exercício 2: Relacione

### Conceitos

```text
A. Tag

B. Release

C. Major

D. Minor

E. Patch

F. Changelog

G. Pré release

H. Asset
```

### Definições

```text
1. Arquivo adicional anexado a uma publicação.

2. Marca um ponto do histórico.

3. Mudança incompatível.

4. Documento contínuo de mudanças.

5. Publicação associada a uma tag.

6. Correção compatível.

7. Versão ainda não considerada estável.

8. Nova funcionalidade compatível.
```

## 180. Exercício 3: Complete os comandos

### Listar tags

```bash
git __________
```

### Criar tag anotada

```bash
git tag __________ v1.0.0 __________ "Primeira versão"
```

### Inspecionar

```bash
git __________ v1.0.0
```

### Publicar uma tag

```bash
git push origin __________
```

### Excluir localmente

```bash
git tag __________ v1.0.0
```

### Excluir remotamente

```bash
git push origin __________ v1.0.0
```

## 181. Exercício 4: Escolha a versão

Considere a versão atual `1.4.2`.

### Situação 1

Correção de erro de ortografia.

Resposta:

```text
________________
```

### Situação 2

Nova página de notícias compatível.

Resposta:

```text
________________
```

### Situação 3

Remoção incompatível da página utilizada por integrações.

Resposta:

```text
________________
```

### Situação 4

Correção de vulnerabilidade sem mudança incompatível.

Resposta:

```text
________________
```

### Situação 5

Nova opção de tema visual compatível.

Resposta:

```text
________________
```

## 182. Exercício 5: Identifique a versão

Classifique:

```text
2.0.0

1.8.0

1.8.4

3.0.0-beta.1

1.0.0-rc.2

1.0.0+build.18
```

Indique:

1. Major.
2. Minor.
3. Patch.
4. Pré lançamento.
5. Metadado, quando existir.

## 183. Exercício 6: Organize o lançamento

Coloque na ordem correta:

```text
Publicar a Release.

Criar a tag.

Testar o projeto.

Atualizar o changelog.

Publicar a tag.

Atualizar a main.

Revisar as notas.
```

## 184. Exercício 7: Avalie o changelog

Qual entrada é mais adequada?

### Opção A

```text
Várias alterações e correções.
```

### Opção B

```text
Adicionado filtro de projetos por tecnologia.
Corrigido link da página de contato.
Melhorado contraste do menu.
```

Explique sua escolha.

## 185. Exercício 8: Analise o cenário

A tag `v1.0.0` foi criada localmente, mas não aparece no GitHub.

Responda:

1. Qual comando verifica a tag local?
2. Qual comando publica a tag específica?
3. Por que somente `git push` pode não resolver?

## 186. Exercício 9: Comparação

Escreva comandos para:

1. Mostrar commits entre `v1.0.0` e `v1.1.0`.
2. Mostrar arquivos alterados.
3. Mostrar estatísticas.
4. Mostrar a tag mais próxima do commit atual.

# Parte 35: Desafios

## 187. Desafio 1: Primeira tag

Em um repositório de laboratório:

1. Crie três commits.
2. Crie uma tag leve no segundo commit.
3. Crie uma tag anotada no terceiro commit.
4. Compare com `git show`.
5. Explique as diferenças.

## 188. Desafio 2: Changelog completo

Crie um `CHANGELOG.md` com:

1. Seção Não publicado.
2. Versão 1.0.0.
3. Versão 1.0.1.
4. Versão 1.1.0.
5. Categorias adequadas.
6. Datas.
7. Links de comparação.

## 189. Desafio 3: Decisão de versões

Para cada mudança, indique a próxima versão e justifique:

1. Correção de desempenho compatível.
2. Nova API compatível.
3. Remoção de parâmetro obrigatório antigo.
4. Correção de documentação.
5. Nova funcionalidade opcional.
6. Mudança incompatível no formato de dados.

## 190. Desafio 4: Pré release

Crie:

```text
v2.0.0-beta.1
```

Depois:

1. Publique a tag.
2. Crie uma pré release.
3. Escreva riscos conhecidos.
4. Informe como os alunos devem testar.
5. Não marque como versão estável.

## 191. Desafio 5: Release Candidate

Crie:

```text
v2.0.0-rc.1
```

As notas deverão informar:

1. Funcionalidades concluídas.
2. Testes realizados.
3. Problemas conhecidos.
4. Condição para publicar `v2.0.0`.

## 192. Desafio 6: Correção urgente

Depois de publicar `v1.2.0`, simule um erro importante.

Execute todo o fluxo:

1. Issue.
2. Milestone `v1.2.1`.
3. Branch `fix/`.
4. Pull Request.
5. Revisão.
6. Merge.
7. Changelog.
8. Tag.
9. Release.

## 193. Desafio 7: Notas automáticas

Crie:

```text
.github/release.yml
```

Organize categorias por labels.

Crie uma Release em rascunho e analise o resultado gerado.

## 194. Desafio 8: Asset da Release

Crie um arquivo ZIP do projeto ou um documento de instruções.

Anexe a uma Release de laboratório.

Registre:

1. Nome.
2. Tamanho.
3. Finalidade.
4. Procedimento de validação.

## 195. Desafio 9: Auditoria de uma Release

Escolha uma Release pública de um projeto conhecido.

Analise:

1. Número da versão.
2. Tag.
3. Data.
4. Notas.
5. Assets.
6. Indicação de pré release.
7. Comparação com a versão anterior.

Não copie o conteúdo integral. Produza sua própria análise.

## 196. Desafio 10: Plano da versão 2.0.0

Crie um documento com:

1. Mudanças incompatíveis.
2. Plano de migração.
3. Milestone.
4. Issues.
5. Estratégia de beta.
6. Estratégia de release candidate.
7. Critérios para estabilidade.
8. Comunicação aos usuários.

# Parte 36: Avaliação

## 197. Critérios

A atividade poderá valer 10 pontos.

### Preparação da main: 1 ponto

O aluno atualizou e verificou a branch principal.

### Changelog: 2 pontos

O arquivo documenta mudanças relevantes e utiliza uma estrutura organizada.

### Versionamento: 2 pontos

O número escolhido corresponde ao impacto da entrega.

### Tag: 1 ponto

A tag anotada foi criada no commit correto.

### Publicação: 1 ponto

A tag foi enviada ao GitHub.

### Release notes: 1 ponto

As notas são claras e orientadas ao usuário.

### Release: 1 ponto

A publicação foi configurada corretamente.

### Explicação: 1 ponto

O aluno justificou as decisões tomadas.

## 198. Evidências

O aluno deverá apresentar:

1. Resultado de `git status`.
2. `CHANGELOG.md`.
3. Número da versão.
4. Justificativa.
5. Resultado de `git show`.
6. Tag no GitHub.
7. Release em rascunho ou publicada.
8. Release notes.
9. Comparação com a versão anterior.

# Parte 37: Gabarito

## 199. Gabarito do exercício 1

### Questão 1

Tag é uma referência utilizada para marcar um ponto específico do histórico.

### Questão 2

A branch avança com novos commits. A tag normalmente permanece no commit marcado.

### Questão 3

A tag marca o commit. A Release apresenta e distribui a versão associada à tag.

### Questão 4

É uma tag com objeto próprio, autor, data e mensagem.

### Questão 5

Porque registra informações adicionais e documenta a finalidade da marcação.

### Questão 6

Serve para comunicar o impacto e a compatibilidade das versões.

### Questão 7

Mudanças incompatíveis.

### Questão 8

Novas funcionalidades compatíveis.

### Questão 9

Correções compatíveis.

### Questão 10

Versão anterior à entrega estável.

### Questão 11

Documentar mudanças relevantes de cada versão.

### Questão 12

O changelog é contínuo. As release notes descrevem uma publicação específica.

## 200. Gabarito do exercício 2

```text
A corresponde a 2.

B corresponde a 5.

C corresponde a 3.

D corresponde a 8.

E corresponde a 6.

F corresponde a 4.

G corresponde a 7.

H corresponde a 1.
```

## 201. Gabarito do exercício 3

### Listar

```bash
git tag
```

### Criar anotada

```bash
git tag -a v1.0.0 -m "Primeira versão"
```

### Inspecionar

```bash
git show v1.0.0
```

### Publicar

```bash
git push origin v1.0.0
```

### Excluir local

```bash
git tag -d v1.0.0
```

### Excluir remota

```bash
git push origin --delete v1.0.0
```

## 202. Gabarito do exercício 4

Versão atual:

```text
1.4.2
```

### Situação 1

```text
1.4.3
```

### Situação 2

```text
1.5.0
```

### Situação 3

```text
2.0.0
```

### Situação 4

```text
1.4.3
```

### Situação 5

```text
1.5.0
```

## 203. Gabarito do exercício 5

### 2.0.0

```text
Major 2
Minor 0
Patch 0
```

### 1.8.0

```text
Major 1
Minor 8
Patch 0
```

### 1.8.4

```text
Major 1
Minor 8
Patch 4
```

### 3.0.0-beta.1

```text
Major 3
Minor 0
Patch 0
Pré lançamento beta.1
```

### 1.0.0-rc.2

```text
Major 1
Minor 0
Patch 0
Pré lançamento rc.2
```

### 1.0.0+build.18

```text
Major 1
Minor 0
Patch 0
Metadado build.18
```

## 204. Gabarito do exercício 6

Ordem correta:

```text
Atualizar a main.

Testar o projeto.

Atualizar o changelog.

Criar a tag.

Publicar a tag.

Revisar as notas.

Publicar a Release.
```

## 205. Gabarito do exercício 7

A opção B é mais adequada porque apresenta mudanças específicas e organizadas.

## 206. Gabarito do exercício 8

### Verificar localmente

```bash
git tag
```

### Publicar

```bash
git push origin v1.0.0
```

### Explicação

O envio normal da branch não publica necessariamente todas as tags locais.

## 207. Gabarito do exercício 9

### Commits

```bash
git log v1.0.0..v1.1.0 --oneline
```

### Arquivos

```bash
git diff --name-only v1.0.0..v1.1.0
```

### Estatísticas

```bash
git diff --stat v1.0.0..v1.1.0
```

### Tag mais próxima

```bash
git describe --tags --always
```

# Parte 38: Revisão oral

## 208. Perguntas

1. O que é uma tag?
2. Por que uma tag não é igual a uma branch?
3. O que uma Release acrescenta?
4. Qual é a diferença entre tag leve e anotada?
5. Como publicar uma tag?
6. Quando aumentar Patch?
7. Quando aumentar Minor?
8. Quando aumentar Major?
9. O que significa beta?
10. Para que serve `CHANGELOG.md`?
11. O que são release notes?
12. Por que não devemos mover uma tag publicada?
13. Qual comando compara duas tags?
14. O que deve ser verificado antes de uma Release?

# Parte 39: Resumo dos comandos

## 209. Listar tags

```bash
git tag
```

## 210. Criar tag leve

```bash
git tag v0.1.0
```

## 211. Criar tag anotada

```bash
git tag -a v1.0.0 -m "Mensagem da versão"
```

## 212. Criar em commit específico

```bash
git tag -a v1.0.0 CODIGO_DO_COMMIT -m "Mensagem"
```

## 213. Inspecionar

```bash
git show v1.0.0
```

## 214. Publicar uma tag

```bash
git push origin v1.0.0
```

## 215. Publicar todas

```bash
git push origin --tags
```

## 216. Excluir local

```bash
git tag -d v1.0.0
```

## 217. Excluir remota

```bash
git push origin --delete v1.0.0
```

## 218. Ordenar

```bash
git tag --sort=-v:refname
```

## 219. Descrever o commit atual

```bash
git describe --tags --always
```

## 220. Comparar commits

```bash
git log v1.0.0..v1.1.0 --oneline
```

## 221. Comparar arquivos

```bash
git diff --name-only v1.0.0..v1.1.0
```

# Parte 40: Fluxo completo da aula

## 222. Preparação

```bash
git switch main

git pull origin main

git status
```

## 223. Documentação

```bash
git add CHANGELOG.md

git commit -m "Documenta as mudanças da versão 1.0.0"

git push origin main
```

## 224. Tag

```bash
git tag -a v1.0.0 -m "Primeira versão estável do Portal da Turma"

git show v1.0.0

git push origin v1.0.0
```

## 225. GitHub

```text
Criar Release

Selecionar v1.0.0

Escrever notas

Revisar

Publicar
```

## 226. Próxima correção

```text
Issue

Branch fix

Pull Request

Merge

CHANGELOG

Tag v1.0.1

Release v1.0.1
```

# Parte 41: Encerramento

## 227. O que aprendemos

Nesta aula, eu mostrei que uma versão profissional não é apenas um número colocado no projeto.

Ela representa uma decisão de entrega.

Aprendemos que:

```text
Commit registra uma mudança.

Branch acompanha uma linha de desenvolvimento.

Tag marca um ponto específico.

Versionamento comunica impacto e compatibilidade.

Changelog documenta a evolução.

Release apresenta a versão aos usuários.
```

Também aprendemos que o número da versão deve ser escolhido pelo significado da mudança.

```text
Major para incompatibilidade.

Minor para funcionalidade compatível.

Patch para correção compatível.
```

## 228. Preparação para a próxima aula

Na Aula 8, vamos concluir o curso com:

1. Introdução ao GitHub Actions.
2. Criação de workflows.
3. Execução automática em push e Pull Request.
4. Verificações de arquivos.
5. Publicação com GitHub Pages.
6. Revisão do fluxo completo.
7. Apresentação do projeto final.

## 229. Frase de encerramento

Uma tag marca onde o projeto chegou.

Uma versão explica o que essa chegada significa.

Uma Release transforma o histórico técnico em uma entrega compreensível para usuários, equipes e organizações.

# Referências

1. Documentação oficial do Git sobre tags  
   https://git-scm.com/docs/git-tag/pt_BR

2. Livro oficial Pro Git sobre tags  
   https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Tags

3. Documentação oficial do GitHub sobre Releases  
   https://docs.github.com/pt/repositories/releasing-projects-on-github/about-releases

4. Documentação oficial do GitHub sobre gerenciamento de Releases  
   https://docs.github.com/pt/repositories/releasing-projects-on-github/managing-releases-in-a-repository

5. Documentação oficial do GitHub sobre notas automáticas  
   https://docs.github.com/pt/repositories/releasing-projects-on-github/automatically-generated-release-notes

6. Especificação oficial do Versionamento Semântico 2.0.0  
   https://semver.org/lang/pt-BR/spec/v2.0.0.html

7. Keep a Changelog  
   https://keepachangelog.com/pt-BR/1.1.0/

8. Referência oficial de comandos Git  
   https://git-scm.com/docs
