# Aula 3: Branches e Desenvolvimento Paralelo

## Git e GitHub na Prática

### Carga horária

4 horas

### Tema da aula

Criação, utilização, publicação, comparação e organização de branches para desenvolver funcionalidades separadas sem alterar diretamente a branch principal do projeto.

## 1. Apresentação da aula

Nas duas primeiras aulas, eu ensinei você a criar um repositório Git, registrar commits e sincronizar o projeto com o GitHub.

Até agora, trabalhamos principalmente na branch `main`.

Nesta aula, vamos aprender a criar linhas separadas de desenvolvimento.

Essas linhas recebem o nome de branches.

Uma branch permite que eu desenvolva uma funcionalidade, corrija um problema ou faça uma experiência sem alterar imediatamente a versão principal do projeto.

O fluxo principal da aula será:

```text
Atualizar a branch main

Criar uma nova branch

Entrar na nova branch

Modificar o projeto

Criar commits

Publicar a branch no GitHub

Comparar a branch com a main

Trocar de branch com segurança
```

Durante a prática, continuaremos utilizando o projeto:

```text
portal_da_turma
```

Cada aluno desenvolverá uma parte diferente do portal em uma branch própria.

## 2. Objetivos da aula

Nesta aula, eu vou ensinar você a:

1. Entender o que é uma branch.

2. Compreender por que branches são importantes.

3. Identificar a branch atual.

4. Listar branches locais.

5. Listar branches remotas.

6. Criar uma nova branch.

7. Trocar de uma branch para outra.

8. Criar uma branch e entrar nela com um único comando.

9. Registrar commits em uma branch específica.

10. Publicar uma branch no GitHub.

11. Entender o acompanhamento entre branch local e remota.

12. Comparar duas branches.

13. Visualizar o histórico em formato de gráfico.

14. Criar nomes organizados para branches.

15. Baixar uma branch criada por outro integrante.

16. Excluir branches que não são mais necessárias.

17. Evitar alterações diretas na branch principal.

18. Desenvolver funcionalidades em paralelo com outros alunos.

## 3. Resultados esperados

Ao final da aula, você deverá conseguir executar o seguinte processo:

```text
main atualizada

        ↓

criação de uma branch

        ↓

desenvolvimento isolado

        ↓

commits na nova branch

        ↓

publicação no GitHub

        ↓

comparação com a main

        ↓

preparação para revisão e integração
```

Os principais comandos serão:

```bash
git branch

git branch --show-current

git switch main

git switch -c feature/pagina_sobre

git status

git add .

git commit -m "Cria a página sobre"

git push -u origin feature/pagina_sobre

git branch -a

git branch -r

git log --oneline --all --graph

git diff main..feature/pagina_sobre

git branch -d nome_da_branch

git push origin --delete nome_da_branch
```

## 4. Conhecimentos necessários

Para acompanhar esta aula, você deverá conhecer:

1. `git status`

2. `git add`

3. `git commit`

4. `git log`

5. `git push`

6. `git pull`

7. `git fetch`

8. `git clone`

9. Repositório local.

10. Repositório remoto.

11. Branch `main`.

12. Remote `origin`.

## 5. Recursos necessários

1. Computador conectado à internet.

2. Git instalado.

3. Visual Studio Code.

4. Conta no GitHub.

5. Repositório `portal_da_turma`.

6. Projeto publicado no GitHub.

7. Pelo menos três commits criados nas aulas anteriores.

## 6. Organização das quatro horas

### Primeiro momento: 30 minutos

Revisão das aulas anteriores e apresentação do conceito de branch.

### Segundo momento: 35 minutos

Demonstração de criação, listagem e troca de branches.

### Terceiro momento: 50 minutos

Desenvolvimento guiado de uma nova funcionalidade.

### Quarto momento: 30 minutos

Publicação e comparação da branch no GitHub.

### Intervalo: 15 minutos

### Quinto momento: 45 minutos

Trabalho paralelo em equipes.

### Sexto momento: 25 minutos

Branches remotas, acompanhamento e exclusão.

### Sétimo momento: 30 minutos

Exercícios, desafios, revisão e avaliação.

# Parte 1: Revisão do fluxo estudado

## 7. O que já sabemos

Nas aulas anteriores, utilizamos este fluxo:

```bash
git status

git add .

git commit -m "Descrição da alteração"

git pull

git push
```

Esse processo funciona, mas existe um problema quando várias pessoas alteram diretamente a `main`.

Imagine que três alunos estejam trabalhando no mesmo projeto.

O primeiro aluno cria uma página sobre a turma.

O segundo aluno cria uma lista de alunos.

O terceiro aluno corrige o menu.

Se todos fizerem alterações diretamente na `main`, as mudanças podem se misturar antes de serem revisadas.

Uma funcionalidade incompleta também poderá afetar a versão principal.

É por isso que utilizamos branches.

## 8. Preparando o projeto

Antes de criar uma nova branch, eu abro o terminal dentro do projeto:

```text
portal_da_turma
```

Depois, verifico a situação:

```bash
git status
```

O resultado ideal será semelhante a:

```text
On branch main

Your branch is up to date with origin/main.

nothing to commit, working tree clean
```

Agora recebo possíveis alterações do GitHub:

```bash
git pull origin main
```

Depois, confirmo novamente:

```bash
git status
```

> ⚠️ Eu não começo uma nova funcionalidade em uma `main` desatualizada.

# Parte 2: O que é uma branch?

## 9. Conceito inicial

Branch significa ramo.

No Git, uma branch representa uma linha de desenvolvimento.

A branch principal normalmente é chamada:

```text
main
```

Quando eu crio uma nova branch, posso trabalhar sem alterar imediatamente a `main`.

Um exemplo seria:

```text
main

    Versão principal do projeto

feature/pagina_sobre

    Desenvolvimento da página sobre
```

## 10. Comparação com uma estrada

Eu posso imaginar a `main` como uma estrada principal.

