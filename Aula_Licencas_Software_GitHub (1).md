# Aula: Licenças de Software no GitHub

## 1. Introdução

Quando publicamos um projeto no GitHub, não estamos apenas mostrando nosso código.

Também precisamos informar o que outras pessoas podem fazer com ele.

É justamente para isso que existe uma licença de software.

A licença funciona como um conjunto de regras que informa se outras pessoas podem usar, copiar, modificar, distribuir ou até vender um software desenvolvido por nós.

Sem uma licença definida, outras pessoas podem visualizar o código em um repositório público, mas isso não significa automaticamente que elas possuem autorização para copiar, modificar ou redistribuir o projeto.

Nesta aula, nós vamos conhecer quatro licenças muito utilizadas em projetos de software:

1. MIT

2. Apache 2.0

3. GPL

4. BSD

Vamos entender o que cada uma permite, quais responsabilidades cria e em quais situações podemos utilizá la.

## 2. Antes de Escolher uma Licença

Antes de escolher uma licença, precisamos pensar em algumas perguntas.

### Pergunta 1

Eu quero permitir que outras pessoas utilizem meu código livremente?

### Pergunta 2

Eu quero permitir que empresas utilizem meu código em produtos comerciais?

### Pergunta 3

Se alguém modificar meu projeto, quero obrigar essa pessoa a publicar também o código modificado quando distribuir essa nova versão?

### Pergunta 4

Eu preciso de uma licença com regras mais detalhadas sobre patentes?

### Pergunta 5

Meu objetivo é ensino, projeto pessoal, biblioteca, projeto comercial ou software livre?

As respostas ajudam bastante na escolha.

# 3. Licença MIT

## 3.1 O que é

A licença MIT é uma das licenças mais conhecidas e simples do desenvolvimento de software.

Ela é considerada uma licença permissiva.

Isso significa que ela permite que outras pessoas façam bastante coisa com o código.

Uma pessoa pode:

1. Usar o projeto.

2. Copiar o código.

3. Modificar o código.

4. Distribuir o projeto.

5. Utilizar o código em projetos comerciais.

6. Criar outro software baseado nele.

A principal obrigação é manter o aviso de direitos autorais e o texto da licença.

## 3.2 Exemplo simples

Imagine que nós criamos uma biblioteca Java para validar CPF.

Nós publicamos essa biblioteca utilizando a licença MIT.

Uma empresa poderia utilizar nossa biblioteca dentro de um sistema comercial.

Ela também poderia modificar o código.

A empresa não seria obrigada a transformar todo o sistema dela em código aberto.

Ela precisaria respeitar os avisos da licença.

## 3.3 Quando usar MIT

A licença MIT costuma ser uma boa escolha quando queremos:

1. Compartilhar projetos educacionais.

2. Criar bibliotecas abertas.

3. Permitir ampla reutilização do código.

4. Facilitar o uso do projeto por outros desenvolvedores.

5. Permitir uso comercial.

6. Manter poucas exigências para quem reutilizar o código.

## 3.4 Exemplo de projeto

```text
BibliotecaValidacaoJava
```

Objetivo:

Criar métodos reutilizáveis para validar CPF, CNPJ, email e telefone.

Nesse caso, a licença MIT pode fazer bastante sentido porque queremos que outras pessoas consigam utilizar a biblioteca facilmente.

## 3.5 Resumindo MIT

Podemos pensar assim:

MIT permite usar, copiar, modificar e distribuir, desde que os avisos exigidos pela licença sejam preservados.

# 4. Licença Apache 2.0

## 4.1 O que é

A licença Apache 2.0 também é uma licença permissiva.

Ela permite:

1. Usar o software.

2. Modificar.

3. Distribuir.

4. Utilizar comercialmente.

5. Incorporar o código em outros projetos.

Ela é parecida com a MIT em vários aspectos.

Porém, a Apache 2.0 possui regras mais detalhadas.

Uma das diferenças importantes é o tratamento explícito de patentes.

## 4.2 O que isso significa

Em projetos maiores, principalmente aqueles desenvolvidos por empresas ou comunidades grandes, pode existir preocupação com tecnologias que envolvem patentes.

A Apache 2.0 possui uma concessão explícita de patente feita pelos contribuidores, dentro das condições estabelecidas pela própria licença.

Para nossos alunos, podemos simplificar assim:

A Apache 2.0 oferece permissões amplas, como a MIT, mas possui regras jurídicas mais detalhadas e uma proteção mais clara em relação a patentes.

## 4.3 Quando usar Apache 2.0

