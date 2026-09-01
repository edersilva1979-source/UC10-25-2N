# Aula: Documentação Profissional em Projetos Git e GitHub

## 1. Introdução

Quando começamos a trabalhar com Git e GitHub, é comum imaginar que um projeto é formado apenas pelo código fonte.

Na prática, um projeto bem organizado também precisa de documentação.

A documentação ajuda outras pessoas a entenderem o projeto, instalarem o sistema, colaborarem com o código, identificarem alterações entre versões e saberem como reportar problemas.

Nesta aula, nós vamos conhecer os principais arquivos utilizados em projetos Git e GitHub e entender a função de cada um.

Também vamos aprender como organizar um modelo de repositório para projetos.

## 2. Objetivos da Aula

Ao final desta aula, nós seremos capazes de:

1. Entender por que a documentação é importante em um projeto.
2. Criar um `README.md`.
3. Criar e configurar um `.gitignore`.
4. Entender a função do arquivo `LICENSE`.
5. Criar um `CHANGELOG.md`.
6. Criar um `CONTRIBUTING.md`.
7. Criar modelos de Issue.
8. Criar um modelo de Pull Request.
9. Organizar uma pasta `docs`.
10. Montar uma estrutura padrão de repositório para projetos Java.

# 3. Um Projeto Não é Apenas Código

Quando alguém acessa um repositório no GitHub, normalmente essa pessoa quer responder rapidamente algumas perguntas.

Qual é o objetivo do projeto?

Como instalar?

Como executar?

Quais tecnologias foram utilizadas?

Como colaborar?

Onde reportar um erro?

Qual é a licença?

Quais alterações foram realizadas nas últimas versões?

Essas respostas não devem ficar escondidas dentro do código.

Nós utilizamos arquivos de documentação justamente para organizar essas informações.

# 4. Estrutura Recomendada

Uma estrutura organizada pode ficar assim:

```text
MeuProjeto
│
├── README.md
├── .gitignore
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
│
├── .github
│   ├── PULL_REQUEST_TEMPLATE.md
│   │
│   └── ISSUE_TEMPLATE
│       ├── bug_report.md
│       └── feature_request.md
│
├── docs
│   ├── 01_instalacao.md
│   ├── 02_estrutura_projeto.md
│   ├── 03_banco_de_dados.md
│   ├── 04_padrao_de_commits.md
│   └── 05_guia_documentacao.md
│
├── sql
│
└── src
```

Cada arquivo possui uma responsabilidade.

Nós não precisamos utilizar todos eles em qualquer projeto.

Porém, quanto maior e mais colaborativo for o projeto, mais importante se torna uma boa documentação.

# 5. README.md

## 5.1 O que é

O `README.md` é normalmente a primeira documentação visualizada quando alguém acessa o repositório.

Podemos pensar nele como a página inicial do projeto.

Ele deve apresentar as informações mais importantes de maneira direta.

## 5.2 O que colocar no README

Um bom README pode conter:

1. Nome do projeto.
2. Descrição.
3. Objetivos.
4. Tecnologias utilizadas.
5. Funcionalidades.
6. Requisitos.
7. Instruções de instalação.
8. Como executar.
9. Estrutura do projeto.
10. Documentação complementar.
11. Autor.
12. Licença.

## 5.3 Exemplo