Quando preciso construir algo novo, abro uma estrada lateral.

Nessa estrada lateral, posso trabalhar, testar e corrigir.

Quando o trabalho estiver pronto, ele poderá ser integrado à estrada principal.

```text
main
────────────────────────────────────────────>

                 \
                  \
feature/pagina_sobre
                    ─────────────────────────>
```

A integração será estudada com mais detalhes na próxima aula.

## 11. Por que utilizar branches?

Branches ajudam a:

1. Separar funcionalidades.

2. Evitar mudanças diretas na versão principal.

3. Trabalhar em equipe.

4. Testar ideias.

5. Corrigir problemas isoladamente.

6. Organizar revisões.

7. Preparar Pull Requests.

8. Diminuir o risco de publicar uma funcionalidade incompleta.

## 12. Branch não é uma cópia completa da pasta

Quando eu crio uma branch, o Git não precisa duplicar manualmente todos os arquivos do projeto.

A branch funciona como uma referência dentro do histórico.

Ela aponta para uma sequência de commits.

Por isso, criar e trocar branches costuma ser rápido.

## 13. Representação simples

Imagine que a `main` possui três commits:

```text
A → B → C
```

Agora eu crio uma branch chamada:

```text
feature/pagina_sobre
```

No momento da criação, as duas branches apontam para o mesmo commit:

```text
A → B → C
          ↑
          main
          feature/pagina_sobre
```

Depois, crio um novo commit na branch de funcionalidade:

```text
A → B → C
          ↑
          main
           \
            D
            ↑
            feature/pagina_sobre
```

A `main` continua no commit C.

A nova branch avança para o commit D.

# Parte 3: Conhecendo a branch atual

## 14. Listando as branches

Dentro do projeto, executo:

```bash
git branch
```

Um resultado possível será:

```text
* main
```

O asterisco mostra a branch atual.

Nesse exemplo, estou trabalhando na `main`.

## 15. Mostrando somente a branch atual

Posso utilizar:

```bash
git branch --show-current
```

Resultado:

```text
main
```

Esse comando é útil quando quero confirmar rapidamente onde estou.

## 16. O Git sempre trabalha em alguma branch?

Na maior parte do fluxo normal, sim.

Quando faço um commit, ele será registrado na branch atual.

Por isso, antes de alterar um projeto, eu verifico:

```bash
git branch --show-current
```

## 17. Um cuidado importante

Se eu acreditar que estou na branch de uma funcionalidade, mas estiver na `main`, os commits serão criados na `main`.

Para evitar isso, eu utilizo com frequência:

```bash
git status
```

O próprio `git status` informa a branch atual.

# Parte 4: Criando uma branch

## 18. Criando sem trocar

Para criar uma branch sem entrar nela, utilizo:

```bash
git branch feature/pagina_sobre
```

Depois, verifico:

```bash
git branch
```

Resultado possível:

```text
  feature/pagina_sobre
* main
```

A branch foi criada, mas eu continuo na `main`.

## 19. Entrando na nova branch

Para entrar na branch criada, utilizo:

```bash
git switch feature/pagina_sobre
```

O terminal poderá apresentar:

```text
Switched to branch 'feature/pagina_sobre'
```

Agora verifico:

```bash
git branch
```

Resultado:

```text
* feature/pagina_sobre
  main
```

## 20. Criando e entrando com um comando

Também posso criar e entrar na branch com:

```bash
git switch -c feature/pagina_sobre
```

A opção `-c` indica que uma nova branch será criada.

Esse é o comando que utilizaremos com mais frequência nesta aula.

## 21. Evitando erro de branch já existente

Se a branch já existir, este comando apresentará erro:

```bash
git switch -c feature/pagina_sobre
```

Nesse caso, eu apenas entro nela:

```bash
git switch feature/pagina_sobre
```

## 22. Fluxo recomendado

```bash
git switch main

git pull origin main

git switch -c feature/pagina_sobre
```

Primeiro, entro na `main`.

Depois, atualizo a `main`.

Por último, crio a nova branch a partir dela.

# Parte 5: Nomes de branches

## 23. Por que padronizar nomes?

Em uma equipe, nomes organizados ajudam a identificar rapidamente o objetivo de cada branch.

Compare:

```text
teste

nova

branch1

coisas
```

Com:

```text
feature/pagina_sobre

feature/lista_alunos

fix/correcao_menu

docs/atualiza_readme
```

A segunda lista explica melhor o trabalho realizado.

## 24. Prefixos utilizados

### feature

Utilizo para uma nova funcionalidade.

```text
feature/pagina_sobre
```

```text
feature/formulario_contato
```

### fix

Utilizo para corrigir um problema.

```text
fix/correcao_menu
```

```text
fix/link_quebrado
```

### docs

Utilizo para alterações de documentação.

```text
docs/atualiza_readme
```

```text
docs/adiciona_instrucoes
```

### refactor

Utilizo para reorganizar o código sem mudar o objetivo principal.

```text
refactor/organiza_estilos
```

### test

Utilizo para testes.

```text
test/validacao_formulario
```

## 25. Regras simples de nomenclatura

Eu recomendo:

1. Utilizar letras minúsculas.

2. Evitar espaços.

3. Informar o tipo de trabalho.

4. Utilizar um nome curto e específico.

5. Evitar nomes genéricos.

6. Combinar o padrão com a equipe.

## 26. Exemplos adequados

```text
feature/pagina_contato

feature/lista_projetos

fix/correcao_rodape

docs/atualiza_comandos

refactor/separa_estilos
```

## 27. Exemplos inadequados

```text
teste

nova_branch

coisas

agora_vai

final

branch_do_joao
```

Esses nomes não explicam claramente o objetivo técnico do trabalho.

# Parte 6: Projeto guiado

## 28. Funcionalidade da aula

Vamos criar uma página sobre a turma.

A branch será:

```text
feature/pagina_sobre
```

