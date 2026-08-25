# Serviços e Categorias

A AWS oferece um amplo conjunto de serviços baseados na nuvem em diferentes categorias de produto ou serviço. Cada categoria é composta por um ou mais serviços.

<img width="1204" height="548" alt="image" src="https://github.com/user-attachments/assets/0955fe60-7439-4ce7-aafe-287ca0faf130" />


## Categoria de serviço de Armazenamento

Os serviços de armazenamento da AWS incluem os serviços listados aqui e muitos outros:

**Amazon Simple Storage Service (Amazon S3):** é um serviço de **armazenamento de objetos** que oferece escalabilidade, disponibilidade de dados, segurança e desempenho. Use para **armazenar** e **proteger** qualquer quantidade de dados para sites, aplicativos móveis, backup e restauração, arquivo, aplicativos empresariais, dispositivos da Internet das Coisas (IoT) e análises de big data. 

**Amazon Elastic Block Store (Amazon EBS):** Armazenamento em bloco de alto desempenho projetado para uso com o Amazon EC2, ideal para cargas de trabalho intensivas em transações e transferência, como bancos de dados, aplicativos empresariais, contêineres e sistemas de arquivos.

**Amazon Elastic File System (Amazon EFS):** Sistema de arquivos NFS totalmente gerenciado, dimensionável e elástico para serviços da nuvem AWS e recursos locais, que cresce e diminui automaticamente sob demanda até petabytes, reduzindo a necessidade de provisionar capacidade.

**Amazon Simple Storage Service Glacier:** Classe de armazenamento de baixo custo do S3 para arquivamento e backup de longo prazo, projetada com 11 noves (99,99999999999%) de durabilidade e recursos rigorosos de segurança e conformidade.

## Categoria de serviço de Computação

**Amazon Elastic Compute Cloud** **(Amazon EC2)**: oferece uma capacidade de computação redimensionável como máquinas virtuais na nuvem.

**Amazon EC2 Auto Scaling**: permite adicionar ou remover automaticamente instâncias de EC2 de acordo com as condições definidas. 

**AWS Elastic Beanstalk**: é um serviço para implantação e dimensionamento de aplicativos e serviços web em servidores familiares, como Apache HTTP Server e Microsoft Internet Information Services (IIS). 

**AWS Lambda**: permite executar código sem provisionamento ou gerenciamento de servidores. Você paga apenas pelo tempo de computação que consome, portanto não será cobrado quando o código não estiver em execução.

## Categoria de serviço de Contêineres

**Amazon Elastic Container Service (Amazon ECS):** é um serviço de orquestração de contêineres altamente dimensionável e de alto desempenho compatível com contêineres Docker.

**Amazon Elastic Container Registry (Amazon ECR):** é um registro de contêineres Docker totalmente gerenciado que facilita aos desenvolvedores o armazenamento, gerenciamento e implantação de imagens de contêineres Docker.

**Amazon Elastic Kubernetes Service (Amazon EKS):** facilita a implantação, gerenciamento e dimensionamento de aplicativos em contêineres que usam Kubernetes na AWS.

**AWS Fargate:** é um mecanismo de computação para Amazon ECS que permite executar contêineres sem gerenciar servidores ou clusters.

## Categoria de serviço de Banco de Dados

**Amazon Relational Database Service (Amazon RDS):** facilita a criação, operação e dimensionamento de um banco de dados relacional na nuvem. Oferece capacidade redimensionável enquanto automatiza tarefas administrativas demoradas, como provisionamento de hardware, configuração de banco de dados, aplicação de patches e backups.

**Amazon Aurora:** é um banco de dados relacional compatível com MySQL e PostgreSQL. É até cinco vezes mais rápido que os bancos de dados padrão MySQL e três vezes mais rápido que bancos de dados padrão PostgreSQL.

**Amazon Redshift:** permite executar consultas de análise contra petabytes de dados armazenados localmente no Amazon Redshift. Também é possível fazer consultas diretamente contra exabytes de dados armazenados no Amazon S3. Oferece um desempenho rápido em qualquer escala.

