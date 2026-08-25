# Aula 1: Introdução ao Git e ao Controle de Versão

## Git e GitHub na Prática

### Tema da aula

Introdução ao controle de versão, instalação e configuração do Git, criação de um repositório local e realização dos primeiros commits.

## 1. Objetivos da aula

Nesta aula, eu vou ensinar você a:

1. Entender o que é controle de versão.

2. Identificar problemas causados pela criação de várias cópias de um mesmo projeto.

3. Diferenciar Git de GitHub.

4. Instalar e configurar o Git.

5. Criar um repositório local.

6. Verificar a situação dos arquivos do projeto.

7. Preparar arquivos para um commit.

8. Registrar alterações por meio de commits.

9. Consultar o histórico do projeto.

10. Escrever mensagens de commit que expliquem corretamente as alterações realizadas.

## 2. Resultados esperados

Ao final da aula, você deverá conseguir criar uma pasta de projeto, transformá la em um repositório Git e registrar diferentes versões dos arquivos.

Você também deverá compreender o seguinte fluxo:

```text
Criar ou alterar arquivos

Verificar a situação do projeto

Preparar os arquivos

Criar um commit

Consultar o histórico
```

Esse fluxo será realizado com os seguintes comandos:

```bash
git init

git status

git add

git commit

git log
```

## 3. Recursos necessários

Para acompanhar esta aula, você precisará de:

1. Um computador com Windows, Linux ou macOS.

2. Acesso à internet para instalar o Git.

3. Visual Studio Code ou outro editor de código.

4. Terminal, Prompt de Comando, PowerShell ou Git Bash.

5. Conhecimentos básicos sobre arquivos e pastas.

6. Conhecimentos básicos de HTML.

## 4. Organização das quatro horas

### Primeiro momento: 

Introdução ao controle de versão, explicação sobre Git, GitHub, repositório, commit e histórico.

### Segundo momento: 

Instalação do Git, verificação da instalação e configuração do nome e email.

### Terceiro momento:

Criação do projeto Meu Primeiro Site, inicialização do repositório e primeiro commit.

### Quarto momento: 

Criação de novos arquivos, realização de novos commits e consulta ao histórico.

### Quinto momento: 

Exercícios, atividade colaborativa, desafios e correção.

# Parte 1: Por que precisamos de controle de versão?

## 5. Uma situação muito comum

Antes de começar a utilizar o Git, eu quero apresentar uma situação que provavelmente você já encontrou.

Imagine que estamos desenvolvendo um projeto chamado Sistema Escolar.

Durante o desenvolvimento, criamos as seguintes pastas:

```text
Sistema Escolar

Sistema Escolar Novo

Sistema Escolar Atualizado

Sistema Escolar Atualizado 2

Sistema Escolar Final

Sistema Escolar Final Corrigido

Sistema Escolar Final Agora Vai
```

No início, parece que estamos protegendo o projeto. Na prática, estamos criando vários problemas.

Depois de algum tempo, podemos não saber:

1. Qual pasta contém a versão mais recente.

2. Qual versão está funcionando.

3. Em qual pasta corrigimos um erro.

4. Qual arquivo foi alterado.

5. Quem realizou determinada mudança.

6. Como retornar para uma versão anterior.

7. Como reunir alterações feitas por diferentes pessoas.

O controle de versão foi criado para organizar esse processo.

## 6. O que é controle de versão?

Controle de versão é uma forma de registrar a evolução de um projeto.

Em vez de criar várias cópias da mesma pasta, eu mantenho um histórico das alterações realizadas.

Esse histórico permite responder perguntas como:

1. O que foi alterado?

2. Quando a alteração foi realizada?

3. Quem realizou a alteração?

4. Por que a alteração foi necessária?

5. Qual era o conteúdo anterior?

6. Em qual momento o erro apareceu?

Eu costumo comparar o controle de versão com o histórico de um documento.

Cada vez que concluímos uma alteração importante, criamos um registro daquele momento.

No Git, esse registro recebe o nome de commit.

## 7. O que é Git?

Git é um sistema de controle de versão.

Eu utilizo o Git para acompanhar alterações em arquivos e consultar o histórico de um projeto.

Embora seja muito utilizado em projetos de programação, o Git também pode controlar versões de documentos, arquivos Markdown, páginas HTML, configurações e outros arquivos de texto.

Com um repositório Git, eu posso registrar alterações, comparar versões, criar linhas separadas de desenvolvimento e retornar a estados anteriores do projeto.

## 8. O que é GitHub?

GitHub é uma plataforma que trabalha com repositórios Git.

O Git funciona no computador. O GitHub permite armazenar e compartilhar repositórios pela internet.

