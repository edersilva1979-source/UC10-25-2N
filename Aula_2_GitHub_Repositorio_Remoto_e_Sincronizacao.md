# Aula 2: GitHub, Repositório Remoto e Sincronização

## Git e GitHub na Prática

### Carga horária


### Tema da aula

Criação de repositório no GitHub, conexão entre repositório local e remoto, autenticação e utilização dos comandos clone, remote, push, fetch e pull.

## 1. Apresentação da aula

Na primeira aula, eu ensinei você a utilizar o Git no computador.

Nós criamos um repositório local, adicionamos arquivos à área de preparação, registramos commits e consultamos o histórico do projeto.

Nesta segunda aula, vamos dar um passo muito importante.

Vamos conectar o projeto local ao GitHub.

A partir desse momento, teremos duas versões relacionadas do projeto:

```text
Repositório local

Fica armazenado no computador.

Repositório remoto

Fica armazenado no GitHub.
```

O objetivo não será apenas enviar uma pasta para a internet.

Eu quero que você compreenda como as alterações circulam entre o computador e o GitHub.

O fluxo básico será:

```text
Computador

        ↓ push

GitHub

        ↓ fetch ou pull

Computador
```

## 2. Objetivos da aula

Nesta aula, eu vou ensinar você a:

1. Compreender a diferença entre repositório local e remoto.

2. Criar um repositório no GitHub.

3. Escolher entre repositório público e privado.

4. Entender a função do README.

5. Criar e configurar um arquivo `.gitignore`.

6. Compreender a finalidade de uma licença.

7. Conectar um repositório local a um repositório remoto.

8. Entender o significado do nome `origin`.

9. Enviar commits locais com `git push`.

10. Buscar informações remotas com `git fetch`.

11. Receber e integrar alterações com `git pull`.

12. Criar uma cópia local com `git clone`.

13. Compreender as formas de autenticação HTTPS e SSH.

14. Identificar e corrigir erros comuns de sincronização.

15. Evitar o envio de senhas, tokens e informações confidenciais.

## 3. Resultados esperados

Ao final da aula, você deverá conseguir executar o seguinte fluxo:

```text
Criar um projeto local

Criar commits

Criar um repositório vazio no GitHub

Conectar o projeto local ao GitHub

Enviar os commits

Alterar um arquivo no GitHub

Buscar informações remotas

Receber as alterações no computador

Criar uma nova alteração local

Enviar a nova alteração

Clonar o projeto em outra pasta
```

Os principais comandos utilizados serão:

```bash
git remote add origin URL_DO_REPOSITORIO

git remote -v

git push -u origin main

git fetch origin

git pull origin main

git clone URL_DO_REPOSITORIO
```

## 4. Conhecimentos necessários

Para acompanhar esta aula, você deverá conhecer:

1. `git init`

2. `git status`

3. `git add`

4. `git commit`

5. `git log`

6. Criação de arquivos e pastas.

7. Utilização básica do terminal.

8. Utilização básica do Visual Studio Code.

## 5. Recursos necessários

1. Computador conectado à internet.

2. Git instalado.

3. Visual Studio Code.

4. Navegador atualizado.

5. Conta no GitHub.

6. Projeto Portal da Turma criado na Aula 1.

7. Endereço de email válido.

## 6. Organização das quatro horas

### Primeiro momento: 20 minutos

Revisão da Aula 1 e apresentação do fluxo local e remoto.

### Segundo momento: 30 minutos

Conceitos de GitHub, repositório remoto, visibilidade, README, `.gitignore` e licença.

### Terceiro momento: 35 minutos

Criação da conta e do primeiro repositório remoto.

### Quarto momento: 45 minutos

Conexão do projeto local e realização do primeiro push.

### Intervalo: 15 minutos

### Quinto momento: 45 minutos

Prática com alterações remotas, fetch e pull.

### Sexto momento: 25 minutos

Prática com clone e simulação de um novo computador.

### Sétimo momento: 25 minutos

Exercícios, desafios, correção e encerramento.

# Parte 1: Revisão da aula anterior

## 7. O que já sabemos

Na primeira aula, trabalhamos com um projeto armazenado no computador.

Utilizamos o seguinte fluxo:

```bash
git status

git add .

git commit -m "Mensagem do commit"

git log --oneline
```

Esse processo criou um histórico local.

Até agora, o projeto existe apenas no computador onde foi criado.

Se o computador apresentar algum problema, nós poderemos perder os arquivos e o histórico local.

Além disso, outras pessoas ainda não conseguem acessar facilmente o projeto.

É nesse momento que o GitHub entra no nosso processo.

## 8. Verificando o projeto da Aula 1

Antes de continuar, eu abro o terminal dentro da pasta do projeto:

```text
portal-da-turma
```

Depois, executo:

```bash
git status
```

O resultado esperado será semelhante a:

```text
On branch main

nothing to commit, working tree clean
```

Essa mensagem indica que não existem alterações pendentes.

Também consulto o histórico:

```bash
git log --oneline
```

Um exemplo de resultado seria:

```text
d0b81a2 Cria estilos da página inicial

734bf29 Adiciona área de projetos

048fb12 Cria seção de conteúdos

ac614b8 Adiciona informações da turma

482ae21 Cria a estrutura inicial do portal
```

Antes de publicar um projeto, eu verifico se os arquivos estão organizados e se os commits foram criados corretamente.

# Parte 2: O que é GitHub?

## 9. Entendendo o GitHub

GitHub é uma plataforma que hospeda repositórios Git.

Eu posso utilizar o Git localmente sem o GitHub.

Porém, o GitHub acrescenta recursos importantes, como:

1. Armazenamento remoto.

2. Compartilhamento de projetos.

3. Colaboração entre desenvolvedores.

4. Revisão de código.

5. Registro de problemas e tarefas.

6. Pull Requests.

7. Releases.

8. Automação.

9. Publicação de sites.

Nesta aula, vamos trabalhar principalmente com armazenamento e sincronização.

## 10. Git e GitHub não são a mesma coisa

Eu gosto de reforçar esta diferença:

```text
Git

Controla as versões dos arquivos.

GitHub

Hospeda e compartilha os repositórios Git.
```

Outro modo de entender seria:

```text
Git registra a história do projeto.

GitHub permite publicar e compartilhar essa história.
```

## 11. Repositório local

O repositório local fica armazenado no computador.

Ele contém:

1. Os arquivos do projeto.

