Instalação PostGres em Docker

- Baixar a imagem
docker pull postgres

- Criar o diretorio externo para armazenar dados
mkdir -p $HOME/docker/volumes/postgres

- Rodar a imagem
docker run --rm --name pg-docker -e POSTGRES_PASSWORD=docker -d -p 5432:5432 -v $HOME/docker/volumes/postgres:/var/lib/postgresql/data postgres

- Verificar se levantou o container
docker container ls -a

- Instale o cliente para testar o acesso
apt-get install -y postgresql-client

- Teste o acesso
psql -h localhost -U postgres






