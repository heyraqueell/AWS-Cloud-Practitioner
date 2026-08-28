# Computação na AWS

A AWS oferece diferentes opções de computação para atender a diversos tipos de cargas de trabalho. Elas podem ser divididas em **quatro categorias principais**: **máquinas virtuais (VMs), contêineres, PaaS e computação sem servidor (serverless)**. Além delas, existem **soluções especializadas** para necessidades específicas.

<img width="1156" height="356" alt="image" src="https://github.com/user-attachments/assets/08850cda-edd0-455a-b5fe-32cca40a177a" />


**Máquinas virtuais:** o **Amazon EC2** fornece servidores virtuais seguros e redimensionáveis na nuvem, enquanto o **Amazon Lightsail** oferece servidores privados virtuais para cargas de trabalho simples e de baixo custo.

**Contêineres:** o **Amazon ECS** permite executar aplicações em contêineres Docker na AWS.

**PaaS:** o **AWS Elastic Beanstalk** executa aplicações web e serviços desenvolvidos em linguagens como Java, .NET, PHP, Node.js, Python, Ruby, Go e Docker.

**Serverless:** o **AWS Lambda** executa código sem que seja necessário gerenciar servidores, suportando Java, Go, PowerShell, Node.js, C#, Python e Ruby. O **AWS Fargate** também é serverless e fornece computação para **contêineres**.

# Amazon EC2

**O EC2 no Amazon EC2 significa Elastic Compute Cloud:**

- **Elastic:** Se refere ao fato de que é possível aumentar ou reduzir facilmente o número de servidores que você executa para oferecer suporte a um aplicativo automaticamente. Elasticidade é adaptação à demanda.
- **Compute:** Se refere ao motivo pelo qual a maioria dos usuários executa servidores: para hospedar aplicativos em execução ou para processar dados. Essas ações exigem recursos de computação, incluindo capacidade de processamento (CPU) e memória (RAM).

O Amazon EC2 oferece máquinas virtuais na nuvem e controle administrativo total sobre o sistema operacional ***Microsoft Windows*** ou ***Linux*** executado na instância.

- Um sistema operacional executado em uma máquina virtual geralmente é chamado de ***SO convidado*** para distingui-lo do sistema operacional host.

Com o Amazon EC2, é possível iniciar qualquer número de instâncias, de qualquer tamanho, em qualquer Zona de Disponibilidade e em qualquer lugar do mundo em minutos.

As instâncias são iniciadas em **imagens de máquinas da Amazon** **(AMIs)**, que são efetivamente modelos de máquina virtual.

É possível controlar o tráfego de ida e volta de instâncias usando security groups. Além disso, como os servidores são executados na nuvem AWS, é possível construir soluções que utilizam vários serviços da AWS.

---

## Amazon Machine Image (AMI)

Uma **Amazon Machine Image (AMI)** é um **modelo (template) usado para criar uma instância EC2**.

Ela contém as informações necessárias para iniciar uma máquina virtual, como:

- **Sistema operacional** (Linux, Windows etc.)
- **Aplicações e softwares** instalados
- **Configurações** do sistema
- Permissões e outras definições necessárias para inicialização

---

## Instância

O Amazon EC2 oferece uma seleção de tipos de instâncias, para se adequarem a diferentes casos de uso. Os tipos de instância tem combinações variadas de **CPU**, **memória**, **armazenamento** e **capacidade de rede**.

### Denominação e tamanhos de tipo de instância

O nome de um tipo de instância do EC2 tem várias partes. Por exemplo: **t3.large**

- T é o nome da família
- O número é o número de geração desse tipo (Em geral, quanto mais alto o número, mais poderosos são).
- large é o tamanho da instância.

Sintaxe de uma instância: ***família***+ ***geração*** + ***tamanho***.

Também é importante observar que a largura de banda da rede também está vinculada ao tamanho da instância do EC2.

### Casos de uso de tipo de instância

Os tipos de instância variam de várias maneiras, incluindo o tipo de **CPU**, a **contagem de CPUs** ou de **núcleos**, **tipo de armazenamento**, **quantidade de armazenamento**, **quantidade de memória** e **desempenho de rede**.

<img width="1135" height="442" alt="image" src="https://github.com/user-attachments/assets/5f51b7a5-d8b2-4bdf-b46f-411cd38df50b" />


| Tipo | Foco | Principais usos |
| --- | --- | --- |
| **T3** | **Uso geral** | Sites, aplicações web, desenvolvimento, testes, microsserviços e servidores de compilação. Possui **CPU com capacidade de intermitência**. |
| **C5** | **Computação** | Cargas intensivas de CPU, processamento em lote, modelagem científica, jogos, anúncios e codificação de vídeo. |
| **R5** | **Memória** | Bancos de dados de alto desempenho, análise de dados, caches, processamento de Big Data e aplicações empresariais. |