2. A pasta oculta `.git`.

3. O histórico de commits.

4. As configurações locais.

5. As branches locais.

Nós podemos criar commits sem internet porque o Git trabalha localmente.

## 12. Repositório remoto

O repositório remoto fica armazenado em outro local.

Nesta aula, esse local será o GitHub.

O repositório remoto permite que os commits sejam enviados para a plataforma e acessados por outras pessoas autorizadas.

## 13. Representação do fluxo

```text
┌─────────────────────────────┐
│ Repositório local           │
│                             │
│ Arquivos do computador      │
│ Commits locais              │
└─────────────────────────────┘

             ↓ push

┌─────────────────────────────┐
│ Repositório remoto          │
│                             │
│ Projeto hospedado no GitHub │
│ Commits publicados          │
└─────────────────────────────┘

          ↓ fetch ou pull

┌─────────────────────────────┐
│ Repositório local atualizado│
└─────────────────────────────┘
```

# Parte 3: Criando uma conta no GitHub

## 14. Cadastro inicial

Para utilizar o GitHub, eu preciso criar uma conta.

Durante o cadastro, normalmente serão solicitados:

1. Endereço de email.

2. Senha.

3. Nome de usuário.

4. Confirmação do endereço de email.

## 15. Escolhendo um nome de usuário

O nome de usuário fará parte da identificação pública da conta.

Um exemplo seria:

```text
edersilva
```

O endereço de um repositório poderá conter:

```text
github.com/edersilva/portal-da-turma
```

Por isso, eu escolho um nome de usuário que seja:

1. Fácil de lembrar.

2. Adequado para uso acadêmico e profissional.

3. Sem informações desnecessárias.

4. Sem palavras ofensivas.

5. Próximo do meu nome ou da minha identidade profissional.

## 16. Protegendo a conta

Eu recomendo que você:

1. Utilize uma senha exclusiva.

2. Não compartilhe sua senha.

3. Ative a autenticação em dois fatores.

4. Guarde os códigos de recuperação.

5. Não envie tokens ou chaves em arquivos do projeto.

# Parte 4: Criando um repositório no GitHub

## 17. Iniciando a criação

Depois de entrar na conta, eu localizo a opção para criar um novo repositório.

O formulário apresentará campos como:

1. Proprietário.

2. Nome do repositório.

3. Descrição.

4. Visibilidade.

5. README.

6. `.gitignore`.

7. Licença.

## 18. Nome do repositório

Para esta aula, eu utilizarei:

```text
portal-da-turma
```

O ideal é evitar espaços no nome do repositório.

Podemos separar palavras com hífen:

```text
portal-da-turma
```

## 19. Descrição

A descrição deve explicar rapidamente o objetivo do projeto.

Exemplo:

```text
Projeto colaborativo desenvolvido durante o curso de Git e GitHub.
```

## 20. Repositório público

Um repositório público pode ser visualizado por qualquer pessoa.

Isso é útil para:

1. Projetos acadêmicos.

2. Portfólios.

3. Projetos de código aberto.

4. Materiais de estudo.

5. Exemplos de programação.

Antes de tornar um repositório público, eu verifico se ele contém informações pessoais, credenciais ou dados confidenciais.

## 21. Repositório privado

Um repositório privado fica disponível apenas para o proprietário e para as pessoas autorizadas.

Isso é útil para:

1. Projetos internos.

2. Atividades ainda não publicadas.

3. Projetos de empresas.

4. Projetos que contenham informações restritas.

5. Trabalhos que ainda serão avaliados.

> 💡 Para uma atividade pública de portfólio, podemos utilizar um repositório público. Para atividades com dados pessoais ou informações restritas, utilizamos um repositório privado.

## 22. Uma escolha importante para esta aula

O projeto já foi criado localmente durante a Aula 1.

Ele já possui:

1. Arquivos.

2. README.

3. Histórico de commits.

4. Repositório Git local.

Por isso, ao criar o repositório no GitHub, eu não marco as opções para adicionar automaticamente:

1. README.

2. `.gitignore`.

3. Licença.

O repositório remoto deverá ser criado vazio.

Essa orientação evita a criação de um histórico remoto separado antes da conexão com o projeto local.

## 23. Configuração utilizada

```text
Nome

portal-da-turma

Descrição

Projeto colaborativo desenvolvido durante o curso de Git e GitHub.

Visibilidade

Público ou privado, conforme orientação do professor.

README automático

Não selecionar.

.gitignore automático

Não selecionar.

Licença automática

Não selecionar.
```

Depois, finalizo a criação do repositório.

# Parte 5: Entendendo o remote

## 24. O que é um remote?

Um remote é uma referência para outro repositório Git.

No nosso caso, será uma referência do projeto local para o projeto hospedado no GitHub.

O repositório local precisa saber para qual endereço deverá enviar os commits.

A conexão será criada com:

```bash
git remote add origin URL_DO_REPOSITORIO
```

## 25. O que significa origin?

`origin` é o nome convencional dado ao repositório remoto principal.

Ele não é um comando especial e pode ser substituído por outro nome.

Mesmo assim, a maioria dos projetos utiliza:

```text
origin
```

Eu posso interpretar `origin` como:

```text
Este é o repositório remoto principal de onde este projeto se originou ou com o qual ele está conectado.
```

## 26. Estrutura do comando

```bash
git remote add origin URL_DO_REPOSITORIO
```

### git

Executa o Git.

### remote

Trabalha com repositórios remotos.

### add

Adiciona uma nova referência remota.

### origin

Define o nome da referência.

### URL_DO_REPOSITORIO

Informa o endereço do repositório no GitHub.

# Parte 6: Conectando o projeto local ao GitHub

## 27. Copiando o endereço do repositório

Na página do repositório, o GitHub apresentará o endereço HTTPS.

Um exemplo seria:

```text
https://github.com/USUARIO/portal-da-turma.git
```

Eu copio o endereço correspondente ao meu repositório.

## 28. Abrindo o terminal na pasta correta

No Visual Studio Code, abro o projeto:

```text
portal-da-turma
```

Depois, abro o terminal integrado.

Verifico o local atual:

```bash
pwd
```

No Prompt de Comando do Windows, posso utilizar:

```cmd
cd
```

## 29. Confirmando que estou no repositório

Executo:

```bash
git status
```

Se o comando apresentar informações sobre a branch e os arquivos, estou no local correto.

## 30. Verificando o nome da branch

Executo:

```bash
git branch --show-current
```

O resultado esperado será:

```text
main
```

Caso a branch ainda tenha outro nome, posso renomeá la:

```bash
git branch -M main
```

## 31. Adicionando o remote

Executo:

```bash
git remote add origin URL_DO_REPOSITORIO
```

Exemplo:

```bash
git remote add origin https://github.com/usuario/portal-da-turma.git
```

> ⚠️ O endereço acima é apenas um exemplo. Cada aluno deverá utilizar o endereço do próprio repositório.

## 32. Verificando a conexão

Executo:

```bash
git remote -v
```

Um resultado possível será:

```text
origin  https://github.com/usuario/portal-da-turma.git (fetch)

origin  https://github.com/usuario/portal-da-turma.git (push)
```

A palavra `fetch` indica o endereço utilizado para buscar alterações.

A palavra `push` indica o endereço utilizado para enviar alterações.

## 33. Verificando informações detalhadas

Também posso utilizar:

```bash
git remote show origin
```

Esse comando poderá apresentar:

1. Endereço do repositório.

2. Branch principal.

3. Situação da conexão.

4. Branches acompanhadas.

# Parte 7: Realizando o primeiro push

## 34. O que é push?

Push significa enviar commits locais para o repositório remoto.

É importante compreender que o `git push` não envia apenas o arquivo que está aberto.

Ele envia commits.

Por isso, antes do push, eu verifico se as alterações já foram registradas:

```bash
git status
```

Depois, consulto o histórico:

```bash
git log --oneline
```

## 35. Primeiro envio

Executo:

```bash
git push -u origin main
```

## 36. Entendendo o comando

```bash
git push -u origin main
```

### push

Envia commits para o repositório remoto.

### origin

Indica qual repositório remoto será utilizado.

### main

Indica qual branch será enviada.

### opção u

Configura a ligação de acompanhamento entre a branch local e a branch remota.

Depois dessa configuração, em muitos casos poderei utilizar apenas:

```bash
git push
```

## 37. Autenticação

Durante o primeiro push, o sistema poderá solicitar autenticação.

Dependendo da instalação e da configuração do computador, poderá ocorrer uma destas situações:

1. O navegador será aberto para confirmar a conta.

2. O Git Credential Manager solicitará autenticação.

3. O GitHub CLI poderá ser utilizado.

4. Um token de acesso pessoal poderá ser solicitado em uma configuração HTTPS.

5. Uma chave SSH poderá ser utilizada.

## 38. Confirmando o envio

Depois do push, atualizo a página do repositório no navegador.

Agora deverão aparecer:

1. `index.html`

2. `README.md`

3. Pasta `css`

4. Arquivo `estilo.css`

5. Histórico de commits.

6. Branch `main`.

## 39. O projeto foi enviado como arquivos soltos?

Não.

O GitHub recebeu os commits e o histórico do projeto.

Eu posso acessar a área de commits e visualizar a evolução registrada localmente.

Essa é uma diferença importante entre fazer upload manual de arquivos e utilizar Git.

# Parte 8: O arquivo README

## 40. Para que serve o README?

O README é o arquivo de apresentação do projeto.

Quando alguém abre o repositório, normalmente encontrará o conteúdo do README abaixo da lista de arquivos.

Ele pode explicar:

1. Nome do projeto.

2. Objetivo.

3. Tecnologias utilizadas.

4. Instruções de instalação.

5. Como executar.

6. Funcionalidades.

7. Autores.

8. Licença.

9. Formas de contribuição.

## 41. Modelo de README

```md
# Portal da Turma

Projeto desenvolvido durante o curso de Git e GitHub.

## Objetivo

Criar um portal colaborativo para apresentar a turma, os conteúdos estudados e os projetos desenvolvidos.

## Tecnologias utilizadas

1. HTML
2. CSS
3. Git
4. GitHub

## Funcionalidades

1. Apresentação da turma
2. Lista de conteúdos
3. Área de projetos
4. Informações de contato

## Como executar

1. Faça o clone do repositório.
2. Abra a pasta no Visual Studio Code.
3. Abra o arquivo index.html no navegador.

## Autores

Alunos da turma de Desenvolvimento de Sistemas.

## Situação do projeto

Em desenvolvimento.
```

## 42. README não é um arquivo decorativo

Um README bem construído ajuda outras pessoas a utilizarem o projeto.

Um README vazio ou desatualizado poderá causar dúvidas mesmo quando o código estiver funcionando.

Sempre que o funcionamento do projeto mudar, eu verifico se a documentação também precisa ser atualizada.

# Parte 9: O arquivo .gitignore

## 43. Para que serve o .gitignore?

O arquivo `.gitignore` informa ao Git quais arquivos e pastas não deverão entrar normalmente no controle de versão.

Ele pode ignorar:

1. Arquivos temporários.

2. Credenciais.

3. Dependências que podem ser instaladas novamente.

4. Registros de execução.

5. Configurações pessoais do editor.

6. Arquivos gerados automaticamente.

O `.gitignore` deve ficar normalmente na raiz do repositório e pode ser registrado em um commit para compartilhar as mesmas regras com outras pessoas.

## 44. Criando o arquivo

Na raiz do projeto, crio:

```text
.gitignore
```

Adiciono:

```gitignore
.env
*.log
.vscode/
node_modules/
dist/
```

## 45. Entendendo as regras

### .env

Ignora o arquivo chamado `.env`.

Esse tipo de arquivo costuma armazenar configurações e variáveis sensíveis.

### *.log

Ignora arquivos que terminam com `.log`.

Exemplo:

```text
sistema.log
```

### .vscode/

Ignora a pasta de configurações locais do Visual Studio Code.

Em alguns projetos, a equipe poderá decidir compartilhar determinadas configurações dessa pasta.

Essa decisão deverá ser combinada.

### node_modules/

Ignora a pasta de dependências de projetos Node.

Essa pasta pode ser recriada por meio do gerenciador de pacotes.

### dist/

Ignora uma pasta de arquivos gerados durante a compilação ou publicação.

## 46. Registrando o .gitignore

Depois de criar o arquivo, executo:

```bash
git status
```

Depois:

```bash
git add .gitignore
```

Crio o commit:

```bash
git commit -m "Adiciona regras de arquivos ignorados"
```

Envio:

```bash
git push
```

## 47. Arquivo já rastreado

Adicionar um arquivo ao `.gitignore` não remove automaticamente um arquivo que já estava sendo rastreado.