Ela pode ser interessante quando:

1. O projeto é uma biblioteca importante.

2. Muitas pessoas ou empresas poderão colaborar.

3. Existe possibilidade de uso comercial.

4. Queremos uma licença permissiva.

5. Queremos regras mais detalhadas sobre contribuições e patentes.

## 4.4 Exemplo de projeto

```text
FrameworkRelatoriosJava
```

Esse projeto cria uma estrutura para gerar relatórios em aplicações Java.

Empresas poderão utilizar o framework em seus próprios sistemas.

Como queremos permitir uso comercial, mas também desejamos uma licença mais detalhada, podemos escolher Apache 2.0.

## 4.5 Resumindo Apache 2.0

Podemos pensar assim:

Apache 2.0 é parecida com a MIT, mas possui regras mais detalhadas e atenção explícita a patentes.

# 5. Licença GPL

## 5.1 O que é

GPL significa GNU General Public License.

Ela possui uma característica muito diferente das licenças MIT e Apache 2.0.

A GPL utiliza um princípio conhecido como copyleft.

Esse princípio procura garantir que versões derivadas distribuídas continuem mantendo as liberdades oferecidas pelo projeto original.

## 5.2 Exemplo simples

Imagine que nós criamos um sistema utilizando GPL.

Outra pessoa copia esse sistema, modifica várias partes e distribui uma nova versão baseada naquele código.

Em diversas situações previstas pela GPL, essa nova versão distribuída também precisará disponibilizar o código fonte sob os termos da GPL.

Isso é muito diferente da MIT.

Com MIT, alguém pode utilizar o código dentro de um produto fechado.

Com GPL, projetos derivados distribuídos ficam sujeitos às obrigações estabelecidas pela GPL.

## 5.3 Quando usar GPL

A GPL pode ser interessante quando queremos:

1. Criar software livre.

2. Permitir que outras pessoas estudem e modifiquem o código.

3. Evitar que uma versão derivada distribuída seja simplesmente transformada em software proprietário sem respeitar as condições da GPL.

4. Incentivar que melhorias distribuídas continuem disponíveis dentro do mesmo modelo de licença.

## 5.4 Exemplo de projeto

```text
SistemaEscolarLivre
```

Nosso objetivo é criar um sistema de gestão escolar totalmente aberto para que outras escolas possam estudar, modificar e distribuir suas próprias versões.

Queremos que versões derivadas distribuídas continuem seguindo as condições da GPL.

Nesse caso, GPL pode ser uma escolha adequada.

## 5.5 Um cuidado importante

A GPL possui várias versões.

As mais conhecidas são GPL versão 2 e GPL versão 3.

Por isso, não basta escrever apenas GPL.

Precisamos observar qual versão está sendo adotada.

## 5.6 Resumindo GPL

Podemos pensar assim:

GPL permite usar e modificar, mas busca garantir que versões derivadas distribuídas continuem respeitando as mesmas liberdades da licença.

# 6. Licença BSD

## 6.1 O que é

BSD não representa apenas uma única licença.

Existe uma família de licenças BSD.

Entre as variantes mais conhecidas estão:

1. BSD 2 Clause

2. BSD 3 Clause

Elas são consideradas permissivas.

Na prática, possuem uma filosofia parecida com MIT.

Permitem reutilização ampla do código, inclusive em muitos projetos comerciais.

## 6.2 BSD 2 Clause

A BSD 2 Clause possui poucas condições.

Ela normalmente exige a preservação dos avisos de direitos autorais e das condições da licença quando o código é redistribuído.

## 6.3 BSD 3 Clause

A BSD 3 Clause acrescenta uma condição relacionada ao uso do nome dos autores ou colaboradores.

De maneira simplificada, ela evita que alguém utilize o nome do autor para promover outro produto sem autorização.

## 6.4 Quando usar BSD

BSD pode ser interessante quando queremos:

1. Uma licença permissiva.

2. Permitir uso comercial.

3. Permitir modificações.

4. Permitir integração em projetos proprietários.

5. Manter poucas exigências.

## 6.5 Exemplo de projeto

```text
BibliotecaEstruturasJava
```

Ela contém estruturas e métodos que podem ser utilizados em diferentes projetos.

Queremos permitir que universidades, empresas e outros desenvolvedores reutilizem o código.

Nesse caso, uma licença BSD pode ser uma opção.

## 6.6 Resumindo BSD

Podemos pensar assim:

BSD permite bastante liberdade para reutilizar o código, com poucas condições.

# 7. MIT ou BSD

MIT e BSD possuem filosofias muito parecidas.

