# Aula 5: Conflitos e Recuperação de Alterações

## Git e GitHub na Prática

### Carga horária

4 horas

### Tema da aula

Identificação e resolução de conflitos, cancelamento de integrações e recuperação segura de alterações com `restore`, `revert`, `reset`, `stash` e `reflog`.

## 1. Apresentação da aula

Nas aulas anteriores, eu ensinei você a criar branches, desenvolver funcionalidades separadamente, abrir Pull Requests, revisar alterações e realizar merges.

Quando duas branches modificam arquivos diferentes, o Git normalmente consegue integrar tudo automaticamente. O mesmo costuma acontecer quando as alterações estão em linhas diferentes.

O conflito aparece quando duas mudanças competem pelo mesmo espaço ou quando uma branch altera um arquivo que outra branch excluiu.

Exemplo:

```html
<h1>Portal Acadêmico da Turma</h1>
```

Em outra branch:

```html
<h1>Comunidade de Desenvolvedores</h1>
```

O Git não sabe qual decisão representa a vontade da equipe. Por isso, interrompe o merge e pede nossa participação.

Nesta aula, eu vou tratar o conflito como uma decisão pendente. Também vou mostrar como recuperar alterações sem agir por tentativa.

## 2. Objetivos da aula

Nesta aula, eu vou ensinar você a:

1. Entender o que é um conflito.

2. Identificar situações que provocam conflitos.

3. Criar um conflito controlado.

4. Interpretar as mensagens do Git.

5. Localizar arquivos não integrados.

6. Interpretar marcadores de conflito.

7. Escolher o conteúdo final.

8. Remover os marcadores.

9. Marcar arquivos como resolvidos.

10. Concluir ou cancelar um merge.

11. Resolver conflitos no Visual Studio Code.

12. Compreender conflitos em Pull Requests.

13. Utilizar `git restore`.

14. Retirar arquivos da área de preparação.

15. Utilizar `git revert`.

16. Diferenciar os modos de `git reset`.

17. Guardar alterações com `git stash`.

18. Recuperar referências com `git reflog`.

19. Escolher o comando adequado para cada situação.

20. Evitar perda de trabalho.

## 3. Resultados esperados

Ao final da aula, você deverá compreender este fluxo:

```text
Identificar o conflito

Executar git status

Abrir o arquivo conflitante

Comparar as versões

Escolher o conteúdo final

Remover os marcadores

Testar o projeto

Executar git add

Concluir o merge

Publicar a resolução
```

Também deverá compreender esta relação:

```text
Alteração local sem commit

git restore
```

```text
Commit compartilhado que precisa ser desfeito

git revert
```

```text
Histórico local que precisa ser reposicionado

git reset
```

```text
Trabalho incompleto que precisa ser guardado

git stash
```

```text
Commit aparentemente perdido

git reflog
```

## 4. Conhecimentos necessários

1. Repositório local e remoto.

2. Branch `main`.

3. Branch de funcionalidade.

4. Área de trabalho.

5. Área de preparação.

6. Commit.

7. Merge.

8. Pull Request.

9. Comandos básicos do Git.

## 5. Recursos necessários

1. Computador conectado à internet.

2. Git instalado.

3. Visual Studio Code.

4. Conta no GitHub.

5. Repositório de laboratório.

6. Projeto com pelo menos uma página HTML.

## 6. Organização das quatro horas

### Primeiro momento: 25 minutos

Revisão de merge e apresentação do conceito de conflito.

### Segundo momento: 45 minutos

Criação controlada de um conflito.

### Terceiro momento: 40 minutos

Resolução pelo terminal e pelo Visual Studio Code.

### Intervalo: 15 minutos

### Quarto momento: 30 minutos

Conflitos em Pull Requests e cancelamento de merge.

### Quinto momento: 45 minutos

Prática com `restore`, `revert` e `reset`.

### Sexto momento: 25 minutos

Prática com `stash` e `reflog`.

### Sétimo momento: 15 minutos

Exercícios, desafios e encerramento.

# Parte 1: Entendendo conflitos

## 7. O Git tenta integrar automaticamente

Quando executo:

```bash
git switch main

git merge feature/pagina_sobre
```

o Git compara os históricos.

Se as alterações não competirem, ele conclui o merge sem pedir ajuda.

