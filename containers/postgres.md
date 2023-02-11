## Instalação PostGres em Docker

#### Baixar a imagem do Postgres Server
```
docker pull postgres
```

#### Criar o diretorio externo (volume) para armazenar dados do Postgres Server
```
mkdir -p $HOME/docker/volumes/postgres
```

#### Rodar a imagem Docker do Postgres Server
```
docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres
```

#### Verificar se levantou o Container Docker com o Postgres Server
```
docker container ls -a
```

#### Instale o Postgres Client na sua maquina para testar o acesso ao Postgres Server
```
apt-get install -y postgresql-client
```

#### Testar o acesso ao Postgres Server
```
psql -h localhost -U postgres
```





