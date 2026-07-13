## Anotações e ponderações para aws ALB
### 1.Crie uma instância EC2 para servir de modelo.
### 2.Crie uma imagem dessa máquina.
  L___ Isso permitirá criar cópias idênticas dessa instância
### 3.Criar um Auto-Scaling
####  L___ CheckList: 
[O]Target Group <p>(Target Groups definem para onde mandar o trafégo que vem para o Load Balancer. O Application Load Balancer pode enviar tráfego para diferentes Target Groups dependendo do URL da requisição recebida, por exemplo, mandar as requisições vindas de um aplicativo mobile para um diferente grupo de servidores. Porém, na maioria das vezes, só utilizarei um target group)
*Configuração Padrão --> Tipo:instâncias; Inserir Nome; Inserir VPC; Deixa o resto no padrão; Não registre nenhum Target por enquanto.*
</p>
<p>
[O]Criar Load Balancer
<p>*Configuração Padrão --> Tipo:Application Load Balancer; Inserir Nome; Inserir VPC; Duas Subnets públicas em duas Zonas de Disponibilidade diferentes; Inserir Security Group</p>
</p>