Exemplo:

```text
main alterou index.html

feature/pagina_sobre criou sobre.html
```

## 8. Quando o Git precisa de ajuda

Conflitos comuns:

1. Duas branches alteraram a mesma linha.

2. Uma branch alterou um arquivo e outra excluiu esse arquivo.

3. Duas branches renomearam o mesmo arquivo de formas diferentes.

4. Alterações próximas não podem ser combinadas com segurança.

5. Um Pull Request ficou incompatível com a branch base.

## 9. Conflito não significa trabalho errado

Duas pessoas podem ter criado soluções tecnicamente válidas. O conflito mostra apenas que o projeto precisa escolher uma versão final.

```text
Git encontrou duas possibilidades.

Ele não conhece a intenção da equipe.

A equipe precisa decidir.
```

# Parte 2: Criando o laboratório

## 10. Criando o repositório

```bash
mkdir laboratorio_conflitos

cd laboratorio_conflitos

git init

git branch -M main
```

## 11. Criando index.html

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Portal da Turma</title>
</head>

<body>
    <header>
        <h1>Portal da Turma</h1>

        <p>Aprendendo Git e GitHub.</p>
    </header>

    <main>
        <h2>Conteúdos</h2>

        <ul>
            <li>Git</li>
            <li>GitHub</li>
            <li>Branches</li>
            <li>Pull Requests</li>
        </ul>
    </main>
</body>
</html>
```

## 12. Primeiro commit

```bash
git status

git add index.html

git commit -m "Cria a página inicial do laboratório"
```

# Parte 3: Criando o conflito controlado

## 13. Criando a branch

```bash
git switch -c feature/cabecalho
```

Na branch, altero o cabeçalho para:

```html
<h1>Comunidade de Desenvolvedores</h1>

<p>Aprendendo tecnologia de forma colaborativa.</p>
```

Registro:

```bash
git add index.html

git commit -m "Atualiza o cabeçalho do portal"
```

## 14. Alterando a main

```bash
git switch main
```

Na `main`, altero as mesmas linhas para:

```html
<h1>Portal Acadêmico da Turma</h1>

<p>Curso prático de controle de versão.</p>
```

Registro:

```bash
git add index.html

git commit -m "Atualiza o título principal do portal"
```

## 15. Visualizando as linhas

```bash
git log --oneline --all --graph --decorate
```

Resultado possível:

```text
* a912f10 (HEAD -> main) Atualiza o título principal do portal
| * c721b44 (feature/cabecalho) Atualiza o cabeçalho do portal
|/
* 43a8b72 Cria a página inicial do laboratório
```

# Parte 4: Provocando o conflito

## 16. Executando o merge

```bash
git merge feature/cabecalho
```

Mensagem possível:

```text
Auto-merging index.html

CONFLICT (content): Merge conflict in index.html

Automatic merge failed; fix conflicts and then commit the result.
```

## 17. Verificando

```bash
git status
```

O Git poderá apresentar:

```text
You have unmerged paths.

both modified: index.html
```

Nesse momento:

1. O merge não foi concluído.

2. O arquivo precisa de decisão.

3. Não devo executar push.

4. Preciso resolver ou cancelar.

# Parte 5: Marcadores de conflito

## 18. Estrutura dos marcadores

```html
<<<<<<< HEAD
<h1>Portal Acadêmico da Turma</h1>

<p>Curso prático de controle de versão.</p>
=======
<h1>Comunidade de Desenvolvedores</h1>

<p>Aprendendo tecnologia de forma colaborativa.</p>
>>>>>>> feature/cabecalho
```

## 19. HEAD

```text
<<<<<<< HEAD
```

Representa o conteúdo da branch atual. Como o merge começou na `main`, esse bloco pertence à `main`.

## 20. Separador

```text
=======
```

Divide as duas versões.

## 21. Outra branch

```text
>>>>>>> feature/cabecalho
```

Identifica o conteúdo que veio da branch integrada.

## 22. Regra essencial

Os marcadores não podem permanecer no arquivo final.

# Parte 6: Resolvendo o conflito

## 23. Possíveis decisões

Manter a versão da `main`:

```html
<h1>Portal Acadêmico da Turma</h1>

