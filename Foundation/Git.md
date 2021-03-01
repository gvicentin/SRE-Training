# Git - Guia de estudo :pencil:

![Git gif](https://media.giphy.com/media/kH6CqYiquZawmU1HI6/giphy.gif)

O Git é um `version control system (VCS)` bastante popular que permite manter o controle das alterações em arquivos. É bastante usado para coordenar o trabalho coletivo entre desenvolvedores.


## Instalação

O guia de instalação do git para todos os sistemas operacionais pode ser encontrado [aqui](https://git-scm.com/downloads).


## Setup

### Configurações

Após instalar o git na máquina é possível alterar algumas configurações de preferências. Existem dois níveis de configuração, o **global** que irá permitir que todos os repositórios compartilhem tais preferências. O arquivo que contém tais configs fica em `~/.gitconfig`. Além desse nível temos o **local** que é único para cada repositorio e fica em `.git/config`. *As preferências locais podem sobreescrever as globais.*

Para listar as preferências atuais, podemos usar o comando:
```
git config -l
```

Para adicionar ou modificar uma configuração podemos fazer como no exemplo abaixo, para fazer a configuração ser global adicionamos o `--global`. Podemos adicionar um *nome* e um *email* as preferências para serem mostrados junto aos commits que fizermos.
```
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

### Alias

Uma configuração comumente utilizada é fornecer **formas mais curtas de executar um comando mais complexo**. Podemos realizar isso definindo alguns *alias*, como por exemplo, podemos executar o comando `checkout` apenas usando `co` ou transformar um comando com parâmetros como `status -sb` em apenas `st`.
```
git config --global alias.co checkout
git config --global alias.st 'status -sb'
```

### Plataformas

Existem diversas plataformas para hospedagem de código utilizando o git como sistema de controle de versionamento, como por exemplo o [GitHub](https://github.com) e o [Bitbucket](https://bitbucket.org). Depois de criar uma conta em uma dessas plataformas é possível hospedar seus projetos e trabalhar em colaboração com outros desenvolvedores.


### Setup SSH keys

Ao configurar a chave SSH, você cria um par de chaves que contém uma **chave privada** (salva em seu computador local) e uma **chave pública** (carregada no host de repositórios remotos). O host usa o par de chaves para autenticar qualquer coisa que a conta associada possa acessar. Este mecanismo bidirecional evita ataques man-in-the-middle. Veja como gerar e configurar as chaves nos hosts GitHub e Bitbucket.

* [Bitbucket - Set up an SSH key](https://confluence.atlassian.com/bitbucket/set-up-an-ssh-key-728138079.html)

* [GitHub - Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)


## Trabalhando com repositórios

**Material de referência:**: [Apêndice sobre Git - Eng. de Software Moderna (Livro Digital)](https://engsoftmoderna.info/capAp.html)

*Este é um resumo do conteúdo apresentado no material de referência, recomendo a leitura do artigo completo e esse guia como referência rápida nos tópicos principais.*

### Começando

Para iniciar um novo repositório vazío utilizamos o comando `init`
```
git init
```

Para criar um repositorio que já existe em algum host, utilizaremos o `clone` que irá iniciar um repositório git e copiará os commits do repositório remoto.
```
git clone https://github.com/NOME-USER/NOME-REPO
``` 

### Add and Commit

Após fazer alterações nos arquivos podemos fazer um `add` neles, o que fará com essas mudançam fiquem em uma área intermediária chamada de **index** ou **stage**, a partir de onde tais mudanças possam ser rastreadas (**tracked**). Depois de adicionado as mudanças, elas ainda não estão no repositório local. Para salvar tais mudanças que estão no index para o repo local fazemos um `commit`.
```
git add README.md
git commit -m "Adicionando um readme ao projeto"
```

### Status, Diff & Log

* `status` permite visualizar as diferenças entre o repositório local (*HEAD commit*), a área de *index* e a *working_tree*.
* `diff` mostra as diferenças entre *commits*, ou entre *commit* e *working tree*.
* `log` lista os *commits*.

### Push & Pull

O comando `push` permite enviar os commits de um repositório local para um repositório remoto. Enquanto o `pull` faz o processo reverso, ele atualiza seu repo local a partir do repo remoto.
```
git pull
# --
git push origin main
```

### Conflitos de Merge

Os conflitos acontecem quando dois desenvolvedores alteram o mesmo trecho de código ao mesmo tempo. Quando o segundo desenvolvedor for executar um `push` receberá um erro pois aquele conteúdo que ele está alterando também foi modificado pelo primeiro dev. Esse segundo deve então realizar um `pull` para trazer o conteúdo do repositório remoto, corrigir o conflito e em seguida realizar um `commit` e `push`. O conflito pode ser resolvido mantendo o trecho de código que deverá permancer nos arquivos conflitantes e removendo os trechos que não deverão permanecer (os marcadores criados automaticamente pelo git também precisam ser removidos).


## Materiais complementares

[Understanding Git (part 1) — Explain it Like I’m Five](https://hackernoon.com/understanding-git-fcffd87c15a3)

[Understanding Git (part 2) — Contributing to a Team](https://hackernoon.com/understanding-git-2-81feb12b8b26)

[Git Fundamentals](https://www.pluralsight.com/courses/git-fundamentals)

[Git e Github: Controle e compartilhe seu código](https://www.alura.com.br/curso-online-git-github-controle-de-versao)