Nesta primeira aula, vamos trabalhar principalmente com o Git local.

O envio do projeto para o GitHub será estudado na próxima aula.

## 9. Diferença entre Git e GitHub

Eu explico essa diferença da seguinte maneira:

```text
Git

Ferramenta de controle de versão instalada no computador.

GitHub

Plataforma utilizada para armazenar e colaborar em projetos Git pela internet.
```

Uma comparação simples seria:

```text
Git é a ferramenta que registra a história.

GitHub é um local onde essa história pode ser compartilhada.
```

O Git não precisa do GitHub para funcionar.

Eu posso utilizar Git localmente sem publicar o projeto na internet.

Por outro lado, o GitHub utiliza os recursos do Git para organizar o histórico dos projetos e permitir a colaboração entre pessoas.

# Parte 2: Conceitos fundamentais

## 10. O que é um repositório?

Um repositório é uma pasta de projeto controlada pelo Git.

Quando eu transformo uma pasta comum em um repositório, o Git passa a acompanhar o que acontece dentro dela.

Por exemplo, podemos ter a seguinte pasta:

```text
meu primeiro site
```

Depois de inicializar o Git nessa pasta, ela passa a ser um repositório local.

O comando utilizado será:

```bash
git init
```

Esse comando cria a estrutura interna utilizada pelo Git para armazenar informações sobre o repositório e seu histórico.

Essa estrutura fica em uma pasta oculta chamada `.git`.

## 11. O que é um commit?

Um commit é um registro criado no histórico do projeto.

Eu posso imaginar um commit como uma fotografia de um momento importante do projeto.

Por exemplo:

```text
Commit 1

Cria a página inicial
```

Depois:

```text
Commit 2

Adiciona o título da página
```

Depois:

```text
Commit 3

Cria os estilos do site
```

Cada commit possui informações como:

1. Identificador.

2. Autor.

3. Data.

4. Mensagem.

5. Alterações registradas.

Um commit não deve ser criado a cada letra digitada.

Eu crio um commit quando concluo uma alteração que possui um objetivo compreensível.

## 12. O que é uma mensagem de commit?

A mensagem de commit explica o que foi alterado.

Observe estas mensagens:

```text
Alteração

Coisas novas

Atualização

Teste

Pronto
```

Essas mensagens não ajudam a entender o histórico.

Agora observe mensagens mais específicas:

```text
Cria a estrutura inicial da página

Adiciona formulário de contato

Corrige o link da página de produtos

Atualiza as informações do aluno

Adiciona estilos ao menu principal
```

Essas mensagens permitem compreender o que aconteceu sem precisar abrir todos os arquivos.

### Uma regra simples

Eu procuro completar mentalmente a frase:

```text
Este commit...
```

Exemplo:

```text
Este commit cria a estrutura inicial da página.
```

Por isso, uma boa mensagem seria:

```text
Cria a estrutura inicial da página
```

## 13. Os três estados principais

Para entender o funcionamento do Git, eu separo o projeto em três partes.

### 13.1 Área de trabalho

É onde eu crio e altero os arquivos.

Exemplos:

```text
index.html

estilo.css

README.md
```

### 13.2 Área de preparação

É onde eu escolho quais alterações entrarão no próximo commit.

Essa área também é conhecida como staging area.

O comando utilizado para preparar arquivos é:

```bash
git add
```

O comando `git add` prepara o conteúdo atual do arquivo.

Se o arquivo for alterado novamente depois desse comando, será necessário executar `git add` outra vez para preparar a nova alteração.

### 13.3 Repositório

É onde os commits ficam registrados.

O comando utilizado para criar um commit é:

```bash
git commit
```

## 14. Entendendo o fluxo

Observe o fluxo completo:

```text
Área de trabalho

Eu crio ou altero um arquivo.

        ↓

Área de preparação

Eu escolho o que será incluído no próximo commit.

        ↓

Repositório

Eu registro a alteração no histórico.
```

Os comandos seguem o mesmo fluxo:

```bash
git status

git add .

git commit -m "Mensagem do commit"
```

## 15. Uma comparação simples

Imagine que estou preparando uma encomenda.

A área de trabalho é a mesa onde estão todos os objetos.

A área de preparação é a caixa onde coloco somente os objetos que quero enviar.

O commit é o momento em que eu fecho, identifico e registro aquela caixa.

Nesse exemplo:

```text
Mesa

Área de trabalho
```

```text
Caixa aberta

Área de preparação
```

```text
Caixa fechada e registrada

Commit
```

# Parte 3: Instalação e configuração do Git

## 16. Instalando o Git no Windows

Para instalar o Git no Windows, eu sigo estes passos:

1. Acesso o site oficial do Git.

