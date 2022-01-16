
### `Kubernetes concepts`

```
container runtime - containerd
etcd - "banco de dados" do meu cluster, onde armazena todas as informacoes do meu cluster
kubeapi - API do Kubernetes
kubelet - agente do kubernetes que roda nos meus nos (conversa com o master)
kubeprox - ele que sabe onde esta rodando cada POD, cada servico
POD - menor unidade do kubernetes. Dentro do POD pode ter 1 ou mais containers (compartilha o mesmo namespace)
Controllers - ele que fala com a API server
Deployment - como se fosse o service do Swarm, fazer o deployment para depois criar o service.
```

### `Basic commands`

```
$ kubectl get nodes - mostra os nodes do cluster Kubernetes
$ kubeadm token create --print-join-command - fornece o token para pormover um no como worker
$ kubeadm init - inicializa o cluster Kubernetes
$ kubeadm config images pull - faz o pull das imagens que compoem o Kubernetes
$ kubectl get pods --all-namespaces - obter todos os namespaces presente do Kubernetes
$  kubectl get pods --all-namespaces -o wide - opcao estendida do comando para mostrar mais resultados
```

