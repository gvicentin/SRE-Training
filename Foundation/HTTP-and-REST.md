# HTTP Basics and REST

## HTTP e HTTPS

O HTTP é um protocolo de comunicação, ou seja, um conjunto de regras e especificações que define as normas para comunicação entre um **cliente** e um **servidor** na internet. É o protocolo mais utilizado no mundo Web porém não é o único. A Sigla HTTP vem de **H**yper**T**ext **T**ransfer **P**rotocol o que significa que nesse padrão a informação trafega em formato de texto. O HTTPS adiciona uma camada de criptografia ao HTTP, uma vez que este não apresenta mecanismos para previnir que um intermediário possa ler e alterar os dados.

### URL

Uma URL define um caminho para um recurso na internet, começamos especificando o protocólo usado (por exemplo https://) seguido pelo subdomínio (video) e domínio (www.google.co.uk). Depois temos a porta, que por padrão no HTTP é 80 e no HTTPS é 443 (pode ser omitido). Após esse esquema temos a especificação do recurso (nesse caso /videoplay). O conteúdo que vem após o *?* e está separado por *&* são os parametros passados para aquele recurso. E por fim temos o fragmento, mais relevente a parte frontend que apresentará diferentes informações ao usuário dependendo desse valor.

![URL explained](https://doepud.co.uk/images/blogs/complex_url.png)

### Arquitetura Client-Server

O protocolo HTTP segue o padrão de arquitetura cliente e servidor, o que significa dizer que sempre um cliente sempre inicia a comunicação. Essa comunicação entre o cliente e o servidor se chama **requisição** e deve conter todas as informações para o servidor gerar uma **resposta**. O HTTP é stateless, ou seja, não salva as informações sobre uma requisição para usar em outra. Normalmente os sites utilizam **sessões** que são colocadas em cada requisição para poder guardar as informações sobre o cliente.


## REST

O REST é um padrão arquitetural para comunicação entre aplicações usando o protocolo HTTP. Nesse padrão os recursos são definidos via URI e utilizamos os métodos `GET/POST/PUT/DELETE`. Os cabeçalhos `Accept/Content-Type` são bastante utilizados para especificar as representações `json/XML`.

## cURL

O `curl` é uma ferramenta de linha de comando que permite fazer requisições HTTP direto do terminal. Os principais parametros que podemos especificar são: 
* O método utilizado através do `-X`.
* O header através do `-H`.
* O corpo através do `-d`.
* Incluir os headers de resposta na saída `-i`.

Podemos testar as requisições e encontrar diversos exemplos através [deste site](https://httpbin.org)

```bash
curl -X GET "https://httpbin.org/get?a=123&b=Guilherme+Vicentin" -H "Content-Type: application/json"
curl -X POST "https://httpbin.org/post" -H "Content-Type: application/json" -d '{"a": 123, "b": "Guilherme Vicentin"}' -i
```

## Material complementar

[Fundamentos HTTP](https://www.alura.com.br/curso-online-http-fundamentos/)

[Designing RESTful Web APIs](https://www.pluralsight.com/courses/designing-restful-web-apis)

[REST API concepts and examples](https://www.youtube.com/watch?v=7YcW25PHnAA)

[cURL command](https://www.freecodecamp.org/news/how-to-start-using-curl-and-why-a-hands-on-introduction-ea1c913caaaa/)