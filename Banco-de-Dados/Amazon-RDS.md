# Amazon Relational Database Service (Amazon RDS)

## O que é o Amazon RDS?

O **Amazon RDS (Relational Database Service)** é um serviço da AWS para executar **bancos de dados relacionais na nuvem** sem precisar cuidar manualmente de grande parte da infraestrutura.

Um banco de dados relacional organiza informações em **tabelas**, com linhas e colunas, e normalmente utiliza **SQL** para consultar e manipular os dados.

A grande ideia do RDS é: **Você cuida do banco de dados e da aplicação; a AWS cuida de grande parte da infraestrutura e das tarefas administrativas.**

Por exemplo, a AWS pode automatizar tarefas como:

- backups;
- recuperação;
- manutenção;

- provisionamento da infraestrutura;
- algumas tarefas de escalabilidade;
- alta disponibilidade.

Isso torna o RDS uma opção mais simples do que instalar e administrar um banco de dados diretamente em uma EC2.



# Quais bancos de dados o RDS suporta?

O Amazon RDS suporta vários mecanismos de banco de dados relacionais.

| Banco | Tipo |
|---|---|
| MySQL | Relacional |
| PostgreSQL | Relacional |
| MariaDB | Relacional |
| Oracle | Relacional |
| Microsoft SQL Server | Relacional |
| Amazon Aurora | Relacional desenvolvido pela AWS |


 **RDS não é um banco de dados específico.** Ele é um **serviço gerenciado** que permite utilizar diferentes mecanismos de banco de dados.

RDS = serviço da AWS para gerenciar bancos relacionais. Dentro dele você pode escolher, por exemplo, MySQL, PostgreSQL ou MariaDB.


# O que é uma instância de banco de dados?

Uma **instância de banco de dados (DB instance)** é o ambiente onde o seu banco de dados é executado. Ela possui recursos computacionais, como:

CPU, memória, armazenamento e rede.

A capacidade da instância depende principalmente da **classe da instância** escolhida.



# Backup do Amazon RDS

O RDS oferece **backups automáticos e manuais**. 

### Backup automático

O RDS pode realizar backups automaticamente durante uma **janela de backup** configurada.

Esses backups permitem recuperar os dados caso aconteça algum problema.

- O primeiro snapshot contém todos os dados.
- Os snapshots seguintes são **incrementais**.

Isso evita que cada snapshot precise armazenar novamente todos os dados.

Os backups automáticos possuem um **período de retenção**. Ou seja, você define por **quanto tempo** os backups automáticos devem ser mantidos.

### Backup manual

São snapshots do volume de armazenamento criados manualmente pelo próprio usuário. Diferente dos automáticos, esses backups não expiram sozinhos; eles permanecem salvos até que você os exclua explicitamente.

> **Snapshot = cópia do armazenamento da instância naquele momento.**
> 



# Alta disponibilidade com multi-AZ: replicação

Uma das funcionalidades mais importantes do RDS para garantir alta disponibilidade é a **implantação Multi-AZ (Múltiplas Zonas de Disponibilidade)**.

Nessa configuração, a AWS cria automaticamente uma cópia exata e síncrona do seu banco de dados (chamada de **instância em espera** ou *standby*) em uma Zona de Disponibilidade diferente, mas dentro da mesma VPC.

<img width="973" height="469" alt="image" src="https://github.com/user-attachments/assets/f91dbeb0-4caf-478c-a280-c2d90ac6df0b" />


### Como funciona o Failover?

Se a instância principal (primária) falhar por qualquer motivo (queda de energia, falha de hardware, etc.), o RDS executa um processo automático chamado **Failover**:

1. A instância em *standby* assume imediatamente o papel de instância primária.
2. O tráfego das aplicações é redirecionado automaticamente para a nova instância.
3. Como a replicação entre as zonas é **síncrona**, não há perda de dados.

As aplicações continuam acessando o banco pelo **endpoint DNS do RDS**, então não é necessário alterar o código da aplicação.

<img width="963" height="461" alt="image" src="https://github.com/user-attachments/assets/2dccfa7c-3e45-47db-bc06-49d23dd8e387" />


# Escalabilidade com Amazon RDS

O RDS permite aumentar a capacidade da instância alterando sua **classe de instância** ou seu **armazenamento**.

- Alterar a **classe** aumenta os recursos de **CPU e memória** disponíveis para a instância.
- Já aumentar o **armazenamento** aumenta a **capacidade** disponível para guardar dados, podendo ser feito **sem tempo de inatividade**.

**Atenção:** alterar a classe da instância exige tempo de inatividade.

### Réplicas de Leitura (Read Replicas)

Quando a sua aplicação realiza muitas consultas de leitura (como relatórios ou pesquisas de usuários), a instância principal pode ficar sobrecarregada. Para resolver isso, cria-se uma ou mais **Réplicas de Leitura**.

- A replicação de dados para as réplicas de leitura é **assíncrona**.
- O aplicativo redireciona o tráfego pesado de leitura para a réplica, aliviando a carga da instância principal.
- Podem ser criadas em regiões geográficas diferentes para aproximar os dados dos usuários locais ou para planos de recuperação de desastres.
- Uma Réplica de Leitura pode ser promovida a banco principal, mas isso exige **intervenção manual**.



# RDS x DynamoDB

| Amazon RDS | Amazon **DynamoDB** |
|---|---|
| Banco de dados **relacional** | Banco de dados **NoSQL** |
| Indicado para **transações e consultas complexas** | Indicado para solicitações simples de **GET ou PUT** |
| Utiliza mecanismos como MySQL, PostgreSQL e MariaDB | É uma solução de banco de dados **NoSQL** |
| Pode ser usado quando a aplicação precisa de um banco relacional | Pode ser usado quando o RDS não é adequado ao tipo de aplicação |



# Quando usar ou não usar o Amazon RDS?

| **Use** o Amazon RDS quando... | Não use o Amazon RDS quando... |
|---|---|
| A aplicação precisa de **transações**. | A aplicação precisa de solicitações simples de **GET ou PUT** que um banco NoSQL pode processar. |
| A aplicação precisa realizar **consultas complexas**. | A aplicação exige muita **personalização do sistema de gerenciamento do banco relacional**. |
| A aplicação precisa de **alta durabilidade**. | Nesse caso, pode ser utilizada uma solução NoSQL, como o **DynamoDB**. |
|  | Outra alternativa é executar o banco relacional em uma **instância EC2**, que oferece mais opções de personalização. |



# Casos de uso do Amazon RDS

O Amazon RDS é adequado para **aplicações web e móveis** que precisam de alta taxa de **transferência**, **escalabilidade de armazenamento** e **alta disponibilidade**.

Também pode ser utilizado em **comércio eletrônico**, oferecendo uma solução de banco de dados flexível, segura e econômica para vendas e varejo online.

Em **jogos online e para dispositivos móveis**, o RDS oferece alta taxa de transferência e disponibilidade, enquanto gerencia a infraestrutura do banco de dados.
