# 🧪 Exercício Prático de Git e GitHub

## Criando uma nova Feature a partir da Branch Develop

Neste exercício, nós vamos praticar a criação de uma nova branch de desenvolvimento a partir da branch `develop`.

A nova funcionalidade será representada pela branch:

```bash
feature/relatorio
```

Dentro dessa branch, nós criaremos dois arquivos relacionados a relatórios e, ao final, enviaremos a nova branch para o GitHub.

---

## 🎯 Objetivos do Exercício

Ao concluir esta atividade, nós deveremos ser capazes de:

1. Acessar um repositório Git existente
2. Mudar para a branch `develop`
3. Atualizar a branch `develop`
4. Criar uma nova branch a partir da `develop`
5. Criar novos arquivos dentro da branch
6. Adicionar os arquivos ao controle de versão
7. Criar um commit
8. Enviar a nova branch para o GitHub
9. Conferir os arquivos diretamente no GitHub

---

## 📌 Situação do Exercício

Nós já possuímos um projeto Git com a branch:

```text
develop
```

A partir dela, nós deveremos criar uma nova branch chamada:

```text
feature/relatorio
```

Essa nova branch representará o desenvolvimento da funcionalidade de relatórios do sistema.

---

# Parte 1. Acessar o Projeto

Abra o terminal dentro da pasta do projeto.

Podemos verificar em qual branch estamos com:

```bash
git branch
```

---

# Parte 2. Acessar a Branch Develop

Antes de criar a nova branch, nós devemos acessar a branch `develop`.

Execute:

```bash
git checkout develop
```

Confira novamente:

```bash
git branch
```

A branch `develop` deverá aparecer marcada como a branch atual.

---

# Parte 3. Atualizar a Branch Develop

Antes de iniciar uma nova funcionalidade, é uma boa prática garantir que a nossa branch `develop` esteja atualizada com o repositório remoto.

Execute:

```bash
git pull origin develop
```

---

# Parte 4. Criar a Branch Feature

Agora nós vamos criar uma nova branch chamada:

```text
feature/relatorio
```

Primeiro, crie a branch:

```bash
git branch feature/relatorio
```

Depois, acesse a nova branch:

```bash
git switch feature/relatorio
```

Confira:

```bash
git branch
```

O resultado deverá indicar que estamos trabalhando na branch:

```text
feature/relatorio
```

---

# Parte 5. Criar os Arquivos

Dentro da branch `feature/relatorio`, nós deveremos criar os seguintes arquivos:

```text
rel_cliente.txt
rel_produtos.txt
```

Os arquivos podem ser criados pelo editor de código, pelo explorador de arquivos ou diretamente pelo terminal.

### Arquivo 1

Nome:

```text
rel_cliente.txt
```

Exemplo de conteúdo:

```text
RELATÓRIO DE CLIENTES

Este arquivo representa o relatório de clientes do sistema.
```

### Arquivo 2

Nome:

```text
rel_produtos.txt
```

Exemplo de conteúdo:

```text
RELATÓRIO DE PRODUTOS

Este arquivo representa o relatório de produtos do sistema.
```

---

# Parte 6. Verificar os Arquivos

Depois de criar os arquivos, execute:

```bash
git status
```

O Git deverá informar que existem dois novos arquivos ainda não adicionados ao controle de versão.

---

# Parte 7. Adicionar os Arquivos

Agora nós vamos adicionar os dois arquivos ao controle de versão.

Execute:

```bash
git add rel_cliente.txt rel_produtos.txt
```

Depois, confira novamente:

```bash
git status
```

---

# Parte 8. Criar o Commit

Agora nós devemos registrar as alterações com um commit.

Execute:

```bash
git commit -m "Adiciona relatórios de clientes e produtos"
```

Podemos conferir o histórico com:

```bash
git log
```

---

# Parte 9. Enviar a Branch para o GitHub

Agora nós vamos enviar a nova branch para o repositório remoto no GitHub.

Execute:

```bash
git push origin feature/relatorio
```

Após o envio, a branch deverá aparecer no repositório do GitHub.

---

# Parte 10. Conferir no GitHub

Acesse o repositório pelo navegador.

No GitHub, nós deveremos verificar se existe a branch:

```text
feature/relatorio
```

Depois, abra essa branch e confira se os seguintes arquivos estão disponíveis:

```text
rel_cliente.txt
rel_produtos.txt
```

---

# ✅ Resultado Esperado

Ao final do exercício, o repositório deverá possuir a seguinte organização:

```text
main
develop
feature/relatorio
    rel_cliente.txt
    rel_produtos.txt
```

A branch `feature/relatorio` deverá ter sido criada a partir da branch `develop`.

Os dois arquivos deverão estar versionados e publicados no GitHub.

---

# 📤 Entrega do Exercício

O aluno deverá entregar:

1. Link do repositório no GitHub
2. Evidência da branch `feature/relatorio`
3. Evidência dos arquivos `rel_cliente.txt` e `rel_produtos.txt`
4. Evidência do commit realizado
5. Evidência de que a branch foi enviada ao GitHub

---

# 🔍 Checklist de Conferência

Antes de entregar, confirme:

✅ Estou trabalhando no repositório correto

✅ A branch `develop` existe

✅ Criei a branch `feature/relatorio` a partir da `develop`

✅ Criei o arquivo `rel_cliente.txt`

✅ Criei o arquivo `rel_produtos.txt`

✅ Adicionei os arquivos com `git add`

✅ Realizei o commit

✅ Enviei a branch para o GitHub

✅ Conferi os arquivos diretamente no GitHub

---


## 📚 Conclusão

Neste exercício, nós praticamos um fluxo muito comum em projetos profissionais com Git e GitHub.

Criamos uma branch específica para uma funcionalidade, adicionamos novos arquivos, registramos as alterações e publicamos a branch no GitHub.

Esse processo ajuda a manter o desenvolvimento organizado e permite que novas funcionalidades sejam desenvolvidas sem alterar diretamente a branch principal do projeto.
