# Containers

![Conainers](https://media.giphy.com/media/cUMNWzWZ5n75LvcCIe/giphy.gif)

Os containers nos ajudam a resolver o problema de rodar uma aplicação em diferentes ambientes, o que poderia causar comportamentos inesperados. Ao contrário das máquinas virtuais, os containers não precisam de um sistema operacional próprio, o que os tornam mais leves e simples de configurar.


## Docker

O **Docker** é uma plataforma que possui todas as ferramentas para trabalharmos com os containers.


### Imagem 

Uma imagem contém todas as informações necessárias para rodar um container, o que inclui codigo, bibliotecas, variáveis de ambiente, etc. Os `Dockerfile` são usados para especificar as images.

```Dockerfile
FROM node:latest
WORKDIR /app
COPY . .
RUN pip3 -r requirements.txt
CMD ["python3", "app.py"]
```


### Container

Um container é a instância de uma image. Para cada imagem mais de um container pode ser instanciado em diferentes máquinas usando o Docker.

![Docker](https://www.docker.com/sites/default/files/d8/2018-11/docker-containerized-appliction-blue-border_2.png)


### Principais comandos

* **images**: Lista de images que temos no host.
* **search**: Busca por imagem.
* **pull**: Baixar imagem do Hub.
* **run**: Cria um container a partir de uma imagem.
* **ps**: Lista os containers ativos. `-a` para listar os parados também.
* **stats**: Lista status do container.
* **inspect**: Mostra informações úteis sobre containers ou imagens.
* **rmi**: Remover imagem.
* **exec**: Executar comando sem precisar startar o console deles.


### Volumes

Os containers são voláteis e perdem o conteúdo salvo após o encerramento. Precisamos usar volumes para persistir os dados, tais volumes ficam salvos no Host e não no container.
```
docker run -v "[CAMINHO_VOLUME_LOCAL]:[CAMINHO_VOLUME_CONTAINER]" image
``` 


## Materiais Complementares

[Docker — Beginner’s Guide — Part 1: Images & Containers](https://medium.com/codingthesmartway-com-blog/docker-beginners-guide-part-1-images-containers-6f3507fffc98)

[Docker — Beginner’s Guide — Part 2: Services](https://medium.com/codingthesmartway-com-blog/docker-beginners-guide-part-2-services-eb49117b4241)

[Docker: Criando containers sem dor de cabeça](https://www.alura.com.br/curso-online-docker-e-docker-compose)

[Docker for Web Developers](https://www.pluralsight.com/courses/docker-web-development)