Antes de criar a branch, verifico:

```bash
git status
```

Entro na `main`:

```bash
git switch main
```

Atualizo:

```bash
git pull origin main
```

Crio a branch:

```bash
git switch -c feature/pagina_sobre
```

Confirmo:

```bash
git branch --show-current
```

Resultado esperado:

```text
feature/pagina_sobre
```

## 29. Criando o arquivo sobre.html

Na raiz do projeto, crio:

```text
sobre.html
```

Adiciono:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Sobre a Turma</title>

    <link rel="stylesheet" href="css/estilo.css">
</head>

<body>
    <header>
        <h1>Sobre a Turma</h1>

        <nav>
            <a href="index.html">Início</a>
            <a href="sobre.html">Sobre</a>
        </nav>
    </header>

    <main>
        <section>
            <h2>Quem somos</h2>

            <p>
                Somos uma turma de Desenvolvimento de Sistemas
                estudando Git, GitHub e trabalho colaborativo.
            </p>
        </section>

        <section>
            <h2>Objetivos da turma</h2>

            <ul>
                <li>Aprender desenvolvimento de sistemas</li>
                <li>Trabalhar com controle de versão</li>
                <li>Desenvolver projetos em equipe</li>
                <li>Construir um portfólio profissional</li>
            </ul>
        </section>
    </main>

    <footer>
        <p>Portal da Turma</p>
    </footer>
</body>
</html>
```

## 30. Alterando o index.html

No arquivo `index.html`, adiciono um link para a nova página:

```html
<nav>
    <a href="index.html">Início</a>
    <a href="sobre.html">Sobre</a>
</nav>
```

## 31. Verificando os arquivos

Executo:

```bash
git status
```

O Git deverá mostrar:

```text
modified: index.html

untracked: sobre.html
```

O arquivo `index.html` foi modificado.

O arquivo `sobre.html` é novo e ainda não está sendo rastreado.

## 32. Comparando as alterações

Antes de preparar os arquivos, executo:

```bash
git diff
```

Esse comando mostra as alterações ainda não preparadas.

Eu verifico se o link foi inserido corretamente e se não modifiquei partes desnecessárias.

## 33. Preparando os arquivos

```bash
git add index.html sobre.html
```

Depois:

```bash
git status
```

Agora os dois arquivos deverão aparecer como preparados.

## 34. Criando o primeiro commit da branch

```bash
git commit -m "Cria a página sobre a turma"
```

## 35. Criando uma segunda alteração

Agora adiciono estilos específicos ao arquivo `css/estilo.css`:

```css
nav {
    display: flex;
    gap: 16px;
    margin-bottom: 30px;
}

nav a {
    color: #1f4b99;
    font-weight: bold;
    text-decoration: none;
}

nav a:hover {
    text-decoration: underline;
}

section {
    background-color: #ffffff;
    border-radius: 8px;
    margin-bottom: 20px;
    padding: 24px;
}
```

## 36. Registrando o segundo commit

```bash
git status

git diff

git add css/estilo.css

git commit -m "Adiciona estilos da página sobre"
```

## 37. Consultando o histórico da branch

```bash
git log --oneline
```

Resultado possível:

```text
9b312f1 Adiciona estilos da página sobre

682f75a Cria a página sobre a turma

b308f31 Adiciona lista inicial de aulas

70a54ac Atualiza conteúdo da aula no README
```

Os dois primeiros commits pertencem ao trabalho atual.

# Parte 7: Trocando de branch

## 38. Voltando para a main

Executo:

```bash
git switch main
```

Agora verifico os arquivos.

A página `sobre.html` poderá não aparecer na pasta enquanto estou na `main`.

Isso acontece porque ela foi criada e registrada somente na branch:

```text
feature/pagina_sobre
```

## 39. Entrando novamente na branch

```bash
git switch feature/pagina_sobre
```

O arquivo `sobre.html` volta a aparecer.

Essa experiência mostra que cada branch pode representar um estado diferente do projeto.

## 40. O Git apagou o arquivo?

Não.

O arquivo está registrado no histórico da branch de funcionalidade.

Quando troco de branch, o Git ajusta a área de trabalho para representar o conteúdo daquela branch.

## 41. Cuidado com alterações não registradas

Se eu modificar um arquivo e tentar trocar de branch sem criar um commit, o Git poderá:

1. Levar a alteração para a outra branch, quando for seguro.

2. Impedir a troca, quando houver risco de sobrescrever o trabalho.

Para iniciantes, eu recomendo trocar de branch apenas quando:

```bash
git status
```

mostrar:

```text
nothing to commit, working tree clean
```

## 42. Verificação antes da troca

Eu utilizo:

```bash
git status
```

Se houver alterações, decido se devo:

1. Concluir o trabalho.

2. Preparar os arquivos.

3. Criar o commit.

4. Descartar uma alteração, quando tiver certeza.

5. Guardar temporariamente com stash, assunto que será aprofundado em outra aula.

# Parte 8: Publicando uma branch

## 43. A branch existe somente no computador?

Depois de criar a branch local, ela ainda não aparece automaticamente no GitHub.

Para publicar, utilizo:

```bash
git push -u origin feature/pagina_sobre
```

## 44. Entendendo o comando

```bash
git push -u origin feature/pagina_sobre
```

### push

Envia os commits.

### opção u

Configura o acompanhamento entre a branch local e a branch remota.

### origin

Indica o repositório remoto.

### feature/pagina_sobre

Indica a branch enviada.

## 45. Próximos envios

Depois de configurar o acompanhamento, posso utilizar:

```bash
git push
```

O Git saberá qual branch remota corresponde à branch local atual.

## 46. Confirmando no GitHub

Na página do repositório, posso abrir a lista de branches.

Deverão aparecer:

```text
main

