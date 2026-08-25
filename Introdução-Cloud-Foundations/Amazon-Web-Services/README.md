# Serviços Web

A AWS oferece três modelos diferentes de serviços de nuvem: infraestrutura como serviço, plataforma como serviço e software como serviço. Todos esses serviços estão na nuvem AWS.

**Infraestrutura como serviço** (IaaS): Você gerencia o **servidor**, que pode ser físico ou virtual, e o **sistema operacional** (Microsoft Windows ou Linux). Em geral, o provedor de data center não tem acesso ao seu servidor.

Os componentes básicos de TI na nuvem incluem: 

- Recursos de rede
- Computação
- Espaço de armazenamento de dados

**Plataforma como serviço** (PaaS): Um terceiro gerencia o hardware e os sistemas operacionais subjacentes. Dessa forma, é possível executar aplicativos sem gerenciar a infraestrutura subjacente (aplicação de patches, atualizações, manutenção, hardware, sistemas operacionais). O PaaS também oferece uma estrutura para desenvolvedores que pode ser usada na construção de aplicativos personalizados.

**Software como serviço** (SaaS): Você gerencia seus arquivos e o provedor de serviços gerencia todos os data centers, servidores, redes, armazenamento, manutenção e aplicação de patches. Você apenas precisa se preocupar com o software e saber como quer usá-lo. O Facebook e o Dropbox são exemplos de SaaS. Você gerencia seus contatos do Facebook e os arquivos do Dropbox, e os provedores de serviços gerenciam os sistemas. 

## O que são Serviços Web?

Um serviço web é qualquer software disponibilizado pela Internet ou em redes privadas (intranet). Um serviço web usa um formato padronizado para solicitação e resposta de uma interação de interface de programação de aplicativo (API). Um serviço web é autodescrito por meio de um arquivo de definição de interface e é detectável.

---

# Serviços da AWS

A AWS é um provedor de serviços de nuvem seguro que oferece diversos serviços para ajudar as empresas a dimensionar e a crescer.

V eja a seguir algumas outras ofertas de Computação da AWS que podem ser selecionadas para uso nos exemplos de casos de uso:

- **Amazon EC2**: você quer ter controle total sobre seus recursos de computação da AWS.
- **AWS Lambda**: você quer executar seu código e não gerenciar ou provisionar servidores.
- **AWS Elastic Beanstalk**: você quer um serviço que implante, gerencie e dimensione aplicativos web para você.
- **Amazon Lightsail**: você precisa de uma plataforma em nuvem leve para um aplicativo web simples.
- **AWS Batch**: você precisa executar centenas de milhares de cargas de trabalho em lote.
- **AWS Outposts**: você quer executar a infraestrutura da AWS em seu data center no local.
- **Amazon Elastic Container Service** (Amazon ECS), **Amazon Elastic Kubernetes Service** (Amazon EKS) ou **AWS Fargate**: você quer implementar uma arquitetura de micros serviços ou de contêineres.
- **VMware Cloud on AWS**: você tem uma plataforma de virtualização de servidor no local e quer migrá-la para a AWS.

Da mesma forma, é possível escolher entre vários serviços nas outras categorias, e o número de ofertas continua a crescer.

## Três maneiras de interagir com a AWS

**Console de gerenciamento da AWS | AWS Management Console**

- Interface gráfica
- O console também pode ser acessado em um aplicativo móvel

**AWS Command Line Interface | AWS CLI**

- Acesso a serviços por meio de comandos ou scripts discretos

**Kits de Desenvolvimento de Software da AWS | SDKs**

- Acesse serviços diretamente do seu código (como Java, Python e outros).

## AWS Cloud Adoption Framework (AWS CAF)

O **AWS CAF** é uma estrutura que ajuda organizações a **planejar e executar a migração para a nuvem** de forma eficiente.

- O sucesso depende do alinhamento entre **pessoas, processos e tecnologia**.
- Ajuda a **desenvolver habilidades**, adaptar processos e aproveitar melhor os serviços de nuvem.

Divide o planejamento da migração em **6 perspectivas (perspectives)**:

- **Negócios** → objetivos e resultados do negócio.
- **Pessoas** → habilidades e organização.
- **Governança** → gestão e controle.
- **Plataforma** → infraestrutura e tecnologia.
- **Segurança** → proteção dos recursos e dados.
- **Operações** → gerenciamento e funcionamento dos sistemas.

