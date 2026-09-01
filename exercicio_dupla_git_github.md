# Exercício em Dupla: Git e GitHub

## Tema

Trabalho colaborativo com repositório remoto, clone, branches, commits, push, pull request e revisão de código.

## Objetivo

Neste exercício, nós vamos praticar um fluxo de trabalho colaborativo utilizando Git e GitHub.

Ao final da atividade, a dupla deverá ter praticado:

1. Criação de repositório no GitHub
2. Adição de colaborador
3. Clone de repositório
4. Criação da branch develop
5. Criação da branch feature/cadastro
6. Criação e edição de arquivos
7. Commit
8. Push
9. Pull
10. Pull request
11. Revisão e merge
12. Sincronização do repositório local
13. Inversão de papéis entre os integrantes da dupla

## Organização da dupla

A atividade será realizada em duas etapas.

Na primeira etapa:

Aluno A será o proprietário do repositório.

Aluno B será o colaborador.

Na segunda etapa:

Aluno B será o proprietário de um novo repositório.

Aluno A será o colaborador.

## Atenção

Para evitar conflito entre arquivos com o mesmo nome, cada aluno deverá criar uma pasta com seu primeiro nome.

Exemplo:

```text
feature/cadastro

eder/
cliente.txt

joao/
cliente.txt
```

Cada arquivo cliente.txt deverá conter os dados do respectivo aluno.

Exemplo:

```text
Nome completo: Éder Silva
Endereço: Rua Exemplo, 100
Telefone: 51999999999
```

# Etapa 1

## Parte 1: criação do repositório

O Aluno A deverá acessar o GitHub e criar um novo repositório.

Nome sugerido:

```text
atividade_dupla_git
```

O repositório poderá ser público ou privado.

Depois da criação, o Aluno A deverá adicionar o Aluno B como colaborador do projeto.

No GitHub, acesse:

```text
Settings
Collaborators
Add people
```

O Aluno B deverá aceitar o convite.

## Parte 2: clone do repositório

Os dois alunos deverão ter uma cópia local do projeto.

O Aluno B deverá clonar o repositório criado pelo Aluno A.

Exemplo:

```bash
git clone URL_DO_REPOSITORIO
```

O Aluno A também poderá clonar o próprio repositório caso ainda não tenha uma cópia local.

Depois, ambos deverão entrar na pasta do projeto.

```bash
cd atividade_dupla_git
```

## Parte 3: criação da branch develop

O Aluno A deverá criar a branch develop.

```bash
git branch develop
git switch develop
```

Depois deverá enviar a branch para o GitHub.

```bash
git push origin develop
```

O Aluno B deverá atualizar as informações do repositório remoto.

```bash
git fetch origin
```

Depois deverá acessar a branch develop.

```bash
git switch develop
```

Caso a branch ainda não exista localmente, poderá ser criada a partir da branch remota.

```bash
git branch develop origin/develop
git switch develop
```

## Parte 4: trabalho do Aluno A

O Aluno A deverá estar na branch develop.

Confirme com:

```bash
git branch
```

Depois deverá criar a branch feature/cadastro.

```bash
git branch feature/cadastro
git switch feature/cadastro
```

Agora deverá criar uma pasta com seu primeiro nome.

Exemplo:

```text
eder
```

Dentro dessa pasta, deverá criar o arquivo:

```text
cliente.txt
```

O arquivo deverá conter:

```text
Nome completo:
Endereço:
Telefone:
```

Depois deverá adicionar o arquivo ao Git.

```bash
git add .
```

Criar o commit.

```bash
git commit -m "Cadastro do aluno A"
```

Enviar a branch para o GitHub.

```bash
git push origin feature/cadastro
```

## Parte 5: primeiro pull request

O Aluno A deverá acessar o GitHub e criar um pull request.

Origem:

```text
feature/cadastro
```

Destino:

```text
develop
```

Título sugerido:

```text
Cadastro do aluno A
```

O Aluno B deverá revisar o pull request.

Depois da revisão, o pull request deverá ser aprovado e integrado à branch develop.

## Parte 6: atualização dos dois computadores