feature/pagina_sobre
```

A `main` continua sendo a branch principal.

A branch de funcionalidade contém os novos commits.

## 47. A branch publicada altera a main?

Não.

Publicar uma branch não integra automaticamente o conteúdo à `main`.

As duas continuam separadas.

A integração será feita por merge ou Pull Request, assunto principal da Aula 4.

# Parte 9: Listando branches locais e remotas

## 48. Branches locais

```bash
git branch
```

Exemplo:

```text
* feature/pagina_sobre
  main
```

## 49. Branches remotas

Primeiro, atualizo as referências:

```bash
git fetch origin
```

Depois:

```bash
git branch -r
```

Exemplo:

```text
origin/feature/pagina_sobre

origin/main
```

## 50. Todas as branches

```bash
git branch -a
```

Exemplo:

```text
* feature/pagina_sobre
  main
  remotes/origin/feature/pagina_sobre
  remotes/origin/main
```

## 51. Diferença entre local e remota

```text
feature/pagina_sobre

Branch local.
```

```text
origin/feature/pagina_sobre

Referência da branch existente no remote origin.
```

# Parte 10: Comparando branches

## 52. Por que comparar?

Antes de integrar uma branch, eu preciso entender o que ela possui de diferente.

Posso comparar:

1. Arquivos.

2. Linhas modificadas.

3. Commits.

4. Histórico visual.

## 53. Comparando o conteúdo

Estando em qualquer branch, posso executar:

```bash
git diff main..feature/pagina_sobre
```

O Git mostrará as diferenças entre as duas branches.

## 54. Comparando somente os nomes dos arquivos

```bash
git diff --name-only main..feature/pagina_sobre
```

Resultado possível:

```text
css/estilo.css

index.html

sobre.html
```

## 55. Comparando os commits

Para mostrar commits presentes na branch de funcionalidade e ausentes na `main`:

```bash
git log main..feature/pagina_sobre --oneline
```

Resultado:

```text
9b312f1 Adiciona estilos da página sobre

682f75a Cria a página sobre a turma
```

## 56. Histórico em formato gráfico

```bash
git log --oneline --all --graph --decorate
```

Um resultado possível será:

```text
* 9b312f1 (feature/pagina_sobre) Adiciona estilos da página sobre
* 682f75a Cria a página sobre a turma
* b308f31 (HEAD -> main, origin/main) Adiciona lista inicial de aulas
* 70a54ac Atualiza conteúdo da aula no README
```

## 57. Entendendo HEAD

`HEAD` indica a posição atual do trabalho.

Quando estou na `main`, ele normalmente aponta para a `main`.

Exemplo:

```text
HEAD -> main
```

Quando entro na branch de funcionalidade:

```text
HEAD -> feature/pagina_sobre
```

Eu posso pensar no `HEAD` como a indicação de onde estou no histórico.

# Parte 11: Desenvolvimento paralelo

## 58. Situação da equipe

Vamos dividir a equipe em quatro funções.

### Aluno 1

Branch:

```text
feature/pagina_sobre
```

Tarefa:

Criar a página sobre.

### Aluno 2

Branch:

```text
feature/lista_alunos
```

Tarefa:

Criar a página de alunos.

### Aluno 3

Branch:

```text
feature/pagina_projetos
```

Tarefa:

Criar a página de projetos.

### Aluno 4

Branch:

```text
docs/atualiza_readme
```

Tarefa:

Atualizar a documentação.

## 59. Fluxo de cada aluno

```bash
git switch main

git pull origin main

git switch -c NOME_DA_BRANCH
```

Depois:

```bash
git status

git add .

git commit -m "Descrição da alteração"

git push -u origin NOME_DA_BRANCH
```

## 60. Regra principal

Nenhum aluno deverá criar commits diretamente na `main` durante esta atividade.

Cada tarefa terá sua própria branch.

## 61. Vantagem do trabalho paralelo

Enquanto um aluno cria a página sobre, outro pode criar a página de projetos.

As funcionalidades ficam separadas.

A equipe poderá revisar cada trabalho antes de integrar à `main`.

## 62. Responsabilidade de cada aluno

Cada aluno deverá:

1. Atualizar a `main`.

2. Criar uma branch com nome adequado.

3. Confirmar a branch atual.

4. Desenvolver somente a tarefa definida.

5. Criar commits específicos.

6. Publicar a branch.

7. Comparar com a `main`.

8. Apresentar o histórico.

# Parte 12: Recebendo uma branch criada por outro aluno

## 63. Atualizando as informações remotas

Imagine que outro aluno publicou:

```text
feature/lista_alunos
```

Primeiro, executo:

```bash
git fetch origin
```

## 64. Listando branches remotas

```bash
git branch -r
```

Resultado:

```text
origin/feature/lista_alunos

origin/feature/pagina_sobre

origin/main
```

## 65. Criando uma branch local a partir da remota

Posso utilizar:

```bash
git switch --track origin/feature/lista_alunos
```

Em muitas configurações, o Git criará uma branch local chamada:

```text
feature/lista_alunos
```

e configurará o acompanhamento remoto.

## 66. Confirmando

```bash
git branch --show-current
```

Depois:

```bash
git status
```

O resultado deverá indicar que a branch acompanha:

```text
origin/feature/lista_alunos
```

## 67. Outra forma explícita

Também posso escrever:

```bash
git switch -c feature/lista_alunos --track origin/feature/lista_alunos
```

Esse comando informa:

1. O nome da branch local.

2. A branch remota utilizada como origem.

3. A configuração de acompanhamento.

# Parte 13: Atualizando uma branch de trabalho

## 68. A main recebeu novos commits

Enquanto trabalho em uma branch, a `main` poderá receber alterações de outros integrantes.

Nesta aula, apenas observaremos a situação.

A integração da `main` atualizada com a branch de funcionalidade será aprofundada na Aula 4.

## 69. Atualizando as referências

```bash
git fetch origin
```

Depois:

```bash
git log --oneline --all --graph --decorate
```

Assim, consigo visualizar se `origin/main` avançou.

## 70. Comparando minha branch com a main remota

```bash
git diff origin/main..feature/pagina_sobre
```

Também posso consultar os commits:

```bash
git log origin/main..feature/pagina_sobre --oneline
```

## 71. Não integrar sem compreender

Nesta etapa, eu não utilizo comandos aleatórios para forçar a atualização.

Primeiro, analiso:

```bash
git status