2. Escolho a versão para Windows.

3. Faço o download do instalador.

4. Executo o arquivo baixado.

5. Avanço pelas etapas de instalação.

6. Mantenho as configurações recomendadas para uma instalação inicial.

7. Finalizo a instalação.

Depois disso, posso utilizar:

1. Git Bash.

2. Prompt de Comando.

3. PowerShell.

4. Terminal integrado do Visual Studio Code.

## 17. Abrindo o terminal no Visual Studio Code

No Visual Studio Code, eu posso abrir o terminal da seguinte forma:

1. Abro o menu Terminal.

2. Seleciono Novo Terminal.

Também posso utilizar o atalho:

```text
Ctrl + '
```

O terminal normalmente será aberto na parte inferior do editor.

## 18. Verificando a instalação

Depois de instalar o Git, eu executo:

```bash
git --version
```

Uma resposta possível será semelhante a:

```text
git version 2.xx.x
```

O número exato poderá variar conforme a versão instalada.

Se uma versão for exibida, significa que o comando foi reconhecido.

## 19. Possível erro

Caso apareça uma mensagem dizendo que `git` não é reconhecido, verifico:

1. Se a instalação foi concluída.

2. Se o terminal foi fechado e aberto novamente.

3. Se o computador precisa ser reiniciado.

4. Se o Git foi incluído nas variáveis de ambiente.

## 20. Configurando o nome

Antes de criar commits, eu preciso informar ao Git quem está realizando as alterações.

Utilizo:

```bash
git config --global user.name "Nome do Aluno"
```

Exemplo:

```bash
git config --global user.name "Éder Silva"
```

## 21. Configurando o email

Depois, configuro o email:

```bash
git config --global user.email "aluno@email.com"
```

Exemplo:

```bash
git config --global user.email "eder@email.com"
```

Os valores configurados em `user.name` e `user.email` são utilizados nos dados de autoria dos commits.

## 22. O que significa global?

A opção `--global` indica que a configuração será utilizada nos repositórios do usuário atual do computador.

Normalmente, eu preciso configurar o nome e o email apenas uma vez.

## 23. Conferindo a configuração

Para consultar o nome configurado:

```bash
git config --global user.name
```

Para consultar o email:

```bash
git config --global user.email
```

Para visualizar diferentes configurações:

```bash
git config --list
```

## 24. Configurando o nome da branch inicial

Para utilizar `main` como nome padrão da branch inicial em novos repositórios, posso executar:

```bash
git config --global init.defaultBranch main
```

O conceito de branch será estudado detalhadamente nas próximas aulas.

Neste momento, basta entender que `main` representa a linha principal do projeto.

# Parte 4: Projeto prático

## 25. Projeto Meu Primeiro Site

Agora vamos criar nosso primeiro projeto controlado pelo Git.

O objetivo será desenvolver uma página HTML simples e registrar sua evolução em diferentes commits.

Ao final, teremos a seguinte estrutura:

```text
meu primeiro site

    index.html

    README.md

    css

        estilo.css
```

## 26. Criando a pasta do projeto

No terminal, escolho um local para criar o projeto.

Exemplo:

```bash
mkdir meu-primeiro-site
```

Depois, entro na pasta:

```bash
cd meu-primeiro-site
```

Para conferir o local atual no Git Bash:

```bash
pwd
```

Para listar os arquivos:

```bash
ls
```

No Prompt de Comando do Windows, posso utilizar:

```cmd
dir
```

## 27. Abrindo o projeto no Visual Studio Code

Dentro da pasta do projeto, executo:

```bash
code .
```

O ponto representa a pasta atual.

Se o comando `code` não estiver disponível, posso abrir o Visual Studio Code e selecionar a pasta manualmente.

# Parte 5: Criando o primeiro repositório

## 28. Verificando o estado inicial

Antes de inicializar o repositório, posso executar:

```bash
git status
```

Uma mensagem possível será:

```text
fatal: not a git repository
```

Essa mensagem indica que a pasta ainda não está sendo controlada pelo Git.

Não significa que o Git está quebrado.

Significa apenas que precisamos inicializar o repositório.

## 29. Inicializando o repositório

Executo:

```bash
git init
```

Uma mensagem semelhante poderá aparecer:

```text
Initialized empty Git repository
```

A partir desse momento, a pasta passou a ser um repositório Git.

## 30. O que mudou na pasta?

O comando `git init` cria uma pasta oculta chamada:

```text
.git
```

Essa pasta contém as informações utilizadas pelo Git.

Eu não preciso alterar manualmente os arquivos dessa pasta.

Também não devo apagar a pasta `.git` sem compreender o resultado.

Se ela for removida, a pasta do projeto continuará existindo, mas deixará de possuir o histórico Git local.

