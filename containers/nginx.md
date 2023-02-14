

<div style="display: inline_block"><br>
  <img align="right" alt="Docker-container" style="width: auto; height:180px;" 
     src="https://www.nginx.com/wp-content/uploads/2018/08/NGINX-logo-rgb-large.png">
</div>

> # É fácil e direto começar a usar o NGINX no docker.

<br>

## Instalação PostGres em Docker

#### 1. Baixar a imagem do Postgres Server
```
docker pull nginx
```

#### 2. Criar o diretorio externo (volume) para armazenar dados do NGINX Server
```
mkdir -p $HOME/docker/volumes/nginx
```

#### 3. Rodar a imagem Docker do NGINX Server
```
docker run --rm --name nginx -v /host/path/nginx.conf:/etc/nginx/nginx.conf:ro -d -p 8080:80 nginx:latest
```

#### 4. Verificar se levantou o Container Docker com o NGINX Server
```
docker container ls -a
```

OU

```
docker ps
```


<br><br>
Referências
- https://hub.docker.com/_/nginx



  
