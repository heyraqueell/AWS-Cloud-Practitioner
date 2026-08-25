# Amazon S3 🪣

O Amazon S3 é uma solução gerenciada de armazenamento na nuvem que permite armazenar dados como objetos em um bucket. 


> Os objetos podem ser praticamente qualquer arquivo de dados, como documentos, imagens ou vídeos. 


Ao adicionar objetos a um bucket, dê a eles um nome exclusivo, denominado *chave de objeto*. 

Os buckets são contêineres lógicos para objetos. É possível ter um ou mais buckets na sua conta. Para cada bucket, é possível controlar o acesso, ou seja, quem pode criar, excluir e listar objetos no bucket. Também é possível visualizar logs de acesso do bucket e dos respectivos objetos e escolher a região geográfica em que o Amazon S3 armazenará o bucket e seu conteúdo. 

#### Resumo

- O Amazon S3 é um armazenamento em nível de objeto.
- É possível armazenar praticamente quantos objetos desejar, bem como gravar, ler e excluir objetos no bucket.
- Um único objeto pode ter até 5 terabytes (TB).
- Projetado para dimensionar ininterruptamente e oferecer mais de 11 noves (99,99999999999%) de durabilidade.
- Os dados armazenados no Amazon S3 não estão associados a nenhum servidor específico, e você não precisa gerenciar nenhuma infraestrutura diretamente.
- Os dados são armazenados de forma redundante.
- É possível recuperar dados a qualquer momento e em qualquer lugar pela Internet.
- Os nomes de buckets devem ser exclusivos entre todos os nomes de buckets existentes no Amazon S3.

## Classes de Armazenamento do Amazon S3

O Amazon S3 oferece diversas classes de armazenamento no nível do objeto projetadas para diferentes casos de uso. Essas classes incluem:

**Amazon S3 Standard:** oferece armazenamento de objetos com **alta durabilidade, alta disponibilidade e alto desempenho**, sendo indicado para dados acessados com frequência. Possui **baixa latência e alta taxa de transferência.**

- Adequado para aplicações em nuvem, sites dinâmicos, distribuição de conteúdo, aplicativos móveis e de jogos e análise de Big Data.

**Amazon S3 Intelligent-Tiering:** foi desenvolvido para **otimizar custos automaticamente**, movendo os dados para o nível de acesso mais econômico, sem impacto no desempenho. O S3 monitora os padrões de acesso e, após **30 dias sem acesso**, move o objeto para o nível de acesso infrequente. Se o objeto for acessado novamente, ele retorna automaticamente ao nível de acesso frequente. Possui uma pequena taxa mensal de monitoramento e automação por objeto, mas **não cobra taxas de recuperação nem taxas adicionais pela movimentação entre níveis**. 

- É ideal para dados de longa duração com padrões de acesso **desconhecidos ou imprevisíveis**.

**Amazon S3 Standard-IA:** é destinado a dados **acessados com menos frequência**, mas que precisam de acesso rápido quando necessário. Oferece a alta durabilidade, alta taxa de transferência e baixa latência do S3 Standard, porém com **custos menores por GB de armazenamento e recuperação**. 

- É indicado principalmente para **armazenamento e backups de longo prazo** e arquivos de **recuperação de desastres (DR)**.

**Amazon S3 One Zone-IA:** é destinado a **dados pouco acessados** que ainda precisam de **acesso rápido quando necessário**. A principal diferença é que ele armazena os dados em **uma única Zona de Disponibilidade**, enquanto outras classes armazenam os dados em pelo menos três. Por isso, é **mais barato que o Standard-IA**, mas possui menor disponibilidade e resiliência. 

- É indicado para **backups secundários, dados que podem ser recriados facilmente** e dados replicados de outra Região AWS por meio da replicação entre regiões.

