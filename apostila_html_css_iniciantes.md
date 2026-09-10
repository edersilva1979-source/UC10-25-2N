# Apostila de HTML e CSS para Iniciantes

## Do zero ao site pronto

### Material didático para iniciantes

Nesta apostila nós vamos aprender HTML e CSS desde o início.

Nós vamos construir o conhecimento passo a passo, sempre entendendo primeiro o que estamos fazendo e depois colocando em prática.

O objetivo é que, ao final do material, nós consigamos criar um site completo, organizado, bonito, responsivo e pronto para ser publicado na internet.

Não precisamos ter experiência anterior com programação.

Vamos começar do zero.

---

# 1. O que nós vamos aprender

Durante esta apostila nós vamos aprender:

1. O que é HTML.
2. O que é CSS.
3. Como funciona um site.
4. Como criar nosso primeiro arquivo HTML.
5. Como organizar textos, títulos e parágrafos.
6. Como criar links.
7. Como colocar imagens.
8. Como criar listas.
9. Como criar tabelas.
10. Como criar formulários.
11. Como organizar uma página com HTML semântico.
12. Como usar CSS.
13. Como trabalhar com cores.
14. Como alterar fontes.
15. Como trabalhar com margens e espaçamentos.
16. Como usar classes e identificadores.
17. Como trabalhar com o Box Model.
18. Como criar layouts com Flexbox.
19. Como criar layouts com Grid.
20. Como criar menus.
21. Como criar cards.
22. Como criar botões.
23. Como criar páginas responsivas.
24. Como usar Media Queries.
25. Como organizar arquivos de um projeto.
26. Como construir um site completo.
27. Como preparar o site para publicação.

---

# 2. Antes de começar

Para acompanhar as aulas nós vamos precisar de algumas ferramentas.

## 2.1 Editor de código

Nós podemos utilizar o Visual Studio Code.

Ele será o programa onde vamos escrever nossos arquivos HTML e CSS.

Outros editores também podem ser utilizados, mas nesta apostila vamos considerar o Visual Studio Code.

## 2.2 Navegador

Nós também vamos precisar de um navegador.

Podemos utilizar:

1. Google Chrome.
2. Microsoft Edge.
3. Mozilla Firefox.
4. Opera.

O navegador será responsável por interpretar nosso código e mostrar o resultado na tela.

---

# 3. Como funciona um site

Quando acessamos um site, o navegador recebe arquivos e interpreta o conteúdo deles.

Os principais arquivos de uma página simples são:

1. HTML.
2. CSS.
3. JavaScript.

Nesta apostila vamos trabalhar com HTML e CSS.

## HTML

O HTML cria a estrutura da página.

Podemos imaginar o HTML como a estrutura de uma casa.

Ele define onde estarão:

1. Títulos.
2. Textos.
3. Imagens.
4. Botões.
5. Menus.
6. Formulários.
7. Rodapés.

## CSS

O CSS cuida da aparência.

Podemos imaginar o CSS como a pintura, a decoração e o acabamento da casa.

Com CSS podemos controlar:

1. Cores.
2. Tamanhos.
3. Fontes.
4. Espaçamentos.
5. Bordas.
6. Posicionamento.
7. Layout.
8. Responsividade.

---

# 4. Criando nosso primeiro projeto

Vamos criar uma pasta chamada:

```text
meu_primeiro_site
```

Dentro dela vamos criar dois arquivos:

```text
index.html
style.css
```

Nossa estrutura ficará assim:

```text
meu_primeiro_site
    index.html
    style.css
```

O arquivo `index.html` será nossa página principal.

O arquivo `style.css` será responsável pela aparência do site.

---

# 5. Nosso primeiro HTML

Vamos abrir o arquivo `index.html`.

Digite:

```html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Primeiro Site</title>
</head>

<body>

    <h1>Olá, mundo!</h1>
    <p>Este é o meu primeiro site.</p>

</body>

</html>
```

Agora salve o arquivo e abra no navegador.

Nós já temos nosso primeiro site funcionando.

---

# 6. Entendendo a estrutura do HTML

Vamos observar cada parte.

## 6.1 DOCTYPE

```html
<!DOCTYPE html>
```

Essa linha informa ao navegador que estamos utilizando HTML5.

## 6.2 Tag html

```html
<html lang="pt-BR">
```

Ela representa o início do documento HTML.

O atributo `lang="pt-BR"` informa que o conteúdo está em português do Brasil.

## 6.3 Head

```html
<head>
</head>
```

Dentro do `head` colocamos informações importantes sobre a página.

Essas informações geralmente não aparecem diretamente no conteúdo.

## 6.4 Charset

```html
<meta charset="UTF-8">
```

Essa linha permite que nossa página reconheça corretamente caracteres como:

```text
á
é
í
ó
ú
ç
ã
õ
```

## 6.5 Viewport

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Essa configuração ajuda nosso site a funcionar corretamente em celulares e tablets.

## 6.6 Title

```html
<title>Meu Primeiro Site</title>
```

Esse texto aparece na aba do navegador.

## 6.7 Body

```html
<body>
</body>
```

Dentro do `body` colocamos o conteúdo visível da página.

---

# 7. O que são tags HTML

O HTML utiliza tags.

Uma tag normalmente possui abertura e fechamento.

Exemplo:

```html
<p>Meu texto</p>
```

A abertura é:

```html
<p>
```

O fechamento é:

```html
</p>
```

O conteúdo fica entre as duas tags.

---

# 8. Títulos

O HTML possui seis níveis de título.