git branch --show-current

git fetch origin

git log --oneline --all --graph --decorate
```

Depois, escolho conscientemente o próximo passo.

# Parte 14: Renomeando uma branch

## 72. Nome incorreto

Imagine que eu criei:

```text
nova
```

Mas o nome correto seria:

```text
feature/pagina_contato
```

Se eu estiver dentro da branch, posso executar:

```bash
git branch -m feature/pagina_contato
```

## 73. Renomeando uma branch diferente

```bash
git branch -m nova feature/pagina_contato
```

## 74. Branch já publicada

Quando uma branch já foi enviada ao GitHub, renomear localmente não renomeia automaticamente a branch remota.

Um fluxo possível será:

```bash
git branch -m nome_antigo nome_novo

git push -u origin nome_novo

git push origin --delete nome_antigo
```

Antes de excluir a branch remota antiga, eu confirmo se o novo envio foi realizado corretamente.

# Parte 15: Excluindo branches

## 75. Quando excluir?

Normalmente, uma branch é excluída quando:

1. O trabalho foi concluído e integrado.

2. A experiência foi abandonada.

3. A branch foi criada por engano.

4. Ela não é mais necessária.

Nesta aula, excluiremos apenas branches de teste que não contenham trabalho importante.

## 76. Criando uma branch de teste

```bash
git switch main

git switch -c test/experiencia
```

Não criaremos commits nessa branch.

Depois, voltamos:

```bash
git switch main
```

## 77. Excluindo uma branch local

```bash
git branch -d test/experiencia
```

A opção `-d` solicita a exclusão segura.

O Git poderá impedir a exclusão quando detectar trabalho não integrado.

## 78. Exclusão forçada

Existe também:

```bash
git branch -D nome_da_branch
```

> ⚠️ A opção `-D` força a exclusão. Eu não a utilizo sem verificar se a branch contém commits importantes.

## 79. Excluindo uma branch remota

```bash
git push origin --delete nome_da_branch
```

Exemplo:

```bash
git push origin --delete test/experiencia
```

## 80. Confirmando a exclusão

```bash
git fetch --prune origin
```

Depois:

```bash
git branch -a
```

A opção `--prune` remove referências locais de branches remotas que já não existem no servidor.

# Parte 16: Erros comuns

## 81. Erro: branch já existe

### Mensagem possível

```text
fatal: a branch named 'feature/pagina_sobre' already exists
```

### Motivo

A branch já foi criada.

### Solução

```bash
git switch feature/pagina_sobre
```

## 82. Erro: branch não encontrada

### Mensagem possível

```text
fatal: invalid reference
```

### Possíveis causas

1. Nome digitado incorretamente.

2. Branch existe apenas no GitHub.

3. Informações remotas ainda não foram buscadas.

### Verificação

```bash
git branch -a
```

Depois:

```bash
git fetch origin
```

## 83. Erro ao trocar de branch com alterações pendentes

O Git poderá impedir a troca para evitar que arquivos sejam sobrescritos.

### Procedimento

```bash
git status
```

Depois, eu decido se devo criar um commit.

```bash
git add .

git commit -m "Conclui alteração antes de trocar de branch"
```

## 84. Criei commits na main por engano

A solução depende da situação:

1. Os commits foram publicados?

2. Outros alunos já receberam?

3. Existem alterações adicionais?

4. A branch correta já existe?

Para uma turma iniciante, eu interrompo o processo e consulto o professor antes de utilizar reset ou reescrever o histórico.

Uma solução segura poderá ser criar a branch correta a partir do commit atual e depois avaliar como corrigir a `main`.

```bash
git switch -c feature/nome_da_tarefa
```

> ⚠️ Não utilizo `git reset --hard` sem compreender exatamente quais dados serão removidos.

## 85. Publiquei a branch errada

Primeiro, verifico:

```bash
git branch --show-current

git remote -v

git status
```

Se a branch publicada não deveria existir no GitHub e não contém trabalho necessário:

```bash
git push origin --delete nome_da_branch
```

## 86. Push rejeitado

A branch remota poderá ter commits que ainda não existem localmente.

Primeiro, executo:

```bash
git fetch origin
```

Analiso:

```bash
git log --oneline --all --graph --decorate
```

Depois, decido como integrar as alterações.

Não utilizo comandos forçados sem compreender o histórico.

## 87. Não encontro a branch de outro aluno

```bash
git fetch origin

git branch -r
```

Se ainda não aparecer, verifico:

1. Se o aluno executou push.

2. Se o repositório está correto.

3. Se a branch foi publicada no mesmo remote.

4. Se o nome foi informado corretamente.

# Parte 17: Prática guiada completa

## 88. Etapa 1: Atualizar a main

```bash
git switch main

git pull origin main

git status
```

## 89. Etapa 2: Criar a branch

```bash
git switch -c feature/pagina_sobre
```

## 90. Etapa 3: Confirmar

```bash
git branch --show-current
```

## 91. Etapa 4: Criar a funcionalidade

Criar:

```text
sobre.html
```

Alterar:

```text
index.html
```

## 92. Etapa 5: Verificar

```bash
git status

git diff
```

## 93. Etapa 6: Primeiro commit

```bash
git add index.html sobre.html

git commit -m "Cria a página sobre a turma"
```

## 94. Etapa 7: Segundo commit

Alterar:

```text
css/estilo.css
```

Depois:

```bash
git add css/estilo.css

git commit -m "Adiciona estilos da página sobre"
```

## 95. Etapa 8: Publicar

```bash
git push -u origin feature/pagina_sobre
```

## 96. Etapa 9: Comparar

```bash
git diff --name-only main..feature/pagina_sobre

