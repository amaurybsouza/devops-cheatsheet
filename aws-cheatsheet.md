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
IAM - servico global de identidade e controle de acessos na amazon
```

### `AWS Services`

```
apt-gateway - e um gateway na AWS que recebe requisicoes HTTPS, e escala por default 10k de requests por segundo
dynamodb - banco de dados NoSQL da AWS (escalabilidade alta e extremamente rapida)
SQS - sistemas de filas da AWS (escala muito, pode ter milhoes de requests por segundos)
lambda - executar as regras de negocio sao efetuadas nas funcoes lambdas
EBS - volume de blocos para instancias EC2 na AWS
```

### `Shared responsability model`

```
AWS e responsavel pela seguranca DA nuvem
Client e responsavel pela seguranca NA nuvem
```

### `AWS Global Infrastructure`

```
AWS Regions - regiao geografica onde existe um datacenter da amazon
AWS  Availability Zones - sao datacenters dentro de uma regiao (normalmente 3 datacenters por regiao)
AWS Edge Locations - conteudo e entregue para usuarios finais com baixa latencia
Multi AZ - quando determinado servico/produto esta presente em mais de uma AZ dentro de uma regiao na amazon.
```

### `AWS EC2`

```
- modalidade de contrato 
(on-demand) - nesta categoria de contrato voce paga apenas pelas instancias que EC2 que voce utilizar (por hora/segundos)
(reservadas) - oferece um desconto legal de 72% comparada ao modelo on-demanda
(spot) - oferece mais desconto ainda chegando ate 90% em comparacao com o modelo sob-demanda.











```
