### Run a new container
```
docker container run (start a new container from an image)
docker container run -- name app nginx (assign a name for the container)
docker container run -p 8080:80 nginx (map a por os container)
docker container run -P nginx (map all the ports)
docker container run -d nginx (start a container in background)
docker container run --hostname srv nginx (assign a hostname)
docker container run --add-host HOSTNAME:IP IMAGE (add a DNS entry)
docker container run -v ~/:/usr/share/nginx/html nginx (map a local directory into the container)
docker container run -ti  --entrypoint bash nginx (change the entrypoint)
```

### Basic Docker Commands

```
curl -fsSl https://get.docker.com | bash (faz a instalacao do Docker via script)
docker --version (verifica a versao do Docker)
systemctl status docker (verifica se o servico do Docker esta sendo executado)
docker container run hellow-world (executa um container)
docker container run -ti hello-world (executa um container)
```

### Manage Volumes
```
$ docker container run -d -p 80:80 --name phpmessage_container -v volumeteste:/var/www/html --rm phpmessages (executando um container com volume)
$ docker volume inspect teste (inspecionar um volume criado)
```

#### Manage Services
```
docker service create (cria um service)
docker service ls (lista um service)
docker service inspect (mostra detalhes de um service)
docker service scale (aumenta/diminui a quantidade de replicas de um service)
docker service ps (lista os pods de um service)
docker service logs (mostra os logs de um service)
docker service rm (remove um service)
```

### Manage Swarm
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
 
### Manage Containers
```
docker container ls - show a list of containers
docker container ls -a - show a list of all containers
docker container rm app - delete the container
docker container rm -f app - delete a running container
docker container prune - delete stopped containers
docker container stop app - stop a running container
docker container start app - start a stopped container
docker container cp app:/index.html index.html
```