git log main..feature/pagina_sobre --oneline
```

## 97. Etapa 10: Visualizar o gráfico

```bash
git log --oneline --all --graph --decorate
```

## 98. Etapa 11: Voltar à main

```bash
git status

git switch main
```

## 99. Etapa 12: Verificar a separação

```bash
git branch

git log --oneline --all --graph --decorate
```

# Parte 18: Atividade colaborativa

## 100. Organização das equipes

Cada equipe terá entre três e cinco alunos.

Cada integrante receberá uma tarefa e uma branch diferente.

## 101. Tarefas sugeridas

### Tarefa 1

Branch:

```text
feature/pagina_sobre
```

Entrega:

Página sobre a turma.

### Tarefa 2

Branch:

```text
feature/lista_alunos
```

Entrega:

Página com lista de alunos fictícios ou autorizados.

### Tarefa 3

Branch:

```text
feature/pagina_projetos
```

Entrega:

Página com projetos da turma.

### Tarefa 4

Branch:

```text
feature/pagina_contato
```

Entrega:

Página com formulário de contato sem envio real.

### Tarefa 5

Branch:

```text
docs/atualiza_readme
```

Entrega:

README com instruções e informações do projeto.

## 102. Regras da atividade

1. Não criar commits diretamente na `main`.

2. Atualizar a `main` antes de criar a branch.

3. Utilizar nomes padronizados.

4. Fazer somente a tarefa atribuída.

5. Criar pelo menos dois commits.

6. Publicar a branch no GitHub.

7. Comparar a branch com a `main`.

8. Não realizar merge nesta aula.

## 103. Registro individual

Cada aluno deverá apresentar:

```text
Nome da branch

Objetivo da branch

Arquivos alterados

Mensagens dos commits

Resultado do push

Comparação com a main
```

## 104. Comandos da atividade

```bash
git switch main

git pull origin main

git switch -c NOME_DA_BRANCH

git status

git add .

git commit -m "Primeira alteração"

git add .

git commit -m "Segunda alteração"

git push -u origin NOME_DA_BRANCH

git diff --name-only main..NOME_DA_BRANCH

git log main..NOME_DA_BRANCH --oneline
```

# Parte 19: Exercícios de fixação

## 105. Exercício 1: Conceitos

Responda com suas palavras.

1. O que é uma branch?

2. Para que serve a branch `main`?

3. Por que não devemos desenvolver todas as funcionalidades diretamente na `main`?

4. O que significa o asterisco exibido por `git branch`?

5. Qual é a função de `git switch`?

6. Qual é a diferença entre `git branch nome` e `git switch -c nome`?

7. O que significa publicar uma branch?

8. Publicar uma branch altera automaticamente a `main`?

9. O que é uma branch remota?

10. O que representa `origin/main`?

11. Para que serve `git diff main..nome_da_branch`?

12. Quando uma branch pode ser excluída?

## 106. Exercício 2: Relacione os comandos

### Comandos

```text
A. git branch

B. git branch --show-current

C. git switch main

D. git switch -c feature/pagina_contato

E. git push -u origin feature/pagina_contato

F. git branch -r

G. git branch -a

H. git branch -d nome_da_branch
```

### Funções

```text
1. Lista branches locais e remotas.

2. Cria uma branch e entra nela.

3. Exclui uma branch local com verificação de segurança.

4. Lista branches locais.

5. Entra na branch main.

6. Publica a branch e configura acompanhamento.

7. Mostra somente a branch atual.

8. Lista branches remotas.
```

## 107. Exercício 3: Complete os comandos

### Listar branches locais

```bash
git __________
```

### Mostrar a branch atual

```bash
git branch __________
```

### Entrar na main

```bash
git __________ main
```

### Criar e entrar em uma branch

```bash
git switch __________ feature/pagina_projetos
```

### Publicar uma branch

```bash
git push __________ origin feature/pagina_projetos
```

### Listar branches remotas

```bash
git branch __________
```

### Excluir uma branch local

```bash
git branch __________ nome_da_branch
```

## 108. Exercício 4: Escolha a branch

Defina um nome adequado para cada situação.

### Situação 1

Criar uma página de cadastro.

Resposta:

```text
________________________________
```

### Situação 2

Corrigir um link quebrado.

Resposta:

```text
________________________________
```

### Situação 3

Atualizar o README.

Resposta:

```text
________________________________
```

### Situação 4

Reorganizar os estilos CSS.

Resposta:

```text
________________________________
```

### Situação 5

Criar testes para um formulário.

Resposta:

```text
________________________________
```

## 109. Exercício 5: Analise os nomes

Classifique os nomes como adequados ou inadequados.

```text
feature/pagina_contato

teste

fix/correcao_menu

branch_nova

docs/atualiza_readme

agora_vai

refactor/organiza_estilos

coisas
```

Explique por que os nomes inadequados dificultam o trabalho em equipe.

## 110. Exercício 6: Organize o fluxo

Coloque as ações na ordem correta.

```text
Publicar a nova branch.

Atualizar a main.

Criar commits.

Criar a branch.

Comparar a branch com a main.

Desenvolver a funcionalidade.
```

## 111. Exercício 7: Interpretação do histórico

Observe:

```text
* a8137f2 (feature/pagina_contato) Adiciona campos do formulário
* 4e38a19 Cria a página de contato
| * c905b24 (feature/lista_alunos) Cria tabela de alunos
|/
* 53bb821 (main) Atualiza página inicial
```

Responda:

1. Qual branch possui o commit `a8137f2`?

2. Qual branch possui o commit `c905b24`?

3. Qual é o último commit da `main`?

4. A página de contato já está integrada à `main`?

5. Quantas linhas de desenvolvimento aparecem?

# Parte 20: Desafios

## 112. Desafio 1: Página de projetos

Crie a branch:

```text
feature/pagina_projetos
```

Crie o arquivo:

```text
projetos.html
```

A página deverá possuir:

1. Título.

2. Descrição.

3. Três projetos fictícios.

4. Tecnologias utilizadas.

5. Links de navegação.

6. Estilos CSS.

Crie pelo menos dois commits.

Exemplos:

```text
Cria a página de projetos