Nesse caso, posso utilizar:

```bash
git rm --cached nome-do-arquivo
```

Depois, crio um commit:

```bash
git commit -m "Remove arquivo do controle de versão"
```

> ⚠️ Antes de utilizar esse comando, eu confirmo se o arquivo correto foi informado.

# Parte 10: Segurança dos arquivos

## 48. O que nunca devo publicar?

Eu nunca devo enviar para o GitHub:

1. Senhas.

2. Tokens de acesso.

3. Chaves privadas.

4. Credenciais de banco de dados.

5. Dados pessoais de clientes.

6. Arquivos contendo informações confidenciais.

7. Certificados privados.

8. Segredos de serviços externos.

## 49. Exemplo de arquivo perigoso

```env
BANCO_USUARIO=administrador
BANCO_SENHA=senha_secreta
API_TOKEN=token_secreto
```

Esse arquivo não deve ser publicado.

No `.gitignore`, adiciono:

```gitignore
.env
```

## 50. O .gitignore apaga um segredo que já foi publicado?

Não.

Se uma senha ou um token já foi enviado, apenas adicionar o arquivo ao `.gitignore` não remove o conteúdo do histórico.

Nesse caso, eu devo:

1. Revogar ou trocar imediatamente a credencial.

2. Remover o arquivo do controle de versão.

3. Avaliar a necessidade de limpar o histórico.

4. Comunicar o responsável pelo projeto.

O passo mais urgente é invalidar a credencial exposta.

# Parte 11: Licença do projeto

## 51. Para que serve uma licença?

Uma licença informa como outras pessoas podem utilizar, copiar, modificar e distribuir o projeto.

Exemplos conhecidos incluem:

1. MIT.

2. Apache 2.0.

3. GPL.

4. BSD.

A escolha depende dos objetivos do projeto.

## 52. Projeto acadêmico

Em um projeto acadêmico, eu verifico a orientação da instituição e do professor.

Não escolho uma licença apenas porque ela apareceu como opção.

Eu procuro compreender:

1. O que ela permite.

2. O que ela exige.

3. Como trata modificações.

4. Como trata redistribuição.

5. Como trata autoria e avisos.

Nesta aula, a licença será apresentada como conceito.

A escolha definitiva poderá ser realizada posteriormente.

# Parte 12: Alterando um arquivo diretamente no GitHub

## 53. Objetivo da experiência

Agora vamos simular uma alteração feita no repositório remoto.

Essa atividade será útil para compreender que o GitHub poderá possuir commits que ainda não existem no computador.

> ⚠️ Nas próximas aulas, utilizaremos branches e Pull Requests. Nesta experiência inicial, faremos uma alteração direta na branch principal apenas para estudar a sincronização.

## 54. Editando o README

Na página do repositório:

1. Abro o arquivo `README.md`.

2. Seleciono a opção de edição.

3. Acrescento uma nova seção.

```md
## Aula atual

Nesta aula, estamos aprendendo a conectar o Git ao GitHub.
```

4. Escrevo uma mensagem de commit.

```text
Atualiza conteúdo da aula no README
```

5. Confirmo o commit na branch `main`.

## 55. O que aconteceu?

O GitHub agora possui um commit novo.

O computador ainda não possui esse commit.

Temos esta situação:

```text
GitHub

Possui o novo commit.

Computador

Ainda está na versão anterior.
```

# Parte 13: Utilizando git fetch

## 56. O que é fetch?

O comando `git fetch` busca informações e commits do repositório remoto.

Ele atualiza as referências remotas, mas não integra automaticamente essas alterações à branch local atual.

Isso permite analisar o que chegou antes de modificar o trabalho local.

## 57. Executando o fetch

No terminal, executo:

```bash
git fetch origin
```

Depois, consulto:

```bash
git status
```

O Git poderá informar que a branch local está atrás da branch remota.

## 58. Visualizando todos os históricos

Executo:

```bash
git log --oneline --all --graph
```

Poderá aparecer algo semelhante:

```text
* 81d39c2 Atualiza conteúdo da aula no README
* d0b81a2 Adiciona regras de arquivos ignorados
* 734bf29 Cria estilos da página inicial
```

## 59. Visualizando apenas commits remotos novos

Posso utilizar:

```bash
git log HEAD..origin/main --oneline
```

Esse comando mostra os commits que estão em `origin/main`, mas ainda não estão na posição atual da branch local.

## 60. O arquivo local já mudou?

Não.

Depois do `git fetch`, o arquivo `README.md` do computador continuará com o conteúdo anterior.

O Git apenas buscou as informações remotas.

Essa é a principal ideia do fetch:

```text
Buscar primeiro.

Analisar depois.

Integrar quando for adequado.
```

# Parte 14: Utilizando git pull

## 61. O que é pull?

O comando `git pull` busca as alterações do repositório remoto e tenta integrá las à branch local atual.

De forma simplificada, ele realiza:

```text
fetch

mais

integração
```

## 62. Recebendo a alteração

Executo:

```bash
git pull origin main
```

Depois, abro o arquivo:

```text
README.md
```

A nova seção criada no GitHub deverá aparecer no arquivo local.

## 63. Confirmando o histórico

Executo:

```bash
git log --oneline
```

O commit criado no GitHub deverá aparecer no histórico local.

## 64. Fetch e pull comparados

```text
git fetch

Busca informações do repositório remoto.

Não altera automaticamente os arquivos da branch local.

Permite analisar antes de integrar.
```

```text
git pull

Busca informações do repositório remoto.

Integra as alterações à branch local.

Pode modificar os arquivos locais.
```

## 65. Quando utilizar cada um?

Eu utilizo `git fetch` quando quero:

1. Verificar se existem alterações.

2. Analisar commits remotos.

3. Comparar antes de integrar.

4. Atualizar referências remotas.

Eu utilizo `git pull` quando quero:

1. Atualizar minha branch local.

2. Receber alterações já analisadas.

3. Continuar trabalhando sobre a versão mais recente.

4. Sincronizar o computador antes de iniciar uma tarefa.

# Parte 15: Criando uma nova alteração local

## 66. Atualizando o projeto

Depois de receber a alteração remota, eu modifico o arquivo `index.html`.

Adiciono:

```html
<section>
    <h2>Aulas do curso</h2>

    <ol>
        <li>Introdução ao Git</li>
        <li>GitHub e repositórios remotos</li>
    </ol>
</section>
```