<p>Curso prático de controle de versão.</p>
```

Manter a versão da funcionalidade:

```html
<h1>Comunidade de Desenvolvedores</h1>

<p>Aprendendo tecnologia de forma colaborativa.</p>
```

Combinar as ideias:

```html
<h1>Portal Acadêmico da Comunidade de Desenvolvedores</h1>

<p>Aprendendo controle de versão de forma colaborativa.</p>
```

## 24. Resolução escolhida

Para o laboratório, utilizo a versão combinada:

```html
<header>
    <h1>Portal Acadêmico da Comunidade de Desenvolvedores</h1>

    <p>Aprendendo controle de versão de forma colaborativa.</p>
</header>
```

Depois:

1. Apago os marcadores.

2. Salvo o arquivo.

3. Abro a página no navegador.

4. Verifico o conteúdo final.

## 25. Marcando como resolvido

```bash
git add index.html
```

Verifico:

```bash
git status
```

Mensagem possível:

```text
All conflicts fixed but you are still merging.
```

## 26. Concluindo

```bash
git commit -m "Resolve conflito no cabeçalho do portal"
```

Também posso utilizar:

```bash
git merge --continue
```

## 27. Conferindo o histórico

```bash
git log --oneline --all --graph --decorate
```

# Parte 7: Visual Studio Code

## 28. Opções visuais

O editor poderá mostrar opções como:

```text
Accept Current Change

Accept Incoming Change

Accept Both Changes

Compare Changes
```

### Current Change

Mantém a versão da branch atual.

### Incoming Change

Mantém a versão que está chegando.

### Accept Both Changes

Mantém os dois blocos. Ainda preciso reorganizar o resultado.

### Compare Changes

Mostra as versões para comparação.

## 29. Cuidado

Não escolho uma opção apenas para retirar o aviso. Sempre reviso o conteúdo final.

# Parte 8: Conflito de alteração e exclusão

## 30. Situação

Uma branch altera `contato.html`. Outra branch exclui esse arquivo.

A equipe precisa decidir se o arquivo:

1. Continua existindo com a alteração.

2. Permanece excluído.

Para manter:

```bash
git add contato.html
```

Para confirmar a exclusão:

```bash
git rm contato.html
```

Depois:

```bash
git commit -m "Resolve conflito da página de contato"
```

# Parte 9: Cancelando merge

## 31. Quando cancelar

1. Escolhi a branch errada.

2. O conflito precisa ser discutido.

3. A integração ocorreu no momento errado.

4. Quero retornar ao estado anterior.

Comando:

```bash
git merge --abort
```

Depois:

```bash
git status

git log --oneline --all --graph --decorate
```

## 32. Prevenção

Antes de iniciar merge:

```bash
git status

git switch main

git pull origin main
```

A área de trabalho deve estar limpa.

# Parte 10: Conflitos em Pull Requests

## 33. Conflito no GitHub

Quando a branch de comparação conflita com a base, o merge fica bloqueado até a resolução.

Conflitos simples de linhas podem ser resolvidos no editor do GitHub quando a opção estiver disponível.

Conflitos complexos devem ser resolvidos localmente.

## 34. Resolução local

```bash
git fetch origin

git switch feature/pagina_projetos

git pull

git merge origin/main
```

Depois de resolver:

```bash
git add .

git commit -m "Resolve conflitos com a branch main"

git push
```

O Pull Request recebe o novo commit e deve ser revisado novamente.

# Parte 11: Restore, revert e reset

## 35. Diferença conceitual

```text
restore

Trabalha com arquivos na área de trabalho e na preparação.
```

```text
revert

Cria um novo commit que desfaz outro commit.
```

```text
reset

Reposiciona a referência atual e pode modificar preparação e arquivos.
```

# Parte 12: Git restore

## 36. Descartando alteração local

Alterei um arquivo e ainda não executei `git add`.

Verifico:

```bash
git status