---

## Recursos de rede

Além de considerar as necessidades de CPU, de RAM e de armazenamento das cargas de trabalho, também é importante considerar os requisitos de **largura de banda de rede**.

Cada tipo de instância oferece um nível de desempenho de rede documentado. Por exemplo, uma instância **a1.medium** fornecerá até **10 Gbps**, mas uma instância **p3dn.24xlarge** fornece até **100 Gbps**. Escolha um tipo de instância que atenda aos seus requisitos.

## Definições de rede

Depois de escolher uma AMI e um tipo de instância, especifique o local da rede em que a instância do EC2 será implantada. Escolha a Região antes de iniciar o Assistente de execução de instância.

- Ao iniciar uma instância em uma Virtual Private Cloud (VPC) padrão, a AWS atribuirá a ela um endereço IP público.
- Ao iniciar uma instância em uma VPC **não** padrão, a sub-rede tem um atributo que determina se as instâncias iniciadas naquela sub-rede recebem um endereço IP público do grupo de endereços IPv4 públicos.

---

## Função do IAM (opcional)

É possível anexar uma função do IAM ao iniciar a instância, mas também é possível anexar uma função a uma instância do EC2 já em execução. 

Ao definir uma função que pode ser usada por uma instância do EC2, você define quais contas ou serviços da AWS podem assumir a função. 

Você também define quais ações e recursos da API o aplicativo pode usar depois de assumir a função. Se você alterar uma função, a alteração será propagada para todas as instâncias com a função anexada.

---

## Script de dados do usuário (opcional)

Ao criar suas instâncias do EC2, você tem a opção de ***transmitir dados do usuário*** para a instância. Os dados do usuário podem **automatizar** a **conclusão de instalações** e **configurações ao iniciar** a instância. 

Por exemplo, um script de dados do usuário pode aplicar patches e atualizar o sistema operacional da instância, obter e instalar chaves de licença de software ou instalar software adicional.

*Quando a instância do EC2 é criada, o script de dados do usuário será executado com os privilégios do usuário raiz da conta da AWS durante as fases finais do processo de inicialização. Em instâncias do Linux, ele é executado pelo serviço cloud-init. Em instâncias do Microsoft Windows, ele é executado pelo utilitário EC2Config ou EC2Launch. Por padrão, os dados do usuário são executados apenas na primeira vez que a instância é iniciada. Entretanto, se quiser que o script de dados do usuário seja executado sempre que a instância for inicializada, crie um script de dados do usuário como um arquivo de várias partes no formato Multipurpose Internet Mail Extensions (MIME)(esse processo não é comum).*

---

## Especificar armazenamento

Ao criar uma **instância EC2**, você pode definir quais **armazenamentos (volumes)** ela terá.

O principal é o **volume raiz**, onde normalmente fica instalado o **sistema operacional**. Também é possível adicionar outros volumes para armazenar dados separados.

Exemplo:

```jsx
EC2
│
├── Volume raiz → 30 GB → Sistema operacional
│
└── Volume adicional → 100 GB → Dados da aplicação
```

### Opções de armazenamento

#### Amazon EBS

Armazenamento **em bloco, persistente** e de **alto desempenho**, usado principalmente com **EC2**. Indicado para aplicações que exigem **muitas operações de leitura** e **gravação**. Possui diferentes tipos de volume para equilibrar **custo e desempenho** e permite aumentar o tamanho e ajustar o desempenho sem interromper a aplicação.

**Exemplos:**

- Banco de dados em uma EC2.
- Sistema operacional e aplicações de uma EC2.
- Aplicações com muitas operações de leitura/gravação.

#### Amazon EC2 Instance Store

Armazenamento **em bloco temporário (efêmero)**, localizado fisicamente no host da EC2. É indicado para dados que podem ser **perdidos**, como **caches, buffers e arquivos temporários**. Os dados são **excluídos quando a instância é interrompida ou apresenta falha**.

**🔑 Palavra-chave:** **armazenamento temporário da EC2.**

#### Amazon EFS

Sistema de arquivos **gerenciado, compartilhado e elástico**, baseado em **NFS**. Pode ser acessado por várias instâncias e **aumenta ou diminui automaticamente** conforme os arquivos são adicionados ou removidos, sem necessidade de provisionar capacidade previamente.

**Exemplos:**

- Armazenamento que precisa crescer automaticamente.

**🔑 Palavra-chave:** **sistema de arquivos compartilhado.**

#### Amazon S3

Serviço de **armazenamento de objetos**, altamente **escalável, disponível, seguro e durável**. Pode armazenar grandes quantidades de dados para diversos usos.

**Exemplos:**

- Backups.
- Imagens, vídeos e arquivos de sites/aplicações.
- Dados para análise de Big Data.