## 67. Verificando a alteração

Executo:

```bash
git status
```

Depois, analiso a diferença:

```bash
git diff
```

## 68. Preparando e registrando

```bash
git add index.html
```

Depois:

```bash
git commit -m "Adiciona lista inicial de aulas"
```

## 69. Enviando para o GitHub

Como a ligação de acompanhamento já foi configurada, posso utilizar:

```bash
git push
```

Também poderia escrever:

```bash
git push origin main
```

## 70. Confirmando no navegador

Atualizo a página do GitHub.

O novo commit deverá aparecer.

O fluxo completo foi:

```text
Alteração local

git add

git commit

git push

Alteração publicada no GitHub
```

# Parte 16: Entendendo git clone

## 71. O que é clone?

Clone cria uma cópia local de um repositório remoto.

Esse comando é utilizado quando o projeto já está no GitHub e queremos baixá lo com:

1. Arquivos.

2. Histórico.

3. Branches remotas.

4. Configuração do remote `origin`.

## 72. Não confundir clone com download de ZIP

### Download de ZIP

Baixa os arquivos atuais.

Não cria automaticamente um repositório Git completo.

Não configura `origin`.

Não prepara o projeto para sincronização pelo fluxo normal.

### git clone

Baixa os arquivos.

Baixa o histórico.

Cria o repositório local.

Configura o remote `origin`.

Prepara o projeto para pull e push, conforme as permissões.

## 73. Simulando outro computador

Primeiro, fecho o projeto atual.

Depois, acesso uma pasta diferente.

Exemplo:

```bash
cd ..
```

Crio uma pasta para a simulação:

```bash
mkdir computador-teste
```

Entro nela:

```bash
cd computador-teste
```

## 74. Clonando o projeto

Executo:

```bash
git clone URL_DO_REPOSITORIO
```

Exemplo:

```bash
git clone https://github.com/usuario/portal-da-turma.git
```

Depois, entro na pasta criada:

```bash
cd portal-da-turma
```

## 75. Verificando o clone

Executo:

```bash
git status
```

Depois:

```bash
git log --oneline
```

E:

```bash
git remote -v
```

O remote `origin` já deverá estar configurado.

## 76. Abrindo o projeto

```bash
code .
```

Agora temos uma nova cópia local do projeto.

> ⚠️ Durante as atividades, eu evito alterar simultaneamente duas cópias sem compreender qual delas está atualizada. Sempre verifico e sincronizo antes de começar.

# Parte 17: HTTPS e SSH

## 77. Conexão HTTPS

HTTPS utiliza um endereço semelhante a:

```text
https://github.com/usuario/repositorio.git
```

É uma opção simples para iniciantes.

A autenticação poderá ser realizada pelo navegador, pelo Git Credential Manager, pelo GitHub CLI ou por um token, conforme a configuração utilizada.

## 78. Conexão SSH

SSH utiliza um endereço semelhante a:

```text
git@github.com:usuario/repositorio.git
```

Nesse método, o computador utiliza um par de chaves:

1. Chave privada no computador.

2. Chave pública cadastrada no GitHub.

## 79. Comparação inicial

```text
HTTPS

Mais simples para iniciar.

Pode utilizar autenticação pelo navegador.

Funciona bem com o Git Credential Manager.
```

```text
SSH

Utiliza chaves criptográficas.

Exige configuração inicial.

É bastante utilizado em ambientes profissionais.
```

## 80. Qual método utilizaremos?

Durante a prática principal, utilizaremos HTTPS.

SSH será apresentado como opção e poderá ser praticado em um desafio adicional.

# Parte 18: Fluxo diário de sincronização

## 81. Antes de começar a trabalhar

Eu abro o projeto e executo:

```bash
git status
```

Depois:

```bash
git pull
```

Assim, verifico se existem alterações remotas que precisam ser recebidas.

## 82. Durante o trabalho

```bash
git status

git diff
```

Depois de concluir uma alteração:

```bash
git add .

git commit -m "Descrição da alteração"
```

## 83. Depois de concluir

```bash
git pull

git push
```

Durante as próximas aulas, esse fluxo será ajustado para trabalhar com branches.

## 84. Fluxo resumido

```text
Antes do trabalho

git pull

Durante o trabalho

git status
git diff
git add
git commit

Depois do trabalho

git pull
git push
```

# Parte 19: Erros comuns

## 85. Erro: remote origin already exists

### Mensagem possível

```text
error: remote origin already exists
```

### Motivo

Já existe um remote chamado `origin`.

### Primeiro passo

```bash
git remote -v
```

Verifico se o endereço já está correto.

### Alterar o endereço

```bash
git remote set-url origin NOVA_URL
```

### Remover e adicionar novamente

```bash
git remote remove origin
```

Depois:

```bash
git remote add origin URL_DO_REPOSITORIO
```

## 86. Erro: repository not found

### Possíveis causas

1. Endereço incorreto.

2. Repositório inexistente.

3. Repositório privado sem autorização.

4. Conta errada autenticada.

5. Nome do usuário digitado incorretamente.

### Verificação

```bash
git remote -v
```

Confirmo o endereço na página do GitHub.

## 87. Erro de autenticação

### Possíveis causas

1. Credencial antiga armazenada.

2. Conta incorreta.

3. Token expirado.

4. Permissão insuficiente.

5. Chave SSH não cadastrada.

### Ações

1. Confirmo qual conta está autenticada.

2. Tento autenticar novamente pelo navegador.

3. Verifico o Git Credential Manager.

4. Confirmo as permissões do repositório.

5. Verifico se o endereço utiliza HTTPS ou SSH.

## 88. Erro: src refspec main does not match any

### Possíveis causas

1. A branch não se chama `main`.

2. Ainda não existe nenhum commit.

### Verificar branch

```bash
git branch --show-current
```

### Verificar histórico

```bash
git log --oneline
```

### Renomear branch

```bash
git branch -M main
```

Se não houver commit, crio o primeiro commit antes do push.

## 89. Push rejeitado

### Mensagem possível

```text
non-fast-forward
```

Isso geralmente acontece quando o repositório remoto possui commits que ainda não existem localmente.

### Procedimento inicial

```bash
git pull origin main
```

Depois de receber e integrar as alterações:

```bash
git push origin main
```

## 90. Repositório remoto criado com README

Se o projeto local já possuía histórico e o repositório remoto foi criado com um README automático, teremos dois históricos iniciados separadamente.

