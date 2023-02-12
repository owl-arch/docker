<div style="display: inline_block"><br>
  <img align="right" alt="Docker-container" style="width: auto; height:280px;" 
     src="https://user-images.githubusercontent.com/93828234/218291000-ff3de5dd-b24e-4b6b-b747-9cbd25ca3435.png">
</div>

<br>

> # É fácil e direto começar a usar o Mysql no docker.

<br>

## Instalação Mysql em Docker

#### 1. Baixar a imagem do Mysql Server
```
docker pull mysql
```

#### 2. Criar o diretorio externo (volume) para armazenar dados do Mysql Server
```
mkdir -p $HOME/docker/volumes/mysql
```

#### 3. Rodar a imagem Docker do Mysql Server

Ao executar o container criado, iremos passar algumas variáveis de ambiente. As variáveis serão:

- MYSQL_ROOT_PASSWORD: Senha para acessar o banco dentro do container;
- MYSQL_DATABASE: Banco de dados a ser criado;
- MYSQL_USER: Usuário para ter acesso ao banco de dados;
- MYSQL_PASSWORD: Senha do usuário para ter acesso ao banco de dados;

```
docker run --rm --name my-docker -e MYSQL_ROOT_PASSWORD=root -e MYSQL_USER=db -e MYSQL_PASSWORD=123456 -e MYSQL_DATABASE=backoffice -d -p 3306:3306 -v $HOME/docker/volumes/mysql:/var/lib/mysqlql/data mysql
```

- --rm: Remove automaticamente o contêiner e seu sistema de arquivos associado ao sair. Em geral, se estivermos executando muitos contêineres de curto prazo, é uma boa prática passar o sinalizador rm para o comando docker run para limpeza automática e evitar problemas de espaço em disco. Sempre podemos usar a opção v (descrita abaixo) para manter os dados além do ciclo de vida de um contêiner

- --name: Um nome de identificação para o contêiner. Podemos escolher o nome que quisermos. Observe que dois contêineres existentes (mesmo se estiverem parados) não podem ter o mesmo nome. Para reutilizar um nome, você precisa passar o sinalizador rm para o comando docker run ou remover explicitamente o contêiner usando o comando docker rm [nome do contêiner].

- -e: Expõe a variável de ambiente de nome POSTGRES_PASSWORD com janela de encaixe de valor para o contêiner. Esta variável de ambiente define a senha de superusuário para PostgreSQL. Podemos definir POSTGRES_PASSWORD como quisermos. Acabei de escolhê-lo para ser docker para demonstração. Existem variáveis ​​de ambiente adicionais que você pode definir. Isso inclui POSTGRES_USER e POSTGRES_DB. POSTGRES_USER define o nome do superusuário. Se não for fornecido, o padrão do nome do superusuário é mysql. POSTGRES_DB define o nome do banco de dados padrão a ser configurado. Se não for fornecido, o valor padrão é POSTGRES_USER.

- -d: Inicia o contêiner no modo desanexado ou em outras palavras, em segundo plano.

- -p : Vincule a porta 5432 no host local à porta 5432 dentro do contêiner. Esta opção permite que os aplicativos executados fora do contêiner possam se conectar ao servidor Mysql executado dentro do contêiner.

- -v : Monte $HOME/docker/volumes/mysql na máquina host para o caminho do volume do lado do contêiner /var/lib/mysqlql/data criado dentro do contêiner. Isso garante que os dados do mysql persistam mesmo após a remoção do contêiner.

#### 4. Verificar se levantou o Container Docker com o Mysql Server
```
docker container ls -a
```

#### 5. Instale o Mysql Client na sua maquina para testar o acesso ao Mysql Server
```
apt-get install -y mysql-client
```

#### 6. Testar o acesso ao Mysql Server
```
mysql -h 127.0.0.1 -P 3306 -u root -p backoffice
```

Nota: mysql -h localhostnão funciona.

<br><br>
Referências
- 



