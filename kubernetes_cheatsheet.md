
### `Kubernetes concepts`
```
container runtime - containerd
namespace - como se fosse um cercadinho da minha app (maior controle)
etcd - "banco de dados" do meu cluster, onde armazena todas as informacoes do meu cluster
kubeapi - API do Kubernetes
kubelet - agente do kubernetes que roda nos meus nos (conversa com o master)
kubeprox - ele que sabe onde esta rodando cada POD, cada servico
POD - menor unidade do kubernetes. Dentro do POD pode ter 1 ou mais containers (compartilha o mesmo namespace)
Controllers - ele que fala com a API server
Deployment - como se fosse o service do Swarm, fazer o deployment para depois criar o service.
```

### `Kubectl get commands`
```
kubectl get nodes - Lista todos os nodes no cluster
kubectl get namespaces - Lista todos os namespaces disponíveis no cluster
kubectl get pod -n [nome_namespace] - Lista todos os pods no namespace desejado
kubectl get pods --all-namespaces -o wide - Lista os pods de todos os namespaces com
maiores informações
kubectl get services - Lista todos services no namespace
kubectl get events - Lista os eventos do cluster
kubectl get all - Lista todos os recursos recém criados
kubectl get endpoints - Lista todos os EndPoints
kubectl get deployments.apps - Lista os Deployments
kubectl get replicaset - Lista os ReplicaSet
kubectl get daemonset - Lista os DaemonSet
kubectl get pv - Lista todos os PersistentVolume
kubectl get pvc - Lista todos os PersistentVolumeClaim
kubectl get cronjobs - Lista todos os cronjobs
```

### `kubectl create commands`
```
kubectl create -f [nome_arquivo.yaml] - Cria algo a partir de um arquivo yaml
kubectl create deploy [nome_deploy] --image=[imagem_deploy] - Cria um
deployment
kubectl create configmap [nome_config] --from-file=[caminho_arquivo] -
Cria um novo configmap a partir de um arquivo
kubectl create cronjob [nome_cron] --image=[imagem] --schedule="[schedule]"
Cria um cronjob
kubectl create service [tipo_svc] [nome_svc] --tcp=[porta] - Cria um service
```

### `kubectl describe commands`
```
kubectl describe node [nome_node] - Lista os dados e status do node desejado
kubectl describe service [nome_service] - Lista os detalhes do service desejado
kubectl describe pod [nome_pod] - Lista os dados e status do pod desejado
kubectl describe endpoints [nome_endpoint] - Lista os dados do EndPoint desejado
kubectl describe replicaset [nome_replicaset] - Lista os dados do ReplicaSet desejado
```

### `kubeadm commands`
```
kubeadm config images pull - Efetua o download das imagens dos componentes
do kubernetes
kubeadm init - Efetua a inicialização do cluster, executar no node main
kubeadm token create --print-join-command - Lista o token para a adição de
novos nodes
kubeadm join --tok
```

### `Others commands`
```
$ kubectl get nodes - mostra os nodes do cluster Kubernetes
$ kubeadm token create --print-join-command - fornece o token para pormover um no como worker
$ kubeadm init - inicializa o cluster Kubernetes
$ kubeadm config images pull - faz o pull das imagens que compoem o Kubernetes
$ kubectl get pods --all-namespaces - obter todos os namespaces presente do Kubernetes
$ kubectl get pods --all-namespaces -o wide - opcao estendida do comando para mostrar mais resultados
$ kubectl describe nodes localhost.localdomain - mostra mais detalhes do meu node
```

