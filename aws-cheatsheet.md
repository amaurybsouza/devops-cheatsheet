## AWS commands

### `AWS CLI`

```
aws ec2 start-instances --instance-ids i-0c42e1bba4a6db957 - comando para iniciar uma instancia EC2 na AWS
aws ec2 stop-instances --instance-ids i-0c42e1bba4a6db957 - comando para parar uma instancia EC2 na AWS
aws ec2 describe-availability-zones --region sa-east-1 - descreve as zonas de dispoibilidade da regiao de Sao Paulo
```

### `AWS Core services`

```
aws-cli - ferramenta escrita em Pythonpara implementar/criar/modificar recursos na AWS via linha de comando.
ec2 - servico de maquinas virtuais da amazon web services
```

### `Modelo de responsabilidade compartilhada`

```
AWS e responsavel pela seguranca DA nuvem
Client e responsavel pela seguranca NA nuvem
```

### `AWS Global Infrastructure`

```
AWS Regions - regiao geografica onde existe um datacenter da amazon
AWS  Availability Zones - sao datacenters dentro de uma regiao (normalmente 3 datacenters por regiao)
  - mais disponibilidade do servico/produto
  - redundancia de energia
  - conectividade
AWS Edge Locations - 
Multi AZ - quando determinado servico/produto esta presente em mais de uma AZ dentro de uma regiao na amazon.
```