As duas são permissivas.

As duas normalmente permitem:

1. Uso comercial.

2. Modificação.

3. Distribuição.

4. Inclusão do código em projetos proprietários.

Para projetos pequenos e educacionais, a MIT costuma ser bastante simples de explicar e utilizar.

BSD também é uma ótima opção, principalmente quando ela já é padrão dentro de uma comunidade ou projeto.

# 8. MIT ou Apache 2.0

As duas permitem bastante liberdade.

MIT é mais simples e curta.

Apache 2.0 possui regras mais detalhadas.

Uma diferença importante é o tratamento explícito relacionado a patentes na Apache 2.0.

Podemos pensar assim:

MIT é boa quando queremos simplicidade.

Apache 2.0 é interessante quando queremos uma licença permissiva com regras jurídicas mais detalhadas.

# 9. MIT ou GPL

Essa diferença é muito importante.

MIT permite que outra pessoa utilize o código em um projeto proprietário.

GPL possui obrigações de copyleft quando o software derivado é distribuído dentro das condições previstas pela licença.

Podemos imaginar o seguinte cenário.

Criamos uma biblioteca Java.

Com MIT:

Uma empresa pode utilizar a biblioteca dentro de um produto fechado.

Com GPL:

Dependendo da forma de uso e distribuição, a empresa poderá ter obrigações relacionadas à disponibilização do código fonte e ao licenciamento do trabalho derivado.

Essa diferença precisa ser considerada antes de escolher a licença.

# 10. Qual Licença Escolher

Não existe uma única licença perfeita para todos os projetos.

A escolha depende do objetivo.

## Situação 1

Quero publicar um pequeno projeto de aula e permitir que outras pessoas reutilizem facilmente.

Uma escolha possível:

```text
MIT
```

## Situação 2

Quero criar uma biblioteca que poderá ser utilizada por empresas e quero regras mais detalhadas relacionadas a patentes.

Uma escolha possível:

```text
Apache 2.0
```

## Situação 3

Quero criar um software livre e desejo que versões derivadas distribuídas continuem seguindo as regras da GPL.

Uma escolha possível:

```text
GPL
```

## Situação 4

Quero uma licença permissiva, simples e tradicional.

Uma escolha possível:

```text
BSD 2 Clause
```

ou:

```text
BSD 3 Clause
```

# 11. Comparação Simplificada

## MIT

Tipo:

Permissiva.

Pode usar comercialmente:

Sim.

Pode modificar:

Sim.

Pode distribuir:

Sim.

Pode utilizar em projeto proprietário:

Geralmente sim.

Principal característica:

Simplicidade.

## Apache 2.0

Tipo:

Permissiva.

Pode usar comercialmente:

Sim.

Pode modificar:

Sim.

Pode distribuir:

Sim.

Pode utilizar em projeto proprietário:

Geralmente sim.

Principal característica:

Permissões amplas com regras mais detalhadas e tratamento explícito de patentes.

## GPL

Tipo:

Copyleft.

Pode usar comercialmente:

Sim.

Pode modificar:

Sim.

Pode distribuir:

Sim.

Pode utilizar sem observar as obrigações da GPL:

Não.

Principal característica:

Proteção das liberdades do software nas versões derivadas distribuídas.

## BSD

Tipo:

Permissiva.

Pode usar comercialmente:

Sim.

Pode modificar:

Sim.

Pode distribuir:

Sim.

Pode utilizar em projeto proprietário:

Geralmente sim.

Principal característica:

Poucas restrições e ampla liberdade de reutilização.

# 12. Exemplo com Projetos Java

Vamos imaginar quatro projetos.

## Projeto 1

```text
CalculadoraJava
```

Projeto criado para ensinar programação básica.

Queremos permitir que qualquer aluno reutilize e modifique.

Licença sugerida:

```text
MIT
```

## Projeto 2

```text
FrameworkFinanceiroJava
```

Biblioteca aberta que poderá receber contribuições de várias empresas.

Queremos permissões amplas e regras mais detalhadas.

Licença sugerida:

```text
Apache 2.0
```

## Projeto 3

```text
SistemaHospitalarLivre
```

Projeto comunitário em que queremos preservar o modelo de software livre nas versões derivadas distribuídas.

Licença sugerida:

```text
GPL
```

## Projeto 4

```text
BibliotecaAlgoritmosJava
```

Biblioteca que queremos disponibilizar com poucas restrições.

Licença sugerida:

```text
BSD
```

# 13. Onde Colocar a Licença no GitHub

Normalmente criamos um arquivo chamado:

```text
LICENSE
```

na raiz do repositório.

Exemplo:

```text
MeuProjeto
│
├── src
├── docs
├── README.md
├── .gitignore
└── LICENSE
```

Dentro do arquivo `LICENSE`, colocamos o texto oficial da licença escolhida.

Não devemos resumir a licença dentro do arquivo oficial.

O resumo pode ficar no README ou na documentação.

# 14. Como Informar a Licença no README

Podemos criar uma seção como esta:

```markdown
## Licença

Este projeto utiliza a licença MIT.

Consulte o arquivo LICENSE para conhecer os termos completos.
```

Outro exemplo:

```markdown
## Licença

Este projeto está disponível sob os termos da Apache License 2.0.

Consulte o arquivo LICENSE para mais informações.
```

# 15. Erros Comuns

## Erro 1

Publicar um projeto e escrever apenas:

```text
Código livre
```

Isso não substitui uma licença.

## Erro 2

Copiar uma licença sem entender suas regras.

## Erro 3

Alterar o texto oficial de uma licença conhecida.

Ao modificar o texto, podemos deixar de utilizar exatamente aquela licença.

## Erro 4

Usar código de outro projeto sem verificar a licença original.

Antes de copiar ou incorporar código, precisamos verificar quais regras foram definidas pelo autor.

## Erro 5

Misturar códigos com licenças incompatíveis.

Em projetos maiores, é importante verificar se as licenças dos componentes utilizados são compatíveis entre si.

# 16. Regra Prática para Nossos Projetos de Aula

Para muitos projetos educacionais em Java publicados como código aberto, podemos considerar a licença MIT quando o objetivo for permitir reutilização simples.

Isso não significa que MIT seja sempre a melhor licença.

É apenas uma escolha prática para muitos projetos pequenos, acadêmicos e educacionais.

Quando o projeto envolver empresas, patentes, distribuição comercial complexa ou componentes de terceiros, devemos analisar a licença com mais cuidado.

# 17. Atividade Prática

Analise os projetos abaixo e escolha uma licença.

## Situação A

Um aluno criou um jogo simples em Java e quer permitir que qualquer pessoa estude, modifique e reutilize o código.

Qual licença você escolheria?

Explique sua decisão.

## Situação B

Uma empresa criou uma biblioteca Java que poderá ser utilizada por outras empresas e quer regras explícitas relacionadas a patentes.

Qual licença você escolheria?

Explique sua decisão.

## Situação C

Uma comunidade criou um sistema aberto e deseja que versões derivadas distribuídas continuem seguindo as mesmas liberdades.

Qual licença você escolheria?

Explique sua decisão.

## Situação D

Um professor criou uma coleção de algoritmos em Java e deseja permitir ampla reutilização com poucas restrições.

Qual licença você escolheria?

Explique sua decisão.

# 18. Desafio

Crie um repositório fictício chamado:

```text
ProjetoJavaLivre
```

Adicione:

```text
README.md
LICENSE
src
docs
```

Escolha uma das quatro licenças estudadas.

Depois, escreva no README:

1. Qual licença foi escolhida.

2. Por que ela foi escolhida.

3. O que outras pessoas podem fazer com o projeto.

4. Quais condições precisam ser respeitadas.

# 19. Perguntas para Revisão

1. Para que serve uma licença de software?

2. MIT é uma licença permissiva ou copyleft?

3. A licença MIT permite uso comercial?

4. Qual licença estudada possui tratamento explícito relacionado a patentes?

5. O que significa copyleft?

6. Qual é a principal característica da GPL?

7. BSD representa apenas uma única licença?

8. Qual é a diferença básica entre BSD 2 Clause e BSD 3 Clause?

9. Onde normalmente colocamos a licença dentro do repositório?

10. Podemos modificar livremente o texto oficial de uma licença conhecida?

# 20. Conclusão

Escolher uma licença faz parte da publicação responsável de um projeto.

A licença informa quais direitos nós estamos concedendo e quais condições outras pessoas precisam respeitar.

Podemos guardar uma ideia simples:

MIT:

Permissiva, simples e muito utilizada.

Apache 2.0:

Permissiva, detalhada e com tratamento explícito relacionado a patentes.

GPL:

Software livre com copyleft.

BSD:

Permissiva, tradicional e com poucas restrições.

Antes de escolher, devemos pensar no objetivo do projeto e no que desejamos permitir que outras pessoas façam com nosso código.

Em projetos profissionais ou situações jurídicas mais complexas, a escolha da licença pode exigir análise especializada.