Para evitar esse problema nesta aula, criamos o repositório remoto vazio.

Para alunos iniciantes, a solução mais segura poderá ser:

1. Excluir o repositório remoto recém criado, desde que ele não contenha trabalho importante.

2. Criá lo novamente sem README, `.gitignore` ou licença.

3. Conectar o projeto local.

4. Executar o push.

## 91. Alterei o GitHub e o computador ao mesmo tempo

Se a mesma parte de um arquivo for alterada nos dois locais, poderá ocorrer conflito.

A resolução de conflitos será estudada detalhadamente em outra aula.

Para evitar problemas agora:

1. Execute `git pull` antes de começar.

2. Faça uma alteração por vez.

3. Crie o commit.

4. Envie com `git push`.

# Parte 20: Prática guiada completa

## 92. Etapa 1: Verificar o projeto

```bash
git status

git log --oneline
```

## 93. Etapa 2: Confirmar a branch

```bash
git branch --show-current
```

Caso necessário:

```bash
git branch -M main
```

## 94. Etapa 3: Criar o repositório vazio no GitHub

Configurações:

```text
Nome

portal-da-turma

README automático

Não selecionar.

.gitignore automático

Não selecionar.

Licença automática

Não selecionar.
```

## 95. Etapa 4: Conectar o remote

```bash
git remote add origin URL_DO_REPOSITORIO
```

## 96. Etapa 5: Conferir

```bash
git remote -v
```

## 97. Etapa 6: Primeiro push

```bash
git push -u origin main
```

## 98. Etapa 7: Criar o .gitignore

```gitignore
.env
*.log
.vscode/
node_modules/
dist/
```

Depois:

```bash
git add .gitignore

git commit -m "Adiciona regras de arquivos ignorados"

git push
```

## 99. Etapa 8: Alterar o README no GitHub

Adicionar:

```md
## Aula atual

Nesta aula, estamos aprendendo a sincronizar o Git com o GitHub.
```

Mensagem:

```text
Atualiza conteúdo da aula no README
```

## 100. Etapa 9: Buscar sem integrar

```bash
git fetch origin
```

Analisar:

```bash
git log HEAD..origin/main --oneline
```

## 101. Etapa 10: Integrar

```bash
git pull origin main
```

## 102. Etapa 11: Criar uma alteração local

Modificar `index.html`.

Depois:

```bash
git status

git diff

git add index.html

git commit -m "Adiciona lista inicial de aulas"

git push
```

## 103. Etapa 12: Clonar em outra pasta

```bash
git clone URL_DO_REPOSITORIO
```

Depois:

```bash
cd portal-da-turma

git status

git log --oneline

git remote -v
```

# Parte 21: Atividade colaborativa

## 104. Inspeção de repositórios em duplas

Nesta atividade, os alunos formarão duplas.

Cada aluno deverá compartilhar a página pública do repositório ou mostrar a tela ao colega, caso o projeto seja privado.

## 105. O aluno revisor deverá verificar

1. O nome do repositório está adequado.

2. Existe uma descrição.

3. O README explica o projeto.

4. O histórico possui mensagens compreensíveis.

5. O `.gitignore` está presente.

6. Não existem senhas ou credenciais.

7. Os arquivos estão organizados.

8. A branch principal é `main`.

## 106. Registro da revisão

Cada aluno deverá escrever:

```md
# Revisão do repositório

## Ponto positivo

Descrever um aspecto bem organizado.

## Sugestão de melhoria

Descrever uma melhoria específica.

## Commit bem escrito

Copiar uma mensagem que explique corretamente uma alteração.

## Segurança

Informar se foi encontrado algum arquivo que não deveria estar publicado.
```

## 107. Objetivo da atividade

O objetivo não é apenas encontrar erros.

Eu quero que os alunos aprendam a observar um repositório como outro desenvolvedor observaria.

# Parte 22: Exercícios de fixação

## 108. Exercício 1: Conceitos

Responda com suas palavras.

1. O que é um repositório remoto?

2. Qual é a diferença entre repositório local e remoto?

3. Para que serve um remote?

4. O que significa o nome `origin`?

5. Para que serve `git push`?

6. Para que serve `git fetch`?

7. Para que serve `git pull`?

8. Para que serve `git clone`?

9. Qual é a função do README?

10. Para que serve o `.gitignore`?

11. O que é uma licença?

12. Qual é a diferença entre HTTPS e SSH?

## 109. Exercício 2: Relacione os comandos

### Comandos

```text
A. git remote add origin URL

B. git remote -v

C. git push

D. git fetch

E. git pull

F. git clone URL
```

### Funções

```text
1. Cria uma cópia local de um repositório remoto.

2. Busca informações remotas sem integrar automaticamente à branch atual.

3. Envia commits locais.

4. Mostra os remotes configurados.

5. Adiciona uma referência para um repositório remoto.

6. Busca e integra alterações remotas.
```

## 110. Exercício 3: Complete os comandos

### Adicionar um remote

```bash
git __________ add origin URL
```

### Visualizar os remotes

```bash
git remote __________
```

### Primeiro push

```bash
git push __________ origin main
```

### Buscar informações remotas

```bash
git __________ origin
```

### Receber e integrar alterações

```bash
git __________ origin main
```

### Clonar um repositório

```bash
git __________ URL
```

## 111. Exercício 4: Escolha o comando

### Situação 1

Quero enviar meus commits locais para o GitHub.

Resposta:

```text
____________________
```

### Situação 2

Quero baixar um projeto do GitHub com histórico e configuração de remote.

Resposta:

```text
____________________
```

### Situação 3

Quero verificar se existem commits novos no GitHub sem alterar imediatamente meus arquivos locais.

Resposta:

```text
____________________
```

### Situação 4

Quero receber e integrar as alterações da branch remota.

Resposta:

```text
____________________
```

### Situação 5

Quero descobrir o endereço configurado como `origin`.

Resposta:

```text
____________________
```

## 112. Exercício 5: Arquivos ignorados

Considere este `.gitignore`:

```gitignore
.env
*.log
node_modules/
.vscode/
```

Responda:

1. O arquivo `.env` será rastreado normalmente?

2. O arquivo `erros.log` será ignorado?

3. A pasta `node_modules` será ignorada?

4. O arquivo `index.html` será ignorado?

5. A pasta `.vscode` será ignorada?

6. O `.gitignore` deverá ser registrado em um commit?

## 113. Exercício 6: Segurança

