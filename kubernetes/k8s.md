### Instalação do KUBERNETES no Linux Ubuntu 22.04

```bash
# Baixa o K8s
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# Baixe o checksum do arquivo kubectl baixado 
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"

# Agora verifique
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check

kubectl: OK

# Instale o K8s
install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```


<br><br>
Referêncis:
- https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-kubectl-binary-with-curl-on-linux
