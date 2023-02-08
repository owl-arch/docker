## Docker - Instalção no linux ubuntu 22.04

#### Passo 1 - remover versões anteriores
```bash
sudo apt-get remove docker docker-engine docker.io containerd ru
```

#### Passo 2 - Atualiza o índice do pacote apt e instala os pacotes para permitir que o apt use um repositório HTTPS:

```bash
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```	

#### Passo 3 - Adicione a chave GPG oficial do Docke

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

- Verifique se agora você tem a chave com a impressão digital 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88, pesquisando os últimos 8 caracteres da impressão digital.

```bash
sudo apt-key fingerprint 0EBFCD88
```

#### Passo 4 - Use o seguinte comando para configurar o repositório estável. 

```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

#### Passo 5 - Instale o Docker Engine

- Atualize o índice do pacote apt e instale a versão mais recente do Docker Engine e containerd ou vá para a próxima etapa para instalar uma versão específica:

```bash
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

#### Passo 6 - Configura para subir o serviço na Inicialização e verique o status

```bash
systemctl enable docker
systemctl start docker
service docker status
```

<!--
```bash
service docker status
service docker start
```
-->

#### Passo 7 - Autorizar seu usuário para docker

```bash
sudo usermod -aG docker $USER
```

          


<br>

## DOCKER COMPOSE - Instalção no linux ubuntu 22.04

#### Passo 1

```bash
sudo curl -L "https://github.com/docker/compose/rel... -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

#### Passo 2 - defina as permissões corretas para que o comando docker-compose para que seja executável

```bash
sudo chmod +x /usr/local/bin/docker-compose
```

#### Passo 3 verifica se a instalação foi bem sucedida

```bash
docker-compose --version
```






<br><br><br>

#### Testar
```bash
# Ubuntu
sudo apt install docker-ce
```