git diff
```

Descarto:

```bash
git restore index.html
```

A alteração local será perdida.

## 37. Retirando da preparação

Preparei o arquivo por engano:

```bash
git add index.html
```

Retiro da preparação:

```bash
git restore --staged index.html
```

A alteração continua no arquivo.

## 38. Comparação

```bash
git restore index.html
```

Descarta a alteração do arquivo.

```bash
git restore --staged index.html
```

Retira o arquivo da preparação, mantendo a alteração.

## 39. Restaurando de outro commit

```bash
git restore --source CODIGO_DO_COMMIT index.html
```

# Parte 13: Git revert

## 40. Situação

Um commit com problema já foi enviado e outras pessoas podem ter recebido o histórico.

Identifico:

```bash
git log --oneline
```

Reverto:

```bash
git revert CODIGO_DO_COMMIT
```

O Git cria um novo commit inverso.

## 41. Histórico preservado

```text
b74a920 Revert "Altera incorretamente o título"

a90b621 Altera incorretamente o título
```

O commit original continua registrado. O novo commit mostra a correção.

## 42. Sem commit imediato

```bash
git revert --no-commit CODIGO_DO_COMMIT
```

## 43. Conflito durante revert

Depois de resolver:

```bash
git add .

git revert --continue
```

Para cancelar:

```bash
git revert --abort
```

# Parte 14: Git reset

## 44. Conceito

`reset` reposiciona a referência atual.

É mais adequado para histórico local ainda não compartilhado.

## 45. Reset soft

```bash
git reset --soft HEAD~1
```

Resultado:

1. O último commit é desfeito.

2. As alterações continuam preparadas.

3. Posso criar outro commit.

## 46. Reset mixed

```bash
git reset --mixed HEAD~1
```

Ou:

```bash
git reset HEAD~1
```

Resultado:

1. O último commit é desfeito.

2. As alterações saem da preparação.

3. Permanecem nos arquivos.

## 47. Reset hard

```bash
git reset --hard HEAD~1
```

Resultado:

1. Reposiciona o histórico.

2. Atualiza a preparação.

3. Atualiza os arquivos.

4. Pode descartar trabalho.

> ⚠️ Utilize apenas em laboratório ou quando tiver certeza absoluta do resultado.

## 48. Comparação

| Comando | Move o commit atual | Mantém preparado | Mantém nos arquivos |
|---|---:|---:|---:|
| `git reset --soft` | Sim | Sim | Sim |
| `git reset --mixed` | Sim | Não | Sim |
| `git reset --hard` | Sim | Não | Não |

## 49. Regra prática

Commit já compartilhado:

```text
Avaliar git revert
```

Commit apenas local:

```text
Avaliar git reset
```

# Parte 15: Git stash

## 50. Situação

Estou desenvolvendo uma funcionalidade incompleta e preciso trocar de tarefa.

Guardo:

```bash
git stash push -m "Trabalho inicial do rodapé"
```

Verifico:

```bash
git status

git stash list
```

## 51. Inspecionando

```bash
git stash show

git stash show -p stash@{0}
```

## 52. Recuperando

Aplicar e remover da lista:

```bash
git stash pop
```

Aplicar sem remover:

```bash
git stash apply stash@{0}
```

Remover manualmente:

```bash
git stash drop stash@{0}
```

## 53. Arquivos novos

Para incluir arquivos não rastreados:

```bash
git stash push -u -m "Inclui arquivos novos"
```

## 54. Stash não substitui commit

Utilizo stash para armazenamento temporário. Trabalho importante deve receber commits.

# Parte 16: Conflito ao aplicar stash

## 55. Situação

O mesmo arquivo mudou enquanto o trabalho estava guardado.

Ao executar:

```bash
git stash pop
```

pode ocorrer conflito.

Resolvo como um conflito de merge:

1. `git status`.

2. Abrir o arquivo.

3. Escolher o conteúdo.

4. Remover marcadores.

5. `git add`.

6. Criar commit.

# Parte 17: Git reflog

## 56. Conceito

O reflog registra movimentos recentes de referências locais, como `HEAD` e branches.

Comando:

```bash
git reflog
```

Exemplo:

```text
d82f190 HEAD@{0}: reset: moving to HEAD~1

7a1e4c2 HEAD@{1}: commit: Adiciona conteúdo importante