**Amazon DynamoDB**: é um banco de dados de documentos e chave-valor que oferece desempenho de milissegundos de um dígito em qualquer escala, com segurança, backup e restauração incorporados, bem como cache na memória.

## Categoria de serviço de Redes e Entrega de Conteúdo

**Amazon Virtual Private Cloud (Amazon VPC)**: permite provisionar seções logicamente isoladas da AWS Cloud.

**Elastic Load Balancing:** distribui automaticamente o tráfego de entrada de aplicações em diversos destinos, como instâncias EC2 da Amazon, contêineres, endereços IP e funções Lambda.

**Amazon CloudFront:** é um serviço rápido de rede de entrega de conteúdo (CDN) que entrega com segurança dados, vídeos, aplicativos e interfaces de programação de aplicativo (APIs) a clientes em todo o mundo, com baixa latência e alta velocidade de transferência.

**AWS Transit Gateway**: é um serviço que permite aos clientes conectar nuvens virtuais privadas (VPCs) e redes no local a um único gateway. 

**Amazon Route 53:** é um serviço web de sistema de nomes de domínio (DNS) dimensionável e em nuvem, projetado para proporcionar uma maneira confiável de encaminhar os usuários finais para aplicativos da Internet. Traduz nomes (like www.example.com) em endereços IP numéricos (like 192.0.2.1) que os computadores usam para se conectar mutuamente. 

**AWS Direct Connect:** oferece uma maneira de estabelecer uma conexão de rede privada dedicada de data center ou escritório à AWS, o que pode reduzir os custos de rede e aumentar a taxa de transferência da largura de banda.

**AWS VPN**: oferece um túnel privado seguro da sua rede ou dispositivo para a rede global da AWS.

## Categoria de serviço de **Segurança, Identidade e Conformidade**

**AWS Identity and Access Management (IAM):** permite gerenciar com segurança o **acesso** aos **serviços** e **recursos** da AWS. Com o IAM, você pode criar e gerenciar usuários e grupos da AWS. Pode usar as permissões do IAM para permitir e negar o acesso de usuários e grupos aos recursos da AWS.

**AWS Organizations** permite restringir quais serviços e ações são permitidos nas suas contas.

**Amazon Cognito** permite adicionar o controle de acesso, inscrição e conexão de usuários a aplicativos web e móveis.

**AWS Artifact** oferece acesso sob demanda aos relatórios de segurança e conformidade da AWS e seleciona acordos online. 

**AWS Key Management Service** (**AWS KMS**) permite criar e gerenciar chaves. É possível usar o AWS KMS para **controlar o uso de criptografia** em uma ampla variedade de serviços da AWS e seus aplicativos.

**AWS Shield** é um serviço gerenciado de proteção contra negação de serviço distribuída (DDoS) que protege os aplicativos executados na AWS.

## Categoria de serviço de **Gerenciamento de custos**

**AWS Cost and Usage Report** contém o conjunto mais abrangente de dados de custo e uso do AWS disponível, incluindo metadados adicionais sobre serviços, modelo de preço e reservas da AWS.

**AWS Budgets** permite definir orçamentos personalizados que alertam quando seus custos ou uso excedem (ou se houver previsão de exceder) o valor orçado.

**AWS Cost Explorer** tem uma interface fácil de usar que permite visualizar, compreender e gerenciar seus custos e uso da AWS ao longo do tempo.

## Categoria de serviço de **Gerenciamento e Governança**

**AWS Management Console** oferece uma interface de usuário baseada na web para acessar sua conta da AWS.

**AWS Config** oferece um serviço que ajuda a **rastrear** o **inventário** de **recursos** e **alterações**.

**Amazon CloudWatch** permite monitorar recursos e aplicativos.

**AWS Auto Scaling** oferece recursos que permitem dimensionar diversos recursos para atender à demanda.

**Serviço AWS Command Line Interface** oferece uma ferramenta unificada para gerenciar os serviços da AWS.

**AWS Trusted Advisor** ajuda a otimizar o desempenho e a segurança.

**AWS Well-Architected Tool** oferece ajuda na análise e melhoria de cargas de trabalho.

**AWS CloudTrail** rastreia a atividade do usuário e o uso de API.