## 31. Verificando novamente

Agora executo:

```bash
git status
```

O Git poderá informar que ainda não existem commits e que não há arquivos para registrar.

O comando `git status` mostra as diferenças entre a área de trabalho, a área de preparação e o último commit.

Também mostra arquivos que ainda não estão sendo rastreados.

# Parte 6: Criando o primeiro arquivo

## 32. Criando o index.html

No Visual Studio Code, crio um arquivo chamado:

```text
index.html
```

Adiciono o seguinte conteúdo:

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Meu Primeiro Site com Git</title>
</head>

<body>
    <h1>Meu Primeiro Site</h1>

    <p>
        Este projeto será utilizado para aprender Git.
    </p>
</body>
</html>
```

Salvo o arquivo.

## 33. Consultando a situação do projeto

No terminal, executo:

```bash
git status
```

O Git deverá mostrar o arquivo `index.html` como não rastreado.

Em inglês, poderá aparecer:

```text
Untracked files
```

Isso significa que o arquivo existe na pasta, mas ainda não foi incluído no controle de versão.

## 34. Preparando o arquivo

Para preparar somente o arquivo `index.html`, executo:

```bash
git add index.html
```

Agora verifico:

```bash
git status
```

O arquivo deverá aparecer na área destinada às alterações que entrarão no próximo commit.

Em inglês, poderá aparecer:

```text
Changes to be committed
```

## 35. Criando o primeiro commit

Agora registro a alteração:

```bash
git commit -m "Cria a estrutura inicial da página"
```

A opção `-m` permite escrever a mensagem do commit diretamente no comando.

Depois, verifico novamente:

```bash
git status
```

Uma mensagem possível será:

```text
nothing to commit, working tree clean
```

Isso significa que não existem alterações pendentes.

## 36. O que acabamos de fazer?

Nosso processo foi:

```text
Criamos o arquivo index.html.

Executamos git status.

Preparamos o arquivo com git add.

Criamos um commit com git commit.
```

O primeiro ponto da história do projeto foi registrado.

# Parte 7: Criando o segundo commit

## 37. Criando o arquivo README

Agora crio um arquivo chamado:

```text
README.md
```

Adiciono o seguinte conteúdo:

```md
# Meu Primeiro Site

Projeto criado durante a aula de introdução ao Git.

## Objetivo

Aprender os principais comandos de controle de versão.

## Tecnologias

1. HTML
2. CSS
3. Git
```

Salvo o arquivo.

## 38. Verificando o novo arquivo

Executo:

```bash
git status
```

O arquivo `README.md` será apresentado como não rastreado.

## 39. Preparando todos os arquivos alterados

Posso preparar todos os arquivos da pasta atual com:

```bash
git add .
```

O ponto representa a pasta atual e as alterações correspondentes.

Depois, verifico:

```bash
git status
```

## 40. Criando o segundo commit

Executo:

```bash
git commit -m "Adiciona a documentação inicial do projeto"
```

Agora temos dois registros no histórico.

# Parte 8: Criando o terceiro commit

## 41. Criando a pasta CSS

No terminal, posso criar a pasta:

```bash
mkdir css
```

Dentro dela, crio o arquivo:

```text
estilo.css
```

Adiciono:

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    margin: 0;
    padding: 40px;
}

h1 {
    color: #222222;
}

p {
    color: #555555;
    font-size: 18px;
}
```

## 42. Ligando o CSS ao HTML

No arquivo `index.html`, dentro da seção `head`, acrescento:

```html
<link rel="stylesheet" href="css/estilo.css">
```

O conteúdo ficará semelhante a:

```html
<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>Meu Primeiro Site com Git</title>

    <link rel="stylesheet" href="css/estilo.css">
</head>
```

## 43. Verificando as alterações

Executo:

```bash
git status
```

Agora teremos duas situações:

```text
index.html foi modificado.

css/estilo.css ainda não está sendo rastreado.
```

## 44. Preparando as alterações

Executo:

```bash
git add .
```

Depois:

```bash
git status
```

## 45. Criando o terceiro commit

Executo:

```bash
git commit -m "Adiciona estilos à página inicial"
```

Agora o projeto possui três commits.

# Parte 9: Consultando o histórico

## 46. Utilizando git log

Para consultar o histórico completo, executo:

```bash
git log
```

O Git mostrará informações como:

1. Identificador do commit.

2. Autor.

3. Data.

4. Mensagem.

## 47. Identificador do commit

Cada commit possui um código.

Exemplo:

```text
a6b48c973f3f834cfab23173b1262c45f73d4fa1
```

Esse identificador permite localizar um commit específico.

Normalmente, não precisamos digitar o código inteiro.

