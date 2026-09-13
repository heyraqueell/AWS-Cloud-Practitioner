# O que é o AWS IAM?

**IAM (Identity and Access Management)** é o serviço da AWS responsável por **controlar quem pode acessar os recursos** da AWS **e o que cada pessoa, aplicação** ou **serviço pode fazer**.

O IAM trabalha principalmente com:

- **Autenticação:** verifica **quem é** o usuário ou entidade.
- **Autorização:** determina **o que** essa entidade **pode fazer**.

| Conceito | Pergunta principal | Exemplo |
| --- | --- | --- |
| **Autenticação** | Quem é você? | Login + senha + MFA |
| **Autorização** | O que você pode fazer? | Pode visualizar uma instância EC2, mas não encerrá-la |

A autorização é definida por meio do uso de **políticas**. Uma política é um objeto na AWS que, quando associado a uma identidade ou a um recurso, define suas permissões.

O IAM é global. Não é de acordo com a região. Ele se aplica a todas as regiõesAWS.  

## Para que serve o IAM?

O IAM reduz a necessidade de compartilhar senhas ou chaves de acesso ao conceder direitos de acesso a outras pessoas ou sistemas. Isso também facilita a ativação ou a desativação do acesso de um usuário.

O IAM permite gerenciar centralmente:

- **Quem pode** acessar os recursos da AWS.
- **Quais recursos** podem ser acessados.
- **Quais ações** podem ser realizadas.
- **Quais credenciais** são necessárias para cada contexto.

Exemplo: Quem pode **encerrar uma instância EC2**?

O IAM permite definir exatamente quais usuários ou funções podem executar essa ação.

---

# Usuário raiz da conta AWS (Root User)

Ao criar uma conta da AWS pela primeira vez, você começa com uma identidade de login único. Essa entidade tem acesso completo a todos os serviços e recursos da AWS na conta e é chamada de ***usuário raiz da conta da AWS***. O usuário raiz da conta é acessado ao fazer login com o endereço de e-mail e a senha usados para criar a conta.

O usuário raiz possui **acesso total a todos os recursos da conta AWS**. Suas permissões não podem ser controladas por políticas IAM da mesma forma que usuários IAM. AWS recomenda:

**NÃO usar o usuário raiz para tarefas do dia a dia.**

Mesmo tarefas administrativas devem ser feitas preferencialmente por um **usuário IAM com permissões administrativas**.

#### Uso recomendado do Root

Usá-lo somente para tarefas específicas de gerenciamento da conta que não podem ser realizadas de outra maneira. Depois disso, as credenciais devem ser protegidas.

A AWS recomenda fortemente habilitar **MFA** no usuário raiz.

# Privilégio mínimo

O **Princípio do Privilégio Mínimo (Least Privilege)** é uma das ideias mais importantes do IAM. 

Significa conceder **somente as permissões necessárias** para executar uma determinada tarefa. 

**Exemplo**: Um funcionário precisa apenas consultar dados no S3.

- Não é necessário conceder acesso administrativo completo.
- Deve receber apenas **permissão de leitura**.

Como boa prática, comece com o **mínimo de permissões** e aumente **SOMENTE** quando necessário.

---

# Usuário IAM

Um **usuário IAM** é uma identidade criada dentro da AWS para representar uma pessoa ou até mesmo uma aplicação.

Um usuário pode:

- acessar o Console da AWS;
- realizar solicitações aos serviços da AWS;
- possuir permissões específicas;
- possuir credenciais próprias.

Um usuário IAM recém-criado **não possui credenciais padrão**.

## Usuário IAM administrativo

Um usuário do IAM é somente uma **identidade com permissões associadas**. 

A AWS recomenda criar um **usuário IAM separado com permissões administrativas** em vez de usar o Root User no dia a dia.

- Root User
- Criar usuário IAM Admin
- Conceder permissões administrativas
- Usar o usuário IAM no dia a dia


Caso necessário, as permissões desse usuário podem ser posteriormente modificadas, removidas e revogadas.

## Grupos IAM

Um **grupo IAM** é um conjunto de usuários IAM. O principal objetivo é **facilitar o gerenciamento de permissões**.

Exemplo: Criamos o grupo “**Desenvolvedores**” e atribuímos permissões que os desenvolvedores normalmente precisam.

Em vez de criar e configurar permissões individualmente, atribuímos o usuário em um grupo e ele recebe as permissões devidas.

#### Regras importantes dos grupos

- Um grupo pode conter **vários usuários**.
- **Um usuário** pode pertencer a **vários grupos**.
- Grupos **não podem conter outros grupos**.
- Não existe um grupo padrão que contenha todos os usuários.
- Se quiser um grupo padrão, ele deve ser criado manualmente.
- Novos usuários precisam ser adicionados ao grupo.

### Mudança de cargo

Em vez de editar todas as permissões do usuário, basta remover ele do grupo atual e colocar no grupo referente ao novo cargo. Isso facilita muito o gerenciamento.

## Função do IAM (IAM Roles)

Uma **Role** permite conceder **acesso temporário** aos recursos da AWS.

**A grande diferença é:** **As permissões não ficam vinculadas permanentemente ao usuário.**

Quando isso acontece, a AWS fornece: **credenciais de segurança temporárias**.

**Principal vantagem:** Evita usar credenciais de longo prazo.

Em vez de adicionar um usuário dentro de um grupo IAM e depois removê-lo, é mais fácil atribuir uma função/role.

**Roles são muito utilizadas para:**

- aplicações;
- serviços da AWS;
- usuários federados;

- acesso temporário;
- acesso entre contas AWS.

### Usuário federado

Um usuário federado **não possui necessariamente uma identidade IAM permanente** dentro da conta.

Ao criar uma Role, existem dois conceitos fundamentais:

**Trust Policy:** Quem pode assumir essa Role?

**Permissions Policy:** O que a Role pode fazer depois que for assumida?

---

# Políticas do IAM

**Uma política é um documento que lista as permissões explicitamente.** Não há permissões padrão. **Todas as ações são negadas por padrão**, a menos que sejam explicitamente permitidas.

- As políticas são armazenadas no formato JavaScript Object Notation (JSON)

Elas podem especificar:

- **Effect** → permitir ou negar;
- **Action** → qual ação;
- **Resource** → qual recurso;
- **Condition** → em quais condições.

Como são arquivos JSON, políticas também podem ser armazenadas em sistemas de **controle de versão**.

Por padrão: **Tudo é negado!** (Negação implícita)

Ordem lógica de permissão:

<img width="835" height="356" alt="image" src="https://github.com/user-attachments/assets/0c94988a-8388-4d30-9407-1e8db9b77829" />


Uma **negação explícita** sempre prevalece sobre uma permissão.

Política A → Allow
Política B → Deny

Resultado: NEGADO 

**Políticas gerenciadas** são **políticas predefinidas** (**criadas pela AWS** ou pelos administradores) 

# MFA — Multi-Factor Authentication

A AWS recomenda utilizar **MFA** para aumentar a segurança.

Com MFA, além da autenticação normal, é necessário um segundo fator. Pode envolver:

- senha + código;
- dispositivo físico;
- aplicativo autenticador.

Também existe autenticação utilizando **SMS** como alternativa.

Habilitar MFA principalmente no **Root User** e usuários IAM.
