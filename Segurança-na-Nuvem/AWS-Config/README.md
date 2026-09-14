# AWS Config

O **AWS Config** é um serviço que **registra, monitora e avalia a configuração dos recursos da AWS ao longo do tempo**.

A ideia principal é: **“O que mudou nos meus recursos, quando mudou e essa configuração está de acordo com as regras?”**

## O que o AWS Config faz?

- **Inventaria recursos:** descobre quais recursos existem na conta.
- **Registra alterações:** acompanha mudanças de configuração quase continuamente.
- **Mantém histórico:** permite saber **como um recurso estava configurado em determinado momento**.
- **Mostra relações:** identifica como os recursos estão relacionados.
- **Avalia conformidade:** verifica se os recursos seguem regras definidas.
- **Gera notificações:** pode avisar quando recursos são criados, alterados ou excluídos.


## Esses recursos permitem

**Auditoria de conformidade**, **análise de segurança**, **rastreamento de alteração de recursos** e **solução de problemas**. De valor específico são:

- **Detecção**: Crie controles de detecção e identifique e analise anomalias.
- **Conformidade:** Crie regras que avaliem a conformidade de recursos e auxiliem no alinhamento com as certificações SOC e Revise as alterações nas configurações e nas relações entre os recursos da AWS.
- **Controle de Acesso:** O AWS Config precisa de permissões para realizar determinadas tarefas na sua conta AWS. Você configura o AWS Config para monitorar buckets S3.
- **Criptografia/Dados em repouso:** O AWS Config cria um item de configuração sempre que detecta uma alteração em um tipo de recurso que está registrando. Os componentes de um item de configuração incluem metadados, atributos, relações, configuração atual e eventos relacionados.

O AWS Configpermite simplificar a auditoria de conformidade, a análise de segurança, o gerenciamento de alterações e a solução de problemas operacionais.

## Regras do AWS Config

O Config possui **Rules**, que determinam o que é considerado correto ou incorreto. Você pode usar:

- Regras prontas da AWS/parceiros.
- **Regras personalizadas**, usando AWS Lambda.

As regras podem ser avaliadas quando um recurso é **criado ou alterado**, ou periodicamente.

Por exemplo, você pode definir regras que garantam que:

- Os volumes do Amazon Elastic Block Store (Amazon EBS) sejam criptografados.
- As instâncias estejam sendo criadas apenas de imagens de máquina da Amazon (AMIs) aprovadas.
- Elastic IP deve estar associado a uma instância.
- EC2 deve possuir as **tags obrigatórias**.

## Como funciona?

- Recurso AWS muda →
- AWS Config registra a alteração →
- A alteração é armazenada e pode ser consultada →
- As Rules avaliam a configuração →
- Config mostra se está em conformidade →
- Pode enviar notificação via SNS (Amazon Simple Notification Service).

<img width="1193" height="461" alt="image" src="https://github.com/user-attachments/assets/18b3d186-f9de-49e8-a3a7-e5fdbcd30d01" />