d82f190 HEAD@{2}: commit: Cria estrutura inicial
```

## 57. Recuperando o commit

```bash
git branch recuperacao/conteudo_importante 7a1e4c2
```

Depois:

```bash
git switch recuperacao/conteudo_importante
```

## 58. Recuperando branch excluída

Localizo o último commit no reflog e executo:

```bash
git branch feature/recuperada CODIGO_DO_COMMIT
```

## 59. Reflog é local

Ele não é um histórico remoto compartilhado. Quando encontro o commit, crio uma branch para preservá lo.

# Parte 18: Matriz de decisão

## 60. Alteração local sem commit

```bash
git restore nome_do_arquivo
```

## 61. Arquivo preparado por engano

```bash
git restore --staged nome_do_arquivo
```

## 62. Commit compartilhado com problema

```bash
git revert CODIGO_DO_COMMIT
```

## 63. Commit local que será refeito

```bash
git reset --soft HEAD~1
```

## 64. Commit local que será reorganizado

```bash
git reset --mixed HEAD~1
```

## 65. Estado local que será descartado

```bash
git reset --hard CODIGO_DO_COMMIT
```

## 66. Trabalho temporário

```bash
git stash push -m "Descrição"
```

## 67. Commit perdido

```bash
git reflog
```

# Parte 19: Fluxo completo do conflito

## 68. Iniciar

```bash
git switch main

git pull origin main

git merge feature/nome_da_tarefa
```

## 69. Identificar

```bash
git status

git diff
```

## 70. Resolver

1. Abrir os arquivos.

2. Comparar versões.

3. Escolher o conteúdo.

4. Remover marcadores.

5. Salvar.

6. Testar.

## 71. Concluir

```bash
git add nome_do_arquivo

git commit -m "Resolve conflito na área modificada"
```

## 72. Verificar e publicar

```bash
git status

git log --oneline --all --graph --decorate

git push origin main
```

# Parte 20: Erros comuns

## 73. Deixar marcadores no arquivo

O projeto continuará incorreto. Pesquise por:

```text
<<<<<<<

=======

>>>>>>>
```

## 74. Escolher uma versão sem analisar

A alteração da outra branch pode ser necessária.

## 75. Fazer commit antes de resolver tudo

Verifique:

```bash
git status
```

## 76. Executar push durante o conflito

Resolva ou cancele primeiro.

## 77. Usar reset hard por tentativa

Antes:

```bash
git status

git log --oneline

git reflog
```

## 78. Confundir revert com restore

```text
restore trabalha com arquivos

revert cria commit inverso
```

## 79. Usar stash como armazenamento permanente

Crie commits para trabalho importante.

## 80. Não testar

A ausência de marcadores não garante que a decisão final esteja correta.

# Parte 21: Atividade colaborativa

## 81. Organização

Cada dupla terá:

1. Responsável pela `main`.

2. Responsável pela branch.

Depois, as funções serão trocadas.

## 82. Cenário

As duas branches deverão alterar a seção `Objetivo` do `README.md` com textos diferentes.

## 83. Etapas

1. Cada aluno cria seu commit.

2. A dupla visualiza o gráfico.

3. Um aluno inicia o merge.

4. A dupla discute a versão final.

5. Remove os marcadores.

6. Testa o Markdown.

7. Cria o commit de resolução.

8. Apresenta o histórico.

## 84. Registro

```text
Arquivo conflitante

Alteração da main

Alteração da branch

Conteúdo final

Motivo da decisão

Commit de resolução
```

# Parte 22: Exercícios

## 85. Exercício 1: Conceitos

1. O que é conflito?

2. Por que o Git não escolhe automaticamente?

3. O que representa `HEAD`?

4. O que representa o bloco depois de `=======`?

5. O que deve acontecer com os marcadores?

6. Para que serve `git merge --abort`?

7. Qual é a diferença entre `restore` e `revert`?

8. Quando `reset` exige mais cuidado?

9. Para que serve `stash`?

10. Para que serve `reflog`?

## 86. Exercício 2: Relacione

### Comandos

```text
A. git merge --abort

B. git restore arquivo

C. git restore --staged arquivo

D. git revert COMMIT

E. git reset --soft HEAD~1

F. git reset --mixed HEAD~1

G. git stash push

H. git reflog
```

### Funções

```text
1. Cria um commit inverso.

2. Cancela o merge.

3. Retira da preparação.

4. Guarda temporariamente.

5. Mostra movimentos de referências.

6. Desfaz commit mantendo preparado.

7. Desfaz commit mantendo não preparado.

