## AWS commands

### AWS Core services

`EC2` - servico de maquinas virtuais da AWS
  - `AMI` - é a imagem da máquina virtual, clone do sistema (facilita o provisionamento em determinados cenarios)
  - `Security Groups` - e um servico de firewall que atua nas instancias EC2
  - `Elastic IP's` - e um endereco de IPv4 para instancias EC2 (associa esse endereco na instancia EC2 de forma fixa)
  - `Load Balancing` - distribui a carga de trafego de aplicativos para diversos destinos, como EC2, containers
  - `Auto Scaling` - monitora continuamente os aplicativos para garantir que operem nos níveis de desempenho desejados

`IAM` - servico global de identidade e controle de acessos na AWS
  - `Users` - usuarios que podem ser criados na AWS para administracao dos servicos
  - `Grupos` - grupos de usuarios dentro da AWS
  - `Roles` - e uma identidade que voce pode criar com permissoes epecificas
  - `Policies` - e um objeto na AWS que define permissoes
  - `MFA` - multi factor authetication para melhorar a seguranca de acessos na AWS
  
 `VPC` - servico que prove toda a parte de rede da AWS entre os seus recursos
  - `Subnet` - gama de enderecos IP's, particionar a rede dentro da VPC
  - `Route table` - conjunto de regras para que tenha acesso para internet e entre subnets usamos route tables
  - `Gateway de internet` - um gateway que permite acesso a outros recursos na VPC e internet
  - `VPC endpoint` - permite conectar de forma privada a VPC aos servicos compativeis da AWS e aos servicos do VPC endpoint
  - `NAT gateway` - permite que suas instancias de VPC sejam acessadas na internet enquanto estao com subnets privadas. (subnets privadas)
  - `Internet gateway` - permite fazer NAT e permite internet para nossas VPC atraves do route table (subnets publicas)







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
---
EBS - volume de discos usados nas instancias EC2
1 - dispositivos EBS nao sao globais, apenas por regioes.
1.1 - a instancia deve estar na mesma zona de disponiblidade do volume EBS.
1.2 - podemos anexar varios volumes de EBS na instancia do EC2.











```