Uma parte inicial que seja suficiente para identificar o commit poderá ser utilizada em vários comandos.

## 48. Histórico resumido

Para visualizar um histórico mais compacto, executo:

```bash
git log --oneline
```

Uma saída possível será:

```text
c821f30 Adiciona estilos à página inicial

e41ad22 Adiciona a documentação inicial do projeto

91fd401 Cria a estrutura inicial da página
```

O commit mais recente aparece primeiro.

## 49. Saindo da tela do histórico

Dependendo do terminal e da quantidade de informações, o Git poderá abrir o histórico em um visualizador.

Para sair, pressiono:

```text
q
```

# Parte 10: Compreendendo o comportamento do git add

## 50. Uma experiência importante

Vamos realizar um teste.

Primeiro, altero o arquivo `index.html` e acrescento:

```html
<h2>Conteúdos estudados</h2>
```

Depois, preparo o arquivo:

```bash
git add index.html
```

Agora volto ao arquivo e acrescento:

```html
<p>Repositório, status, add, commit e log.</p>
```

Executo:

```bash
git status
```

O Git poderá mostrar o mesmo arquivo em duas áreas.

Uma parte está preparada para o commit.

Outra parte foi alterada depois do comando `git add`.

Isso acontece porque `git add` prepara o conteúdo existente no momento em que o comando é executado.

Alterações posteriores precisam ser preparadas novamente.

## 51. Preparando novamente

Executo:

```bash
git add index.html
```

Agora todas as alterações atuais do arquivo estarão preparadas.

Crio o commit:

```bash
git commit -m "Adiciona lista de conteúdos estudados"
```

# Parte 11: A importância do git status

## 52. Meu comando de consulta

Durante as primeiras aulas, eu recomendo utilizar `git status` com frequência.

Antes de executar um comando, consulte:

```bash
git status
```

Depois de executar um comando, consulte novamente:

```bash
git status
```

Esse hábito ajuda a entender o que mudou.

Um fluxo seguro para iniciantes é:

```bash
git status

git add .

git status

git commit -m "Mensagem"

git status
```

## 53. O que o status pode mostrar?

O comando poderá indicar:

1. Arquivos não rastreados.

2. Arquivos modificados.

3. Arquivos preparados.

4. Arquivos ainda não preparados.

5. Ausência de alterações.

6. Branch atual.

7. Situações que precisam de atenção.

# Parte 12: Boas práticas para commits

## 54. Um commit deve possuir um objetivo

Eu evito colocar mudanças completamente diferentes dentro do mesmo commit.

Imagine que eu:

1. Criei uma página de contato.

2. Corrigi a cor do menu.

3. Alterei o nome de um produto.

4. Removi uma imagem.

Se eu registrar tudo em um único commit, será mais difícil compreender o histórico.

O ideal é separar as alterações por objetivo.

Exemplo:

```text
Commit 1

Cria a página de contato
```

```text
Commit 2

Corrige a cor do menu principal
```

```text
Commit 3

Atualiza o nome do produto
```

```text
Commit 4

Remove imagem duplicada
```

## 55. Características de uma boa mensagem

Uma boa mensagem deve ser:

1. Objetiva.

2. Específica.

3. Relacionada ao conteúdo do commit.

4. Compreensível para outra pessoa.

5. Útil quando consultada no futuro.

## 56. Comparando mensagens

### Mensagem pouco informativa

```bash
git commit -m "Alterações"
```

### Mensagem melhor

```bash
git commit -m "Adiciona informações de contato ao rodapé"
```

### Mensagem pouco informativa

```bash
git commit -m "Correção"
```

### Mensagem melhor

```bash
git commit -m "Corrige o endereço da imagem principal"
```

### Mensagem pouco informativa

```bash
git commit -m "Teste"
```

### Mensagem melhor

```bash
git commit -m "Adiciona validação ao campo de email"
```

# Parte 13: Erros comuns

## 57. Executar git status fora do projeto

### Mensagem possível

```text
fatal: not a git repository
```

### Motivo

O terminal não está dentro de uma pasta inicializada pelo Git.

### Como verificar

No Git Bash:

```bash
pwd
```

Depois, acesso a pasta correta:

```bash
cd caminho-do-projeto
```

## 58. Esquecer de executar git add

O aluno altera um arquivo e tenta executar:

```bash
git commit -m "Atualiza a página"
```

O Git poderá informar que existem alterações, mas nenhuma está preparada.

### Solução

```bash
git add .

git commit -m "Atualiza a página"
```

## 59. Esquecer a mensagem do commit

Ao executar apenas:

```bash
git commit
```

O Git poderá abrir um editor para que a mensagem seja escrita.