Depois do merge, os dois alunos deverão atualizar suas cópias locais.

Primeiro, acessar develop.

```bash
git switch develop
```

Depois atualizar.

```bash
git pull origin develop
```

## Parte 7: trabalho do Aluno B

Depois que o primeiro pull request estiver concluído, a branch feature/cadastro poderá ser reutilizada.

Caso ela ainda exista localmente no computador do Aluno B, deverá ser removida antes da recriação.

```bash
git branch
```

O Aluno B deverá estar na branch develop.

Depois deverá criar novamente a branch feature/cadastro.

```bash
git branch feature/cadastro
git switch feature/cadastro
```

Agora o Aluno B deverá criar uma pasta com seu primeiro nome.

Exemplo:

```text
joao
```

Dentro da pasta deverá criar:

```text
cliente.txt
```

O arquivo deverá conter:

```text
Nome completo:
Endereço:
Telefone:
```

Depois deverá adicionar os arquivos.

```bash
git add .
```

Criar o commit.

```bash
git commit -m "Cadastro do aluno B"
```

Enviar para o GitHub.

```bash
git push origin feature/cadastro
```

## Parte 8: segundo pull request

O Aluno B deverá criar um novo pull request.

Origem:

```text
feature/cadastro
```

Destino:

```text
develop
```

Título sugerido:

```text
Cadastro do aluno B
```

O Aluno A deverá revisar o pull request.

Depois da revisão, o pull request deverá ser aprovado e integrado à branch develop.

## Parte 9: conferência final

Os dois alunos deverão acessar a branch develop.

```bash
git switch develop
```

Depois deverão atualizar o projeto.

```bash
git pull origin develop
```

Ao final, o projeto deverá possuir uma estrutura semelhante a esta:

```text
atividade_dupla_git

eder/
cliente.txt

joao/
cliente.txt
```

Cada arquivo deverá conter os dados do respectivo aluno.

# Etapa 2

Agora os papéis serão invertidos.

O Aluno B deverá criar um novo repositório no GitHub.

Nome sugerido:

```text
atividade_dupla_git_02
```

O Aluno B será o proprietário do repositório.

O Aluno A será adicionado como colaborador.

Depois, a dupla deverá repetir todo o processo realizado na Etapa 1.

A ordem deverá ser:

1. Aluno B cria o repositório
2. Aluno B adiciona o Aluno A como colaborador
3. Aluno A aceita o convite
4. Os dois alunos clonam ou atualizam o projeto local
5. Criam e utilizam a branch develop
6. Aluno B cria feature/cadastro
7. Aluno B cria sua pasta e seu cliente.txt
8. Aluno B realiza commit e push
9. Aluno B cria o pull request para develop
10. Aluno A revisa e aprova
11. Os dois atualizam develop
12. Aluno A cria novamente feature/cadastro
13. Aluno A cria sua pasta e seu cliente.txt
14. Aluno A realiza commit e push
15. Aluno A cria o pull request
16. Aluno B revisa e aprova
17. Os dois atualizam novamente a branch develop

# Regras da atividade

Cada integrante deverá realizar pelo menos um commit em cada repositório.

Cada integrante deverá realizar pelo menos um push em cada repositório.

Cada integrante deverá criar pelo menos um pull request.

Cada integrante deverá revisar pelo menos um pull request do colega.

Os arquivos deverão ser criados dentro da branch feature/cadastro.

O merge dos pull requests deverá ser realizado na branch develop.

Não deverá ser feito trabalho diretamente na branch principal.

# Evidências para entrega

A dupla deverá apresentar:

1. Link do primeiro repositório
2. Link do segundo repositório
3. Print das branches
4. Print dos commits
5. Print dos pull requests
6. Print dos merges realizados
7. Print da estrutura final dos arquivos
8. Nome dos dois integrantes da dupla

# Resultado esperado

Ao final da atividade, cada aluno deverá compreender o fluxo básico de colaboração utilizado em projetos reais com Git e GitHub.

O objetivo não é apenas executar comandos, mas entender como duas pessoas podem trabalhar no mesmo projeto, enviar alterações, revisar o trabalho do colega e integrar essas alterações de forma organizada.
