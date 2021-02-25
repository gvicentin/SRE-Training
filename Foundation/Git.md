# Git - Guia de estudo :pencil:

![Git gif](https://media.giphy.com/media/kH6CqYiquZawmU1HI6/giphy.gif)

O Git é um `version control system (VCS)` bastante popular que permite manter o controle das alterações em arquivos. É bastante usado para coordenar o trabalho coletivo entre desenvolvedores.


## Instalação

O guia de instalação do git para todos os sistemas operacionais pode ser encontrado [aqui](https://git-scm.com/downloads).


## Setup

### Configurações

Após instalar o git na máquina é possível alterar algumas configurações de preferências. Existem dois níveis de configuração, o **global** que irá permitir que todos os repositórios compartilhem tais configurações, o arquivo que contém tais configs fica em `~/.gitconfig`, e o **local** que é único para cada repositorio e fica em `.git/config`. *As preferências locais podem sobreescrever as globais.*

Para listar as preferências atuais, podemos usar o comando:
```
git config -l
```

Para adicionar ou modificar uma configuração podemos fazer como no exemplo abaixo, para fazer a configuração ser global adicionamos o `--global`. Podemos adicionar um *nome* e um *email* as preferências para ser mostrado junto aos commits que fizermos.
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

Existem diversas plataformas para hospedagem de código utilizando o git como sistema de controle de versionamento, como por exemplo o [GitHub](https:://github.com) e o [Bitbucket](https://bitbucket.org). Depois de criar uma conta em uma dessas plataformas é possível hospedar seus projetos e trabalhar em colaboração com outros desenvolvedores.


### Setup SSH keys

Ao configurar a chave SSH, você cria um par de chaves que contém uma **chave privada** (salva em seu computador local) e uma **chave pública** (carregada no host de repositórios remotos). O host usa o par de chaves para autenticar qualquer coisa que a conta associada possa acessar. Este mecanismo bidirecional evita ataques man-in-the-middle. Veja como gerar e configurar as chaves nos hosts GitHub e Bitbucket.

* [Bitbucket - Set up an SSH key](https://confluence.atlassian.com/bitbucket/set-up-an-ssh-key-728138079.html)

* [GitHub - Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)


## Trabalhando com repositórios (Básico)

**Material de referência:**: [Apêndice sobre Git - Eng. de Software Moderna (Livro Digital)](https://engsoftmoderna.info/capAp.html)


## Materiais para se aprofundar



