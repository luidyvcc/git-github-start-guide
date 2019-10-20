
# Termos/Traduções

pull = puxar

push = empurrar

branch = ramo, setor, ramificação

commit = enviar

  

# Ajuda

Caso queira listar os comando do git, utilize o comando a seguir.
```git
git --help
```
ou
```git
git help
```

Para detalhar um comando específico, no caso, o commit.

    git commit --help

ou

    git help commit

  

# Configurando informações de identificação

Para que outros usuários do projeto saibam quem foi que fez cada alteração (commit) é importante se identificar. Essa identificação é feita apenas uma vez, você pode se identificar somente para o repositório atual ou para o computador inteiro. Na identificação para o computador inteiro, é utilizado o termo --global, caso a configuração seja somente para o repositório atual, basta remover o termo --global (Ex.: git config user.name "Marcos da Silva").

## Nome

    git config --global user.name "Marcos da Silva"

## E-mail

    git config --global user.email "marcosds@gmail.com"

## Editor

Você pode configurar o editor de texto padrão que será utilizado quando o Git precisar que você digite uma mensagem. Por padrão, Git usa o editor padrão do sistema. Caso você queira utilizar um editor diferente, tal como o VS Code, você pode executar o seguinte:

    git config --global core.editor code

## Diff

Outra opção útil que você pode querer configurar é a ferramenta padrão de diff utilizada para resolver conflitos de merge (fusão). Digamos que você queira utilizar o vimdiff.

    git config --global merge.tool vimdiff

## Verificando Configurações

Caso você queira verificar suas configurações, você pode utilizar o comando git config --list para listar todas as configurações que o Git encontrar naquele momento.

    git config --list

Para exibir somente alguma configuração específica, por exemplo, o e-mail, utilize o seguinte comando.

    git config user.email

# Verifica a versão do GIT instalada

    git --version

  

# Transformar um diretório local em um repositório GIT

    git init

  

# Listar arquivos gerenciados pelo GIT

    git ls-files

  

# Exibe estado atual do repositório

    git status

  

# Adicionar arquivos ao gerenciamento local GIT

    git add arquivo01.css arquivo02.html

  

# Gravar alterações no repositório local

    git commit -m 'alteracao na funcao getNome'

  

# Add e Commit em um só comando

Comando somente para modificações de arquivos já existentes, ele add todos arquivos modificados e faz o commit.

    git commit -am “mensagem”

# Desfazer alterações de arquivos que estão em “modified”

    git checkout nomeDoArquivo.html

ou, para desfazer alterações em todos os arquivos:

    git checkout .

# Remover arquivos do “staged” (desfazer git add)

    git reset Head

# Listar Branch local (a branch com * é a que você está atualmente)

    git branch

# Listar Branch remota (a branch com * é a que você está atualmente)

    git branch

# Criar Branch local

    git branch nome_da_branch

# Criar Branch local, ligando-a com a Branch remota

    git branch -t nome_da_branch origin/nome_da_branch

# Criar um branch e mudar para ele ao mesmo tempo

Isso substitui os comandos **git branch nome_da_branch** em seguida de **git checkout nome_da_branch**

    git checkout –b nome_da_branch

# Navegação entre as branch

    git checkout nome_da_branch

# Enviando Branch ao repositório remoto

A utilização do **-u** faz com que os arquivos da Branch local seja sincronizado com a mesma Branch remota.

    git push -u origin nome_da_branch

# Baixando atualizações da branch remota

    git pull

# Lista todos commits da Branch atual

    git log

# Deletando uma Branch local

    git branch –D nome_da_branch

  

# Deletar uma Branch remota

    git push -D origin nome_da_branch
ou

    git push origin :nome_da_branch

# Listar somente as branches remotas do nosso repositório

Uma opção mais completa para o comando abaixo é: **git remote show origin**

    git branch -r

# Lista as Branch's locais e remotas

    git branch –a