```html
<h1>Título principal</h1>

<h2>Subtítulo</h2>

<h3>Título nível 3</h3>

<h4>Título nível 4</h4>

<h5>Título nível 5</h5>

<h6>Título nível 6</h6>
```

O `h1` normalmente representa o título mais importante da página.

Exemplo:

```html
<h1>Curso de Desenvolvimento Web</h1>

<h2>HTML</h2>

<h3>Estrutura básica</h3>
```

---

# 9. Parágrafos

Para criar um parágrafo nós utilizamos a tag `p`.

```html
<p>Este é um parágrafo.</p>
```

Podemos criar vários.

```html
<p>Estamos aprendendo HTML.</p>

<p>Depois vamos aprender CSS.</p>

<p>No final vamos construir um site completo.</p>
```

---

# 10. Quebra de linha

Podemos utilizar a tag `br`.

```html
<p>
    Nome: João da Silva
    <br>
    Cidade: Porto Alegre
    <br>
    Curso: Desenvolvimento Web
</p>
```

---

# 11. Linha horizontal

Podemos utilizar:

```html
<hr>
```

Exemplo:

```html
<h2>Sobre mim</h2>

<p>Meu nome é João.</p>

<hr>

<h2>Contato</h2>

<p>Telefone: 99999 9999</p>
```

---

# 12. Formatação de texto

Podemos destacar partes do texto.

## Negrito

```html
<strong>Texto importante</strong>
```

## Itálico

```html
<em>Texto em destaque</em>
```

## Exemplo

```html
<p>
    Nós estamos estudando
    <strong>HTML</strong>
    e depois vamos estudar
    <em>CSS</em>.
</p>
```

---

# 13. Comentários

Comentários são anotações no código.

Eles não aparecem no navegador.

```html
<!-- Este é um comentário -->
```

Podemos utilizar comentários para organizar o projeto.

```html
<!-- Início do cabeçalho -->

<header>

</header>

<!-- Fim do cabeçalho -->
```

---

# 14. Links

Para criar um link usamos a tag `a`.

```html
<a href="https://www.google.com">Abrir Google</a>
```

## Abrindo em nova aba

```html
<a href="https://www.google.com" target="_blank">
    Abrir Google
</a>
```

## Link para outra página do projeto

Imagine que nós temos:

```text
index.html
sobre.html
```

Podemos criar:

```html
<a href="sobre.html">Sobre</a>
```

---

# 15. Criando várias páginas

Vamos criar:

```text
index.html
sobre.html
contato.html
```

No `index.html` podemos colocar:

```html
<nav>
    <a href="index.html">Início</a>
    <a href="sobre.html">Sobre</a>
    <a href="contato.html">Contato</a>
</nav>
```

Agora nós já temos uma navegação básica entre páginas.

---

# 16. Imagens

Para inserir uma imagem utilizamos:

```html
<img src="imagem.jpg" alt="Descrição da imagem">
```

O atributo `src` informa o caminho da imagem.

O atributo `alt` descreve a imagem.

## Criando uma pasta de imagens

Nossa estrutura pode ficar assim:

```text
meu_primeiro_site
    index.html
    style.css
    imagens
        logo.png
        foto.jpg
```

Para usar a imagem:

```html
<img src="imagens/foto.jpg" alt="Foto de exemplo">
```

---

# 17. Tamanho de imagem

Podemos definir largura usando HTML.

```html
<img src="imagens/foto.jpg" alt="Foto" width="300">
```

Porém, mais adiante vamos aprender que o ideal é controlar tamanhos pelo CSS.

---

# 18. Listas

Nós temos dois tipos principais de lista.

## Lista não ordenada

```html
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>
```

## Lista ordenada

```html
<ol>
    <li>Criar a pasta</li>
    <li>Criar o arquivo HTML</li>
    <li>Criar o arquivo CSS</li>
    <li>Abrir no navegador</li>
</ol>
```

---

# 19. Tabelas

Podemos criar tabelas com HTML.

```html
<table>
    <tr>
        <th>Nome</th>
        <th>Curso</th>
        <th>Turma</th>
    </tr>

    <tr>
        <td>Ana</td>
        <td>HTML</td>
        <td>A</td>
    </tr>

    <tr>
        <td>Carlos</td>
        <td>CSS</td>
        <td>B</td>
    </tr>
</table>
```

## Entendendo as tags

`table` cria a tabela.

`tr` cria uma linha.

`th` cria uma célula de cabeçalho.

`td` cria uma célula de dados.

---

# 20. Formulários

Formulários são muito comuns em sites.

Podemos utilizar formulários para:

1. Cadastro.
2. Login.
3. Contato.
4. Pesquisa.
5. Pedidos.
6. Comentários.

Exemplo:

```html
<form>

    <label>Nome</label>
    <input type="text">

    <label>Email</label>
    <input type="email">

    <button type="submit">Enviar</button>

</form>
```

---

# 21. Tipos de input

## Texto

```html
<input type="text">
```

## Email

```html
<input type="email">
```

## Senha

```html
<input type="password">
```

## Número

```html
<input type="number">
```

## Data

```html
<input type="date">
```

## Checkbox

```html
<input type="checkbox">
```

## Radio

```html
<input type="radio">
```

---

# 22. Campo obrigatório

Podemos utilizar `required`.

```html
<input type="text" required>
```

O navegador vai impedir o envio se o campo estiver vazio.

---

# 23. Placeholder

Podemos mostrar uma dica dentro do campo.

```html
<input
    type="text"
    placeholder="Digite seu nome"
>
```

---

# 24. Textarea

Para textos maiores utilizamos:

```html
<textarea></textarea>
```

Exemplo:

```html
<label>Mensagem</label>

<textarea
    rows="5"
    placeholder="Digite sua mensagem"
></textarea>
```

---

# 25. Select

Podemos criar uma caixa de seleção.

```html
<select>
    <option>HTML</option>
    <option>CSS</option>
    <option>JavaScript</option>
</select>
```

---

# 26. HTML semântico

HTML semântico significa utilizar tags que ajudam a indicar a função de cada parte da página.

Algumas tags importantes:

```html
<header></header>

<nav></nav>

<main></main>

<section></section>

<article></article>

<aside></aside>

<footer></footer>
```

Uma página pode ficar assim:

```html
<body>

    <header>
        <h1>Meu Site</h1>
    </header>

    <nav>
        <a href="#">Início</a>
        <a href="#">Sobre</a>
        <a href="#">Contato</a>
    </nav>

    <main>

        <section>
            <h2>Bem vindo</h2>
            <p>Este é nosso conteúdo principal.</p>
        </section>

    </main>

    <footer>
        <p>Todos os direitos reservados.</p>
    </footer>

</body>
```

---

# 27. Nossa primeira prática de HTML

Vamos criar uma página chamada `perfil.html`.

Ela deverá conter:

1. Um título com nosso nome.
2. Uma foto.
3. Um pequeno texto de apresentação.
4. Uma lista com três interesses.
5. Um link para um site que gostamos.
6. Um formulário de contato simples.

Exemplo de estrutura:

```html
<!DOCTYPE html>
<html lang="pt-BR">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Perfil</title>
</head>

<body>

    <h1>João da Silva</h1>

    <img
        src="imagens/perfil.jpg"
        alt="Foto de perfil"
        width="200"
    >

    <p>
        Estou aprendendo desenvolvimento web.
    </p>

    <h2>Meus interesses</h2>

    <ul>
        <li>Tecnologia</li>
        <li>Filmes</li>
        <li>Jogos</li>
    </ul>

    <h2>Contato</h2>

    <form>

        <label>Nome</label>
        <input type="text">

        <br><br>

        <label>Email</label>
        <input type="email">

        <br><br>

        <button type="submit">Enviar</button>

    </form>

</body>

</html>
```

---

# 28. Introdução ao CSS

Até agora nossa página funciona, mas ainda está simples.

Agora vamos começar a trabalhar com CSS.

CSS significa:

```text
Cascading Style Sheets
```

Em português podemos entender como folhas de estilo em cascata.

É o CSS que vai transformar nossa estrutura HTML em uma interface mais agradável.

---

# 29. Formas de usar CSS

Existem três formas principais.

## CSS inline

```html
<p style="color: blue;">Texto azul</p>
```

## CSS interno

```html
<style>
    p {
        color: blue;
    }
</style>
```

## CSS externo

É a forma que vamos utilizar na maior parte da apostila.

Criamos um arquivo:

```text
style.css
```

Depois conectamos ao HTML.

```html
<link rel="stylesheet" href="style.css">
```

Essa linha deve ficar dentro do `head`.

---

# 30. Primeiro CSS

No `style.css` vamos escrever:

```css
body {
    background-color: #f5f5f5;
    font-family: Arial, sans-serif;
}

h1 {
    color: #333333;
}

p {
    color: #555555;
}
```

Agora salve e atualize o navegador.

Nossa página já mudou.

---

# 31. Como funciona uma regra CSS

Observe:

```css
p {
    color: blue;
}
```

Nós temos três partes principais.

## Seletor

```css
p
```

Indica qual elemento será alterado.

## Propriedade

```css
color
```

Indica o que queremos modificar.

## Valor

```css
blue
```

Indica o novo valor.

---

# 32. Trabalhando com cores

Podemos usar nomes.

```css
color: red;
```

Podemos usar hexadecimal.

```css
color: #ff0000;
```

Podemos usar RGB.

```css
color: rgb(255, 0, 0);
```

Exemplo:

```css
body {
    background-color: #f4f6f8;
}

h1 {
    color: #1d3557;
}
```

---

# 33. Cor de fundo

Utilizamos:

```css
background-color: #eeeeee;
```

Exemplo:

```css
header {
    background-color: #222222;
    color: white;
}
```

---

# 34. Fontes

Podemos alterar a fonte com:

```css
font-family: Arial, sans-serif;
```

Exemplo:

```css
body {
    font-family: Arial, Helvetica, sans-serif;
}
```

---

# 35. Tamanho da fonte

```css
font-size: 18px;
```

Exemplo:

```css
h1 {
    font-size: 40px;
}

p {
    font-size: 18px;
}
```

---

# 36. Peso da fonte

```css
font-weight: bold;
```

Também podemos utilizar valores numéricos.

```css
font-weight: 400;
font-weight: 700;
```

---

# 37. Alinhamento do texto

```css
text-align: center;
```

Outras opções:

```css
text-align: left;
text-align: right;
text-align: justify;
```

---

# 38. Altura da linha

Podemos melhorar a leitura de textos.

```css
line-height: 1.6;
```

Exemplo:

```css
p {
    line-height: 1.6;
}
```

---

# 39. Classes

Classes permitem aplicar o mesmo estilo em vários elementos.

HTML:

```html
<p class="destaque">Texto 1</p>

<p>Texto normal</p>

<p class="destaque">Texto 2</p>
```

CSS:

```css
.destaque {
    color: red;
    font-weight: bold;
}
```

A classe é representada no CSS por um ponto.

```css
.destaque
```

---

# 40. Identificador

Podemos utilizar `id`.

HTML:

```html
<h1 id="titulo-principal">
    Curso de HTML e CSS
</h1>
```

CSS:

```css
#titulo-principal {
    color: darkblue;
}
```

O identificador é representado por `#`.

---

# 41. Diferença entre class e id

Normalmente usamos `class` quando o estilo pode aparecer várias vezes.

Usamos `id` quando queremos identificar um elemento específico.

Exemplo:

```html
<div class="card"></div>

<div class="card"></div>

<div class="card"></div>
```

Podemos repetir a classe.

---

# 42. Bordas

Podemos criar bordas.

```css
.card {
    border: 1px solid #cccccc;
}
```

Também podemos controlar o arredondamento.

```css
.card {
    border-radius: 10px;
}
```

---

# 43. Margem

Margem é o espaço externo do elemento.

```css
h1 {
    margin: 20px;
}
```

Podemos controlar cada lado.

```css
margin-top: 10px;
margin-right: 20px;
margin-bottom: 30px;
margin-left: 40px;
```

---

# 44. Padding

Padding é o espaço interno do elemento.

```css
.card {
    padding: 20px;
}
```

Imagine uma caixa.

A margem fica fora da caixa.

O padding fica entre a borda e o conteúdo.

---

# 45. Box Model

Todo elemento HTML pode ser imaginado como uma caixa.

Essa caixa possui:

1. Conteúdo.
2. Padding.
3. Borda.
4. Margem.

Exemplo:

```css
.caixa {
    width: 300px;
    padding: 20px;
    border: 2px solid black;
    margin: 20px;
}
```

---

# 46. Box sizing

Uma configuração muito utilizada é:

```css
* {
    box-sizing: border-box;
}
```

Ela facilita o controle dos tamanhos dos elementos.

Nós vamos utilizar essa regra em praticamente todos os nossos projetos.

---

# 47. Largura e altura

Podemos utilizar:

```css
width: 300px;
height: 200px;
```

Também podemos trabalhar com porcentagem.

```css
width: 100%;
```

---

# 48. Largura máxima

Uma técnica muito útil é:

```css
.container {
    max-width: 1200px;
    margin: 0 auto;
}
```

Isso cria um conteúdo centralizado e evita que ele fique largo demais em telas grandes.

---

# 49. Estilizando imagens

Podemos fazer:

```css
img {
    max-width: 100%;
    height: auto;
}
```

Assim a imagem se adapta melhor ao tamanho da tela.

---

# 50. Criando um container

HTML:

```html
<div class="container">

    <h1>Meu Site</h1>

    <p>Conteúdo da página.</p>

</div>
```

CSS:

```css
.container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 20px;
}
```

---

# 51. Estilizando links

HTML:

```html
<a href="#">Saiba mais</a>
```

CSS:

```css
a {
    color: #0056b3;
    text-decoration: none;
}
```

Quando o mouse passar por cima:

```css
a:hover {
    text-decoration: underline;
}
```

---

# 52. Criando botões

HTML:

```html
<a class="botao" href="#">
    Saiba mais
</a>
```

CSS:

```css
.botao {
    display: inline-block;
    background-color: #0056b3;
    color: white;
    padding: 12px 20px;
    border-radius: 8px;
    text-decoration: none;
}

.botao:hover {
    background-color: #003f82;
}
```

---

# 53. Display

Alguns valores importantes:

```css
display: block;
display: inline;
display: inline-block;
display: none;
display: flex;
display: grid;
```

Vamos estudar `flex` e `grid` com mais atenção.

---

# 54. Introdução ao Flexbox

Flexbox facilita o alinhamento dos elementos.

HTML:

```html
<div class="linha">

    <div>Item 1</div>

    <div>Item 2</div>

    <div>Item 3</div>

</div>
```

CSS:

```css
.linha {
    display: flex;
}
```

Agora os elementos ficam lado a lado.

---

# 55. Gap

Podemos criar espaço entre os elementos.

```css
.linha {
    display: flex;
    gap: 20px;
}
```

---

# 56. Justify content

Podemos controlar o alinhamento horizontal.

```css
.linha {
    display: flex;
    justify-content: center;
}
```

Outros valores:

```css
justify-content: flex-start;
justify-content: flex-end;
justify-content: space-between;
justify-content: space-around;
justify-content: space-evenly;
```

---

# 57. Align items

Podemos controlar o alinhamento vertical.

```css
.linha {
    display: flex;
    align-items: center;
}
```

---

# 58. Flex direction

Por padrão o Flexbox organiza em linha.

```css
flex-direction: row;
```

Podemos mudar para coluna.

```css
flex-direction: column;
```

---

# 59. Flex wrap

Se os elementos não couberem na mesma linha:

```css
.linha {
    display: flex;
    flex-wrap: wrap;
}
```

---

# 60. Criando cards

HTML:

```html
<section class="cards">

    <div class="card">
        <h3>HTML</h3>
        <p>Estrutura das páginas.</p>
    </div>

    <div class="card">
        <h3>CSS</h3>
        <p>Estilo das páginas.</p>
    </div>

    <div class="card">
        <h3>JavaScript</h3>
        <p>Interatividade das páginas.</p>
    </div>

</section>
```

CSS:

```css
.cards {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
}

.card {
    flex: 1;
    min-width: 250px;
    padding: 20px;
    border: 1px solid #dddddd;
    border-radius: 12px;
    background-color: white;
}
```

---

# 61. Criando um menu

HTML:

```html
<header>

    <div class="container cabecalho">

        <h1>Meu Site</h1>

        <nav>
            <a href="#">Início</a>
            <a href="#">Sobre</a>
            <a href="#">Serviços</a>
            <a href="#">Contato</a>
        </nav>

    </div>

</header>
```

