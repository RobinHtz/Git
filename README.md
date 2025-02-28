Arquivo para revisão do funcionamento do git e seus comandos básicos.

# Git

 **Git** é um sistema de controle de versões distribuído usado para rastrear alterações em arquivos ao longo do tempo. Ele permite que desenvolvedores trabalhem em projetos colaborativamente, mantendo um histórico completo de modificações.

- **GitHub** é uma plataforma que hospeda o Git na nuvem.

Git foi desenvolvido pelo **Linus Torvalds**, criador do Linux, para o controle do kernel do linux.

Uma grande vantagem do git é a possibilidade de muitas pessoas trabalhar em um mesmo projeto com diversas facilidades por conta de seu versionamento.

## Cada projeto no git é dividido em três estágios: 

**1- Working Directory** > A pasta local do projeto, onde você edita arquivos.

    git add

**2- Staging Area** > Sala de espera onde é selecionado quais alterações do Working Directory serão incluídas no próximo commit.

	git commit

**3- Git Directory** > Repositório local do projeto.

[Documentação do git](https://git-scm.com/docs/git)

*Git Bach* é o terminal do git para o Windows. Para novos usuários é preciso configurar o git:

    $ git config --global user.name "nome"

    $ git config --global user.email "email"

------------------------------------------------------------------------
## Comandos Básicos do Git Bach.

    $ cd NomeDaPasta > Para entrar em uma pasta com o git.

    $ cd .. > Para voltar para a pasta anterior.

    $ clear > Limpar a tela do Git Bach.

    $ git init > Cria um repositório na pasta local.

    $ git status > Apresenta como está o repositório atualmente.

    $ git add NomeDoArquivo (ou * para adicionar todos os arquivos) > Serve para adicionar os arquivos no Staging Area.

    $ git commit -m "mensagem do commit" > Para mandar os arquivos do Staging Area para o Git Directory/repositório principal com uma mensagem.

.gitignore é um arquivo que dentro dele há o nome dos arquivos e pastas que não queremos que passe para o commit. Lembrando que as pastas terão uma / após seu nome no gitignore.

------------------------------------------------------------------------

## Comandos sobre diferenças nos repositórios.

    $ git diff > Mostra o que alterou em arquivos locais antes do git add.

    $ git diff --staged > Mostra as alterações dos arquivos na Staging Area.

    $ git log > Mostra o histórico de todos os commits.
    - Aqui mostra as chaves de commits para voltar a essas versões.

    $ git log -p > Mostra todos os commits e as diferenças de todos os commits.
    - Apertar letra Q para voltar ao normal.
 
    $ git log -p -1 > Mostra o último commit que foi feito, alterar o número por n número mostra n quantidades de n commits feitos.
    - Contra intuitivo usar esses comandos em cmd, mais fácil ver o visualizador de relatório usando o comando gitk no git bach.

    $ git log --pretty=oneline > Verificação do histórico de commits de maneira limpa visualmente.

------------------------------------------------------------------------

## Comandos para reverter mudanças no repositório principal.

    $ git commit --amend -m "mensagem" > Resulta em uma edição do último commit com novas adições.

    $ git restore --staged NomeDoArquivo > Para remover um arquivo anteriormente adicionado ao Staged.

    $ git checkout -- NomeDoArquivo > Desfaz as alterações de um único arquivo.

    $ git rm NomeDoArquivo > Remove o arquivo do repositório principal.
    
------------------------------------------------------------------------

## Comandos de Tag e Branch

Tags(ponteiros) no git geralmente são usadas para marcar as diferentes versões do projeto, facilitando as consultas e as trocas de versão. 

    $ git tag -a NomeTagNova -m "Mensagem" > Cria uma tag com nome utilizando a versão atual do projeto.

    $ git tag  > Retorna as tags existentes.

    $ git tag -a v0.0 TagAntiga -m "Mensagem" > Para criar tag em uma versão antiga.

    $ git show NomeTag > Mostra detalhes e o histórico da tag selecionada.

    $ git checkout NomeTag > Muda os arquivos do projeto atual para os arquivos da versão escolhida. Muda o Working Directory para a tag escolhida.

    $ git tag -d NomeTag > Deleta uma tag específica.


Branchs são ramificações dentro do controle de versão, as branchs permitem commits em segmentações diferentes do projeto.

> O branch padrão é chamado main.
> Praticamente as branchs funcionam como cópias do projeto principal permitindo testes sem perca de dados.

    $ git checkout main > Muda para a versão principal.

    $ git branch NomeBranch > Cria uma nova branch no projeto.

    $ git checkout  NomeBranch > Transfere os arquivos atuais para a branch escolhida.

    $ git checkout -b NomeBranch > Cria uma nova branch e transfere arquivos atuais para essa branch, além de mudar o Working Directory para a branch nova.

    $ git merge NomeBranch > Faz uma mescla dos arquivos da branch escolhida para a branch atual.

    $ git branch -d teste > Deleta uma branch.

- Conflitos que impedem o merge precisam de correção manual no arquivo.

------------------------------------------------------------------------


## Git em rede local

  

    $ git init --bare > Para iniciar um repositório que será disponibilizado para outros computadores na rede local.

  

- O primeiro acesso a esse repositório deve clonar o repositório para fazer a base do projeto.

  

    $ git clone file:////local nome > Clonagem do projeto para máquina local.

  

    $ git remote > Retorna o nome do servidor remoto.

  

    $ git push NomeRemote main > Para enviar o commit para o servidor remoto.

  

    $ git pull NomeRemote main > Traz os arquivos do servidor para o computador utilizado, mas fazendo um merge com os arquivos locais.

  

    $ git fetch NomeRemote NomeBranch > Traz os arquivos do servidor para a branch selecionada.

  

------------------------------------------------------------------------

  

## Github em conjunto com git

  

    $ ssh-keygen > Chave necessária para conectar o git com github.

  

- Para usar um repositório criado no github em um pc local, precisa fazer clone do repositório no computador:

  

    $ git clone ChaveRepositórioGithub NomePasta