Para evitar isso durante a aula inicial, utilizamos:

```bash
git commit -m "Mensagem do commit"
```

## 60. Nome ou email não configurado

O Git poderá informar que não conhece a identidade do autor.

### Solução

```bash
git config --global user.name "Nome do Aluno"

git config --global user.email "aluno@email.com"
```

## 61. Criar um commit sem alterações

Se eu executar um commit sem possuir alterações preparadas, o Git informará que não existe nada para registrar.

Isso não é um problema.

Significa apenas que nenhum arquivo novo ou modificado está pronto para um novo commit.

## 62. Escrever uma mensagem muito genérica

Evito mensagens como:

```text
Atualização

Mudança

Pronto

Teste

Coisas

Final
```

Procuro explicar a ação:

```text
Atualiza o texto de apresentação

Adiciona o menu de navegação

Corrige a cor do título

Cria a página de contato
```

## 63. Apagar a pasta .git

Se a pasta `.git` for apagada, os arquivos do projeto continuam existindo, mas o histórico local e a configuração daquele repositório deixam de estar disponíveis.

Por isso, não altero ou removo essa pasta durante as atividades.

# Parte 14: Prática guiada completa

## 64. Sequência de comandos da aula

### Verificar a instalação

```bash
git --version
```

### Configurar o nome

```bash
git config --global user.name "Nome do Aluno"
```

### Configurar o email

```bash
git config --global user.email "aluno@email.com"
```

### Criar a pasta

```bash
mkdir meu-primeiro-site
```

### Entrar na pasta

```bash
cd meu-primeiro-site
```

### Abrir no Visual Studio Code

```bash
code .
```

### Inicializar o repositório

```bash
git init
```

### Consultar a situação

```bash
git status
```

### Preparar um arquivo específico

```bash
git add index.html
```

### Preparar todas as alterações

```bash
git add .
```

### Criar um commit

```bash
git commit -m "Cria a estrutura inicial da página"
```

### Consultar o histórico completo

```bash
git log
```

### Consultar o histórico resumido

```bash
git log --oneline
```

# Parte 15: Exercícios de fixação

## 65. Exercício 1: Conceitos

Responda com suas palavras.

1. O que é controle de versão?

2. Qual é a diferença entre Git e GitHub?

3. O que é um repositório?

4. O que é um commit?

5. Para que serve a mensagem de commit?

6. O que é a área de preparação?

7. Qual comando mostra a situação dos arquivos?

8. Qual comando prepara um arquivo?

9. Qual comando registra uma alteração no histórico?

10. Qual comando mostra o histórico dos commits?

## 66. Exercício 2: Relacione os comandos

Relacione cada comando com sua função.

### Comandos

```text
A. git init

B. git status

C. git add

D. git commit

E. git log
```

### Funções

```text
1. Mostra o histórico de commits.

2. Inicializa um repositório.

3. Registra alterações no histórico.

4. Mostra a situação dos arquivos.

5. Prepara arquivos para o próximo commit.
```

## 67. Exercício 3: Complete os comandos

### Verificar a versão instalada

```bash
git __________
```

### Inicializar um repositório

```bash
git __________
```

### Verificar a situação dos arquivos

```bash
git __________
```

### Preparar todos os arquivos

```bash
git add __________
```

### Criar um commit

```bash
git commit __________ "Cria a página inicial"
```

### Consultar o histórico resumido

```bash
git log __________
```

## 68. Exercício 4: Avaliação de mensagens

Classifique cada mensagem como adequada ou inadequada.

1. `Alterações`

2. `Cria a página de cadastro`

3. `Teste`

4. `Corrige o cálculo do valor total`

5. `Pronto`

6. `Adiciona estilos ao formulário`

7. `Coisas novas`

8. `Atualiza o endereço da empresa`

Depois, reescreva as mensagens inadequadas.

## 69. Exercício 5: Organize o fluxo

Coloque as ações na ordem correta.

```text
Criar o commit

Alterar o arquivo

Executar git add

Executar git status

Consultar o histórico
```

## 70. Exercício 6: Projeto individual

Crie um projeto chamado:

```text
minha apresentação
```

O projeto deverá possuir:

```text
index.html

README.md

css/estilo.css
```

O arquivo `index.html` deverá apresentar:

1. Seu nome.

2. Sua turma.

3. Uma breve apresentação.

4. Três tecnologias que deseja aprender.

5. Um objetivo profissional.

O projeto deverá possuir pelo menos quatro commits.

### Sugestão de commits

```text
Cria a estrutura inicial da apresentação

Adiciona informações pessoais

Adiciona lista de tecnologias

Cria os estilos da página
```

# Parte 16: Atividade colaborativa

## 71. Revisão de histórico em duplas

