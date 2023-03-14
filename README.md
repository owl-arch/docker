<div style="display: inline_block"><br>
  <img align="right" alt="Docker-container" style="width: auto; height:380px;" 
     src="https://tel4vn.edu.vn/uploads/2020/10/tong-quan-kien-truc-cua-docker-tel4vn-01.png">
</div>

<div style="display: inline_block"><br>
  <img align="left" alt="docker" style="width: auto; height:60px;" 
     src="https://upload.wikimedia.org/wikipedia/commons/4/4e/Docker_%28container_engine%29_logo.svg">
</div>

<br><br><br>

### Conteúdo

#### 1. Instalação
- [x] [Docker install](https://github.com/dev-carvalho/docker/blob/main/docker-install.md)
- [x] [Docker commands](https://github.com/dev-carvalho/docker/blob/main/docker-commands.md)

#### 2. Containers
- [ ] [NGINX Server](https://github.com/dev-carvalho/docker/tree/main/containers/nginx.md)
- [x] [PostgreSQL Server](https://github.com/dev-carvalho/docker/tree/main/containers/postgres.md)
- [x] [MySQL Server](https://github.com/dev-carvalho/docker/tree/main/containers/mysql.md)

| Command                       | Description                                                                              |
| :---------------------------- | :--------------------------------------------------------------------------------------- |
| `docker build`                | Build an image from a Dockerfile                                                         |
| `docker container inspect`    | Display detailed information on one or more containers                                   |
| `docker container ls`         | List all the running docker containers                                                   |
| `docker container ls -a`      | List all running and stopped containers                                                  |
| `docker image build`          | Build an image from a Dockerfile (same as docker build)                                  |
| `docker image inspect`        | Display detailed information on one or more images                                       |
| `docker image ls`             | List docker images                                                                       |
| `docker image push`           | Push an image or repository to a remote registry                                         |
| `docker image rm`             | Remove one or more images                                                                |
| `docker image tag`            | Add a name and tag to a particular image                                                 |
| `docker container logs`       | Fetch the logs of a docker container                                                     |
| `docker network create`       | Create a new network                                                                     |
| `docker network connect`      | Connect a container to a network                                                         |
| `docker network disconnect`   | Disconnect a container from a network                                                    |
| `docker network inspect`      | Return information about one or more networks                                            |
| `docker network ls`           | List all networks the engine daemon knows about, including those spanning multiple hosts |
| `docker network rm`           | Remove one or more networks                                                              |
| `docker container port`       | List port mappings or a specific mapping for the container                               |
| `docker pull`                 | Pull an image or a repository from a registry                                            |
| `docker container run`        | Create a new container and start it using the specified command                          |
| `docker container run -it`    | Create a new container and start it in an interactive shell                              |
| `docker container rm`         | Remove the specified container(s)                                                        |
| `docker container rm -f`      | Force the removal of a running container (uses SIGKILL)                                  |
| `docker container start`      | Start one or more stopped containers                                                     |
| `docker container restart`    | Restart one or more containers
| `docker stop $(docker ps -q)` | Stop all running containers                                                              |
| `docker container stop`       | Stop one or more running containers                                                      |
| `docker top`                  | Display the running processes of a container                                             |
| `docker volume inspect`       | Display detailed information about one or more volumes                                   |
| `docker volume ls`            | List all the volumes known to docker                                                     |
| `docker volume prune`         | Cleanup dangling volumes                                                                 |
| `docker container exec`       | Run a new command in a running container                                                 |
| `docker container exec -it`   | Run a new command in a running container in an interactive shell                         |