**Amazon S3 Glacier**: é uma classe **segura, durável e de baixo custo**, destinada principalmente ao **arquivamento de dados**. Permite armazenar grandes volumes de dados por um custo competitivo e oferece **três opções de recuperação**, que podem levar de **alguns minutos** a **várias horas**. Os objetos podem ser enviados diretamente ao Glacier ou transferidos para ele por meio das **políticas de ciclo de vida do S3**, que permitem movimentar dados entre as classes de armazenamento do S3.

**Amazon S3 Glacier Deep Archive**: é a **classe de armazenamento de menor custo do Amazon S3**, destinada à **retenção de longo prazo** e à preservação digital de dados acessados apenas **uma ou duas vezes por ano**. É especialmente indicada para setores regulamentados, como serviços financeiros, saúde e setor público, que precisam manter dados por **7 a 10 anos ou mais** para cumprir exigências de conformidade. Também pode ser usada para **backup e recuperação de desastres** e como alternativa aos sistemas de fita magnética. 

- Armazena os objetos em pelo menos **três Zonas de Disponibilidade geograficamente distribuídas** e permite restaurá-los em **até 12 horas**.

## Estrutura do URL do Objeto e do Bucket

O código da Região é o primeiro, seguido por amazonaws.com e pelo nome do bucket

<img width="1522" height="660" alt="image" src="https://github.com/user-attachments/assets/08a57bb5-ee20-45d7-bc9b-0e8aff13bfd0" />

O Amazon S3 se refere a arquivos como objetos. Assim que você tiver um bucket, poderá armazenar praticamente qualquer número de objetos nele. Um objeto é composto por dados e quaisquer metadados que descrevam o arquivo. 

Nesse exemplo, o objeto Preview2.mp4 é armazenado no bucket. A URL do arquivo inclui o nome do objeto no final.

## Redundância no Amazon S3

Ao criar um bucket no Amazon S3, ele é associado a uma Região da AWS específica. Sempre que você armazena dados no bucket, eles são armazenados de forma redundante em várias instalações da AWS na Região selecionada. 

O Amazon S3 foi projetado para armazenar dados de forma durável, mesmo no caso de perda simultânea de dados em duas instalações da AWS.

## Casos de uso comuns

O Amazon S3 permite armazenar uma quantidade **praticamente ilimitada de dados** e acessá-los de qualquer lugar, tornando-o adequado para diversos cenários.

- **Local compartilhado para aplicativos:** Os **buckets do S3** podem funcionar como um local compartilhado para armazenar objetos acessados por diferentes instâncias de uma aplicação, seja no **Amazon EC2 ou em servidores tradicionais**. Pode ser usado para **arquivos de mídia gerados por usuários, logs de servidores e outros arquivos**. Como os dados podem ser acessados diretamente pela web, os clientes podem obtê-los diretamente do S3, sem que a aplicação precise entregá-los.
- **Hospedagem de sites estáticos:** O Amazon S3 pode hospedar e disponibilizar o conteúdo estático de sites, como **HTML, CSS, JavaScript** e outros arquivos.
- **Backup e recuperação de desastres**: A **alta durabilidade** do S3 o torna adequado para armazenar **backups**. Para aumentar a disponibilidade e a capacidade de recuperação de desastres, é possível usar a **replicação entre regiões**, fazendo com que os dados de um bucket em uma Região AWS sejam automaticamente replicados para outra Região.
- **Big Data e análise:** O **armazenamento dimensionável e o alto desempenho** do S3 permitem armazenar dados temporariamente ou por longo prazo para análise com diversas ferramentas de **Big Data**. Como é fácil armazenar e acessar dados no S3, ele pode ser integrado frequentemente a **outros serviços da AWS e diferentes partes das aplicações**.

## Modelo de preço

**Pague somente pelo que usa:**

- GBs por mês
- Transferência para FORA, para outras Regiões
- Solicitações PUT, COPY, POST, LIST e GET

**Você NÃO precisa pagar por:**

- Transferir PARA o Amazon S3.
- Transferência para FORA do Amazon S3 para o Amazon CloudFront ou Amazon EC2 na mesma Região.
