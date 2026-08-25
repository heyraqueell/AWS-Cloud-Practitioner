# Visão geral da Infraestrutura

A Infraestrutura global da AWS foi projetada e construída para oferecer um ambiente de computação em nuvem **flexível**, **confiável**, **dimensionável** e **seguro** com desempenho de rede global de alta qualidade

<img width="1483" height="616" alt="image" src="https://github.com/user-attachments/assets/ed960ec5-4448-428b-8127-a3dff40078b2" />

A infraestrutura global da AWS pode ser dividida em três elementos: ***Regiões***, ***Zonas de Disponibilidade*** e ***Pontos de presença***.

## Data Centers

Os data centers são locais físicos onde residem dados e ocorre o processamento, organizados em clusters por várias Regiões globais, abrigando normalmente de 50.000 a 80.000 servidores cada um.

- Os locais não são divulgados, possuem acesso restrito e cada site passa por avaliações rigorosas para mitigar riscos ambientais.
- Possuem design redundante para tolerar falhas mantendo os níveis de serviço, com backups em Zonas de Disponibilidade isoladas.
- A AWS monitora o uso continuamente para garantir capacidade e, em caso de falhas, processos automatizados desviam o tráfego para fora da área afetada.

## Zona de Disponibilidade

Cada Zona de disponibilidade é:

- Composta por **um ou mais** data centers
- Projetada para **isolamento de falhas**
- Interconectada com outras **Zonas de disponibilidade** por meio de links privados de alta velocidade
- **Você escolhe** suas Zonas de Disponibilidade

Cada uma tem recursos redundantes de energia, de redes e de conectividade alojadas em instalações separadas.

Algumas Zonas de Disponibilidade têm até **seis data centers**. Entretanto, nenhum data center pode fazer parte de duas Zonas de Disponibilidade.

As Zonas de Disponibilidade são fisicamente separadas em uma região metropolitana típica. Elas estão localizadas em planícies de menor risco de inundação com categorização específica de zona de inundação que varia de acordo com a Região. 

## Regiões da AWS

A infraestrutura da nuvem AWS é construída ao redor de Regiões e em Zonas de Disponibilidade. 

<img width="774" height="670" alt="image" src="https://github.com/user-attachments/assets/b7fc21f9-dd59-41b4-a6c3-a5aae1ebff3f" />


- Uma Região da AWS é uma área geográfica.
- Cada Região é composta por duas ou mais Zonas de Disponibilidade.
- A AWS tem 39 regiões ao redor do mundo e mais de 120 zonas de disponibilidade (2026).

Quando os dados são armazenados em uma Região específica, eles não são replicados fora dessa Região. A AWS nunca transfere seus dados para fora da Região em que você os coloca. Você é responsável por replicar os dados entre Regiões, se o negócio exigir. 

A AWS fornece informações sobre o país e, quando aplicável, sobre o estado em que cada Região reside. Você é responsável por selecionar a Região para armazenar os dados de acordo com seus requisitos de conformidade e de latência de rede.

É possível implantar aplicativos facilmente em múltiplos locais (como aproximar o sistema de uma base de clientes) com poucos cliques, reduzindo a latência rapidamente.

### Considerações

Você deve considerar alguns fatores ao selecionar a Região ou as Regiões ideais para armazenar dados e usar os serviços da AWS.

Uma consideração essencial é a **governança de dados** e os **requisitos legais**. As leis locais podem exigir que determinadas informações **sejam mantidas em limites geográficos**. Essas leis podem restringir as Regiões onde é possível oferecer conteúdo ou serviços.

Se todos os demais fatores permanecerem inalterados, é recomendável executar os aplicativos e armazenar os dados em uma Região que esteja **mais próxima possível do usuário** e dos sistemas que os acessarão. Isso ajudará você a reduzir a latência. 

Por último, há alguma **variação no custo** da execução de serviços, que pode depender da Região escolhida.

## Pontos de presença

Um ponto de presença é o local em que os usuários finais acessam os serviços da AWS por meio do serviço Amazon CloudFront ou Amazon Route 53

Imagine que o seu servidor principal da AWS fica lá nos Estados Unidos, mas você tem um cliente acessando seu site do Brasil. Se o computador dele tiver que buscar a imagem ou o vídeo direto lá nos EUA toda vez, vai demorar e travar.

Os **Pontos de Presença** são como **pequenas "filiais" espalhadas pelo mundo inteiro**.

Eles guardam uma cópia dos arquivos mais acessados do seu site bem pertinho de onde o seu usuário está. Assim, quando a pessoa entra no site, ela recebe o conteúdo direto da filial mais próxima, o site abre rapidinho e não fica lento!

A Amazon Web Services (AWS) possui mais de 410 pontos de presença globais — incluindo locais de borda (edge locations) e caches regionais — distribuídos em mais de 90 cidades por dezenas de países. Esses PoPs atendem a solicitações para o Amazon CloudFront e o Amazon Route 53.

- O **Amazon CloudFront** é uma rede de entrega de conteúdo (ou CDN) usada para distribuir conteúdo aos usuários finais para reduzir a latência.
- O **Amazon Route 53** é um serviço de sistemas de nome de domínio (Domain Name System, DNS).

As solicitações enviadas a qualquer um desses serviços serão roteadas automaticamente para o local de borda mais próximo

## Recursos de Infraestrutura

A infraestrutura tem recursos valiosos:

- Primeiro, ela é **elástica** e **dimensionável**. Isso significa que os recursos podem se ajustar dinamicamente para aumentos ou diminuições nos requisitos de capacidade. Também pode se ajustar rapidamente para acomodar o crescimento.
- Em segundo lugar, essa infraestrutura é tolerante a falhas, o que significa que tem redundância de componentes integrada que permite continuar as operações apesar da falha em um componente.
- Por último, exige intervenção mínima a nenhuma intervenção humana, enquanto oferece alta disponibilidade com tempo de inatividade mínimo
