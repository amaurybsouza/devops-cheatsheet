
### `Kubernetes Concepts
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
$ kubectl run nginx --image=nginx - executa um pod de nome nginx usando a imagem do nginx.
$ kubectl get pods - mostra os pods que eu tenho disponivel no Kubernetes
```

### `Kubernetes on VirtualBOX`
#### `Master`
```
    2  apt update
    3  yum update
    4  yum install net-tools -y
    5  ifconfig
    6  pwd
    7  yum install vim git -y
    8  pwd
    9  ifconfig
   10  hostnamectl set-hostname mr_robbot
   11  reboot
   12  poweroff
   13  hostnamectl set-hostname k8s_master
   14  reboot
   15  curl -fsSL https://get.docker.com | bash
   16  apt install auto-complete -y
   17  yum install auto-complete -y
   18  yum install autocomplete -y
   19  yum install bash-completion -y
   20  systemctl start docker
   21  systemctl enable docker
   22  history
   23  cat > /etc/docker/daemon.json <<EOF
   24     13  {
   25     14    "exec-opts": ["native.cgroupdriver=systemd"],
   26     15    "log-driver": "json-file",
   27     16    "log-opts": {
   28     17      "max-size": "100m"
   29     18    },
   30     19    "storage-driver": "overlay2",
   31     20    "storage-opts": [
   32     21      "overlay2.override_kernel_check=true"
   33     22    ]
   46  vim /etc/docker/daemon.json
   47  sudo mkdir -p /etc/systemd/system/docker.service.d
   48  sudo systemctl daemon-reload
   49  sudo systemctl restart docker
   50  sudo systemctl status docker
   51  docker info | grep -i cgroup
   52  vim /etc/yum.repos.d/kubernetes.repo
   53  sudo setenforce 0
   54  sudo systemctl disable firewalld
   55  sudo systemctl stop firewalld
   56  sudo systemctl status firewalld
   57  yum update -y
   58  sudo yum install -y kubelet kubeadm kubectl
   59  sudo systemctl enable docker && sudo systemctl start docker
   60  sudo systemctl enable kubelet && sudo systemctl start kubelet
   61  vim /etc/sysctl.d/k8s.conf
   62  sudo swapoff -a
   63  vim /etc/fstab
   64  reboot
   65  history
   66  sudo kubeadm config images pull
   67  hostnamectl set-hostname k8smaster
   68  reboot
   69  history
   70  sudo kubeadm init
   71  mkdir -p $HOME/.kube
   72  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
   73  sudo chown $(id -u):$(id -g) $HOME/.kube/config
   74  sudo modprobe br_netfilter ip_vs_rr ip_vs_wrr ip_vs_sh nf_conntrack_ipv4 ip_vs
   75  kubectl apply -f "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"
   76  kubectl get nodes
   77  kubectl get pods -n kube-system
   78  kubectl get nodes
```
#### `Cluster nodes`
```
    2  apt update
    3  yum update
    4  yum install net-tools -y
    5  ifconfig
    6  pwd
    7  yum install vim git -y
    8  pwd
    9  ifconfig
   10  hostnamectl set-hostname mr_robbot
   11  reboot
   12  poweroff
   13  hostnamectl set-hostname k8snode01
   14  reboot
   15  systemctl status dokcer
   16  systemctl status docker
   17  curl -fsSL https://get.docker.com | bash
   18  yum install vim git -y
   19   apt install auto-complete -y
   20  yumt install auto-complete -y
   21  yum install auto-complete -y
   22  yum install bash-completion -y
   23  systemctl start docker
   24  systemctl enable docker
   25  vim /etc/docker/daemon.json
   26   sudo mkdir -p /etc/systemd/system/docker.service.d
   27  sudo systemctl daemon-reload
   28  sudo systemctl restart docker
   29  docker info | grep -i cgroup
   30  vim /etc/yum.repos.d/kubernetes.repo
   31  sudo setenforce 0
   32  sudo systemctl stop firewalld
   33  sudo systemctl disable firewalld
   34  sudo yum install -y kubelet kubeadm kubectl
   35  sudo systemctl enable docker && sudo systemctl start docker
   36   sudo systemctl enable kubelet && sudo systemctl start kubelet
   37  vim /etc/sysctl.d/k8s.conf
   38  sudo swapoff -a
   39  vim /etc/fstab
   40  free -h
   41  reboot
   42  pwd
   43  history
   44  kubeadm join 192.168.1.111:6443 --token ez98s9.mx2rida372v3cxeh         --discovery-token-ca-cert-hash sha256:5ea69efc6451dedb940ce665bdf436ac3e54e0e44774fb0654b60562677944f5
```