Nesta atividade, cada aluno deverá trabalhar com um colega.

### Etapa 1

O aluno A executará:

```bash
git log --oneline
```

O aluno B analisará as mensagens.

### Etapa 2

O aluno B verificará:

1. Se as mensagens explicam as alterações.

2. Se existem mensagens genéricas.

3. Se os commits representam etapas compreensíveis.

4. Se o histórico apresenta uma sequência lógica.

### Etapa 3

Os alunos trocam as funções.

### Etapa 4

Cada aluno registra em uma folha ou arquivo:

```text
Uma mensagem de commit bem escrita pelo colega.

Uma mensagem que poderia ser melhorada.

Uma sugestão de nova mensagem.
```

## 72. Discussão com a turma

Depois da atividade, eu apresento algumas perguntas:

1. Foi possível compreender o projeto apenas pelas mensagens?

2. Quais mensagens foram mais fáceis de entender?

3. Quais mensagens causaram dúvidas?

4. Como uma mensagem mal escrita pode prejudicar uma equipe?

5. Por que devemos criar commits em etapas?

# Parte 17: Desafios

## 73. Desafio 1: Linha do tempo do site

Crie um projeto chamado:

```text
linha-do-tempo
```

Crie os arquivos:

```text
index.html

README.md

estilo.css
```

O projeto deverá possuir cinco commits.

### Commit 1

Criar a estrutura HTML.

### Commit 2

Adicionar um título e um parágrafo.

### Commit 3

Adicionar uma lista de eventos.

### Commit 4

Criar os estilos.

### Commit 5

Atualizar o README.

Ao final, execute:

```bash
git log --oneline
```

Copie o resultado e entregue ao professor.

## 74. Desafio 2: Detetive do histórico

Observe este histórico:

```text
8ad2f10 Atualização

1b6c940 Cria a página de contato

14cf002 Coisas

71ad9f1 Corrige o link da página inicial

22b8301 Teste
```

Responda:

1. Quais mensagens estão adequadas?

2. Quais mensagens estão inadequadas?

3. Como você reescreveria as mensagens inadequadas?

4. É possível entender completamente o histórico?

5. Que problema essas mensagens poderiam causar em um projeto com vários participantes?

## 75. Desafio 3: Commit seletivo

Crie dois arquivos:

```text
aluno.html

curso.html
```

Adicione conteúdos diferentes em cada arquivo.

Execute:

```bash
git status
```

Prepare somente o arquivo `aluno.html`:

```bash
git add aluno.html
```

Execute novamente:

```bash
git status
```

Crie o commit:

```bash
git commit -m "Cria a página do aluno"
```

Depois, verifique:

```bash
git status
```

Responda:

1. Qual arquivo entrou no commit?

2. Qual arquivo continuou fora do commit?

3. Por que isso aconteceu?

4. Qual comando deverá ser utilizado para preparar o segundo arquivo?

## 76. Desafio 4: Mudança depois do git add

Crie um arquivo chamado:

```text
anotacoes.md
```

Adicione:

```md
# Anotações da Aula

Hoje comecei a estudar Git.
```

Prepare o arquivo:

```bash
git add anotacoes.md
```

Sem criar o commit, altere novamente o arquivo:

```md
## Comandos estudados

git init

git status

git add
```

Execute:

```bash
git status
```

Observe o resultado.

Depois, execute novamente:

```bash
git add anotacoes.md
```

Crie o commit:

```bash
git commit -m "Registra anotações da primeira aula"
```

Explique por que foi necessário executar `git add` novamente.

## 77. Desafio 5: Projeto Portal da Turma

Este desafio inicia o projeto que será utilizado durante o curso.

Crie uma pasta chamada:

```text
portal-da-turma
```

Dentro dela, crie:

```text
index.html

README.md

css/estilo.css
```

A página deverá possuir:

1. Nome da turma.

2. Nome do curso.

3. Nome da instituição.

4. Lista inicial de conteúdos.

5. Área para projetos.

6. Rodapé com o ano.

Crie pelo menos cinco commits.

### Exemplos de mensagens

```text
Cria a estrutura inicial do portal

Adiciona informações da turma

Cria seção de conteúdos

Adiciona área de projetos

Cria estilos da página inicial
```

Esse projeto será publicado no GitHub nas próximas aulas.

# Parte 18: Perguntas para revisão oral

## 78. Revisão rápida

Ao final da aula, eu posso fazer as seguintes perguntas:

1. Git e GitHub são a mesma coisa?

2. O Git precisa de internet para criar commits locais?

3. Para que serve `git init`?

4. Para que serve `git status`?

5. O que acontece quando executamos `git add`?

6. Para que serve `git commit`?

