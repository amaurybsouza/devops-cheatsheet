## Docker cheatsheet for DevOps community

### `Install Docker`

```
curl -fsSl https://get.docker.com | bash (faz a instalacao do Docker via script)
docker --version (verifica a versao do Docker)
systemctl status docker (verifica se o servico do Docker esta sendo executado)
docker container run hellow-world (executa um container)
docker container run -ti hello-world (executa um container)
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
