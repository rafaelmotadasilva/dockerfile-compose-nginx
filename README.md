<h1>
    <img align="center" width="40px" src="./docker-mark-blue.svg" alt="Docker logo">
    <span>Criando um Docker Compose do Nginx</span>
</h1>

Repositório desenvolvido para fins educativos.

## Objetivo

Criar e executar o Docker Compose buildando o Dockerfile para realizar as seguintes tarefas:

- Copiar um arquivo index.html (https://viacep.com.br/exemplo/jquery/)
    
- Expor a porta 80

- Build do Dockerfile

- Criar um docker compose com build para imagem do nginx
    
- Mapear a porta 8080

## Exemplo de Dockerfile

```
FROM nginx

COPY static-html-directory /usr/share/nginx/html/
EXPOSE 80
```

## Exemplo de Docker Compose

```
version: '3.8'

services:
  nginx:
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "8080:80"
```

## Estrutura do projeto

Certifique-se de que o projeto tenha a seguinte estrutura:

```
.
├── docker-compose.yml
├── Dockerfile
└── static-html-directory
    └── index.html
```

## Instruções do Dockerfile e o Docker Compose

### Execute o contêiner

No diretório onde estão o Dockerfile e o arquivo docker-compose.yml, execute:

```
sudo docker-compose up -d
```
