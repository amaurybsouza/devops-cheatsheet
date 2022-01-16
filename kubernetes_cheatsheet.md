
### `Kubernetes concepts`

1. `container` runtime  containerd
2. `etcd`  "banco de dados" do meu cluster, onde armazena todas as informacoes do meu cluster
3. `kubeapi`  API do Kubernetes
4. `kubelet`  agente do kubernetes que roda nos meus nos (conversa com o master)
5. `kubeprox`  ele que sabe onde esta rodando cada POD, cada servico
6. `POD`  menor unidade do kubernetes. Dentro do POD pode ter 1 ou mais containers (compartilha o mesmo namespace)
7. `Controllers`  ele que fala com a API server
8. `Deployment`  como se fosse o service do Swarm, fazer o deployment para depois criar o service.


### `Basic commands`

```
$ kubectl get nodes - mostra os nodes do cluster Kubernetes
$ kubeadm token create --print-join-command - fornece o token para pormover um no como worker
$ kubeadm init - inicializa o cluster Kubernetes
$ kubeadm config images pull - faz o pull das imagens que compoem o Kubernetes
$ kubectl get pods --all-namespaces - obter todos os namespaces presente do Kubernetes
```

