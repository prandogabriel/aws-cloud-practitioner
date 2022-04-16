# Certificação AWS Cloud Practitioner

Compilado de todas as anotações que fiz durante o estudo para tirar a certificação **[AWS Certified Cloud Practitioner](https://aws.amazon.com/pt/certification/certified-cloud-practitioner).** 

* [Tópicos da certificação](#Tópicos)
    - [Sobre a prova](#about)
    - [Conceitos de Cloud](#cloud_computing)
    - [Serviços da AWS](#services)
    - [Instâncias EC2](#ec2)
    - [Storage S3](#s3)
    - [IAM](#iam)
    - [Cobrança e preços](#pricing)
    - [Segurança](#security)
* [Referências](#links)


<hr> 
<div id="Tópicos"></div> 

## Tópicos
Domain 1: Cloud Concepts 26%  
Domain 2: Security and Compliance 25%  
Domain 3: Technology 33%  
Domain 4: Billing and Pricing 16%  
TOTAL 100%  

Domain 1: Cloud Concepts  
1.1 Define the AWS Cloud and its value proposition  
1.2 Identify aspects of AWS Cloud economics  
1.3 List the different cloud architecture design principles  
Domain 2: Security and Compliance  
2.1 Define the AWS shared responsibility model  
2.2 Define AWS Cloud security and compliance concepts  
2.3 Identify AWS access management capabilities  
2.4 Identify resources for security support  
Domain 3: Technology  
3.1 Define methods of deploying and operating in the AWS Cloud  
3.2 Define the AWS global infrastructure  
3.3 Identify the core AWS services  
3.4 Identify resources for technology support  
Domain 4: Billing and Pricing  
4.1 Compare and contrast the various pricing models for AWS  
4.2 Recognize the various account structures in relation to AWS billing and pricing  
4.3 Identify resources available for billing support  


<hr> 
<div id="about"></div> 

## Sobre a prova
- A Prova vale de 0 a 1000 pontos, para ganhar o certificado, você deve tirar a cima de 700 pontos
- Os pesos estão listados a cima
- São questões de multipla escolha e escolha múltipla
- A prova é assistida por um instrutor da AWS
<hr> 
<div id="cloud_computing"></div> 

## Conceitos de Cloud
Cloud computing (Computação em nuvem), empresas de grande poder de compra que alugam seus data centers para terceiros, onde provem serviços já configurados para o consumidor final, como backup, processamento sob demanda, etc. Então o usuário que precise de serviços de computação, não precisa mais comprar seu servidor e manter localmente, nem tenha que fazer upgrade físico toda vez que precise aumentar recursos, tudo se torna mais fácil

### Vantagens
- Capital expense Vs variable expenses
  - Capital expense é quando você sabe quanto vai gastar, você contrata X recursos, e pelo período contratado, você tem certeza do custo total
  - Variable expenses é quando não sabe quanto vai gastar, você acaba comprando seu hardware, e nunca sabe quanto vai gastar no final, pois sempre pode ter algum upgrade ou manutenção imprevista
- Economia, como temos muitas pessoas migrando para nuvem, mais barato fica para a AWS, pois ela consegue comprar mais material/hardware em lote a preço menor, logo fica mais barato
- Escalabilidade e capacidade dinâmica, alterar recursos com base na demanda e crescimento do seu negócio
- Velocidade e agilidade, com facilidade podemos criar um servidor em alguns cliques, fazer upgrade e etc
- Zero manutenção de datacenter, isso fica sob responsabilidade do seu cloud provider
- Rapidez para criar seus recursos e serviços. Implantação global em questão de minutos. Com a nuvem, você pode ampliar as atividades para novas regiões geográficas e implantar globalmente em minutos. Por exemplo, a AWS tem infraestrutura em todo o mundo, o que permite que você implante aplicativos em vários locais físicos com apenas alguns cliques. Aproximar os aplicativos dos usuários finais reduz a latência e melhora a experiência desses usuários

### Tipos de clouds
Temos 3 tipos de clouds, veremos a seguir. ***A AWS se encaixa nos 3***
#### IAAS
Infrastructure as a service (infraestrutura como serviço). Quando utilizamos a infraestrutura da empresa, como por exemplo o serviço AWS EC2 que utilizamos os hardwares da AWS para montar nossos servidores. Geralmente oferece acesso a recursos de rede, computadores (virtuais ou em hardware dedicado) e espaço de armazenamento de dados
#### PAAS
plataform as a service (plataforma como serviço), quando você tem um serviço totalmente gerenciado, ex: quer ter um site e contrata um wordpress gerenciado, você não sabe o que tem por baixo da infra e como está implementado, você só usa. Não precisa mais gerenciar a infraestrutura subjacente (geralmente, hardware e sistemas operacionais) e pode manter o foco na implantação e no gerenciamento de aplicativos.
#### SAAS
SaaS – software as a service (software como serviço). Quando você só utiliza o software, ex o gmail.


<hr> 
<div id="services"></div> 

## Serviços da AWS
Atualmente a AWS provem mais de 200 serviços. Temos regions e ***availability zones***, uma região sempre é um pais e uma availability zones é um local onde temos os datacenters dentro do pais, como por exemplo, region Brasil e availability zones São Paulo 

<hr> 
<div id="ec2"></div> 

## Instâncias EC2 (Amazon Elastic Compute Cloud)
Máquinas virtuais na AWS, temos várias capacidades de hardware/memória disponíveis em diversas regions e zonas

#### Definição de preço
- 750h gratuitas por mês gratuitas por mês durante os primeiros 12 meses
- Sob demanda
  - Com as instâncias sob demanda, você paga pela capacidade computacional por hora ou por segundo, dependendo das instâncias executadas. Não são necessários compromissos de longo prazo nem pagamentos antecipados. Você pode aumentar ou diminuir a capacidade computacional dependendo das demandas do aplicativo e pagar apenas as taxas por hora especificadas para a instância utilizada
- Instâncias spot
  - As instâncias spot do Amazon EC2 permitem solicitar capacidade computacional extra do Amazon EC2 com desconto de até 90% em relação ao preço das instâncias sob demanda. São recursos ociosos da AWS, que ela "aluga" com esse preço baixíssimo mas caso preciso de volta, ela desliga sua máquina e cobra somente pelo tempo que você utilizou
- Savings Plans
  - Planos de 1 a 3 anos, que tem um preço muito menor comparado ao sob demanda
- Host dedicados
  - Servidor físico do EC2 dedicado exclusivamente ao seu uso
  - Os hosts dedicados ajudam você a reduzir custos, permitindo que você use licenças existentes de software vinculadas ao servidor, incluindo Windows Server, SQL Server

  #### Categorias de instâncias
  Temos 4 categorias de instâncias EC2
  - Uso geral
  - Computacional otimizada (mais memória ou processamento)
  - Storage (Armazenamento) otimizada
  - Computação acelerada

Depende para seu caso de uso. Dentro de cada categoria temos várias subdcategorias, com especificações diferentes de memória, conectividade com rede, processamento, etc.

#### EBS Elastic block store
A AWS não usa discos diretamente nos seus servidores, para armazenamento ela utiliza o recurso chamado EBS, onde temos SSDs e HDDs.
Dentro dessas duas divisões temos mais algumas subdivisões. que podem variar em:
- Durabilidade
- **IOPS** (Input output per second) Entrada e saida por segundo 

Para armazenar dados é recomendado HDD, para rodar sistema operacional recomendado SSD

### Load Balancer (Servico -> Elastic Load Balancer)
Responsável por fazer o balanceamento de carga entre serviços replicados, assim aumentando a capacidade de carga em uma aplicação

Existem 3 tipos de load balancer:

#### Application
- Inteligente, visualiza dados na camada da aplicação e redistribui com base nesses dados
#### Network
- Não se preocupa com os dados, mas sim de onde vem essa requisição
#### Classic
- Junção do network e application

### Auto Scaling
Serviço que monitora e aumenta recursos automaticamente conforme a demanda aumenta, para isso temos que definir:
- Grupos, a qual grupo pertence o scaling
- Template, qual tipo de instância irá subir 
- Options, definição quantas máquinas irá subir, o máximo e mínimo, etc. Exemplo quero que suba 20 máquinas novas quando tiver X tráfego

#### Estratégias de auto scaling
- All times
  - definimos o número mínimo de instâncias e máximo, ele sempre vai manter no mínimo o minimo definido e se a carga aumentar irá subir máquinas até chegar no máximo
- Scale manual
  - Pouco usado, o usuário informa manualmente quantas máquinas quer subir ou derrubar
- Schedule
  - Agendamos datas e horários específicos para subir ou derrubar máquinas, ex: se meu serviços só tem tráfego no final de semana, durante a semana eu quero 3 máquinas e no final de semana eu quero 10
- Demand
  - Defino um número máximo de máquinas e seto regras para subir novas, por exemplo, sempre que der 50% de uso de um máquina, quero que suba uma nova
- Preditivo
  - Se baseaia em métricas de outros serviços e escala conforme os outros tem um uso maior
<hr> 
<div id="s3"></div> 

## Storage S3
O Amazon S3 é um armazenamento de objetos criado para armazenar e recuperar qualquer quantidade de dados de qualquer local na Internet. Ele é um serviço de armazenamento simples que oferece uma infraestrutura de armazenamento de dados com escalabilidade infinita a um custo bastante reduzido.

Características:
- Object-Based Storage, onde armazenamos arquivos
- **Não é um Block-Based Storage**, por tanto **não podemos instalar nenhum SO nele**
- Tamanho de um arquivo pode variar **entre 0 e 5TB**
- Bucket (como se fosse uma "pasta" de arquivos)
- Cada bucket tem que ter um nome único global
- Podemos fazer upload, download e visualização de um arquivo
- Tamanho ilimitado de storage

### Tipos de armazenamento S3
O Amazon S3 oferece uma ampla variedade de classes de armazenamento para diferentes casos de uso. 
- S3 Standard, para armazenamento geral de dados acessados com frequência
- S3 Intelligent-Tiering, para dados com padrões de acesso desconhecido ou dinâmico
- S3 Standard-Infrequent Access (S3 Standard – IA) 
- S3 One Zone-Infrequent Access (S3 One Zone – IA) para dados de longa vida, mas acessados com menos frequência 
- S3 Glacier (S3 Glacier) e Amazon S3 Glacier Deep Archive (S3 Glacier Deep Archive) para preservação digital e arquivamento de dados de longo prazo. 

### S3 Preço
Pagamos pelo armazenamento e também pela taxa de transferência (seja download ou upload), os valores podem variar de região para região, devido aos impostos dos locais

<hr> 
<div id="iam"></div> 

## IAM ( Identity Access Management)
Gerenciador de acesso da AWS, onde podemos criar usuário, grupos e etc dentro da conta AWS. Podemos setar roles, regras e permissões/políticas para acessar um determinado recursos
- Não é boa prática utilizar conta root da AWS.

<hr> 
<div id="pricing"></div> 

## Cobrança e preços
A AWS tem uma filosofia quanto ao pagamento, `cliente sempre está em primeiro lugar, proteja seu cliente e você estará protegendo sua empresa`.
Todos os serviços são pagos por segundos
- Pago conforme uso, conta no início do mês é 0, e conforme vai usando o valor incrementa, até final do mês quando é pago
- Pago de acordo com o uso
- Pague menos por quanto mais você utilize, conforme seu uso for maior, os preços começam a diminuir
- Pague muito menos quando você reserva, serviços que são do tipo reserved, quando você reserva aquele serviço, ficará mais barato do que on demand

#### CAPEX Vs OPEX
- CAPEX (Capital Expenditure) - Você paga antes de utilizar, valor fixo e mais caro
- OPEX (Operation Expenditure) - Paga de acordo com o que você utiliza

### Budget Vs Cost Explorer
- Budget - Orçamento que colocamos na AWS
  - Possível criar alertas em cima desse orçamento
  - Antes de atingir
- Cost Explorer - Relatório do que foi gasto
  - Mostrará com o que foi gasto
<hr> 

#### Planos da AWS para suporte
Temos 4 tipos de planos para suporte da AWS
- Básico (free)
  - Incluido em todas as contas, suporte é selfm então você tem que buscar as coisa dentro da base de suporte, temos também checagem de status da conta
- Developer ($29 / mês)
  - tudo o que tem no básico, e tem email direto para o suporte, com limite de 1 email de suporte por hora, com SLA de resposta de até 12h
- Business ($100 / mês)
  - Tudo que tem no developer, mas com limites maiores de suporte e tempo de resposta menor
- Enterprise (a partir de $15000 / mÊ)
  - Tudo o que tem no busines, mas com limites maiores e suporte com tempo de resposta menor
  - Gerente de tecnologia para ajudar em seus problemas
<div id="security"></div> 

## Segurança

<hr> 
<div id="links"></div> 

## Referências