8. Descarta alteração local.
```

## 87. Exercício 3: Complete

```bash
git merge __________
```

```bash
git __________ index.html
```

```bash
git restore __________ index.html
```

```bash
git __________ CODIGO
```

```bash
git __________ push -m "Trabalho temporário"
```

```bash
git __________
```

## 88. Exercício 4: Marcadores

Observe:

```html
<<<<<<< HEAD
<h1>Portal Profissional</h1>
=======
<h1>Portal dos Alunos</h1>
>>>>>>> feature/titulo
```

Responda:

1. Qual conteúdo pertence à branch atual?

2. Qual pertence à branch integrada?

3. Quais linhas devem ser removidas?

4. Crie uma versão combinada.

## 89. Exercício 5: Escolha

1. Alteração local sem `git add`.

2. Arquivo preparado por engano.

3. Commit publicado que precisa ser desfeito.

4. Trabalho incompleto que precisa ser guardado.

5. Commit não aparece depois de reset.

Informe o comando adequado.

## 90. Exercício 6: Reset

Complete:

| Modo | Preparado | Nos arquivos |
|---|---:|---:|
| soft |  |  |
| mixed |  |  |
| hard |  |  |

## 91. Exercício 7: Ordem

Organize:

```text
Executar git add.

Abrir o arquivo.

Executar git status.

Remover marcadores.

Testar.

Criar commit.

Escolher conteúdo final.
```

# Parte 23: Desafios

## 92. Desafio 1: Conflito em HTML

Crie duas branches que alterem o mesmo menu. Resolva combinando as opções de navegação.

Entrega:

1. Gráfico antes.

2. Arquivo conflitante.

3. Conteúdo final.

4. Commit de resolução.

5. Gráfico depois.

## 93. Desafio 2: Conflito em CSS

Altere a mesma propriedade em duas branches e escolha uma terceira solução aprovada pela dupla.

## 94. Desafio 3: Cancelamento

Crie um conflito e execute:

```bash
git merge --abort
```

Comprove o retorno com `git status`.

## 95. Desafio 4: Restore

1. Altere dois arquivos.

2. Prepare somente um.

3. Retire o arquivo da preparação.

4. Descarte a alteração do outro.

5. Mostre o status em cada etapa.

## 96. Desafio 5: Revert

1. Crie um commit incorreto.

2. Publique em repositório de teste.

3. Execute `git revert`.

4. Publique a reversão.

5. Explique o histórico.

## 97. Desafio 6: Modos de reset

Teste os três modos em cópias separadas do laboratório e compare `git status`.

## 98. Desafio 7: Dois stashes

Crie dois stashes com mensagens diferentes. Aplique o mais antigo sem removê lo.

## 99. Desafio 8: Reflog

1. Crie um commit.

2. Execute reset em laboratório.

3. Localize o commit.

4. Crie uma branch de recuperação.

## 100. Desafio 9: Pull Request conflitante

1. Abra um Pull Request.

2. Modifique a `main` na mesma região.

3. Resolva localmente.

4. Envie o commit.

5. Solicite nova revisão.

## 101. Desafio 10: Guia de emergência

Crie `GUIA_DE_RECUPERACAO.md` explicando cada comando estudado.

# Parte 24: Avaliação

## 102. Critérios

### Criação do conflito: 1 ponto

### Identificação: 1 ponto

### Interpretação dos marcadores: 1 ponto

### Resolução: 2 pontos

### Teste: 1 ponto

### Commit: 1 ponto

### Recuperação: 2 pontos

### Justificativa: 1 ponto

## 103. Evidências

1. Histórico antes.

2. Mensagem do conflito.

3. `git status`.

4. Marcadores.

5. Conteúdo final.

6. Commit de resolução.

7. Histórico depois.

8. Exercício de recuperação.

# Parte 25: Gabarito

## 104. Exercício 1

1. Conflito é uma situação em que alterações incompatíveis exigem decisão humana.

2. O Git não conhece a intenção do projeto.

3. `HEAD` representa a branch atual.

4. O bloco depois do separador pertence à outra branch.

5. Os marcadores devem ser removidos.

6. Cancela o merge em andamento.

7. `restore` atua em arquivos. `revert` cria um novo commit.

8. Quando pode reescrever ou descartar histórico e arquivos.

9. Guarda alterações temporariamente.

10. Ajuda a localizar referências e commits recentes.

## 105. Exercício 2

```text
A corresponde a 2.