Adiciona estilos dos cartões de projetos
```

Publique:

```bash
git push -u origin feature/pagina_projetos
```

## 113. Desafio 2: Branch de documentação

Crie:

```text
docs/atualiza_readme
```

Atualize o README com:

1. Objetivo do projeto.

2. Estrutura de arquivos.

3. Tecnologias.

4. Comandos para clonar.

5. Integrantes.

6. Situação do projeto.

Crie dois commits específicos.

## 114. Desafio 3: Comparação completa

Escolha uma branch publicada e execute:

```bash
git diff --name-only main..NOME_DA_BRANCH
```

Depois:

```bash
git log main..NOME_DA_BRANCH --oneline
```

E:

```bash
git log --oneline --all --graph --decorate
```

Registre:

1. Arquivos diferentes.

2. Commits exclusivos.

3. Posição da `main`.

4. Posição da branch.

5. Posição do `HEAD`.

## 115. Desafio 4: Recebendo a branch de um colega

1. Peça ao colega o nome da branch publicada.

2. Execute:

```bash
git fetch origin
```

3. Liste:

```bash
git branch -r
```

4. Crie a branch local:

```bash
git switch --track origin/NOME_DA_BRANCH
```

5. Consulte:

```bash
git log --oneline
```

6. Abra os arquivos.

7. Não altere nem publique nada sem autorização.

## 116. Desafio 5: Troca segura

1. Entre em uma branch de teste.

2. Modifique um arquivo.

3. Não crie commit.

4. Execute:

```bash
git status
```

5. Tente trocar para outra branch.

6. Registre a mensagem apresentada pelo Git.

7. Crie um commit ou desfaça a alteração com orientação do professor.

8. Tente novamente.

Explique por que o Git pode impedir uma troca de branch.

## 117. Desafio 6: Branch temporária

Crie:

```text
test/branch_temporaria
```

Confirme:

```bash
git branch
```

Volte para a `main`:

```bash
git switch main
```

Exclua:

```bash
git branch -d test/branch_temporaria
```

Confirme novamente:

```bash
git branch
```

## 118. Desafio 7: Investigando branches remotas

Execute:

```bash
git fetch origin

git branch -r

git branch -a
```

Crie uma tabela contendo:

```text
Nome da branch

Local ou remota

Objetivo provável

Possui branch local correspondente
```

## 119. Desafio 8: Trabalho paralelo da equipe

Cada aluno deverá criar uma funcionalidade diferente.

Ao final, a equipe deverá apresentar:

1. Branches criadas.

2. Responsável por cada branch.

3. Arquivos modificados.

4. Quantidade de commits.

5. Mensagens utilizadas.

6. Branches publicadas.

7. Histórico em formato gráfico.

Nenhuma branch deverá ser integrada nesta aula.

# Parte 21: Avaliação

## 120. Critérios de avaliação

A atividade poderá valer 10 pontos.

### Atualização da main: 1 ponto

O aluno atualizou a branch principal antes de iniciar.

### Nome da branch: 1 ponto

A branch possui nome específico e padronizado.

### Criação e troca: 1 ponto

O aluno criou e entrou na branch correta.

### Desenvolvimento isolado: 1 ponto

A funcionalidade foi desenvolvida fora da `main`.

### Commits: 2 pontos

A branch possui pelo menos dois commits específicos.

### Publicação: 1 ponto

A branch foi publicada no GitHub.

### Acompanhamento remoto: 1 ponto

A branch local acompanha a branch remota.

### Comparação: 1 ponto

O aluno comparou a branch com a `main`.

### Histórico: 1 ponto

O aluno apresentou o gráfico das branches.

## 121. Evidências de aprendizagem

O aluno deverá apresentar:

1. Nome da branch.

2. Resultado de `git branch`.

3. Resultado de `git status`.

4. Histórico da branch.

5. Branch publicada no GitHub.

6. Resultado da comparação com a `main`.

7. Gráfico do histórico.

8. Respostas dos exercícios.

# Parte 22: Gabarito

## 122. Gabarito do exercício 1

### Questão 1

Branch é uma linha de desenvolvimento dentro do repositório.

### Questão 2

A `main` representa normalmente a versão principal do projeto.

### Questão 3

Trabalhar diretamente na `main` pode misturar funcionalidades incompletas e dificultar a revisão.

### Questão 4

O asterisco indica a branch atual.

### Questão 5

`git switch` troca a branch atual.

### Questão 6

`git branch nome` cria a branch sem entrar nela. `git switch -c nome` cria e entra na nova branch.

### Questão 7

Publicar uma branch significa enviá la para o repositório remoto.

### Questão 8

Não. Publicar a branch não altera automaticamente a `main`.

### Questão 9

Branch remota é uma branch existente no repositório remoto ou uma referência local correspondente a ela.

### Questão 10

`origin/main` representa a referência da branch `main` no remote `origin`.

### Questão 11

O comando compara as diferenças entre a `main` e a branch informada.

### Questão 12

Uma branch pode ser excluída quando o trabalho não é mais necessário ou já foi integrado e confirmado.

## 123. Gabarito do exercício 2

```text
A corresponde a 4.

B corresponde a 7.

C corresponde a 5.

D corresponde a 2.

E corresponde a 6.

F corresponde a 8.

G corresponde a 1.

