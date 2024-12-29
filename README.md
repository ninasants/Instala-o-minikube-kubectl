# Instalação-minikube-kubectl
Siga o passo detalhado abaixo: 
Instalação-minikube_kubectl 

Passo 1: Atualizar o sistema
Antes de começar, atualize o sistema para garantir que você tenha os pacotes mais recentes.

```
sudo apt update && sudo apt upgrade -y
```

Passo 2: Baixar o binário do kubectl
Baixe o binário mais recente do kubectl diretamente do site oficial do Kubernetes.

Obter a versão mais recente disponível:

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

Verificar o binário (opcional, mas recomendado): Faça o download do checksum e verifique a integridade do binário baixado:

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```

Para iniciar seu cluster digite o comando: 

```
minikube start
```

Para verificar de o kubectl foi instalado digite o comando: 

 ```
kubectl version --client 
 ```

Passo 3 (Opcional): Instalar via Gerenciador de Pacotes Snap
Se preferir usar o Snap para instalar o kubectl, use o comando abaixo:

```
sudo snap install kubectl --classic
```

Verifique a instalação com o comando:

```
kubectl version --client
```

Interaja com seu cluster
Se você já tiver o kubectl instalado (veja a documentação ), agora você pode usá-lo para acessar seu novo cluster:

```
kubectl get po -A
```

Alternativamente, o minikube pode baixar a versão apropriada do kubectl e você poderá usá-lo assim:

```
minikube kubectl -- get po -A
```





Inicialmente, alguns serviços, como o storage-provisioner, podem ainda não estar em um estado Running. Esta é uma condição normal durante a ativação do cluster e se resolverá momentaneamente. Para obter insights adicionais sobre o estado do seu cluster, o minikube agrupa o Kubernetes Dashboard, permitindo que você se aclimate facilmente ao seu novo ambiente:


minikube dashboard