Classifique cada arquivo como permitido ou perigoso para publicação.

```text
index.html

README.md

estilo.css

.env com senha do banco

imagem pública do site

chave privada SSH

arquivo com token de API

documentação do projeto
```

Explique suas respostas.

## 114. Exercício 7: Sequência correta

Organize as ações:

```text
Executar git push.

Criar o repositório vazio no GitHub.

Criar commits locais.

Adicionar o remote origin.

Conferir com git remote -v.
```

# Parte 23: Desafios

## 115. Desafio 1: Repositório publicado

Crie e publique um projeto chamado:

```text
meu-portfolio-inicial
```

O projeto deverá possuir:

1. `index.html`

2. `README.md`

3. `css/estilo.css`

4. `.gitignore`

5. Pelo menos quatro commits.

6. Descrição no GitHub.

7. Histórico publicado.

### Sugestões de commits

```text
Cria estrutura inicial do portfólio

Adiciona informações profissionais

Cria seção de tecnologias

Adiciona estilos da página

Cria documentação do projeto
```

## 116. Desafio 2: Investigador do remote

Dentro de um repositório conectado, execute:

```bash
git remote -v
```

Depois:

```bash
git remote show origin
```

Registre:

1. Endereço do remote.

2. Nome da branch principal.

3. Endereço utilizado para fetch.

4. Endereço utilizado para push.

5. Situação da branch local.

## 117. Desafio 3: Fetch antes do pull

1. Altere o README diretamente no GitHub.

2. Crie um commit remoto.

3. No computador, execute:

```bash
git fetch origin
```

4. Não execute pull imediatamente.

5. Utilize:

```bash
git log HEAD..origin/main --oneline
```

6. Registre o commit encontrado.

7. Execute:

```bash
git pull origin main
```

8. Confirme a alteração no arquivo local.

### Pergunta

Qual foi a diferença observada antes e depois do pull?

## 118. Desafio 4: Simulação de novo computador

1. Crie uma nova pasta fora do projeto original.

2. Clone o repositório.

3. Abra a nova cópia.

4. Execute:

```bash
git status
```

5. Execute:

```bash
git log --oneline
```

6. Execute:

```bash
git remote -v
```

7. Explique quais configurações foram criadas automaticamente pelo clone.

## 119. Desafio 5: Arquivo confidencial

Crie um arquivo de exemplo chamado:

```text
.env
```

Adicione somente dados fictícios:

```env
USUARIO=usuario_teste
SENHA=senha_ficticia
```

Depois:

1. Adicione `.env` ao `.gitignore`.

2. Execute `git status`.

3. Verifique se o arquivo aparece como disponível para commit.

4. Não envie o arquivo ao GitHub.

5. Registre apenas o `.gitignore`.

```bash
git add .gitignore

git commit -m "Protege arquivos de configuração local"

git push
```

## 120. Desafio 6: Corrigindo um remote

Adicione propositalmente um endereço fictício em um repositório de teste:

```bash
git remote add origin https://github.com/usuario/endereco-incorreto.git
```

Verifique:

```bash
git remote -v
```

Depois, corrija:

```bash
git remote set-url origin URL_CORRETA
```

Confirme novamente:

```bash
git remote -v
```

## 121. Desafio 7: Comparação entre ZIP e clone

Faça duas cópias do mesmo projeto:

1. Uma utilizando download em ZIP.

2. Outra utilizando `git clone`.

Em cada pasta, execute:

```bash
git status
```

Depois, responda:

1. Qual pasta foi reconhecida como repositório Git?

2. Qual possui a pasta `.git`?

3. Qual possui o remote `origin`?

4. Qual está pronta para executar pull?

5. Por que clone e download não são equivalentes?

## 122. Desafio adicional: Teste de conexão SSH

Este desafio é opcional.

Depois de criar e cadastrar uma chave SSH no GitHub, teste:

```bash
ssh -T git@github.com
```

Na primeira conexão, o terminal poderá solicitar confirmação da identidade do servidor.

Eu verifico as informações apresentadas antes de confirmar.

Depois, posso alterar a URL do remote:

```bash
git remote set-url origin git@github.com:usuario/portal-da-turma.git
```

Confiro:

```bash
git remote -v
```

# Parte 24: Avaliação da aula

## 123. Critérios de avaliação

A atividade poderá valer 10 pontos.

### Repositório criado no GitHub: 1 ponto

O aluno criou o repositório com nome e descrição adequados.

### Conexão local e remota: 1 ponto

O remote `origin` foi configurado corretamente.

### Primeiro push: 1 ponto

O histórico local foi enviado para o GitHub.

### README: 1 ponto

O arquivo apresenta o objetivo e as informações do projeto.

### .gitignore: 1 ponto

O arquivo contém regras adequadas e foi registrado.

### Fetch e análise: 1 ponto

O aluno buscou e identificou uma alteração remota.

### Pull: 1 ponto

O aluno integrou corretamente a alteração.

### Novo push: 1 ponto

O aluno criou e publicou uma nova alteração local.

### Clone: 1 ponto

O repositório foi clonado e verificado.

### Segurança e organização: 1 ponto

O projeto não apresenta credenciais ou arquivos confidenciais.

## 124. Evidências de aprendizagem

O aluno deverá apresentar:

1. Página do repositório no GitHub.

2. Resultado de `git remote -v`.

3. Histórico de commits.

4. Arquivo README.

5. Arquivo `.gitignore`.

6. Alteração remota recebida.

7. Novo commit enviado.

8. Pasta criada por clone.

9. Respostas dos exercícios.

# Parte 25: Gabarito

## 125. Gabarito do exercício 1

### Questão 1

Repositório remoto é uma versão do repositório armazenada em outro local, como o GitHub.

### Questão 2

O repositório local fica no computador.

O remoto fica hospedado em outro local e pode ser acessado por meio da rede.

### Questão 3

Remote é uma referência que conecta o repositório local a outro repositório.

### Questão 4

`origin` é o nome convencional utilizado para o repositório remoto principal.

### Questão 5

`git push` envia commits locais para o repositório remoto.

### Questão 6

`git fetch` busca informações e commits remotos sem integrá los automaticamente à branch local atual.

### Questão 7

`git pull` busca e integra alterações remotas.

### Questão 8

`git clone` cria uma cópia local completa de um repositório remoto.

### Questão 9

README apresenta e documenta o projeto.

### Questão 10

`.gitignore` informa quais arquivos e pastas deverão ser ignorados pelo Git.