B corresponde a 8.

C corresponde a 3.

D corresponde a 1.

E corresponde a 6.

F corresponde a 7.

G corresponde a 4.

H corresponde a 5.
```

## 106. Exercício 3

```bash
git merge --abort
```

```bash
git restore index.html
```

```bash
git restore --staged index.html
```

```bash
git revert CODIGO
```

```bash
git stash push -m "Trabalho temporário"
```

```bash
git reflog
```

## 107. Exercício 4

1. `Portal Profissional`.

2. `Portal dos Alunos`.

3. `<<<<<<< HEAD`, `=======` e `>>>>>>> feature/titulo`.

4. Exemplo:

```html
<h1>Portal Profissional dos Alunos</h1>
```

## 108. Exercício 5

1. `git restore arquivo`.

2. `git restore --staged arquivo`.

3. `git revert COMMIT`.

4. `git stash push`.

5. `git reflog`.

## 109. Exercício 6

| Modo | Preparado | Nos arquivos |
|---|---:|---:|
| soft | Sim | Sim |
| mixed | Não | Sim |
| hard | Não | Não |

## 110. Exercício 7

```text
Executar git status.

Abrir o arquivo.

Escolher conteúdo final.

Remover marcadores.

Testar.

Executar git add.

Criar commit.
```

# Parte 26: Revisão oral

## 111. Perguntas

1. O que é conflito?

2. Como o Git identifica os blocos?

3. Como marcar arquivo como resolvido?

4. Como concluir o merge?

5. Como cancelar?

6. Para que serve restore?

7. Para que serve revert?

8. Qual é o risco do reset hard?

9. Para que serve stash?

10. Para que serve reflog?

# Parte 27: Resumo dos comandos

```bash
git status

git diff

git add nome_do_arquivo

git merge --continue

git merge --abort

git restore nome_do_arquivo

git restore --staged nome_do_arquivo

git revert CODIGO_DO_COMMIT

git reset --soft HEAD~1

git reset --mixed HEAD~1

git reset --hard HEAD~1

git stash push -m "Descrição"

git stash list

git stash pop

git reflog

git branch recuperacao/nome CODIGO_DO_COMMIT
```

# Parte 28: Encerramento

## 112. O que aprendemos

Conflitos acontecem quando o Git encontra decisões incompatíveis.

Resolver exige:

```text
Identificar

Comparar

Decidir

Editar

Testar

Registrar
```

Cada comando de recuperação possui uma finalidade:

```text
restore trabalha com arquivos

revert desfaz com novo commit

reset reposiciona histórico local

stash guarda temporariamente

reflog localiza referências anteriores
```

## 113. Preparação para a próxima aula

Na próxima aula, vamos organizar o trabalho com:

1. Issues.

2. Labels.

3. Responsáveis.

4. Milestones.

5. GitHub Projects.

6. Templates.

7. Documentação de contribuição.

## 114. Frase de encerramento

Conflitos não são resolvidos escolhendo rapidamente um dos lados.

Eles são resolvidos quando a equipe compreende as duas alterações e constrói conscientemente a versão final.

Recuperar um projeto também não depende de decorar comandos. Depende de identificar onde a alteração está e escolher a ferramenta adequada.

# Referências

1. Documentação oficial do Git sobre merge  
   https://git-scm.com/docs/git-merge

2. Livro oficial Pro Git sobre branches e merge  
   https://git-scm.com/book/pt-br/v2/Branches-no-Git-O-b%C3%A1sico-de-Ramifica%C3%A7%C3%A3o-Branch-e-Mesclagem-Merge.html

3. Documentação oficial do GitHub sobre conflitos  
   https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts

4. Documentação oficial do Git sobre restore  
   https://git-scm.com/docs/git-restore

5. Documentação oficial do Git sobre revert  
   https://git-scm.com/docs/git-revert

6. Documentação oficial do Git sobre reset  
   https://git-scm.com/docs/git-reset

7. Documentação oficial do Git sobre stash  
   https://git-scm.com/docs/git-stash

8. Documentação oficial do Git sobre reflog  
   https://git-scm.com/docs/git-reflog