CSS:

```css
header {
    background-color: #222222;
    padding: 20px 0;
}

.cabecalho {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

header h1 {
    color: white;
}

nav {
    display: flex;
    gap: 20px;
}

nav a {
    color: white;
    text-decoration: none;
}
```

---

# 62. Criando uma seção principal

HTML:

```html
<section class="hero">

    <div class="container">

        <h2>Aprenda desenvolvimento web</h2>

        <p>
            Comece pelo HTML, avance para o CSS
            e construa seus próprios sites.
        </p>

        <a class="botao" href="#">
            Começar agora
        </a>

    </div>

</section>
```

CSS:

```css
.hero {
    padding: 80px 20px;
    text-align: center;
    background-color: #f2f5f9;
}

.hero h2 {
    font-size: 42px;
    margin-bottom: 20px;
}

.hero p {
    font-size: 18px;
    margin-bottom: 30px;
}
```

---

# 63. CSS Grid

Grid é outra ferramenta poderosa de layout.

HTML:

```html
<div class="grade">

    <div class="card">1</div>

    <div class="card">2</div>

    <div class="card">3</div>

</div>
```

CSS:

```css
.grade {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Agora nós temos três colunas.

---

# 64. Grid com duas colunas

```css
.grade {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
}
```

---

# 65. Quando usar Flexbox ou Grid

De forma simples:

Flexbox é excelente quando estamos organizando elementos em uma direção principal.

Pode ser uma linha ou uma coluna.

Grid é excelente quando queremos trabalhar com linhas e colunas ao mesmo tempo.

Não existe obrigação de usar apenas um.

Em muitos projetos nós vamos utilizar os dois.

---

# 66. Responsividade

Um site responsivo se adapta ao tamanho da tela.

Ele deve funcionar bem em:

1. Computadores.
2. Notebooks.
3. Tablets.
4. Celulares.

Uma página que fica bonita somente no computador não está completa.

---

# 67. Media Queries

Podemos criar regras específicas para telas menores.

```css
@media (max-width: 768px) {

    .cabecalho {
        flex-direction: column;
        gap: 20px;
    }

}
```

Quando a tela tiver até 768 pixels, a regra será aplicada.

---

# 68. Menu responsivo simples

```css
@media (max-width: 768px) {

    nav {
        flex-direction: column;
        align-items: center;
    }

}
```

---

# 69. Cards responsivos

Com Grid:

```css
.cards-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

Tablet:

```css
@media (max-width: 900px) {

    .cards-grid {
        grid-template-columns: repeat(2, 1fr);
    }

}
```

Celular:

```css
@media (max-width: 600px) {

    .cards-grid {
        grid-template-columns: 1fr;
    }

}
```

---

# 70. Unidades de medida

Nós vamos encontrar várias unidades em CSS.

## Pixels

```css
font-size: 18px;
```

## Porcentagem

```css
width: 100%;
```

## Rem

```css
font-size: 1.2rem;
```

## Viewport width

```css
width: 100vw;
```

## Viewport height

```css
min-height: 100vh;
```

Para começar, podemos trabalhar principalmente com `px`, `%` e `rem`.

---

# 71. Border radius

Podemos arredondar cantos.

```css
.card {
    border-radius: 12px;
}
```

Para criar um círculo:

```css
.foto {
    width: 150px;
    height: 150px;
    border-radius: 50%;
}
```

---

# 72. Sombra

Podemos criar sombras.

```css
.card {
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}
```

Não precisamos decorar os valores.

O importante é entender que podemos controlar posição, intensidade e transparência.

---

# 73. Hover

Podemos mudar um elemento quando o mouse passa sobre ele.

```css
.card:hover {
    transform: translateY(-5px);
}
```

Também podemos combinar com transição.

```css
.card {
    transition: 0.3s;
}

.card:hover {
    transform: translateY(-5px);
}
```

---

# 74. Transition

Transições deixam mudanças visuais mais suaves.

```css
.botao {
    transition: 0.3s;
}
```

Quando o botão mudar de cor no `hover`, a mudança acontecerá de forma gradual.

---

# 75. Cursor

Podemos alterar o cursor.

```css
button {
    cursor: pointer;
}
```

---

# 76. Estilizando formulários

HTML:

```html
<form class="formulario">

    <label for="nome">Nome</label>

    <input
        type="text"
        id="nome"
        placeholder="Digite seu nome"
        required
    >

    <label for="email">Email</label>

    <input
        type="email"
        id="email"
        placeholder="Digite seu email"
        required
    >

    <label for="mensagem">Mensagem</label>

    <textarea
        id="mensagem"
        rows="5"
    ></textarea>

    <button type="submit">
        Enviar
    </button>

</form>
```

CSS:

```css
.formulario {
    max-width: 600px;
    margin: 0 auto;
}

.formulario label {
    display: block;
    margin-bottom: 6px;
    font-weight: bold;
}

.formulario input,
.formulario textarea {
    width: 100%;
    padding: 12px;
    margin-bottom: 18px;
    border: 1px solid #cccccc;
    border-radius: 8px;
    font-size: 16px;
}

.formulario button {
    background-color: #0056b3;
    color: white;
    border: none;
    padding: 12px 20px;
    border-radius: 8px;
    cursor: pointer;
}
```

---

# 77. Estilizando tabelas

HTML:

```html
<table class="tabela">

    <tr>
        <th>Curso</th>
        <th>Carga horária</th>
    </tr>

    <tr>
        <td>HTML</td>
        <td>20 horas</td>
    </tr>

    <tr>
        <td>CSS</td>
        <td>20 horas</td>
    </tr>

</table>
```