H corresponde a 3.
```

## 124. Gabarito do exercício 3

### Listar branches

```bash
git branch
```

### Mostrar a branch atual

```bash
git branch --show-current
```

### Entrar na main

```bash
git switch main
```

### Criar e entrar

```bash
git switch -c feature/pagina_projetos
```

### Publicar

```bash
git push -u origin feature/pagina_projetos
```

### Listar remotas

```bash
git branch -r
```

### Excluir local

```bash
git branch -d nome_da_branch
```

## 125. Gabarito do exercício 4

### Situação 1

```text
feature/pagina_cadastro
```

### Situação 2

```text
fix/link_quebrado
```

### Situação 3

```text
docs/atualiza_readme
```

### Situação 4

```text
refactor/organiza_estilos
```

### Situação 5

```text
test/formulario_contato
```

## 126. Gabarito do exercício 5

### Adequados

```text
feature/pagina_contato

fix/correcao_menu

docs/atualiza_readme

refactor/organiza_estilos
```

### Inadequados

```text
teste

branch_nova

agora_vai

coisas
```

Os nomes inadequados não informam claramente o objetivo técnico da branch.

## 127. Gabarito do exercício 6

Ordem correta:

```text
Atualizar a main.

Criar a branch.

Desenvolver a funcionalidade.

Criar commits.

Publicar a nova branch.

Comparar a branch com a main.
```

## 128. Gabarito do exercício 7

1. O commit `a8137f2` está em `feature/pagina_contato`.

2. O commit `c905b24` está em `feature/lista_alunos`.

3. O último commit da `main` é `53bb821`.

4. Não. Os commits aparecem em uma linha separada da `main`.

5. Aparecem três linhas de desenvolvimento: `main`, página de contato e lista de alunos.

# Parte 23: Revisão oral

## 129. Perguntas para a turma

1. O que é uma branch?

2. Qual branch representa normalmente a versão principal?

3. Como verificamos a branch atual?

4. Como criamos uma branch sem entrar nela?

5. Como criamos e entramos em uma branch?

6. Como voltamos para a `main`?

7. Como publicamos uma branch?

8. Publicar é o mesmo que integrar?

9. Como listamos branches remotas?

10. Como comparamos duas branches?

11. O que representa `HEAD`?

12. Quando uma branch pode ser excluída?

# Parte 24: Resumo dos comandos

## 130. Listar branches

```bash
git branch
```

## 131. Mostrar a branch atual

```bash
git branch --show-current
```

## 132. Criar uma branch

```bash
git branch NOME_DA_BRANCH
```

## 133. Trocar de branch

```bash
git switch NOME_DA_BRANCH
```

## 134. Criar e trocar

```bash
git switch -c NOME_DA_BRANCH
```

## 135. Publicar

```bash
git push -u origin NOME_DA_BRANCH
```

## 136. Listar branches remotas

```bash
git branch -r
```

## 137. Listar todas

```bash
git branch -a
```

## 138. Comparar conteúdo

```bash
git diff main..NOME_DA_BRANCH
```

## 139. Comparar arquivos

```bash
git diff --name-only main..NOME_DA_BRANCH
```

## 140. Comparar commits

```bash
git log main..NOME_DA_BRANCH --oneline
```

## 141. Visualizar gráfico

```bash
git log --oneline --all --graph --decorate
```

## 142. Receber uma branch remota

```bash
git fetch origin

git switch --track origin/NOME_DA_BRANCH
```

## 143. Renomear

```bash
git branch -m NOME_NOVO
```

## 144. Excluir local

```bash
git branch -d NOME_DA_BRANCH
```

## 145. Excluir remota

```bash
git push origin --delete NOME_DA_BRANCH
```

# Parte 25: Fluxo completo da aula

## 146. Preparação

```bash
git switch main

git pull origin main

git status
```

## 147. Criação

```bash
git switch -c feature/nome_da_funcionalidade
```

## 148. Desenvolvimento

```bash
git status

git diff

git add .

git commit -m "Descrição da alteração"
```

## 149. Publicação

```bash
git push -u origin feature/nome_da_funcionalidade
```

## 150. Comparação

```bash
git diff --name-only main..feature/nome_da_funcionalidade

git log main..feature/nome_da_funcionalidade --oneline

git log --oneline --all --graph --decorate
```

# Parte 26: Encerramento

## 151. O que aprendemos

Nesta aula, eu mostrei que uma branch permite desenvolver uma parte do projeto sem alterar imediatamente a versão principal.

Aprendemos que:

```text
main representa a linha principal.

git branch lista ou cria branches.

git switch troca a branch atual.

git switch -c cria e entra em uma branch.

git push publica a branch.

git diff compara branches.

git log mostra a evolução do histórico.
```

Também vimos que várias pessoas podem desenvolver funcionalidades diferentes ao mesmo tempo.

Cada integrante trabalha em uma branch própria.

As alterações continuam separadas até o momento da integração.

## 152. Preparação para a próxima aula

Agora temos branches publicadas no GitHub.

Na próxima aula, vamos aprender a:

1. Integrar alterações.

2. Utilizar merge.

3. Criar Pull Requests.

4. Revisar o trabalho de outros alunos.

5. Aprovar ou solicitar mudanças.

6. Excluir branches depois da integração.

## 153. Frase de encerramento

Uma branch não serve apenas para separar arquivos.

Ela separa responsabilidades, decisões e etapas do desenvolvimento.

Quando cada tarefa possui sua própria branch, a equipe consegue trabalhar em paralelo sem perder o controle da versão principal.

# Referências

1. Documentação oficial do Git sobre branches  
   https://git-scm.com/docs/git-branch/pt_BR

2. Documentação oficial do Git sobre troca de branches  
   https://git-scm.com/docs/git-switch/pt_BR

3. Livro oficial Pro Git sobre gestão de branches  
   https://git-scm.com/book/pt-br/v2/Branches-no-Git-Gest%C3%A3o-de-Branches

4. Documentação oficial do GitHub sobre branches  
   https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches

5. Documentação oficial do GitHub sobre envio de branches  
   https://docs.github.com/pt/get-started/using-git/pushing-commits-to-a-remote-repository

6. Referência oficial de comandos Git  
   https://git-scm.com/docs