### Questão 11

Licença informa as condições de utilização, modificação e distribuição do projeto.

### Questão 12

HTTPS utiliza uma conexão web autenticada.

SSH utiliza um par de chaves criptográficas.

## 126. Gabarito do exercício 2

```text
A corresponde a 5.

B corresponde a 4.

C corresponde a 3.

D corresponde a 2.

E corresponde a 6.

F corresponde a 1.
```

## 127. Gabarito do exercício 3

### Adicionar remote

```bash
git remote add origin URL
```

### Visualizar remotes

```bash
git remote -v
```

### Primeiro push

```bash
git push -u origin main
```

### Buscar informações remotas

```bash
git fetch origin
```

### Receber e integrar

```bash
git pull origin main
```

### Clonar

```bash
git clone URL
```

## 128. Gabarito do exercício 4

### Situação 1

```bash
git push
```

### Situação 2

```bash
git clone URL
```

### Situação 3

```bash
git fetch
```

### Situação 4

```bash
git pull
```

### Situação 5

```bash
git remote -v
```

## 129. Gabarito do exercício 5

1. O `.env` será ignorado.

2. `erros.log` será ignorado.

3. `node_modules` será ignorado.

4. `index.html` não será ignorado pelas regras apresentadas.

5. `.vscode` será ignorada.

6. Sim. O `.gitignore` deverá ser registrado para compartilhar as regras do projeto.

## 130. Gabarito do exercício 6

### Permitidos

```text
index.html

README.md

estilo.css

imagem pública do site

documentação do projeto
```

### Perigosos

```text
.env com senha do banco

chave privada SSH

arquivo com token de API
```

## 131. Gabarito do exercício 7

Ordem correta:

```text
Criar commits locais.

Criar o repositório vazio no GitHub.

Adicionar o remote origin.

Conferir com git remote -v.

Executar git push.
```

# Parte 26: Revisão oral

## 132. Perguntas para a turma

1. GitHub e Git são a mesma ferramenta?

2. O que acontece quando executamos push?

3. Push envia arquivos não registrados em commit?

4. O que significa origin?

5. Fetch modifica imediatamente o arquivo local?

6. Pull pode modificar os arquivos locais?

7. Clone baixa somente os arquivos atuais?

8. Qual é a função do README?

9. Para que serve o `.gitignore`?

10. É seguro publicar um arquivo `.env`?

11. Qual é a diferença entre HTTPS e SSH?

12. Por que devemos executar pull antes de começar uma nova tarefa?

# Parte 27: Resumo dos comandos

## 133. Conexão remota

```bash
git remote add origin URL_DO_REPOSITORIO

git remote -v

git remote show origin
```

## 134. Alteração do endereço remoto

```bash
git remote set-url origin NOVA_URL
```

## 135. Remoção de remote

```bash
git remote remove origin
```

## 136. Primeiro push

```bash
git push -u origin main
```

## 137. Push após configurar o acompanhamento

```bash
git push
```

## 138. Buscar alterações

```bash
git fetch origin
```

## 139. Receber e integrar

```bash
git pull origin main
```

## 140. Clonar

```bash
git clone URL_DO_REPOSITORIO
```

## 141. Verificar a branch

```bash
git branch --show-current
```

## 142. Renomear a branch para main

```bash
git branch -M main
```

## 143. Visualizar commits remotos ainda não integrados

```bash
git log HEAD..origin/main --oneline
```

# Parte 28: Fluxo completo da aula

## 144. Projeto local para GitHub

```bash
git status

git log --oneline

git branch -M main

git remote add origin URL_DO_REPOSITORIO

git remote -v

git push -u origin main
```

## 145. GitHub para projeto local

```bash
git fetch origin

git log HEAD..origin/main --oneline

git pull origin main
```

## 146. Nova alteração local

```bash
git status

git diff

git add .

git commit -m "Descrição da alteração"

git push
```

## 147. Novo computador

```bash
git clone URL_DO_REPOSITORIO

cd NOME_DO_REPOSITORIO

git status

git log --oneline

git remote -v
```

# Parte 29: Encerramento

## 148. O que aprendemos

Nesta aula, eu mostrei que o Git e o GitHub trabalham juntos, mas possuem funções diferentes.

O Git registra a evolução do projeto.

O GitHub hospeda e compartilha o repositório.

Aprendemos que:

```text
push envia commits.

fetch busca informações.

pull busca e integra alterações.

clone cria uma cópia local completa.

origin identifica o repositório remoto principal.
```

Também aprendemos que sincronizar um projeto exige atenção.

Antes de começar uma atividade, eu verifico se existem alterações remotas.

Depois de terminar, eu registro meus commits e os envio.

## 149. Frase de encerramento

Um repositório remoto não é apenas uma cópia de segurança.

Ele é um ponto de encontro entre o histórico do projeto, o trabalho dos desenvolvedores e as próximas etapas da equipe.

Quando entendemos o caminho entre local e remoto, deixamos de utilizar comandos por tentativa e começamos a controlar conscientemente a evolução do projeto.

# Referências

1. Documentação oficial do GitHub sobre repositórios remotos  
   https://docs.github.com/pt/get-started/git-basics/about-remote-repositories

2. Documentação oficial do GitHub sobre envio de commits  
   https://docs.github.com/pt/get-started/using-git/pushing-commits-to-a-remote-repository

3. Documentação oficial do Git sobre push  
   https://git-scm.com/docs/git-push/pt_BR

4. Documentação oficial do GitHub sobre obtenção de alterações remotas  
   https://docs.github.com/pt/get-started/using-git/getting-changes-from-a-remote-repository

5. Documentação oficial do GitHub sobre clone  
   https://docs.github.com/pt/repositories/creating-and-managing-repositories/cloning-a-repository

6. Documentação oficial do GitHub sobre arquivos ignorados  
   https://docs.github.com/pt/get-started/git-basics/ignoring-files

7. Documentação oficial do GitHub sobre README  
   https://docs.github.com/pt/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes

8. Documentação oficial do GitHub sobre autenticação  
   https://docs.github.com/pt/authentication/keeping-your-account-and-data-secure/about-authentication-to-github

9. Documentação oficial do GitHub sobre SSH  
   https://docs.github.com/pt/authentication/connecting-to-github-with-ssh/about-ssh

10. Documentação oficial do GitHub sobre licenças  
    https://docs.github.com/pt/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/licensing-a-repository