CSS:

```css
.tabela {
    width: 100%;
    border-collapse: collapse;
}

.tabela th,
.tabela td {
    border: 1px solid #cccccc;
    padding: 12px;
    text-align: left;
}

.tabela th {
    background-color: #222222;
    color: white;
}
```

---

# 78. Variáveis CSS

Podemos criar valores reutilizáveis.

```css
:root {
    --cor-principal: #0056b3;
    --cor-texto: #333333;
    --cor-fundo: #f5f5f5;
}
```

Depois podemos usar:

```css
body {
    color: var(--cor-texto);
    background-color: var(--cor-fundo);
}

.botao {
    background-color: var(--cor-principal);
}
```

Isso ajuda a manter o projeto organizado.

---

# 79. Organizando nosso CSS

Uma organização simples pode seguir esta ordem:

```css
/* Reset */

/* Configurações gerais */

/* Cabeçalho */

/* Menu */

/* Seção principal */

/* Cards */

/* Formulários */

/* Rodapé */

/* Responsividade */
```

Comentários ajudam bastante na manutenção.

---

# 80. Reset básico

Podemos começar nosso CSS assim:

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

Depois:

```css
body {
    font-family: Arial, Helvetica, sans-serif;
    color: #333333;
    background-color: #ffffff;
    line-height: 1.6;
}
```

---

# 81. Projeto final

Agora nós vamos construir um site completo.

Nosso site terá:

1. Cabeçalho.
2. Menu.
3. Seção principal.
4. Seção sobre.
5. Seção de serviços.
6. Cards.
7. Formulário de contato.
8. Rodapé.
9. Responsividade.

---

# 82. Estrutura do projeto final

Vamos criar:

```text
site_final
    index.html
    style.css
    imagens
        hero.jpg
        sobre.jpg
```

---

# 83. HTML completo do projeto final

Crie o arquivo `index.html`.

```html
<!DOCTYPE html>
<html lang="pt-BR">

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>WebStart</title>

    <link
        rel="stylesheet"
        href="style.css"
    >

</head>

<body>

    <header>

        <div class="container cabecalho">

            <h1 class="logo">WebStart</h1>

            <nav>

                <a href="#inicio">Início</a>

                <a href="#sobre">Sobre</a>

                <a href="#servicos">Serviços</a>

                <a href="#contato">Contato</a>

            </nav>

        </div>

    </header>

    <main>

        <section
            class="hero"
            id="inicio"
        >

            <div class="container">

                <h2>
                    Criando sites do zero
                </h2>

                <p>
                    Nós aprendemos HTML e CSS
                    construindo projetos reais.
                </p>

                <a
                    href="#servicos"
                    class="botao"
                >
                    Conhecer serviços
                </a>

            </div>

        </section>

        <section
            class="secao"
            id="sobre"
        >

            <div class="container duas-colunas">

                <div>

                    <h2>Sobre nós</h2>

                    <p>
                        Este projeto foi criado durante
                        nosso estudo de HTML e CSS.
                    </p>

                    <p>
                        Aqui colocamos em prática
                        estrutura, estilização,
                        Flexbox, Grid e responsividade.
                    </p>

                </div>

                <div>

                    <img
                        src="imagens/sobre.jpg"
                        alt="Pessoa trabalhando em um computador"
                    >

                </div>

            </div>

        </section>

        <section
            class="secao secao-cinza"
            id="servicos"
        >

            <div class="container">

                <h2 class="titulo-central">
                    Nossos serviços
                </h2>

                <div class="cards-grid">

                    <article class="card">

                        <h3>Sites institucionais</h3>

                        <p>
                            Criamos páginas organizadas
                            para empresas e profissionais.
                        </p>

                    </article>

                    <article class="card">

                        <h3>Landing pages</h3>

                        <p>
                            Criamos páginas focadas
                            em apresentar produtos,
                            serviços ou campanhas.
                        </p>

                    </article>

                    <article class="card">

                        <h3>Sites responsivos</h3>

                        <p>
                            Construímos páginas que
                            funcionam bem em computadores,
                            tablets e celulares.
                        </p>

                    </article>

                </div>

            </div>

        </section>

        <section
            class="secao"
            id="contato"
        >

            <div class="container">

                <h2 class="titulo-central">
                    Entre em contato
                </h2>

                <form class="formulario">

                    <label for="nome">
                        Nome
                    </label>

                    <input
                        type="text"
                        id="nome"
                        placeholder="Digite seu nome"
                        required
                    >

                    <label for="email">
                        Email
                    </label>

                    <input
                        type="email"
                        id="email"
                        placeholder="Digite seu email"
                        required
                    >

                    <label for="mensagem">
                        Mensagem
                    </label>

                    <textarea
                        id="mensagem"
                        rows="5"
                        placeholder="Digite sua mensagem"
                    ></textarea>

                    <button type="submit">
                        Enviar mensagem
                    </button>

                </form>

            </div>

        </section>

    </main>

    <footer>

        <div class="container">

            <p>
                WebStart. Projeto desenvolvido
                durante nosso curso de HTML e CSS.
            </p>

        </div>

    </footer>

</body>

</html>
```

---

# 84. CSS completo do projeto final

Agora crie o arquivo `style.css`.