```markdown
# Sistema de Cadastro de Clientes

Sistema desktop desenvolvido em Java para gerenciamento de clientes.

## Objetivo

Este projeto foi desenvolvido para praticarmos Java, Swing, JDBC, PostgreSQL, Git e GitHub.

## Tecnologias

JavaScript

Typescript

PostgreSQL

JDBC

Git

GitHub

## Funcionalidades

Cadastro de clientes

Consulta de clientes

Alteração de dados

Exclusão de registros

## Requisitos

Java JDK

PostgreSQL

VsCode

## Executando o Projeto

Clone o repositório.

```bash
git clone URL_DO_REPOSITORIO
```

Abra o projeto na IDE.

Configure o banco de dados.

Execute a classe principal.

## Autor

Nome do aluno

## Licença

Este projeto utiliza a licença MIT.
``

## 5.4 Dica

O README deve apresentar o projeto.

Quando uma explicação começa a ficar muito grande, nós podemos criar um documento separado dentro da pasta `docs`.

# 6. .gitignore

## 6.1 O que é

O `.gitignore` informa ao Git quais arquivos ou pastas não devem ser incluídos no controle de versão.

Durante o desenvolvimento, várias ferramentas geram arquivos automaticamente.

Esses arquivos normalmente não precisam ser enviados ao GitHub.

## 6.2 Exemplo para Java

``gitignore
# Arquivos compilados
*.class

# Diretórios de compilação
build/
dist/
out/
target/

# Pacotes gerados
*.jar
*.war
*.ear

# Logs
*.log

# NetBeans
nbproject/private/
nbbuild/
nbdist/

# IntelliJ
.idea/
*.iml

# VS Code
.vscode/

# Arquivos de ambiente
.env
.env.local

# Sistema operacional
.DS_Store
Thumbs.db
Desktop.ini
``

## 6.3 Informações sensíveis

Nunca devemos publicar:

1. Senhas.
2. Tokens.
3. Chaves de API.
4. Credenciais do banco.
5. Chaves privadas.
6. Arquivos contendo informações confidenciais.

Se utilizarmos um arquivo local chamado `.env`, por exemplo, ele deve estar no `.gitignore`.

```gitignore
.env
```

# 7. LICENSE

## 7.1 O que é

O arquivo `LICENSE` informa juridicamente como outras pessoas podem utilizar o projeto.

Sem uma licença definida, não devemos assumir que qualquer pessoa pode copiar, modificar ou redistribuir o código livremente.

## 7.2 Licenças conhecidas

Algumas licenças comuns são:

1. MIT
2. Apache 2.0
3. GPL
4. BSD

Para muitos projetos educacionais e projetos de código aberto simples, a licença MIT é bastante utilizada.

## 7.3 Importante

Nós não devemos inventar um texto de licença sem conhecer suas consequências jurídicas.

O recomendado é escolher uma licença conhecida e utilizar seu texto oficial.

## 7.4 Referência no README

``markdown
## Licença

Este projeto utiliza a licença MIT.

Consulte o arquivo LICENSE para conhecer os termos completos.
``

# 8. CHANGELOG.md

## 8.1 O que é

O `CHANGELOG.md` registra as principais alterações realizadas entre as versões do projeto.

Ele não substitui os commits.

O histórico de commits mostra cada alteração feita no código.

O CHANGELOG apresenta as alterações que são importantes para quem utiliza o projeto.

## 8.2 Exemplo

``markdown
# Histórico de Alterações

## Versão 1.2.0

Data: 17 de agosto de 2026

### Adicionado

Cadastro de fornecedores.

Consulta de fornecedores.

Controle de permissões.

### Alterado

Tela principal reorganizada.

### Corrigido

Erro na exclusão de clientes.

## Versão 1.1.0

### Adicionado

Cadastro de clientes.

Consulta de clientes.

## Versão 1.0.0

Primeira versão do sistema.
``

# 9. Versionamento Semântico

Uma forma conhecida de organizar versões utiliza três números.

```text
MAJOR.MINOR.PATCH
```

Exemplo:

``text
1.4.2
``

Podemos interpretar assim:

`1` representa uma versão principal.

`4` representa novas funcionalidades compatíveis.

`2` representa correções.

Exemplo:

```text
1.0.0
```

Primeira versão estável.

```text
1.1.0
```

Nova funcionalidade.

```text
1.1.1
```

Correção de problema.

```text
2.0.0
```

Mudança importante que pode exigir adaptações.

# 10. CONTRIBUTING.md

## 10.1 O que é

O `CONTRIBUTING.md` explica como outras pessoas podem colaborar com o projeto.

Quando várias pessoas trabalham no mesmo repositório, é importante que todos sigam um processo parecido.

## 10.2 O que podemos definir

1. Como clonar o projeto.
2. Como criar uma branch.
3. Como fazer commits.
4. Como testar.
5. Como enviar alterações.
6. Como criar Pull Requests.
7. Como atualizar a documentação.

## 10.3 Exemplo

``markdown
# Como Contribuir

Obrigado pelo interesse em contribuir com este projeto.

## Antes de Começar

Leia o README.

Consulte a documentação.

Verifique as Issues existentes.

## Criando uma Branch

``bash
git switch main
git pull
git switch cadastro_cliente
``

## Commits

Utilize mensagens objetivas.

Exemplos:

```text
Adiciona cadastro de clientes

Corrige validação do login

Atualiza documentação do banco
```

## Enviando a Branch

```bash
git push origin cadastro_cliente
```

Depois, abra um Pull Request no GitHub.
``

# 11. Mensagens de Commit

Uma boa mensagem de commit deve explicar o que foi alterado.

## Bons exemplos

```text
Adiciona cadastro de clientes

Cria tela de login

Corrige consulta de produtos

Atualiza documentação de instalação

Remove método não utilizado
```

## Exemplos ruins

```text
mudança

teste

novo

alterado

