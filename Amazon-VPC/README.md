# Recapitulação das redes virtuais

Comparação entre **Topologia tradicional x Serviço da AWS**

| **Topologia tradicional** | **Serviço da AWS** |
| --- | --- |
| Data Center | Amazon VPC |
| Roteador | Tabela de rotas |
| Comutadores (sub-redes) | Sub-redes |
| Firewall | Grupo de segurança e lista de controle de acesso de rede (ACLs de rede) |
| Servidores e Sistemas operacionais | Instâncias do Amazon Elastic Compute Cloud (Amazon EC2) |
| Modem | Gateway de internet |

---

# Amazon VPC

A **Amazon VPC (Virtual Private Cloud)** é um serviço da AWS que permite criar uma **rede virtual privada e isolada dentro da nuvem**. Ela possibilita definir como os recursos da AWS, como instâncias EC2 e bancos de dados, serão organizados e como poderão se comunicar entre si e com a internet. 

A VPC oferece controle sobre aspectos de rede, como endereçamento IP, sub-redes, rotas e regras de acesso, permitindo criar uma infraestrutura de rede de acordo com as necessidades da aplicação.

# Pilares de Arquitetura do Amazon VPC

- **Conta AWS Dedicada:** A VPC é criada dentro da sua conta AWS, garantindo que o gerenciamento de permissões, cobrança e recursos computacionais (como instâncias EC2 e bancos de dados) fiquem sob sua total governança.
- **Escopo Regional (Uma Região AWS):** Cada VPC reside estritamente dentro de uma única Região geográfica da AWS (por exemplo, `sa-east-1` em São Paulo). Ela não ultrapassa fronteiras de regiões diretamente, servindo como o limite geográfico principal da sua rede.
- **Resiliência Multi-AZ (Zonas de Disponibilidade):** Embora a VPC pertença a uma única Região, ela pode abranger múltiplas Zonas de Disponibilidade (AZs). Isso permite criar sub-redes em diferentes data centers físicos independentes, garantindo alta disponibilidade e tolerância a falhas para a aplicação.
- **Isolamento Lógico:** Por padrão, uma VPC é completamente isolada de outras redes e de outras VPCs (mesmo dentro da mesma conta). O tráfego só entra ou sai se forem configurados componentes explícitos de conectividade, como Internet Gateways, NAT Gateways ou VPC Peering.

Uma VPC tem escopo regional para que a sua infraestrutura de rede nunca dependa de um único ponto de falha. Ao abranger várias Zonas de Disponibilidade, a VPC fornece a base para que seus servidores e bancos de dados operem em alta disponibilidade e redundância automática.


<img width="1095" height="636" alt="image" src="https://github.com/user-attachments/assets/6945c498-3b9f-4cbb-b7ed-7ad2b471d6e8" />


# Endereçamento IP na VPC

Ao criar uma VPC, você deve especificar o intervalo de endereços IPv4 escolhendo um bloco CIDR, como 10.0.0.0/16. 

- O intervalo de endereços de uma Amazon VPC pode ser tão grande quanto /16 (65.536 endereços) ou tão pequeno quanto /28 (16 endereços).
- Os intervalos de IPs privados devem ser usados de acordo com o guia RFC 1918.
- O intervalo de endereços IP de uma Amazon VPC é especificado como um bloco CIDR.

# Intervalo de endereços IP privados

O **CIDR** é apenas uma forma simplificada de dizer **onde uma rede começa** e **quantos endereços IP ela tem**.

- A notação sempre tem o formato: `IP / Prefixo` (exemplo: `10.0.0.0/16` ou `192.168.1.0/24`).
- O número depois da barra (CIDR) indica quantos bits são fixos para identificar a rede. O restante dos bits ficam livres para os dispositivos (hosts).

Ao criar uma Amazon VPC, escolha um bloco CIDR nos intervalos de endereços IPv4 privados.

| Intervalo do guia RFC 1918 | Exemplo de bloco CIDR de Amazon VPC |
| --- | --- |
| 10.0.0.0–10.255.255.255 | 10.0.0.0/16  |
| 172.16.0.0–172.31.255.255 | 172.31.0.0/16 |
| 192.168.0.0–192.168.255.255  | 192.168.0.0/16 |
- O menor tamanho de bloco permitido é /28, e o maior é /16.
- É possível usar um bloco CIDR publicamente roteável fora do intervalo privado, mas isso não é recomendado. Essa situação poderá causar problemas se você estiver usando recursos publicamente roteáveis para a internet.

# Conceitos importantes de uma VPC

- **Bloco CIDR:** defina um intervalo privado de /16 a /28.
- **Sub-redes:** aloque um intervalo de endereços IP na sua VPC.
- **Tabela de rota:** regras (também conhecidas como rotas) que a VPC utiliza para rotear tráfego.
- **Gateway de internet:** é anexado à sua VPC e permite a comunicação da VPC com a internet.
- **Endpoint de VPC:** uma conexão privada entre serviços da AWS sem necessidade da internet.

**Maneiras comuns de acessar a Amazon VPC:**

- Console de gerenciamento da AWS
- AWS Command Line Interface (AWS CLI)

## Componentes da Amazon VPC

 Componentes para configurar redes em uma Amazon VPC:

- Amazon VPC
- Gateway de internet
- Gateway de conversão de endereços de rede (NAT)
- Tabela de rota
- Sub-redes pública e privada
- Grupos de segurança
- ACLs de rede

# Gateway de internet

<details>
    <summary>Demonstração</summary>

  <img width="554" height="478" alt="image" src="https://github.com/user-attachments/assets/ddb9c37e-2ea9-468c-a276-ab3a9093685b" />

</details>

**O que é um gateway de internet?** 