---

# Modelo de preço da AWS

Há três fatores fundamentais de custo com a AWS: ***Computação***, ***armazenamento*** e ***transferência de dados de saída***. Essas características variam um pouco, dependendo do produto da AWS e do modelo de preço escolhidos.

| Computação | Armazenamento | Transferência de dados |
| :--- | :--- | :--- |
| Cobrada por hora/segundo. | Cobrado normalmente por GB. | A saída é agregada e cobrada. |
| Varia por tipo de instância. | | A entrada não tem cobrança (com algumas exceções). |
| | | Cobrado normalmente por GB. |


## Como você paga pela AWS?

<img width="1431" height="516" alt="image" src="https://github.com/user-attachments/assets/3e4f32c7-914f-4b90-abff-3759954b2a68" />

- Todos os serviços da AWS estão disponíveis sob demanda, sem a exigência de contratos de longo prazo nem dependências de licenciamento complexo.
- Pague apenas pelo que usar e pelo tempo que precisar.

### Pague menos ao fazer reserva

Para serviços específicos, como o ***Amazon Elastic Compute Cloud*** (**Amazon EC2**) e o ***Amazon Relational Database Service*** (**Amazon RDS**), é possível investir em capacidade reservada. Com instâncias reservadas, é possível economizar significantemente em relação à capacidade sob demanda equivalente. As instâncias reservadas estão disponíveis em três opções: 

- Instância reservada com pagamento **total** antecipado (ou AURI) - **Maior** desconto
- Instância reservada com pagamento antecipado **parcial** (ou PURI) - **Menos** desconto
- Instância reservada **sem** pagamento antecipado (ou NURI) - **Menor** desconto

### Pague menos usando mais

- **Preços em Camadas:** Serviços como **Amazon S3**, **EBS** e **EFS** utilizam modelos de **preço em camadas**, onde o custo por GB diminui conforme o volume de uso aumenta.
- **Transferência de Dados:** A entrada de dados para a AWS não gera cobranças.
- **Otimização por Necessidade:** É possível reduzir custos escolhendo soluções de armazenamento alinhadas à frequência de acesso e ao desempenho necessário, garantindo segurança e durabilidade.
- **Benefício:** O aumento do uso permite aproveitar economias de escala, mantendo os custos controlados à medida que a empresa evolui.

### Pague menos à media que a AWS cresce

A AWS se preocupa em reduzir o custo de fazer negócio, essas otimizações e as economias de escala substanciais e em expansão da AWS permitem repassar as economias de volta para o cliente na forma de preços mais baixos. Desde 2006, a AWS baixou o preço 76 vezes (dados de 2019).

Outro benefício do crescimento da AWS é que os recursos futuros e com maior desempenho substituem os atuais sem custo adicional.

### Modelo de preços personalizados

A AWS sabe que cada cliente tem necessidades diferentes. Se nenhum dos modelos de preço da AWS funcionar para o seu projeto, serão disponibilizados modelos de preços personalizados para projetos de alto volume com requisitos exclusivos.

### Nível gratuito da AWS

Para ajudar novos clientes da AWS a começar a usar a nuvem, a AWS oferece um nível gratuito (o Nível gratuito da AWS) para novos clientes por até um ano. 

- O Nível gratuito da AWS é aplicável a serviços e opções específicos.

## Calculadora de Preço

A calculadora de preço da AWS pode ajudar a estimar a fatura mensal da AWS. Usando essa ferramenta, é possível adicionar, modificar e remover serviços da fatura. Ela recalculará as cobranças mensais estimadas automaticamente.

A calculadora de preço da AWS é uma ferramenta que ajuda você a: 

- Estimar os custos mensais dos serviços da AWS
- Identificar oportunidades de redução de custos
- Usar modelos para modelar soluções para comparar modelos de implantação e serviços

### Custo total de propriedade (TCO)

O TCO é uma estimativa financeira que calcula os custos diretos e indiretos (incluindo despesas correspondentes) de um produto ou sistema. Permite comparar os custos entre executar cargas de trabalho em infraestruturas locais (on-premises / colocation) versus na nuvem.

**Aplicação:** Ideal para auxiliar no orçamento e na construção de um caso de negócio para definir a melhor estratégia de implantação.