```css
:root {
    --cor-principal: #0056b3;
    --cor-principal-escura: #003f82;
    --cor-texto: #333333;
    --cor-clara: #ffffff;
    --cor-fundo: #f5f7fa;
    --cor-borda: #dddddd;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    color: var(--cor-texto);
    background-color: var(--cor-clara);
    line-height: 1.6;
}

img {
    max-width: 100%;
    height: auto;
    display: block;
}

.container {
    width: 90%;
    max-width: 1100px;
    margin: 0 auto;
}

header {
    background-color: #222222;
    padding: 20px 0;
}

.cabecalho {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    color: white;
    font-size: 28px;
}

nav {
    display: flex;
    gap: 24px;
}

nav a {
    color: white;
    text-decoration: none;
    transition: 0.3s;
}

nav a:hover {
    opacity: 0.7;
}

.hero {
    background-color: var(--cor-fundo);
    padding: 100px 20px;
    text-align: center;
}

.hero h2 {
    font-size: 48px;
    margin-bottom: 20px;
}

.hero p {
    font-size: 20px;
    margin-bottom: 30px;
}

.botao {
    display: inline-block;
    background-color: var(--cor-principal);
    color: white;
    padding: 14px 24px;
    border-radius: 8px;
    text-decoration: none;
    transition: 0.3s;
}

.botao:hover {
    background-color: var(--cor-principal-escura);
}

.secao {
    padding: 80px 0;
}

.secao-cinza {
    background-color: var(--cor-fundo);
}

.titulo-central {
    text-align: center;
    margin-bottom: 40px;
    font-size: 34px;
}

.duas-colunas {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 40px;
    align-items: center;
}

.duas-colunas h2 {
    margin-bottom: 20px;
    font-size: 34px;
}

.duas-colunas p {
    margin-bottom: 16px;
}

.duas-colunas img {
    border-radius: 12px;
}

.cards-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
}

.card {
    background-color: white;
    padding: 28px;
    border: 1px solid var(--cor-borda);
    border-radius: 12px;
    transition: 0.3s;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.08);
}

.card h3 {
    margin-bottom: 12px;
}

.formulario {
    max-width: 650px;
    margin: 0 auto;
}

.formulario label {
    display: block;
    margin-bottom: 6px;
    font-weight: bold;
}

.formulario input,
.formulario textarea {
    width: 100%;
    padding: 12px;
    margin-bottom: 18px;
    border: 1px solid var(--cor-borda);
    border-radius: 8px;
    font-size: 16px;
}

.formulario textarea {
    resize: vertical;
}

.formulario button {
    width: 100%;
    background-color: var(--cor-principal);
    color: white;
    border: none;
    padding: 14px;
    border-radius: 8px;
    font-size: 16px;
    cursor: pointer;
    transition: 0.3s;
}

.formulario button:hover {
    background-color: var(--cor-principal-escura);
}

footer {
    background-color: #222222;
    color: white;
    text-align: center;
    padding: 30px 0;
}

@media (max-width: 900px) {

    .cards-grid {
        grid-template-columns: repeat(2, 1fr);
    }

}

@media (max-width: 768px) {

    .cabecalho {
        flex-direction: column;
        gap: 20px;
    }

    nav {
        flex-wrap: wrap;
        justify-content: center;
    }

    .hero h2 {
        font-size: 36px;
    }

    .duas-colunas {
        grid-template-columns: 1fr;
    }

}

@media (max-width: 600px) {

    .hero {
        padding: 70px 20px;
    }

    .hero h2 {
        font-size: 30px;
    }

    .hero p {
        font-size: 17px;
    }

    .cards-grid {
        grid-template-columns: 1fr;
    }

    .secao {
        padding: 60px 0;
    }

}
```

---

# 85. Testando o projeto

Depois de salvar os arquivos nós devemos testar o site.

Vamos verificar:

1. Se o menu funciona.
2. Se os links levam para as seções corretas.
3. Se as imagens aparecem.
4. Se o CSS foi carregado.
5. Se os cards estão organizados.
6. Se o formulário está alinhado.
7. Se o site funciona em uma tela pequena.

---

# 86. Testando no modo responsivo do navegador

No Google Chrome ou Microsoft Edge podemos abrir as ferramentas do desenvolvedor.

Podemos utilizar:

```text
F12
```

Depois podemos ativar o modo de dispositivo móvel.

Assim conseguimos testar diferentes tamanhos de tela.

Nós devemos observar:

1. Se existe conteúdo saindo da tela.
2. Se o texto continua legível.
3. Se o menu continua utilizável.
4. Se as imagens se adaptam.
5. Se os botões continuam fáceis de clicar.

---

# 87. Boas práticas de HTML

Vamos seguir algumas regras importantes.

## Use identação

Evite:

```html
<body><h1>Título</h1><p>Texto</p></body>
```

Prefira:

```html
<body>

    <h1>Título</h1>

    <p>Texto</p>

</body>
```

## Use nomes claros

Prefira:

```html
<section class="servicos">
```

Em vez de:

```html
<section class="x1">
```

## Sempre use alt em imagens

```html
<img
    src="imagem.jpg"
    alt="Aluno utilizando um computador"
>
```

---

# 88. Boas práticas de CSS

## Evite repetir estilos sem necessidade

Em vez de:

```css
h1 {
    color: blue;
}

h2 {
    color: blue;
}

h3 {
    color: blue;
}
```

Podemos fazer:

```css
h1,
h2,
h3 {
    color: blue;
}
```

## Organize o arquivo

Use comentários.

```css
/* Cabeçalho */

/* Conteúdo */

/* Rodapé */

/* Responsividade */
```

---

# 89. Erros comuns

## CSS não funciona

Verifique se o HTML possui:

```html
<link rel="stylesheet" href="style.css">
```

## Imagem não aparece

Verifique o caminho.

