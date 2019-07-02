# Comandos básicos Git e Github
###### 27/06/2019 - sergio a.

------

## Configurando o git

### * Como fazer download do Git?
    No site do próprio Git! 
[Git - Download](https://git-scm.com/downloads)

### * Como configurar o git?
    Para configurar o git de forma global (ou seja, independente do projeto ou branch no qual você esteja trabalhando), com informações como seu nome de usuário, e-mail e editor de texto padrão, basta seguir os seguintes comandos:

* git config --global user.name "seu_nome" 
* git config --global user.email "seu_email"
* git config --global core.editor "__" (utilize code para visual estudio / su para sublime / vi para vim)

### * Como ver minhas informações?
    Para ver todas as informações do seu arquivo .git em particular, basta usar o comando:

* git config --list

------

## Pondo a mão na massa

### * Como iniciar um novo repositório?
    Para iniciar um novo repositório, basta seguir os seguintes passos:

* Primeiro, adentre o local desejado utilizando o comando "cd" do bash. Ele permite que você entre em diretórios, como pastas e a própria area de trabalho. Ex: cd desktop (para entrar em sua área de trabalho)

* Caso você ainda não possua uma pasta criada, poderá utilizar o comando "mkdir" do bash. Ele permitirá a criação de um novo diretório. Ex: mkdir pasta_git (para criar uma pasta chamada pasta_git)

* Entre em sua nova pasta criada utilizando novamente o comando "cd" do bash. Ex: cd pasta_git

* Agora que já estamos dentro da nova pasta criada, basta utilizar o comando "git init".


###### O "git init" criará um novo repositório dentro de sua pasta. Ele ficará a partir de agora, escutando novas mudanças nos arquivos e mundando seus ciclos de vida 

---------

### * Como observar o status do meu repositório?
    Para isso, utilizar o seguinte comando:

* Git status
###### O git status retornará o status do seu repositório em geral. É sempre importante dar vários git status quando se está aprendendo a mexer com git, pois assim, você observa bem o ciclo de vida dos arquivos, e não se perde.

---------

### * Como adicionar arquivos 
    Quando adicionar novos arquivos em seu repositório, utilizar o seguinte comando para que os arquivos possam ser vistos pelo git:

* git add "nome_do_arquivo" 
###### Quando é dado o add, o git já enxerga o arquivo e permite que o mesmo possa ser commitado (estágio staged). Após modificações no arquivo, é importante dar o git add, pois as modificações precisam entrar no arquivo.

--------

### * Como commitar um arquivo?
    Para commitar um novo arquivo, se usa o seguinte comando:

* git commit -m  "mensagem"
###### O "-m" significa que você passará uma mensagem juntamente com o commit. É uma ótima prática por na mensagem em si o que você de fato fez na versão, pois outras pessoas verão a mensagem. Ex: "arrumei o bug tal" ou "Adicionei nova funcionalidade em tal parte do projeto"

---------

### * Como ver quais foram os últimos commits e alterações no meu projeto?
    Para isso, existe o git log. O git log guarda a sequência de commits do projeto, juntamente com sua data, seu autor e seu hash (o número do commit). O git log é o seu amigo. Use-o sempre.

* git log 

###### Algumas outras formas de declarar o git log são:

* git log --decorate
    * o git log --decorate demonstra algumas informações adicionais, como: se houve mudança de branches, se houve algum merge, se alguma tag foi gerada...                


* git log --author = "nome_do_autor"
    * é uma forma de pegar todas os commits feitos pelo autor que você passar como parâmetro.
    * Uma variação do git log --author seria o comando git --shortlog.
        * O shortlog mostra, em ordem alfabética, quais foram as pessoas que commitaram no projeto, quantos commits fez, e seus respectivos comentários
            * Shotlog -sn filtra ainda mais, e mostra somente o numero de commits e o nome do indivíduo

* git log --graph
    * Mostra, de forma gráfca, quais mudanças entre branches ocorreram

----------

### * Para que serve a hash de cada commit?
    a hash de cada commit é única, e serve para identificá-la. Utilizando o comando a seguir, você pode, por exemplo, ver informações importantes acerca da mesma.

* git show hash (substitua "hash" pela hash do seu commit)

--------

### * Como ver as alterações antes mesmo de enviá-las (realizar commit)?
    Utilizando o Git diff! Ele permite que você observe as alterações feitas no seu arquivo antes mesmo de realizar commit

* Git diff

* Git diff --name-only 
    * essa forma de declarar o git diff retornará, como a sintaxe induz, apenas o nome dos arquivos modificados
###### sempre use o git diff; ele é crucialmente importante. Sempre, antes de realizar um commit, utilize-o e dê uma última olhada em suas modificações, apra não mandar nada errado para o ar. Vale lembrar que após dar o "git add", o "git diff" não conseguirá mais achar as mudanças feitas no arquivo. Portanto, utilizá-lo antes do "git add".

-------

### * Como desfazer coisas?
    Para dar um "ctrl z" no arquivo, basta usar o seguinte comando: 

* Git checkout "nome_do_arquivo"
###### O git checkout retornará o arquivo para antes da edição

------

### * Como tirar meu arquivo do staged?
    Caso você tenha dado um "git add" em um arquivo, mas se arrependeu, basta utilizar o seguinte comando para reverter.

* Git reset HEAD "nome_do_arquivo"

-----

### * Como enviar meus arquivos da minha máquina pro GitHub e afins?
    Basta seguir o passo "ligando tutorial local a um remoto",(caso ainda não tenha feito a ligação) e usar o seguinte comando:

* Git push origin master 

-------

### * Como clonar um repositório remoto em um local?
    Caso você queira pegar tudo que está na nuvem e clonar para o repositório local, para usá-lo em sua máquina, basta adentrar em seu repositório local de preferência (ex: pasta), e usar o seguinte comando:

* git clone "link_fornecido_pela_plataforma"

-------

### * Como realizar fork de um projeto?
    O fork é, em um modo bem grosso, copiar um repositório já existente de uma outra pessoa (ou até seu mesmo), e trabalhar nele. Após concluir o trabalho, você envia um request falando quais mudanças você fez para o dono do repositório.

* Essa é uma funcionalidade que você escolhe no próprio GitHub, quando acessa um repositório alheio

###### Qual a diferença do fork para o clone? O clone é basicamente você baixar arquivos que são seus do seu repositório. O fork é baixar de repositórios alheios. Você pode fazer o clone em um repositório alheio, mas não vai conseguir enviar as modificações quando as acabar, já que o repositório não te pertence.

-------

### * Como criar um novo branch?
  Para criar um novo branch, ou seja, uma linha de desenvolvimento paralela à o projeto principal, basta usar o seguinte comando:
  
* git checkout -b "nome_do_branch"

### * Como alternar entre branches?
    Para alternar entre diferentes branches, basta usar o seguinte comando, seguido do branch para qual você quer ir:
    
* git checkout "nome_do_branch"
###### para retornar para o branch padrão, basta trocar "nome_do_branch" por "master"

### * Como deletar um branch?
    Para deletar branches, basta usar o seguinte comando, seguido do branch que você deseja deletar:
    
* git branch -d "branch_a_ser_deletado"

##### Um branch é, até então apenas visivél para o seu criador. Para mandá-lo para o ar, basta utilizar o seguinte comando: 

* git push origin <branch>
 
-------

### * Como atualizar o meu repositório para o mais novo commit feito?

* git pull

-------

### * Como ver quais são os branches disponíveis em meu projeto?

* git branch

-------

### * Como realizar merge de um branch?
    Para inserir o branch à sua linha de desenvolvimento padrão, basta utilizar o seguinte comando:
    
* git merge "branch"

-------

### * Como guardar informações que você ainda não quer subir?
    Para realizar essa ação, "escondendo" o arquivo do git, pra que ele não seja commitado, basta usar o seguinte comando. Os arquivos são adicionados em "WIP" - work in progress

* git stash 

##### * Para reverter essa situação:
    assim, os arquivos guardados serão trazidos de volta para seu workspace, e tirados do WIP

* git stash apply

##### * Para listar todos os meus arquivos em stash:

* git stash list
-------

### * Como adicionar uma tag?
     Tags são muito importantes quando trabalhando em um sistema grande, pois nos ajudam no controle de versões. 

* git tag -a "número_arbitrário_ex: 1.0.0" -m "comentário_sobre_a_tag"

###### A tag será adicionada no último commit feito. Se desejar adicionar uma tag a um commit específico, basta adicionar o id do commit (você consegue esse id olhando no git log) após o número arbitrário

-------

### * Como subir uma tag?

* git push origin master --tags 

###### Para ver todos as tags, basta usar:

* git tag

--------

### * Como apagar tags e branches de repositórios remotos?
    Para apagar localmente, um git checkout -d basta. Mas e em um repositório remoto?
    
* git push origin :número_da_tag_ou_nome_do_branch
-------

### * Git revert
    Digamos que você subiu uma nova função para seu projeto e essa versão quebrou. Você não quer dar um reset e perder tudo o que fez, já que quer estudar o erro mais tarde. O que usar? Git revert!
    
* git revert "log_do_commit"

###### O git revert vai apagar o que você fez, voltando para um commit anterior. Porém, ele não vai apagar o commit que você subiu e deu erro. Portanto, você pode passar isso para um novo branch e estudar sobre mais tarde 

--------
### * Tipos de reset

* git reset --soft
    * O commit é apagado, e o arquivo volta para staged, ainda com as modificações incluidas nele, pronto para um novo commit

* git reset --mixed
    * O commit é apagado, e o arquivo volta para modified, com as modificações ainda recentes.

* git reset --hard
    * O commit é apagado, assim como todas as suas modificações (desde o último commit).

--------

### Ligando repositório local a um remoto
    Para ligar o seu repositório local a um remoto (como github, bitbucket...), basta seguir os passos a seguir:

* Crie um novo repositório, caso ainda não tenha um
    * Caso não saiba como fazer, seguir os passos que estão no começo desse tutorial
* Crie um repositório remoto 
* Utilize o comando: 'git remote add origin "link_que_a_plataforma_fornecerá.git"'
    * Após isso, caso você digite "git remote", ele mostrará que já existe uma ligação criada chamada "origin"
    * Caso você digite "git remote -v", ele dará mais informações, como qual o link do repositório remoto no qual você está ligado
* git push -u origin master
    * O git push envia tudo que eu tenho no meu repositório local para o meu repositório remoto 
    * O git push informa pra onde vai (origin) e de onde vem (master). 

--------

### Ciclo de vida dos status dos arquivos
    Cada arquivo possui um ciclo de vida dentro do repositório GIT. Entenda:

1. Untracked - "não rastreado" 
    * É quando o arquivo é adicionado no repositório (na pasta em si), mas o git ainda não o reconhece. Quando você o adiciona, ele passa pro próximo estágio:

2. Unmodified - "não modificado"
    * É quando o arquivo já existe no git, mas ainda não foi editado (no caso de um arquivo em branco, que você simplesmente adicionou ao git sem editá-lo)

3. Modified - "modificado"
    * Sempre que fizer uma nova atualização no seu arquivo, o arquivo se encontrará em "modified", ou seja, foi modificado. Portanto, para que ele passe para o próximo estágio, é necessário que o comando git add "nome_do_arquivo" seja dado.

4. Staged - "pronto"
    * Quando o arquivo já está adicionado no git e pronto para receber o commit 

###### Após o commit, os arquivos passam de "staged" para "unmodified". Ou seja, ainda não há alterações desde a última atualização, que foi o próprio commit
##### Utilizando mais o git, você perceberá que o ciclo de vida dos arquivos muda constantemente.

--------

### Termos em geral

* Snapshot - É quando o git tira uma "foto" dos arquivos da maneira em que estão. E, assim, caso haja alterações, ao comparar as "fotos" o git perceberá quais foram
* Commit - é quando você pega os arquivos e avisa ao git "toma, esses arquivos estão prontos. Pode fazer um snapshot dessa versão". Com a snapshot feita, os arquivos estão prontos para serem mandados para o seu repositório de preferência.
* Branch - branches são linhas de desenvolvimento. O branch padrão é o "master", que é o primeiro branch criado quando o projeto é iniciado. Branches a mais são processos em paralelo
* Merge - merge é o ato de unificar um branch que estava, até então, em desenvolvimento paralelo, ao branch master. Tornando-o, agora, parte do branch principal. O merge unifica tudo criando um novo commit. Adiciona em ordem cronológica
* Rebase - Pega todo o branch a ser unificado e o põe na mesma linha de desenvolvimento do master, mas na sua frente.
* .gitignore - é um arquivo que funciona, como seu nome indica, para ignorar. O gitignore ignora alguns tipos de arquivo, para que os mesmos não subam para seu repositório. Você pode configurar o gitignore para ignorar arquivos específicos, ou extensões de arquivo, como .xml e afins.
* Tags - Elas servem, por exemplo, para mostrar em qual fase do desenvolvimento o projeto se encontra (ex: 1.0.0, 1.1.2....)
