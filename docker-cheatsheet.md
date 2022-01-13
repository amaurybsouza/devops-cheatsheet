## Docker cheatsheet for DevOps community

### `Install Docker`

```
curl -fsSl https://get.docker.com | bash (faz a instalacao do Docker via script)
docker --version (verifica a versao do Docker)
systemctl status docker (verifica se o servico do Docker esta sendo executado)
docker container run hellow-world (executa um container)
docker container run -ti hello-world (executa um container)
```

### `Troubleshooting`

```
- docker start failed after adding daemon.json file
{
    "exec-opts": ["native.cgroupdriver=systemd"],
    "log-driver": "json-file",
    "log-opts": {
      "max-size": "100m"
    }
  }
```

### `Basic commands`

```
docker container run (executa um container)
"Ctrl + p + q" (para sair do container sem matar o container)
docker container ls (lista os containers em execucao)
docker container ls -a * (lista os containers que estao ocultos)
docker container inspect (mostra detalhes de um container)
docker run -it ubuntu bash (executa um container com a imagem do Ubuntu)
opcao -ti (ja iremos cair dentro do container, ele me dara um terminal + interacao para esse container)
docker container attach great_snyder (para eu acessar novamente o container, usando o nome ou o ID)
docker container run -d nginx (executa um container em modo daemon, seja iniciado em background)
docker container exec 26484f95efd1 ls / (conecta dentro do container do nginx e roda um "ls" no / do sistema)
docker container exec -ti 26484f95efd1 bash (vou me conectar nesse container)
docker container stop 26484f95efd1 (parando um container)
docker container start 26484f95efd1 (iniciando um container)
docker container restart 26484f95efd1 (restartando um container)
docker container rm (remove um container)
docker container rm -f (remove um container em execucao)
docker container top (mostra os processos em execucao)
docker container stats (mostra informacoes de consumo de recursos como CPU/Memoria)
docker container run -d -m 64M --cpus 0.5 nginx (executa um cintainer com limite de CPU/Memoria)
```

### `Services`

```
docker service create (cria um service)
docker service ls (lista um service)
docker service inspect (mostra detalhes de um service)
docker service scale (aumenta/diminui a quantidade de replicas de um service)
docker service ps (lista os pods de um service)
docker service logs (mostra os logs de um service)
docker service rm (remove um service)
```

### `Swarm`

```
docker swarm init (inicia um cluster de swarm)
docker swarm join (comando para adicionar novos nodes ao cluster)
docker node ls (lista os nodes do cluster)
docker swarm join-token manager (lista o token para adicionar novos managers ao cluster)
docker swarm join-token worker (lista o token para adicionar novos workers ao cluster)
docker node inspect (mostra detalhes sobre o node)
docker node promote (promove um node para manager)
docker node demote (muda um node manager para worker
docker node rm (remove um node)
docker swarm leave (para que o node saia do cluster)
docker swarm leave --force (para que um node manager saia do cluster)
```