```html
<img src="imagens/foto.jpg" alt="Foto">
```

## Arquivo não abre corretamente

Verifique se foi salvo com a extensão correta.

```text
index.html
style.css
```

## Alterei o CSS e nada aconteceu

Atualize o navegador.

Podemos utilizar:

```text
Ctrl + F5
```

---

# 90. Exercício 1

Crie uma página chamada:

```text
apresentacao.html
```

Ela deve conter:

1. Seu nome.
2. Sua cidade.
3. Seu curso.
4. Uma foto.
5. Três hobbies.
6. Um link.
7. Um pequeno texto de apresentação.

---

# 91. Exercício 2

Crie uma página sobre um filme, série ou jogo.

Ela deve conter:

1. Título.
2. Imagem.
3. Sinopse.
4. Lista de personagens.
5. Link para um site relacionado.
6. Uma seção com sua opinião.

---

# 92. Exercício 3

Crie uma página de uma empresa fictícia.

Ela deve possuir:

1. Cabeçalho.
2. Nome da empresa.
3. Menu.
4. Seção sobre.
5. Três serviços.
6. Contato.
7. Rodapé.

Depois crie um arquivo CSS para estilizar a página.

---

# 93. Exercício 4

Crie três cards.

Cada card deverá possuir:

1. Título.
2. Texto.
3. Botão.

Os cards deverão ficar lado a lado no computador.

No celular deverão ficar um abaixo do outro.

---

# 94. Exercício 5

Crie um formulário contendo:

1. Nome.
2. Email.
3. Telefone.
4. Cidade.
5. Assunto.
6. Mensagem.
7. Botão enviar.

Depois estilize tudo com CSS.

---

# 95. Desafio final

Agora vamos criar nosso próprio site.

O tema pode ser escolhido pelos alunos.

Algumas ideias:

1. Portfólio pessoal.
2. Restaurante.
3. Loja fictícia.
4. Escola.
5. Academia.
6. Clínica.
7. Curso.
8. Pet shop.
9. Oficina.
10. Banda.
11. Fotografia.
12. Turismo.
13. Tecnologia.
14. Games.
15. Livros.

O site deverá possuir no mínimo:

1. Cabeçalho.
2. Menu.
3. Seção principal.
4. Duas seções de conteúdo.
5. Três cards.
6. Imagens.
7. Formulário.
8. Rodapé.
9. CSS externo.
10. Responsividade.

---

# 96. Checklist do projeto final

Antes de considerar o projeto concluído, vamos conferir:

1. O arquivo principal se chama `index.html`.
2. O CSS está em um arquivo separado.
3. O CSS foi conectado ao HTML.
4. As imagens estão em uma pasta organizada.
5. O menu funciona.
6. O site possui títulos bem definidos.
7. O conteúdo está organizado.
8. As imagens possuem `alt`.
9. O site possui formulário.
10. O site possui rodapé.
11. O layout funciona no computador.
12. O layout funciona no celular.
13. Não existe conteúdo saindo da tela.
14. O código está identado.
15. Os nomes das classes fazem sentido.

---

# 97. Estrutura recomendada para próximos projetos

Podemos organizar nossos projetos assim:

```text
meu_site
    index.html
    css
        style.css
    imagens
        logo.png
        banner.jpg
        foto1.jpg
```

Nesse caso nosso link para o CSS será:

```html
<link
    rel="stylesheet"
    href="css/style.css"
>
```

---

# 98. O que nós aprendemos

Ao longo desta apostila nós aprendemos a:

1. Criar páginas HTML.
2. Trabalhar com títulos e textos.
3. Inserir imagens.
4. Criar links.
5. Criar listas.
6. Criar tabelas.
7. Criar formulários.
8. Organizar páginas com HTML semântico.
9. Conectar HTML e CSS.
10. Trabalhar com cores.
11. Trabalhar com fontes.
12. Trabalhar com margem e padding.
13. Utilizar classes.
14. Utilizar identificadores.
15. Criar botões.
16. Criar menus.
17. Criar cards.
18. Utilizar Flexbox.
19. Utilizar Grid.
20. Criar layouts responsivos.
21. Utilizar Media Queries.
22. Criar um site completo.

---

# 99. Próximos passos

Depois de dominar HTML e CSS, nós podemos avançar para:

1. JavaScript.
2. Git.
3. GitHub.
4. Bootstrap.
5. APIs.
6. Frameworks.
7. Desenvolvimento Front End.
8. Desenvolvimento Full Stack.

Mas existe uma regra importante.

Antes de avançar, precisamos praticar.

HTML e CSS parecem simples quando estamos lendo.

O aprendizado realmente acontece quando nós abrimos o editor e começamos a construir.

Quanto mais páginas criarmos, mais natural será entender a estrutura, os estilos e a organização de um site.

---

# 100. Encerramento

Chegamos ao final da nossa apostila.

Começamos sem nenhuma página criada.

Aprendemos a estrutura do HTML, construímos textos, imagens, links, listas, formulários e seções.

Depois começamos a trabalhar com CSS, cores, fontes, espaçamentos, cards, menus, Flexbox, Grid e responsividade.

Por fim, juntamos tudo em um projeto completo.

Nosso próximo passo é continuar praticando.

Podemos modificar o projeto final.

Podemos trocar as cores.

Podemos trocar as fontes.

Podemos criar novas seções.

Podemos transformar o site em um portfólio.

Podemos criar uma página para uma empresa fictícia.

Podemos criar um site sobre um tema que gostamos.

O mais importante é continuar construindo.

Nós aprendemos desenvolvimento web desenvolvendo.

