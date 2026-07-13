<details>
<summary>✅ CheckList:</summary>
<p>
  - Uma Instância EC2 para servir de modelo.
  <p>
      *Configuração Padrão --> Como quiser*
  </p>
</p>
<p>
  - Crie uma imagem dessa máquina.
</p>
<p>
  - Target Group (Target Groups definem para onde mandar o trafégo que vem para o Load Balancer. O Application Load Balancer pode enviar tráfego para diferentes Target Groups dependendo do URL da requisição recebida, por exemplo, mandar as requisições vindas de um aplicativo mobile para um diferente grupo de servidores. Porém, na maioria das vezes, só utilizarei um target group)
  *Configuração Padrão --> Tipo:instâncias; Inserir Nome; Inserir VPC; Deixa o resto no padrão; Não registre nenhum Target por enquanto.*
</p>
<p>
  - Security Group
  <p>
      *Configuração Padrão --> Inbound: Todos os Ipv4 do tipo SSH, todos od Ipv4 do tipo HTTP; Outbound: todo tráfego*
  </p>
</p>
<p>
  - Load Balancer
  <p>
      *Configuração Padrão --> Tipo:Application Load Balancer; Inserir Nome; Inserir VPC; Duas Subnets públicas em duas Zonas de Disponibilidade     diferentes; Inserir Security Group; Listener-> HTTP:80, Inserir Target Group.*
  </p>
</p>
<p>
  - Launch Template
  <p>
      *Configuração Padrão --> Inserir Nome; Selecione: Provide guidance to help me set up a template that I can use with EC2 Auto Scaling; Imagem: sua imagem; Instance type: t2.micro; Key pair name: vockey; Firewall: Insira seu Security Group; Ative Detailed CloudWatch monitoring(nos Advanced Details)(Isso permitirá que o autoscaling responda rapidamente a mudanças)*
  </p>
</p>
<p>
  - Auto Scaling Group
  <p>
      *Configuração Padrão --> Inserir Nome; Insira seu Launch Template; Insira a VPC; Insira uma subnet privada em cada zona de disponibilidade; Attach to teu load balancer; (daqui pra frente depende muito da tua aplicação ->)Desired Capacity:2;Minimum capacity: 2; Maximum capacity: 6; Scaling policies: Target tracking scaling policy->target value: 30(aqui você define o uso máximo de cpu nas máquinas);Additional settings-> ative: Enable group metrics collection within CloudWatch; Tag: Name, Insira um nome(essa tag vai ser ligada a todas as instâncias que vão ser criadas.*
  </p>
</p>
</details>
