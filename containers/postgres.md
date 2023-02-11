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

- --rm: Remove automaticamente o contêiner e seu sistema de arquivos associado ao sair. Em geral, se estivermos executando muitos contêineres de curto prazo, é uma boa prática passar o sinalizador rm para o comando docker run para limpeza automática e evitar problemas de espaço em disco. Sempre podemos usar a opção v (descrita abaixo) para manter os dados além do ciclo de vida de um contêiner

- --name: Um nome de identificação para o contêiner. Podemos escolher o nome que quisermos. Observe que dois contêineres existentes (mesmo se estiverem parados) não podem ter o mesmo nome. Para reutilizar um nome, você precisa passar o sinalizador rm para o comando docker run ou remover explicitamente o contêiner usando o comando docker rm [nome do contêiner].

- -e: Expõe a variável de ambiente de nome POSTGRES_PASSWORD com janela de encaixe de valor para o contêiner. Esta variável de ambiente define a senha de superusuário para PostgreSQL. Podemos definir POSTGRES_PASSWORD como quisermos. Acabei de escolhê-lo para ser docker para demonstração. Existem variáveis ​​de ambiente adicionais que você pode definir. Isso inclui POSTGRES_USER e POSTGRES_DB. POSTGRES_USER define o nome do superusuário. Se não for fornecido, o padrão do nome do superusuário é postgres. POSTGRES_DB define o nome do banco de dados padrão a ser configurado. Se não for fornecido, o valor padrão é POSTGRES_USER.

- -d: Inicia o contêiner no modo desanexado ou em outras palavras, em segundo plano.

- -p : Vincule a porta 5432 no host local à porta 5432 dentro do contêiner. Esta opção permite que os aplicativos executados fora do contêiner possam se conectar ao servidor Postgres executado dentro do contêiner.

- -v : Monte $HOME/docker/volumes/postgres na máquina host para o caminho do volume do lado do contêiner /var/lib/postgresql/data criado dentro do contêiner. Isso garante que os dados do postgres persistam mesmo após a remoção do contêiner.

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





