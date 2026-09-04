# Exercício Prático Completo de Git e GitHub

## Objetivo

Nesta atividade nós vamos praticar um fluxo completo de trabalho com Git e GitHub, desde a criação do repositório até a publicação de versões com Tags e Releases.

Ao final do exercício nós teremos trabalhado com:

1. Repositório remoto no GitHub
2. Repositório local
3. Commits
4. Branches
5. Pull Request
6. Merge
7. Tags
8. Releases
9. Push
10. Pull
11. Organização do histórico do projeto

## Nome do projeto

Crie um repositório chamado:

```text
ProjetoGitFinal
```

# Parte 1. Criar o repositório remoto

Acesse sua conta no GitHub.

Crie um novo repositório com o nome:

```text
ProjetoGitFinal
```

Crie o repositório vazio.

Não adicione README, .gitignore ou outros arquivos automaticamente pelo GitHub.

Copie o endereço do repositório criado.

# Parte 2. Criar o repositório local

No computador, crie uma pasta chamada:

```text
ProjetoGitFinal
```

Abra o terminal dentro dessa pasta.

Inicie o Git:

```bash
git init
```

Defina a branch principal como main:

```bash
git branch -M main
```

# Parte 3. Criar os arquivos da main

Na branch main deverão ser criados os seguintes arquivos:

```text
Index.html
.gitignore
README.md
```

## Index.html

Crie uma página HTML simples.

Exemplo:

```html
<!DOCTYPE html>
<html>
<head>
    <title>Projeto Git Final</title>
</head>
<body>
    <h1>Projeto Git e GitHub</h1>
    <p>Atividade prática final.</p>
</body>
</html>
```

## .gitignore

Adicione pelo menos três exemplos de arquivos ou pastas que não deverão ser enviados ao GitHub.

Exemplo:

```text
temp/
*.log
config.local
```

## README.md

Crie uma apresentação simples do projeto.

Exemplo:

```text
# Projeto Git Final

Projeto desenvolvido como atividade prática de Git e GitHub.

## Conteúdos praticados

Git

GitHub

Branches

Commits

Pull Request

Merge

Tags

Releases
```

# Parte 4. Criar os primeiros commits

Os arquivos deverão ser adicionados em commits separados.

Primeiro commit:

```bash
git add Index.html
git commit -m "Criação da página inicial"
```

Segundo commit:

```bash
git add .gitignore
git commit -m "Criação do arquivo gitignore"
```

Terceiro commit:

```bash
git add README.md
git commit -m "Criação da documentação inicial"
```

Confira o histórico:

```bash
git log
```

# Parte 5. Conectar o repositório local ao GitHub

Adicione o repositório remoto:

```bash
git remote add origin URL_DO_REPOSITORIO
```

Confira a conexão:

```bash
git remote v
```

Envie a branch main:

```bash
git push -u origin main
```

Acesse o GitHub e confirme se os arquivos foram publicados.

# Parte 6. Criar a branch Develop

A partir da main, crie a branch:

```text
Develop
```

Comando:

```bash
git switch -c Develop
```

Envie para o GitHub:

```bash
git push -u origin Develop
```

# Parte 7. Criar a branch feature/Cadastro

A branch feature/Cadastro deverá ser criada a partir da Develop.

Acesse a Develop:

```bash
git switch Develop
```

Crie a nova branch:

```bash
git switch -c feature/Cadastro
```

Dentro dessa branch crie o arquivo:

```text
cadastro.txt
```

Conteúdo sugerido:

```text
Cadastro de Cliente

Nome:
Endereço:
Telefone:
Cidade:
Email:
```

Adicione o arquivo:

```bash
git add cadastro.txt
```

Crie o commit:

```bash
git commit -m "Criação do cadastro de cliente"
```

Envie a branch:

```bash
git push -u origin feature/Cadastro
```

# Parte 8. Criar o Pull Request da feature

No GitHub, crie um Pull Request com:

```text
Origem: feature/Cadastro
Destino: Develop
```

Título sugerido:

```text
Adicionar cadastro de cliente
```

Não faça o Merge pelo GitHub.

O Merge deverá ser realizado localmente.

# Parte 9. Fazer o Merge da feature localmente

Volte para Develop:

```bash
git switch Develop
```

Atualize:

```bash
git pull origin Develop
```

Faça o Merge:

```bash
git merge feature/Cadastro
```

Envie a Develop atualizada:

```bash
git push origin Develop
```

Confira no GitHub se o Pull Request aparece como integrado.

# Parte 10. Criar a branch fix/Correcao

A branch fix/Correcao deverá ser criada a partir da Develop já atualizada.

Acesse:

```bash
git switch Develop
```

Crie:

```bash
git switch -c fix/Correcao
```

Dentro dessa branch crie:

```text
correcao.txt
```

Conteúdo sugerido:

```text
Registro de Correção

Correção realizada no projeto.

Arquivo criado para representar uma manutenção no sistema.
```

Adicione:

```bash
git add correcao.txt
```

Crie o commit:

```bash
git commit -m "Criação do registro de correção"
```

Envie para o GitHub:

```bash
git push -u origin fix/Correcao
```

# Parte 11. Criar o Pull Request da correção

No GitHub, crie outro Pull Request.

Utilize:

```text
Origem: fix/Correcao
Destino: Develop
```

Título sugerido:

```text
Adicionar registro de correção
```

Não faça o Merge pelo GitHub.

# Parte 12. Fazer o Merge da correção localmente

Volte para Develop:

```bash
git switch Develop
```

Faça o Merge:

```bash
git merge fix/Correcao
```

Envie a Develop atualizada:

```bash
git push origin Develop
```

Agora a Develop deverá possuir:

```text
Index.html
.gitignore
README.md
cadastro.txt
correcao.txt
```