7. O que uma mensagem de commit deve explicar?

8. Qual é a função do `git log`?

9. O que significa um arquivo não rastreado?

10. O que significa a mensagem de área de trabalho limpa?

# Parte 19: Avaliação da aula

## 79. Critérios de avaliação

A atividade prática poderá valer 10 pontos.

### Configuração do Git: 1 ponto

O aluno configurou nome e email corretamente.

### Criação do repositório: 1 ponto

O projeto foi inicializado com `git init`.

### Estrutura do projeto: 2 pontos

Os arquivos solicitados foram criados corretamente.

### Utilização do git status: 1 ponto

O aluno demonstrou compreender a situação dos arquivos.

### Utilização do git add: 1 ponto

Os arquivos foram preparados corretamente.

### Commits: 2 pontos

O projeto possui a quantidade mínima de commits.

### Mensagens: 1 ponto

As mensagens explicam as alterações.

### Histórico: 1 ponto

O aluno conseguiu apresentar o resultado de:

```bash
git log --oneline
```

## 80. Evidências de aprendizagem

O aluno deverá entregar:

1. A pasta do projeto.

2. A estrutura de arquivos.

3. O resultado do histórico resumido.

4. As respostas dos exercícios.

5. Uma breve explicação sobre o fluxo do Git.

# Parte 20: Gabarito

## 81. Gabarito do exercício 1

### Questão 1

Controle de versão é um sistema utilizado para registrar e acompanhar as alterações de um projeto.

### Questão 2

Git é o sistema de controle de versão.

GitHub é uma plataforma utilizada para armazenar e colaborar em repositórios Git pela internet.

### Questão 3

Repositório é uma pasta de projeto controlada pelo Git.

### Questão 4

Commit é um registro criado no histórico do projeto.

### Questão 5

A mensagem explica o que foi alterado no commit.

### Questão 6

A área de preparação é o local onde escolhemos as alterações que serão incluídas no próximo commit.

### Questão 7

```bash
git status
```

### Questão 8

```bash
git add
```

### Questão 9

```bash
git commit
```

### Questão 10

```bash
git log
```

## 82. Gabarito do exercício 2

```text
A corresponde a 2.

B corresponde a 4.

C corresponde a 5.

D corresponde a 3.

E corresponde a 1.
```

## 83. Gabarito do exercício 3

### Verificar a versão

```bash
git --version
```

### Inicializar o repositório

```bash
git init
```

### Verificar a situação

```bash
git status
```

### Preparar todos os arquivos

```bash
git add .
```

### Criar o commit

```bash
git commit -m "Cria a página inicial"
```

### Consultar o histórico resumido

```bash
git log --oneline
```

## 84. Gabarito do exercício 4

### Inadequadas

```text
Alterações

Teste

Pronto

Coisas novas
```

### Adequadas

```text
Cria a página de cadastro

Corrige o cálculo do valor total

Adiciona estilos ao formulário

Atualiza o endereço da empresa
```

As mensagens inadequadas deverão ser reescritas de acordo com a alteração realmente realizada.

## 85. Gabarito do exercício 5

A ordem correta é:

```text
Alterar o arquivo

Executar git status

Executar git add

Criar o commit

Consultar o histórico
```

# Parte 21: Resumo da aula

## 86. O que aprendemos

Nesta aula, eu apresentei o Git como uma ferramenta de controle de versão.

Aprendemos que um projeto Git possui um histórico formado por commits.

Também aprendemos o fluxo básico:

```text
Eu altero os arquivos.

Eu verifico a situação.

Eu preparo as alterações.

Eu crio um commit.

Eu consulto o histórico.
```

Os principais comandos foram:

```bash
git --version

git config --global user.name "Nome"

git config --global user.email "email"

git init

git status

git add .

git commit -m "Mensagem"

git log

git log --oneline
```

## 87. Frase de encerramento

O Git não substitui o ato de salvar um arquivo.

Ele registra momentos importantes da evolução do projeto.

Quando os commits são organizados e possuem mensagens específicas, o histórico deixa de ser apenas uma sequência técnica e passa a explicar como o projeto foi construído.

# Referências

1. Documentação oficial do Git  
   https://git-scm.com/docs

2. Documentação oficial do GitHub sobre Git  
   https://docs.github.com/pt/get-started/using-git/about-git

3. Documentação do comando git init  
   https://git-scm.com/docs/git-init

4. Documentação do comando git add  
   https://git-scm.com/docs/git-add

5. Documentação do comando git status  
   https://git-scm.com/docs/git-status

6. Documentação do comando git commit  
   https://git-scm.com/docs/git-commit

7. Documentação do comando git log  
   https://git-scm.com/docs/git-log
