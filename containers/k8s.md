### Instalação do KUBERNETES no Linux Ubuntu 22.04

```bash
# Baixa o K8s
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"

# Instala o K8s
install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