**Um gateway de internet permite a comunicação da VPC com a internet.** Pode ser dimensionado horizontalmente para atender às necessidades de tráfego, ser redundante e ser altamente disponível. 
    

**Sub-rede pública:**

- **Está associada a uma tabela de rota que tem uma 
rota para o gateway de internet.**
- Terá a rota como 0.0.0.0/0 e o alvo como IGW-xxxxx.

**Endereço IP público:**

Para que uma instância se comunique pela internet, ela deve ter um endereço IPv4 público ou um endereço IP elástico.

# NAT Gateway

<details>
    <summary>Demonstração</summary>

<img width="489" height="684" alt="image" src="https://github.com/user-attachments/assets/886a481d-243f-42a2-a8e0-4807e423ac78" />


</details>


**O que é um NAT gateway?** 

Um gateway NAT permite que instâncias na sub-rede privada se conectem fora da VPC. No entanto, **nada de fora da VPC consegue iniciar uma conexão**. Um sinalizador RESET será enviado.

    

**Sub-rede pública:**

O gateway NAT recebe um endereço IP elástico, que é um endereço IP público e está localizado na sub-rede pública.

**Sub-rede privada:**

A rota será 0.0.0.0/0 e o alvo será nat-xxxxx na tabela de rota associada para a sub-rede privada.

**Endereço IP público:**

Devido ao NAT gateway, as instâncias na sub-rede privada não precisam de um endereço IP público.

## Resumo

A principal diferença é o **sentido da comunicação com a internet**:

**Internet Gateway:** Funciona como uma **rua de mão dupla**. Permite que recursos da VPC acessem a internet **e** que pessoas na internet acessem os recursos da VPC (usado em **Subnets Públicas**).

- Exemplo: O site da sua empresa recebe visitas de clientes de qualquer lugar do mundo.

**NAT Gateway:** Funciona como uma **catraca de saída (mão única)**. Permite que recursos da VPC saiam para a internet (para baixar atualizações, por exemplo), mas **impede** que qualquer pessoa de fora inicie uma conexão com eles (usado para proteger recursos em **Subnets Privadas**).

- Exemplo: O seu banco de dados privado precisa baixar um pacote de atualização de segurança da internet sem correr o risco de ser exposto a ataques diretos.

# Tabela de rotas

**O que é uma tabela de rota?** 

Contém rotas e alvos que direcionam o tráfego de rede na VPC. Ela define **para onde o tráfego deve ir** quando sai de uma subnet dentro de uma VPC.

- O destino é um endereço IP e intervalo CIDR (por exemplo, 0.0.0.0/0, que é a internet).
- Um alvo é um gateway ou uma interface de rede. Serve para o tráfego destinado.
- Cada tabela de rota deve ser associada a uma sub-rede. Uma tabela de rota associa a sub-rede a gateways.

# Sub-redes pública e privada

**O que é uma sub-rede:** É um intervalo de endereços IP dentro da VPC.

**Zona de Disponibilidade:** Há uma sub-rede por Zona de Disponibilidade porque uma sub-rede não pode abranger várias zonas.

**Sub-rede pública:** O tráfego é direcionado a um gateway de internet ao ter uma tabela de rota associada a um gateway de internet como uma rota.

**Sub-rede privada:** O tráfego não é direcionado para a internet.

**Dimensionamento de sub-rede**: Se mais de uma sub-rede for criada em uma VPC, os blocos CIDR das sub-redes não poderão se sobrepor.

# Grupo de Segurança

**Um grupo de segurança é um firewall na instância do EC2 que controla o tráfego de entrada e saída.** Os grupos de segurança são stateful.

- **Stateful** (com estado) significa que o firewall **tem memória**: se uma conexão de entrada for permitida, a resposta de volta para essa mesma conexão é **liberada automaticamente**, independentemente das regras de saída. O inverso também vale: se a instância iniciar um tráfego para fora, a resposta da internet poderá entrar automaticamente.

Um grupo de segurança **bloqueia todo tráfego por padrão**; você deve permitir o protocolo, o intervalo de portas, o tipo de ICMP (Internet Control Message Protocol)e a origem ou o destino.

# ACL de rede

ACL de rede atua como um firewall na **sub-rede**. Ele é Stateless.

- **Stateless** (Sem estado): Não tem memória. Você é obrigado a criar **explicitamente** duas regras: uma para deixar entrar e outra para deixar sair.

**Uma ACL padrão permite todo tráfego**: você pode criar regras para permitir ou negar tráfego.

**Uma ACL personalizada nega todo tráfego**: Bloqueia ou nega todo tráfego (entrada e saída) até adicionar regras.

As ACL de rede têm regras de entrada e saída separadas. Cada regra pode permitir ou negar tráfego em incrementos de 10 ou 100. 

# Exemplo de Amazon VPC

Esta imagem é um exemplo de uma Amazon VPC totalmente funcional

<img width="1136" height="732" alt="image" src="https://github.com/user-attachments/assets/6eaf96b0-9125-46f7-9f3f-c15d8c8a01d3" />


# O que pode ser usado com a Amazon VPC?

A **Amazon VPC** é um serviço fundamental da AWS que permite criar uma **rede virtual isolada dentro da nuvem**. Ela serve como base para a implantação e comunicação de diversos serviços da AWS.

Por exemplo, uma instância do **Amazon EC2** pode ser executada dentro de uma VPC. Outros serviços, como **Amazon RDS, DynamoDB, Elastic Load Balancing, Amazon S3 e Elastic Beanstalk**, também podem se integrar a uma VPC, dependendo da configuração e do serviço.

<img width="731" height="564" alt="image" src="https://github.com/user-attachments/assets/fe7ce125-96b1-45bf-aa78-f623da23c10b" />
