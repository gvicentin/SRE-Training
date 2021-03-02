# Linux Basics

![rm -rf](https://media.giphy.com/media/HCkbgKLdLWq3OCV8YM/giphy.gif)

## Man Pages

O `man` é o manual dos sistemas linux onde é possível encontrar todas as informações necessárias para a utilização dos programas, funções ou utilitários. Para usar o comando basta passar a página de interesse, por exemplo `man cd` para mostrar o manual do comando `cd - change directory`. **Este é comando mais importante para iniciantes!!**


## Trabalhando com arquivos e diretórios

### Principais comandos
* **pwd** - Retorna o diretório atual.
* **ls** - Lista o conteúdo do diretório especificado.
* **echo** - Imprime uma linha de texto.
* **cat** - Concatena arquivos e apresenta o resultado na saída padrão.
* **clear** - Limpa o console.
* **cd** - Muda de diretório.
* **mkdir** - Cria novo diretório.
* **rmdir** - Remove um diretório vazio.
* **rm** - Remove arquivos ou diretórios.
* **cp** - Copia um arquivo.
* **mv** - Move um arquivo.
* **touch** - Atualiza a data de última alteração. Usado também para criar arquivos. 

### Redirecionamento

Usamos comandos de redirecionamento para usar a saída de um programa em outro.

```bash
# <
# Para usar o conteúdo de um arquivo como entrada.
./prog1 < file.in

# >
# Usado para jogar a saída de um programa em um arquivo ao invés do stdout.
./prog2 > file.out

# >>
# Adiciona o conteúdo de saída no fim do arquivo.
echo "Appending..." >> file.out

# |
# Comando Pipe, usa a saída de um programa como entrada de outro.
ps -e | grep chorme
```

### Caracteres coringas

Os caracteres coringas são utilizados para selecionar arquivos por apenas parte do nome.

```bash
# *
# Substitui um ou mais caracteres.
# Listando os arquivos que começam com doc.
ls doc* 

# ?
# Substitui um único caracter.
# Impoimindo os arquivos que começem com file e tenham dois caracteres em seguida.
cat file??

# {text1, text2, ... text3}
# Substitui por cada valor do conjunto.
# Rodando programa com test_a, test_b, test_c
./prog < test_{a, b, c}
```

### Compactando/Descompactando

No linux a principal forma de agrupar multiplos arquivos é através do formato `tar`, Esse formato é apenas um agrupamento de arquivos e utilizamos ele em conjuntos com outros algoritmos de compactação como o `gzip`.

* **zip** - Junta e compacta arquivos.
* **unzip** - Lista arquivos dentro de .zip e permite extraílos.
* **tar** - Faz o arquivamento de arquivos em um único. Também pode trabalhar com compressões.

### Visualização de arquivos

Além do comando `cat` podemos visualizar o conteúdo dos arquivos diretamente do terminal com os seguintes comandos:
```bash
# Mostra o começo do arquivo, é possível especificar o número de linhhas.
head file.txt

# O mesmo que 'head' para o fim do arquivo.
tail file.txt

# Programa para visualizar arquivos maiores e poder navegar dentro dele.
less file.txt
```

## Processos

Um processo é uma instância de um programa que está executando.
```bash
# Listar os processos
ps
top
pstree

# Terminar processos
kill
killall
```

### Jobs

Um **job** é um processo inicializado a partir daquele terminal.
```bash
# Listar os jobs
jobs

# Colocar um job em backgorund / foreground
bg [job]
fg [job]

# Para inicializar um job em background usamos o &
./program &
```


## Material Complementar

[Linux I: Conhecendo e utilizando o terminal](https://cursos.alura.com.br/course/linux-ubuntu)

[Linux II: Programas, processos e pacotes](https://cursos.alura.com.br/course/linux-ubuntu-processos)

[Some basic commands](https://maker.pro/linux/tutorial/basic-linux-commands-for-beginners)

[grep command](https://ostechnix.com/the-grep-command-tutorial-with-examples-for-beginners/)