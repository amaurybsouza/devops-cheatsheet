# Kubernetes Cluster VirtualBox Commands

## Kubernetes commands - controlo plane

```bash
1  yum update
    2  vim
    3  vim /etc/modules-load.d/k8s.conf
    4  vim /etc/sysctl.d/k8s.conf
    5  sysctl --system
    6  apt update
    7  yum update
    8  yum upgrade
    9  reboot
   10  yum install vim net-tools git -y
   11  ifconfig
   12  date
   13  systemctl status firewalld
   14  systemctl stopped firewalld
   15  systemctl stoped firewalld
   16  systemctl stopeed firewalld
   17  systemctl stop firewalld
   18  systemctl disable firewalld
   19  hostnamectl set-hostname kubernetes-master
   20  reboot
   21  sudo yum-config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
   22  yum-config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
   23  yum install yum-config-manager
   24  cat /etc/os-release
   25  yum install yum-utils
   26  sudo yum-config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
   27  sudo yum install -y yum-utils device-mapper-persistent-data lvm2
   28  sudo yum install -y containerd.io
   29  systemctl start containerd
   30  systemctl enable containerd
   31  mkdir -p /etc/containerd
   32  containerd config default > /etc/containerd/config.toml
   33  systemctl enable containerd
   34  systemctl restart containerd
   35  sudo yum-config-manager --add-repo https://mirrors.aliyun.com/kubernetes/yum/repos/kubernetes-el7-x86_64/
   36  sudo yum repolist -n | grep kubernetes
   37  sudo yum install -y kubectl
   38  yum install kubelet kubeadm -y
   39  systemctl start kubelet
   40  sudo systemctl enable kubelet && sudo systemctl start kubelet
   41  history
   42  sudo swapoff -a
   43  sudo sed -i '/ swap / s/^\(.*\)$/#\1/g' /etc/fstab
   44  yum install  apt-transport-https gnupg2
   45  yum install epel-release the
   46  yum install  apt-transport-https
   47  systemctl start kubelet
   48  yum remove kubelet
   49  kulebet version
   50  yum install epel-release the
   51  sudo yum install -y kubelet
   52  yum install -y kubelet kubeadm kubectl --disableexcludes=kubernetes
   53  yum remove  -y kubelet kubeadm kubectl --disableexcludes=kubernetes
   54  yum remove  -y kubelet kubeadm kubectl
   55  cd /etc/yum.repos.d/
   56  ls
   57  rm -v mirrors.aliyun.com_kubernetes_yum_repos_kubernetes-el7-x86_64_.repo
   58  ls
   59  sudo yum install -y kubeadm
   60  cat <<EOF | sudo tee /etc/yum.repos.d/kubernetes.repo
   61  [kubernetes]
   62  name=Kubernetes
   63  baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-\$basearch
   64  enabled=1
   65  gpgcheck=1
   66  gpgkey=https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
   67  exclude=kubelet kubeadm kubectl
   68  EOF
   69  sudo setenforce 0
   70  sudo sed -i 's/^SELINUX=enforcing$/SELINUX=permissive/' /etc/selinux/config
   71  yum install -y kubelet kubeadm kubectl --disableexcludes=kubernetes
   72  systemctl enable --now kubelet
   73  systemctl start kubelet
   74  systemctl status kubelet
   75  systemctl start kubelet
   76  systemctl status kubelet
   77   kubeadm config images pull --cri-socket /run/containerd/containerd.sock
   78  kubeadm init --upload-certs --control-plane-endpoint=192.168.1.129  --cri-socket /run/containerd/containerd.sock
   79  history
   80  cat <<EOF | sudo tee /etc/yum.repos.d/kubernetes.repo
   81  [kubernetes]
   82  name=Kubernetes
   83  baseurl=https://packages.cloud.google.com/yum/repos/kubernetes-el7-\$basearch
   84  enabled=1
   85  gpgcheck=1
   86  gpgkey=https://packages.cloud.google.com/yum/doc/rpm-package-key.gpg
   87  exclude=kubelet kubeadm kubectl
   88  EOF
   89  sudo setenforce 0
   90  sudo sed -i 's/^SELINUX=enforcing$/SELINUX=permissive/' /etc/selinux/config
   91  vim /etc/modules-load.d/k8s.conf
   92  mkdir -p $HOME/.kube
   93  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
   94  sudo chown $(id -u):$(id -g) $HOME/.kube/config
   95  sudo modprobe br_netfilter ip_vs_rr ip_vs_wrr ip_vs_sh nf_conntrack_ipv4 ip_vs
   96  systemctl start kube-apiserver
   97  sudo kubeadm token list
   98  reboot
   99  kubectl get nodes
  100  history
  101  exit
  102  kubectl get nodes
  103  kubectl get pods -
  104  kubectl get pods
  105  kubectl get pods -n all-namespaces
  106  kubectl get pods all-namespaces
  107  kubectl create deployment nginx --image=nginx --port 80
  108  kubectl create deployment webserver --image=nginx --port 80 --replicas=5
  109  kubectl expose deployment webserver --port 80 --type=NodePort
  110  kubectl get services
  111  kubectl get pods
  112  kubectl get nodes -o wide
  ```