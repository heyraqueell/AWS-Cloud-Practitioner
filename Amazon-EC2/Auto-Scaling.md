# Amazon EC2 Auto Scaling

O Amazon EC2 Auto Scaling ajusta automaticamente o número de instâncias do EC2 com base nas mudanças na demanda da aplicação, oferecendo melhor disponibilidade. Ele oferece duas abordagens. O escalonamento dinâmico se ajusta em tempo real às flutuações na demanda. O escalonamento preditivo agenda preventivamente o número certo de instâncias com base na demanda prevista.

Exemplo: Amazon EC2 Auto Scaling

Com o EC2 Auto Scaling, você mantém a quantidade desejada de capacidade computacional para sua aplicação ao ajustar dinamicamente o número de instâncias do EC2 com base na demanda. Você pode criar grupos de Auto Scaling, que são coleções de instâncias do EC2 que podem ser ampliadas ou reduzidas para atender às necessidades da sua aplicação.

## Grupo de Auto Scaling

Um grupo de Auto Scaling é configurado com as três configurações principais a seguir.

#### 1. Capacidade mínima

A capacidade mínima define o menor número de instâncias do EC2 necessárias para manter a aplicação em execução. Isso garante que o sistema nunca seja escalado abaixo desse limite. É também este o número de instâncias EC2 que são provisionadas no momento em que o grupo de Auto Scaling é criado.

#### 2. Capacidade Desejada

A capacidade desejada é o número de instâncias que o Auto Scaling considera ideal e se esforçará para manter, a fim de lidar com a carga de trabalho do momento. Se você não especificar o número desejado de instâncias do EC2 em um grupo do Auto Scaling, a capacidade desejada se tornará a capacidade mínima regular.

#### 3. Capacidade Máxima

A capacidade máxima define um limite máximo para o número de instâncias que podem ser iniciadas, evitando o excesso de escala e controlando os custos. Por exemplo, você pode configurar o grupo Auto Scaling para aumentar a escala horizontalmente em resposta ao aumento da demanda.

<img width="1680" height="1245" alt="image" src="https://github.com/user-attachments/assets/42c0b81d-deef-486c-bfed-73241f2d2cd9" />