# Parte 13. Criar o Pull Request da Develop para a main

No GitHub crie outro Pull Request.

Origem:

```text
Develop
```

Destino:

```text
main
```

Título sugerido:

```text
Publicar primeira versão do projeto
```

Não faça o Merge pelo GitHub.

# Parte 14. Fazer o Merge da Develop na main localmente

Acesse a main:

```bash
git switch main
```

Atualize:

```bash
git pull origin main
```

Faça o Merge:

```bash
git merge Develop
```

Envie a main atualizada:

```bash
git push origin main
```

Confira o resultado no GitHub.

# Parte 15. Criar a primeira Tag

Na main, crie:

```text
v1.0.0
```

Comando:

```bash
git tag v1.0.0
```

Envie a Tag para o GitHub:

```bash
git push origin v1.0.0
```

# Parte 16. Criar a primeira Release

No GitHub acesse a área de Releases.

Crie uma nova Release usando:

```text
v1.0.0
```

Título:

```text
Versão 1.0.0
```

Descrição sugerida:

```text
Primeira versão do projeto.

Conteúdo:

Página inicial

Arquivo gitignore

Documentação README

Cadastro de cliente

Registro de correção
```

Publique a Release.

# Parte 17. Fazer uma nova alteração

Na main, altere o arquivo README.md.

Adicione:

```text
## Versão atual

Projeto atualizado após a primeira publicação.
```

Adicione ao Git:

```bash
git add README.md
```

Faça o commit:

```bash
git commit -m "Atualização da documentação"
```

Envie:

```bash
git push origin main
```

# Parte 18. Criar a segunda Tag

Crie:

```text
v1.1.0
```

Comando:

```bash
git tag v1.1.0
```

Envie para o GitHub:

```bash
git push origin v1.1.0
```

# Parte 19. Criar a segunda Release

No GitHub crie outra Release.

Tag:

```text
v1.1.0
```

Título:

```text
Versão 1.1.0
```

Descrição sugerida:

```text
Segunda versão do projeto.

Atualização da documentação e consolidação dos arquivos desenvolvidos durante a atividade.
```

Publique a Release.

# Estrutura final esperada

Na branch main deverão existir:

```text
ProjetoGitFinal

Index.html
.gitignore
README.md
cadastro.txt
correcao.txt
```

# Branches obrigatórias

O repositório deverá possuir pelo menos:

```text
main
Develop
feature/Cadastro
fix/Correcao
```

# Tags obrigatórias

Deverão existir pelo menos:

```text
v1.0.0
v1.1.0
```

# Releases obrigatórias

Deverão existir duas Releases:

```text
Versão 1.0.0
Versão 1.1.0
```

# Commits

O projeto deverá possuir vários commits.

Não será aceito colocar todos os arquivos em apenas um commit.

Exemplos de commits:

```text
Criação da página inicial

Criação do arquivo gitignore

Criação da documentação inicial

Criação do cadastro de cliente

Criação do registro de correção

Atualização da documentação
```

# Pull Requests obrigatórios

Deverão existir pelo menos três Pull Requests.

Primeiro:

```text
feature/Cadastro para Develop
```

Segundo:

```text
fix/Correcao para Develop
```

Terceiro:

```text
Develop para main
```

# Regras da atividade

1. Todos os arquivos deverão estar publicados no GitHub.

2. Index.html, .gitignore e README.md deverão ser criados inicialmente na main.

3. cadastro.txt deverá ser criado na feature/Cadastro.

4. correcao.txt deverá ser criado na fix/Correcao.

5. feature/Cadastro deverá partir da Develop.

6. fix/Correcao deverá partir da Develop.

7. Os Pull Requests deverão ser criados no GitHub.

8. Os Merges deverão ser realizados no repositório local.

9. Após cada Merge, a branch atualizada deverá ser enviada ao GitHub.

10. O projeto deverá possuir pelo menos duas Tags.

11. O projeto deverá possuir pelo menos duas Releases.

12. O histórico de commits deverá estar organizado.

# Apresentação do trabalho

A apresentação será realizada na próxima aula.

A apresentação deverá ser feita diretamente pelo GitHub.

Não será necessário criar PowerPoint.

Durante a apresentação, cada aluno deverá mostrar:

1. Repositório principal
2. Arquivos da main
3. Branch Develop
4. Branch feature/Cadastro
5. Branch fix/Correcao
6. Histórico de commits
7. Pull Requests
8. Merges realizados
9. Tags
10. Releases
11. cadastro.txt
12. correcao.txt
13. README.md

# Critérios de avaliação

Serão avaliados:

1. Criação correta do repositório remoto
2. Criação correta do repositório local
3. Organização dos commits
4. Criação correta das branches
5. Arquivos criados nas branches corretas
6. Push das branches
7. Pull Requests
8. Merges realizados localmente
9. Publicação final na main
10. Tags
11. Releases
12. Organização do repositório
13. Domínio do aluno durante a apresentação

# Checklist final

Antes da apresentação confira:

```text
Repositório remoto criado

Repositório local criado

Main publicada

Develop publicada

feature/Cadastro publicada

fix/Correcao publicada

Index.html publicado

.gitignore publicado

README.md publicado

cadastro.txt publicado

correcao.txt publicado

Commits realizados

Pull Requests criados

Merges realizados localmente

Tag v1.0.0 publicada

Tag v1.1.0 publicada

Release 1.0.0 publicada

Release 1.1.0 publicada
```

# Resultado esperado

Ao concluir esta atividade nós teremos executado um fluxo completo de versionamento com Git e GitHub.

O objetivo é compreender o papel de cada recurso dentro de um projeto e conseguir apresentar o funcionamento do repositório diretamente pelo GitHub.
