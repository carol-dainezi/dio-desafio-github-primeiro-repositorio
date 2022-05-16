# Anotações e estudos sobre o curso "Introdução ao Git e ao GitHub"

## Comandos básicos da CLI
O Git opera principalmente numa **CLI**, ou **command-line interface** que possui comandos similares aos de SOs com base em Linux/Unix. Alguns comandos existentes são:

 - **ls** - Lista os conteúdos de um diretório.
 - **pwd** - Informa o caminho do diretório atual.
 - **cd** - Muda seu diretório atual para o diretório escolhido. "Change directory".
 - **cd ..** - Retorna um nível no seu diretório atual.
 - **mkdir** - Cria uma pasta.
 - **rm** - Remove um arquivo ou pasta.
 - **cat** - Lê o conteúdo de um arquivo.
 - **echo** - Imprime algo na tela ou imprime o conteúdo para um novo arquivo.

## Comandos específicos ao Git
O Git possui comandos específicos para seu funcionamento, dentre eles:

### Staging, tracking e commit

 - **git init** - Cria um repositório na pasta atual.
 - **git status** - Mostra o status atual dos arquivos do repositório atual.
 - **git add** - Adiciona um arquivo(s) ou pasta(s) ao repositório atual (de untracked/modified para staged). Colocar um * ao invés de um arquivo adiciona todas as mudanças feitas para o repositório atual e as coloca como staged.
 - **git commit -m** - Realiza o commit de todos os arquivos staged para um repositório único. A opção -m "mensagem" imprime uma mensagem personalizada pelo usuário.
 - **git remote add origin github.com:user/repositorio.git** - Cadastra um repositório remoto ao Git com o nome "origin".
 - **git remote -v** - Permite ver uma lista de repositórios remotos cadastrados.
 - **git push origin master** - "Empurra" seu repositório local (branch master) para o repositório remoto especificado, apelidado de origin por convenção.
 - **git pull origin master** - "Puxa" o repositório remoto origin (branch master) para seu repositório local. Pode ser usado para resolver conflitos.

 ### Configurações do Git

 - **git config --list** - Mostra as opções de config do Git, como seu usuário(user.name) e email(user.email).
 - **git config --global user.email "email@@email.com"** - Configura o email padrão para seu Git. De preferência, que seja o mesmo de seu GitHub.
 - **git config --global user.name "username"** - Configura o username padrão para seu Git. De preferência, que seja o mesmo de seu GitHub.
 - **git config --global --unset user.email** - Desconfigura o email de seu perfil global do Git, permitindo a troca do mesmo.
 - **git config --global --unset user.name** - Desconfigura o username do perfil do Git.


## Ciclo de vida de arquivos no Git
Os arquivos no Git podem existir nas seguintes formas:

 - **Untracked** - Não rastreadas pelo Git.
 - **Modified** - O arquivo possui modificações pendentes.
 - **Staged** - O arquivo está pronto para o commit.

## Commit
O **commit** é um processo no qual o Git "faz uma snapshot" das mudanças realizadas no local de trabalho até o momento. Esse commit pode então ser mantido no repositório local e até mesmo lançado para o repositório remoto (no caso, o GitHub).

## SHA-1
**SHA-1 (Secure Hash Algorithm)** é uma função de criptografia que serve para processar informação. No contexto do Git, ele é usado para controlar o versionamento de código, já que a encriptação SHA-1 gera uma string de 40 caracteres completamente única àquele arquivo, especificamente naquele estado específico. Uma simples mudança como apagar uma vírgula gera um SHA-1 totalmente diferente e reverter a mudança retorna o SHA-1 ao seu estado anterior.

## Chave SSH
É um modo de estabelecer uma conexão segura com um servidor remoto, onde um par de chaves únicas são geradas - uma pública e uma privada. Com elas configuradas, a conexão SFTP/SSH para o servidor só é autorizada se a chave privada do usuário for compatível com a chave pública do servidor.

 - **ssh-keygen -t ed25519 -C email@@email.com** - Cria um par de chaves SSH na pasta .ssh/ no local especificado, uma "id_ed25519" e uma "id_ed25519.pub". Elas são, respectivamente, suas chaves privadas e públicas. Para colocar a chave pública no GitHub, ir até Settings > SSH and GPG Keys > New SSH Key e colar o conteúdo do arquivo .pub.*De preferência, usar o mesmo email da sua conta GitHub para o comando.*
 - **eval $(ssh-agent -s)** - Inicia o agente que irá tratar da autenticação das chaves SSH.
 - **ssh-add id_ed25519** - Adiciona sua chave **privada** ao agente. Sempre que necessário, ele irá usar a chave privada pra criptografar/descriptografar arquivos.

 ## Linguagem Markdown

A **linguagem Markdown** é similar à linguagem HTML, porém mais simples. Ela faz uso de uma [sintaxe simples](https://www.markdownguide.org/basic-syntax) para fazer manipular a formatação do texto, sendo muito útil para compartilhar informação em arquivos leves (como em READMEs). Sendo assim, é o formato padrão de arquivos README nos repositórios GitHub, possuindo até mesmo um editor no próprio site.