agora funciona
```

Uma mensagem de commit deve fazer sentido mesmo quando nós a lemos meses depois.

# 12. Pasta .github

O GitHub reconhece algumas configurações especiais quando elas estão dentro da pasta `.github`.

Exemplo:

```text
.github
│
├── PULL_REQUEST_TEMPLATE.md
│
└── ISSUE_TEMPLATE
    ├── bug_report.md
    └── feature_request.md
```

Essa pasta normalmente contém arquivos relacionados ao processo de colaboração.

# 13. Template de Pull Request

## 13.1 O que é um Pull Request

Um Pull Request é uma solicitação para integrar alterações de uma branch ao projeto.

Ele permite que outras pessoas revisem o código antes que a alteração seja incorporada.

## 13.2 Template

Podemos criar:

```text
.github/PULL_REQUEST_TEMPLATE.md
```

Exemplo:

``markdown
# Pull Request

## Descrição

Explique o que foi desenvolvido.

## Motivo da Alteração

Explique por que a alteração foi necessária.

## Tipo de Alteração

Nova funcionalidade

Correção

Refatoração

Documentação

Banco de dados

Interface

## Testes Realizados

Descreva como a alteração foi testada.

## Banco de Dados

Informe se houve alteração em tabelas, campos ou scripts SQL.

## Observações

Inclua informações importantes para a revisão.
``

# 14. Issues

## 14.1 O que são Issues

Issues podem ser utilizadas para registrar:

1. Erros.
2. Sugestões.
3. Melhorias.
4. Tarefas.
5. Novas funcionalidades.
6. Problemas encontrados pelos usuários.

Em vez de criar uma Issue sem organização, podemos utilizar templates.

# 15. Template para Relatório de Problema

Arquivo:

```text
.github/ISSUE_TEMPLATE/bug_report.md
```

Exemplo:

``markdown
# Relatório de Problema

## Descrição

Explique o problema encontrado.

## Como Reproduzir

1. Abra o sistema.
2. Acesse determinada tela.
3. Execute determinada operação.
4. Observe o problema.

## Resultado Esperado

Explique o que deveria acontecer.

## Resultado Obtido

Explique o que aconteceu.

## Ambiente

Sistema operacional:

Versão do Java:

IDE:

Banco de dados:

Versão do projeto:

## Evidências

Adicione mensagens de erro, imagens ou logs.
``

# 16. Template para Nova Funcionalidade

Arquivo:

```text
.github/ISSUE_TEMPLATE/feature_request.md
```

Exemplo:

``markdown
# Solicitação de Funcionalidade

## Necessidade

Explique qual problema ou necessidade motivou a solicitação.

## Funcionalidade Desejada

Descreva a nova funcionalidade.

## Exemplo de Uso

Explique uma situação prática.

## Resultado Esperado

Explique como o sistema deveria funcionar.

## Possíveis Impactos

Banco de dados

Interface

Regras de negócio

Documentação

Permissões

## Observações

Inclua outras informações importantes.
``

# 17. Pasta docs

## 17.1 Por que utilizar

Conforme o projeto cresce, o README pode ficar muito extenso.

Nesse momento, nós podemos separar a documentação detalhada em uma pasta chamada `docs`.

Exemplo:

```text
docs
│
├── 01_instalacao.md
├── 02_estrutura_projeto.md
├── 03_banco_de_dados.md
├── 04_padrao_de_commits.md
└── 05_guia_documentacao.md
```

# 18. Documento de Instalação

Arquivo:

```text
docs/01_instalacao.md
```

Ele deve explicar como preparar o ambiente do zero.

Exemplo:

``markdown
# Instalação

## Requisitos

Java JDK

Git

NetBeans

PostgreSQL

## Verificando o Java

```bash
java -version
```

## Clonando o Projeto

```bash
git clone URL_DO_REPOSITORIO
```

## Executando

Abra o projeto na IDE.

Configure o banco.

Execute a classe principal.
``

# 19. Documento da Estrutura

Arquivo:

```text
docs/02_estrutura_projeto.md
```

Exemplo:

``markdown
# Estrutura do Projeto

## Model

Contém as classes que representam as entidades.

Exemplos:

Cliente

Produto

Fornecedor

Usuario

## View

Contém as telas.

Exemplos:

FrmLogin

FrmPrincipal

FrmCliente

## Controller

Coordena a comunicação entre partes do sistema.

## DAO

Contém as classes responsáveis pelo acesso aos dados.

## Util

Contém classes auxiliares.
``

# 20. Documento do Banco de Dados

Arquivo:

```text
docs/03_banco_de_dados.md
```

Podemos documentar:

1. Banco utilizado.
2. Nome do banco.
3. Principais tabelas.
4. Relacionamentos.
5. Scripts SQL.
6. Configuração da conexão.
7. Alterações realizadas.

Exemplo de estrutura:

```text
sql
│
├── criar_banco.sql
├── criar_tabelas.sql
└── dados_iniciais.sql
```

# 21. Documento do Padrão de Commits

Arquivo:

```text
docs/04_padrao_de_commits.md
```

Podemos registrar o padrão escolhido pela equipe.

Exemplo:

``text
Adiciona cadastro de clientes

Corrige validação do CPF

Atualiza conexão com PostgreSQL

Documenta instalação do projeto
``

Isso ajuda todos os integrantes a manterem um histórico consistente.

# 22. Guia da Documentação

Arquivo:

```text
docs/05_guia_documentacao.md
```

Esse arquivo pode ser utilizado para explicar a função de cada documento do repositório.

É especialmente útil em projetos educacionais.

# 23. Estrutura Padrão para Nossos Projetos Java

Para nossos projetos Java, podemos utilizar a seguinte estrutura:

```text
SistemaJava
│
├── README.md
├── .gitignore
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
│
├── .github
│   ├── PULL_REQUEST_TEMPLATE.md
│   │
│   └── ISSUE_TEMPLATE
│       ├── bug_report.md
│       └── feature_request.md
│
├── docs
│   ├── 01_instalacao.md
│   ├── 02_estrutura_projeto.md
│   ├── 03_banco_de_dados.md
│   ├── 04_padrao_de_commits.md
│   └── 05_guia_documentacao.md
│
├── sql
│
└── src
```

# 24. O Que Considero Essencial

## Projeto pequeno

```text
README.md
.gitignore
LICENSE
```

## Projeto acadêmico

```text
README.md
.gitignore
LICENSE
CHANGELOG.md
docs
```

## Projeto colaborativo

```text
README.md
.gitignore
LICENSE
CHANGELOG.md
CONTRIBUTING.md
.github
docs
```

# 25. Atividade Prática

Agora nós vamos aplicar o conteúdo.

## Objetivo

Criar a documentação inicial de um projeto Java.

## Etapa 1

Crie um novo repositório no GitHub.

## Etapa 2

Adicione:

```text
README.md
.gitignore
LICENSE
CHANGELOG.md
CONTRIBUTING.md
```

## Etapa 3

Crie:

```text
.github
```

Dentro dela:

```text
PULL_REQUEST_TEMPLATE.md
```

Depois:

```text
ISSUE_TEMPLATE
```

Dentro de `ISSUE_TEMPLATE`:

```text
bug_report.md
feature_request.md
```

## Etapa 4

Crie a pasta:

```text
docs
```

Adicione:

```text
01_instalacao.md
02_estrutura_projeto.md
03_banco_de_dados.md
04_padrao_de_commits.md
05_guia_documentacao.md
```

## Etapa 5

Personalize o README com:

1. Nome do projeto.
2. Objetivo.
3. Tecnologias.
4. Funcionalidades.
5. Como executar.
6. Autor.
7. Licença.

## Etapa 6

Realize um commit.

Exemplo:

```text
Cria documentação inicial do projeto
```

Depois envie as alterações para o GitHub.

# 26. Desafio

Crie um projeto TypeScript fictício chamado:

```text
SistemaLivraria
```

O sistema deverá possuir:

1. Cadastro de livros.
2. Cadastro de clientes.
3. Registro de vendas.
4. Consulta de estoque.

Crie a estrutura completa de documentação.

Personalize:

1. README.
2. CHANGELOG.
3. CONTRIBUTING.
4. Relatório de problema.
5. Solicitação de funcionalidade.
6. Documentação de instalação.
7. Documentação do banco de dados.

Depois publique o projeto no GitHub.

# 27. Perguntas para Revisão

1. Para que serve o README?
2. Qual é a função do `.gitignore`?
3. Por que não devemos publicar senhas no GitHub?
4. Para que serve o arquivo LICENSE?
5. Qual é a diferença entre commits e CHANGELOG?
6. Para que serve o CONTRIBUTING?
7. O que é uma Issue?
8. O que é um Pull Request?
9. Por que utilizar templates?
10. Quando devemos criar uma pasta `docs`?

# 28. Conclusão

Um projeto profissional não termina quando o código compila.

Nós também precisamos pensar em documentação, histórico, colaboração, segurança e manutenção.

Um bom repositório permite que outra pessoa compreenda o projeto sem precisar perguntar ao desenvolvedor como tudo funciona.

Por isso, a documentação faz parte do próprio desenvolvimento.

A partir de agora, sempre que criarmos um projeto Java para o GitHub, podemos utilizar esta estrutura como ponto de partida.

Ela nos ajuda a manter os projetos organizados e também cria bons hábitos para trabalhos acadêmicos, projetos pessoais e ambientes profissionais.
