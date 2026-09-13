# AWS CloudTrail

**O CloudTrail é um serviço que registra chamadas de API da AWS para sua conta e entrega arquivos de log.**

O CloudTrail é uma ferramenta crucial para simplificar a governança, a conformidade e a auditoria de riscos. 

Tudo na AWS é uma chamada de API. O CloudTrail registra as chamadas de API feitas em uma conta da AWS entre as regiões AWS. 

Ele faz isso se essa ação foi executada usando a AWS CLI, um kit de desenvolvimento de software (SDK), o console ou diretamente por meio de uma API. 

<img width="1007" height="454" alt="image" src="https://github.com/user-attachments/assets/a14282c2-1c36-4f5b-8cc9-2821ffacb618" />


Os logs de serviço incluem ações como:

- Iniciar ou interromper instâncias.
- Criar ou modificar banco de dados do Amazon RDS.
- Fazer upload de um arquivo para o Amazon S3.

Esse registro **acelera a análise de problemas** operacionais e de segurança ao disponibilizar **visibilidade sobre as ações** em sua conta da AWS.

# Benefícios do CloudTrail

- **Aumento da visibilidade nas atividades** de usuários e recursos. Com essa visibilidade, você pode identificar **quem fez o quê** e **quando** em sua conta da AWS.
- **Auditorias de conformidade** são simplificadas porque as atividades são **registradas** e **armazenadas** automaticamente nos logs de eventos. O registro de atividades permite pesquisar dados de log, identificar ações que não estão em conformidade, acelerar investigações sobre incidentes e, então, agilizar uma resposta.

# Como o CloudTrail funciona?

1. Uma atividade acontece em sua conta.
2. O CloudTrail captura e registra essa atividade, que é chamada de evento do CloudTrail. O evento contém detalhes sobre o seguinte:
    - Quem realizou a solicitação
    - Data e horário da solicitação
    - Endereço IP (Protocolo de Internet) de origem
    - Como a solicitação foi feita
    - Ação executada
    - Região onde a ação foi realizada
    - Resposta

Por padrão, os logs são **armazenados** por **7 dias**. Você pode enviar o log de atividades para outros serviços da AWS. Portanto, é possível reter o histórico de atividades pelo tempo que quiser.

## Uso do ClaudTrail

- Ative a validação de arquivos de log do CloudTrail.
- Agregue arquivos de log a um único bucket do S3.
- Certifique-se de que o CloudTrail esteja ativado globalmente na AWS.
- Restrinja o acesso aos buckets do S3 do CloudTrail.
- Integração com o Amazon CloudWatch.

A integração do CloudTrail ao Amazon CloudWatch **permite definir** **ações a serem executadas** quando o CloudTrail registrar eventos específicos.
