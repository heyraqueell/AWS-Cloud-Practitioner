# Introdução à Segurança

A segurança de TI ou segurança cibernética procura proteger computadores, redes, programas e dados contra acesso, alteração ou destruição não intencionais ou maliciosos. 

# Pilares da Segurança

<img width="1092" height="582" alt="image" src="https://github.com/user-attachments/assets/856213c5-c4d6-489c-804b-715bbef37e10" />

- **Confidencialidade:** Os dados privados estão protegidos para impedir o acesso não autorizado?
- **Integridade:** Existem medidas para garantir que os dados não tenham sido adulterados e sejam corretos e autênticos?
- **Disponibilidade:** Os usuários autorizados conseguem acessar os dados quando precisam deles?

## Por que a segurança é importante?

A falta de segurança deixa a equipe e as organizações abertas para os seguintes riscos de segurança:

- **Roubo de identidade**
- **Roubo de dados**
- **Perda ou danos à reputação comercial**

- **Perda de serviços ou recurso de rede**
- **Sabotagem ou espionagem corporativa**

## Tipos de ameaças

A segurança apropriada ajuda a mitigar os seguintes tipos de ameaças:

- **Malware**
- **Eventos de senha (dicionário, força bruta)**
- **Negação de serviço distribuída (DDoS)**

- **Man-in-the-middle (MitM)**
- **Phishing**
- **Engenharia social**
- **Drive-by**

## Tipos de segurança

- Segurança do **Sistema**
- Segurança de **Infraestrutura**
- Segurança de **Dados**
- Segurança **Física**

- Gerenciamento de **acesso**
- Gerenciamento de **identidades**
- Segurança de **Software**

Com as devidas precauções, as chances de problemas de segurança são reduzidas e seu impacto quando um problema é descoberto pode ser reduzido. 

# Controles de segurança

Os controles de segurança são definidos como três tipos: **preventivo**, **detectivo** e **corretivo**. Eles correspondem a três dos estágios do ciclo de vida da segurança. Para cada tipo de controle, medidas de segurança física, técnica e administrativa podem ser implementadas para garantir a confidencialidade, integridade e disponibilidade das informações.

<img width="1092" height="582" alt="image" src="https://github.com/user-attachments/assets/abb18d1c-b49b-4e3a-ac54-efb4bf5aeb06" />


## Ciclo de vida da segurança

**Prevenção** → **Detecção** → **Resposta** → **Análise**

<img width="1030" height="479" alt="image" src="https://github.com/user-attachments/assets/3cdcd336-fb6e-4c73-b4ed-1f25e502556d" />


## Security Groups da AWS

Os **security groups** atuam como um firewall integrado para os servidores virtuais. O security group atua a nível de instância. Ele fornece controle sobre qual tráfego permitir ou negar. As regras podem variar, desde manter a instância totalmente privada até totalmente pública. Os security groups são stateful.

## Lista de Controle de Acesso

As **ACLs de rede** atuam como um firewall para sub-redes associadas. Elas controlam o tráfego de entrada e de saída no nível da sub-rede.

## Par de chaves

O Amazon EC2 utiliza criptografia de chave pública para criptografar e descriptografar as informações de login. A criptografia de **chave pública** usa uma chave pública para criptografar uma parte dos dados. O destinatário usa a **chave privada** para descriptografar os dados. As chaves privada e pública são conhecidas como *par de chaves*.

- As instâncias do Linux não têm senha, então você usa um par de chaves para fazer login usando o **Secure Shell (SSH)**.
- As instâncias do Microsoft Windows exigem um par de chaves a fim de obter a senha do administrador para que você possa fazer login por meio do **Remote Desktop Protocol (RDP)**.

Os security groups são stateful, mas as ACLs de rede são stateless.

- Stateful: Se tem permissão para entrar, também tem para saída.
- Stateless: Precisa de permissão para ambos.
