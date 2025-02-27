Arquivo para revisão do funcionamento do git e seus comandos básicos.

# Git

 **Git** é um sistema de controle de versões distribuído usado para rastrear alterações em arquivos ao longo do tempo. Ele permite que desenvolvedores trabalhem em projetos colaborativamente, mantendo um histórico completo de modificações.

- **GitHub** é uma plataforma que hospeda o Git.

Git foi desenvolvido pelo **Linus Torvalds**, criador do Linux, para o controle do kernel do linux.

Uma grande vantagem do git é a possibilidade de muitas pessoas trabalhar em um mesmo projeto com diversas facilidades por conta de seu versionamento.

## Cada projeto no git é dividido em três estágios: 

**1- Working Directory** > Diretório onde se está trabalhando no próprio computador.

    git add

**2- Staging Area** > Sala de espera onde os arquivos modificados ficam antes de ser enviado ao repositório.

	git commit

**3- Git Directory** > Repositório principal do projeto.

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

    $ git rm NomeDoArquivo > Remove o arquivo do repositório principal.

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

------------------------------------------------------------------------
## Comandos para reverter mudanças no repositório principal.

    $ git commit --amend -m "mensagem" > Resulta em uma edição do último commit com novas adições.

    $ git restore --staged NomeDoArquivo > Para remover um arquivo anteriormente adicionado ao Staged.

    $ git checkout -- NomeDoArquivo > Desfaz as alterações de um único arquivo.

    $ git rm NomeDoArquivo > Remove o arquivo do repositório principal.
