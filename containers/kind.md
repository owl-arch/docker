
### Instalação do KIND no Linux Ubuntu 22.04

```bash
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.17.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```


### Criando um cluster

```bash
root@i7ultra:~# kind create cluster --name zeta
Creating cluster "zeta" ...
 ✓ Ensuring node image (kindest/node:v1.25.3) 🖼
 ✓ Preparing nodes 📦
 ✓ Writing configuration 📜
 ✓ Starting control-plane 🕹️
 ✓ Installing CNI 🔌
 ✓ Installing StorageClass 💾
Set kubectl context to "kind-zeta"
You can now use your cluster with:

kubectl cluster-info --context kind-zeta

Thanks for using kind! 😊
```


### Apagando um cluster

```bash
root@i7ultra:~# kind delete cluster --name zeta
Deleting cluster "zeta" ...
```


<br><br>
Referências:
- https://kind.sigs.k8s.io/
- https://www.zup.com.br/blog/kind-cluster-kubernetes
