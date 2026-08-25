# Modelo de Responsabilidade compartilhada

A segurança é a maior prioridade na AWS. Depois que o cliente começa a usar a AWS, a Amazon compartilha a responsabilidade de proteger os dados na nuvem AWS, o que torna a segurança da AWS uma responsabilidade compartilhada. Esse conceito é conhecido como modelo de responsabilidade compartilhada. 

### Segurança DA nuvem

A AWS é responsável pela segurança **da** nuvem. Mas o que isso significa?

Isso significa que a AWS é responsável por proteger a infraestrutura global que executa todos os serviços oferecidos na nuvem AWS, que incluem as Regiões, as Zonas de Disponibilidade e os locais de borda da AWS.

- **Segurança física dos data centers**: com acesso controlado e baseado em necessidades; localizados em instalações não identificadas e etc.
- **Infraestrutura de hardware:** incluindo servidores, serviços de armazenamento e outros recursos dos quais os serviços da AWS dependem.
- **Infraestrutura de software**: que hospeda sistemas operacionais, aplicativos de serviços e software de virtualização.
- **Infraestrutura de rede**: como roteadores, roteadores, balanceadores de carga, firewalls e cabeamento.
- **Infraestrutura de virtualização**: incluindo isolamento de instâncias.

### Segurança **NA** nuvem

Embora a infraestrutura de nuvem seja protegida e mantida pela AWS, os clientes são responsáveis pela segurança de tudo o que colocam na nuvem.

As etapas de segurança que um cliente deve seguir dependem dos serviços usados e da complexidade do sistema.

Essas etapas incluem: selecionar o sistema operacional da instância, proteger o aplicativo, configurar os security groups e os firewalls e gerenciar a configuração de rede e as contas dos usuários.

<img width="763" height="410" alt="image" src="https://github.com/user-attachments/assets/46c697f5-f438-4df3-a6ab-d7b5b417a610" />


## Caso de Uso

Nesse cenário, o cliente utiliza o Amazon S3 para armazenamento e configura uma Amazon VPC para executar uma instância do EC2 e um banco de dados Oracle.

O cliente é totalmente responsável pelo gerenciamento da instância do EC2, o que inclui atualizar o sistema operacional convidado, aplicar patches de segurança, manter os softwares instalados, configurar o firewall (security group) e definir as condições de rede na VPC.

A responsabilidade pelo banco de dados Oracle varia conforme a forma de execução: se rodar em uma instância do EC2, o cliente deve gerenciar as atualizações e patches. Entretanto, se o banco de dados for executado como uma instância do Amazon RDS, a AWS será responsável por aplicar atualizações e patches de software da Oracle. Como o **Amazon RDS é uma oferta de banco de dados gerenciada**, as tarefas demoradas de administração de banco de dados (que incluem provisionamento, backups, aplicação de patches de software, monitoramento e dimensionamento de hardware) são processadas pela AWS.

## Conclusão

- A AWS é responsável por proteger a infraestrutura.

- O cliente é responsável por executar as tarefas necessárias de configuração e de gerenciamento de segurança.
