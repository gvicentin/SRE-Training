# Shell Script

Shell scripts são utilizados para automatizar os processos do shell, agrupando um conjunto de comandos que normalmente usamos manualmente no terminal comum e adicionando outros elementes como condicionais e funções para tornar as operações mais genéricas e conseguir criar programas para realizar o trabalho repetitivo de um administrador de sistemas. Para criarmos um **Shell Script** basta inserir a seguinte linha no começo de um arquivo, especificando qual shell será utilizado. Temos algumas opções de shell como o `sh` e o `bash` que são os mais utilizados por questão de compatibilidade, o `sh` sempre estará presente porém o `bash` é mais completo.
```
#!bin/bash
```

## Executando um script
Para executarmos um script precisamos ter permissão de execução para tal arquivo e a partir disso podemos executá-lo como qualquer outro programa.
```bash
# Concedendo permissão de execução
chmod +x script.sh
# Executando o script
./script
```

Para acessar o script globalmente pelo terminal podemos colocá-lo em alguma pasta especificada pelo `$PATH`. Por exemplo, podemos criar uma pasta de executáveis para aquele usuário em `$HOME/bin` ou `$HOME/.local/bin`. Se quisermos que o script seja acessado por qualquer usuário podemos utilizar algum caminho da pasta `/usr` (Universal System Resources).


## Comentários

Para inserirmos comentários nos scripts basta adicionar um `#` no começo da linha e o conteúdo que vier após será ignorado pelo interpretador.
```bash
#!bin/bash

# Meu Script
```


## Variáveis

No shell uma variável é um label que armazena um valor para ser utilizado posteriormente sem precisar de repetição.

```bash
#!bin/bash

# Criando e utilizando uma variável
NOME=João da Silva
echo "Bom dia, $NOME."

# Atribuindo o resultado de um comando
SYS_INFO=$(df -h)
SYS_INFO=`df -h`    # mesmo resultado
```


## Condicionais

```bash
# Sintaxe do if
if [ CONDIÇÃO ]; then
    AÇÃO
fi

# Sintaxe do if/else
if [ CONDIÇÃO ]; 
    then
        AÇÃO
    else
        OUTRA AÇÃO
fi
```

**Principais parâmetros para testagem:**

* *n string*: comprimento de string != 0.
* *z string*: comprimento de string == 0.
* *string1 = string2*: strings identicas.
* *string1 != string2*: strings diferentes.
* *eq, ne, gt, ge, lt, le*: equals, not equals, greater than, greater equals, assim por diante (teste de valores inteiros).
* *e nome_arq*: verifica se arquivo existe
* *d nome_arq*: verifica se é diretório


## Argumentos

Podemos acessar argumentos passados para um script da seguinte forma:
* `$0`: nome do script.
* `$1 ... $n`: argumento em ordem.
* `$#`: número de argumentos que foram passados.
* `$* ou $@`: representa todos os argumentos.


## Material Complementar

[Shell Scripting parte 1: Começando seus scripts de automação de tarefas](https://www.alura.com.br/curso-online-shellscripting/)