**🔑 Palavra-chave:** **armazenamento de objetos.**

#### Caso de uso

O **Amazon EBS** oferece armazenamento persistente para instâncias EC2, mantendo o sistema operacional e os dados mesmo após uma parada e reinicialização da instância. Já o **armazenamento de instâncias (Instance Store)** é temporário: seus dados são perdidos quando a instância é encerrada ou reiniciada. Por isso, ele é indicado para informações temporárias, como **cache, buffers e dados de scratch**, enquanto dados importantes e de longo prazo devem ser armazenados em serviços duráveis, como **EBS, EFS ou S3**.

---

## Adicionar tags

**Tag** é uma forma de **identificar e organizar recursos da AWS**, como instâncias EC2, volumes e VPCs. Ela funciona como uma **etiqueta** que você coloca em um recurso para saber o que ele representa.

Uma tag é formada por:

- **Chave (Key)** → categoria da informação.
- **Valor (Value)** → informação específica daquela categoria.

**Exemplo:**

```powershell
Key: Ambiente
Value: Produção
```

---

## Security Group

Um security group é um **conjunto de regras de firewall** que controlam o tráfego para a instância. Ele controla **quais conexões podem entrar e sair** da instância.

Ele funciona por meio de **regras**, que definem:

- **Protocolo** → TCP, UDP, ICMP etc.
- **Porta** → por exemplo, 22, 80 ou 443.
- **Origem/Destino** → de onde a conexão pode vir ou para onde pode ir.

Ao criar uma instância em uma VPC, é necessário associá-la a um Security Group, podendo usar um existente ou criar um novo.

As regras podem ser alteradas a qualquer momento e as mudanças são aplicadas automaticamente às instâncias associadas.

Por padrão, o Security Group permite todo o tráfego de saída, mas isso pode ser restringido. 

- Listas de controle de acesso à rede (Network ACLs) também podem ser usadas como firewalls para proteger sub-redes em uma VPC.

---

## Par de chaves

O Amazon EC2 usa criptografia de chave pública para criptografar e decodificar as informações de login. 

A tecnologia usa uma **chave pública** para **criptografar** uma parte dos dados. 

Em seguida, o destinatário usa a **chave privada** para **decodificar** os dados. As chaves pública e privada são conhecidas como um **par de chaves**. 

- A criptografia de chave pública permite acessar as instâncias com segurança usando a chave privada em vez de uma senha.

Ao iniciar uma instância, você especifica um par de chaves. É possível especificar um par de chaves existente ou um novo par de chaves que você cria ao iniciar a instância. 

- Se você criar um novo par de chaves, baixe e salve em um local seguro. Essa é a única chance que você tem de salvar o arquivo de chave privada.

---

## Modelos de preço do Amazon EC2

#### **Instâncias sob demanda**

- Pagamento por hora.
- Maior flexibilidade, sem contratos de longo prazo e taxas baixas.
- Qualificado para o nível gratuito da AWS.
- Os preços das instâncias sob demanda funcionam bem para cargas de trabalho com picos ou se você apenas precisa testar ou executar um aplicativo por um breve período (por exemplo, durante o desenvolvimento ou testes de um aplicativo).

#### **Hosts dedicados**

- Um servidor físico com capacidade de instância do EC2 totalmente dedicada para o seu uso.
- Uma boa opção se tiver restrições de licenciamento para o software que quer executar no Amazon EC2 ou requisitos específicos de conformidade ou regulamentares que impedem o uso de outras opções de implantação.

#### **Instâncias dedicadas**

- Instâncias que são executadas em uma VPC em hardware dedicado a um único cliente.

#### **Instâncias reservadas**

- Pagamento total, parcial ou sem pagamento antecipado para a instância que você reservar.
- Desconto na cobrança por hora para essa instância.
- Período de um ou três anos.
- Uma boa opção se você tiver necessidades de computação previsíveis ou estáveis (por exemplo, uma instância que você sabe que quer manter a execução durante meses ou anos).

#### **Instâncias reservadas programadas**

- Compre uma reserva de capacidade que esteja disponível em uma programação recorrente especificada por você. Período de um ano.

#### **Instâncias spot**

- As instâncias são executadas desde que estejam disponíveis e sua sugestão de preço esteja acima do preço da instância spot
- Elas **podem ser interrompidas pela AWS** com uma notificação enviada com **2 minutos** de antecedência
- As opções de interrupção incluem encerrada, interrompida ou hibernada
- Os **preços** podem ser **bem menores** em comparação às instâncias sob demanda
- É uma boa opção se tiver flexibilidade sobre quando os aplicativos podem ser executados
- Oferece grande escala por um preço significativamente menor.

***Faturamento por segundo*** está disponível para instâncias sob demanda, instâncias reservadas e instâncias spot que executam o Amazon Linux ou Ubuntu.