# Criar uma Branch local já ligada com a Branch remota e já navegando até ela

    git checkout -t origin/nome_da_branch

# Cria uma Branch e já faz o checkout nela

    git checkout -b nome_da_branch

# Lista todas atualizações que foram realizadas no repositório remoto

    git fetch origin

# Atualizando o repositório local

    git pull

# Atualiza Branch local

    git rebase branch_remota branch_local

Quando estamos no meio do processo de rebase, e houve um conflito que devemos tratar manualmente, como se chama a branch temporária para a qual somos movidos?

A branch (no branch), que dá a entender que você não está em branch nenhuma, é apenas temporária, criada pelo Git para que possamos resolver o conflito.

O objetivo do comando git rebase é fazer com que a branch em que se está tenha um novo HEAD, "copiado" de outra branch. Ou seja, a base da branch, a partir da qual você vai realizar seus commits, deverá ser modificada. Para isso, caso haja commits novos na branch que terá a base trocada, o Git os coloca em um local temporário e em seguida começa a aplicar a nova base. Após a atualização do HEAD, o Git começa a aplicar seus commits sobre a nova base.

# Funções adicionais ao comando git rebase

`--continue` deve ser utilizado após a resolução manual de conflitos;

`--skip` faz com que suas alterações sejam descartadas;

`--abort` volta atrás em todo o processo de rebase

# Atualiza uma branch com os commits de outra branch

Para utilizá-lo, primeiro é preciso ir para a branch para a qual se quer levar os commits, no caso, a "master" (git checkout master). Em seguida, deve-se dizer para o comando **git merge** de qual branch virão os commits novos, que, no caso, é a branch "desenvolvimento". Para isso, basta executar **git merge desenvolvimento**.

# Estratégias de criação de commits

Com diversos commits pequenos, suas alterações ficam mais fáceis de visualizar e têm um histórico mais detalhado. Consequentemente, durante a resolução de conflitos fica mais fácil definir o que cada desenvolvedor quis fazer e decidir qual a abordagem que deve ser adotada. É mais simples também fazer uma reversão de um pequeno trecho, já que cada pequeno pedaço de código está separado em um único commit.
  

# Volta o arquivo ao último estado que está no repositório

Caso tenha baixado uma branch, feito uma alteração indesejada, mas ainda não foi indexado(git add) nem comitado (git commit). Basta executar o seguinte comando:

    git checkout nome_do_arquivo.php

Caso o arquivo tenha sido indexado (git add) recentemente, basta desfazer a última indexação com o seguinte comando:

    git reset HEAD nome_do_arquivo.php

* HEAD: última indexação

  

Caso já tenha sido comitado (git commit), basta desfazer o commit com o seguinte comando:

    git reset tsdt8f6asdf7a6d7a6sdtfa7sd6ft7ds6fta7d6tf

**tsdt8f6asdf7a6d7a6sdtfa7sd6ft7ds6fta7d6tf**: Identificação do comit. pode ser visualizada pelo comando: git log

# Desfazer um commit

tsdt8f...a7d6tf: Identificação do commit. pode ser visualizada pelo comando: git log

    git revert tsdt8f6asdf7a6d7a6sdtfa7sd6ft7ds6fta7d6tf

# Tagging

## Listando Tags

    git tag

## Ver Tag + Commit

    git show

## Deletar tag local e remoto

    git tag -d 12345

    push origin :refs/tags/12345

## Renomear tag local e remoto

### Clone a tag

    git tag nova.tag antiga.tag

### Delete a antiga tag

    git tag -d antiga.tag

### Envie a informação de tag deletada ao repositório remoto

    git push origin :refs/tags/antiga.tag

### Envie a nova tag ao repositório remoto

    git push --tags

## Criando uma tag local

    git tag -a v.01.02 -m “Aula 02 do módulo 01 finalizada”

## Subir Tags para repositório remoto

    git tag origin --tags

# Fonte

git-scm.com/book/pt-br/v2
stackedit.io

