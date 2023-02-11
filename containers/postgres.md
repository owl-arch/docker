## Instalação PostGres em Docker

#### 1. Baixar a imagem do Postgres Server
```
docker pull postgres
```

#### 2. Criar o diretorio externo (volume) para armazenar dados do Postgres Server
```
mkdir -p $HOME/docker/volumes/postgres
```

#### 3. Rodar a imagem Docker do Postgres Server
```
docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres
```

#### 4. Verificar se levantou o Container Docker com o Postgres Server
```
docker container ls -a
```

#### 5. Instale o Postgres Client na sua maquina para testar o acesso ao Postgres Server
```
apt-get install -y postgresql-client
```

#### 6. Testar o acesso ao Postgres Server
```
psql -h localhost -U postgres
```





