# AWS Trusted Advisor

O AWS Trusted Advisor é um recurso que ajuda a reduzir custos, aumentar o desempenho e melhorar a segurança ao otimizar o seu ambiente da AWS. 

Ele fornece as práticas recomendadas (ou verificações) em cinco categorias:

1. **Otimização de custos**: Economize dinheiro reduzindo **recursos não utilizados** e **ociosos** ou assumindo compromissos de capacidade reservada.
2. **Desempenho**: Aprimore o desempenho do serviço verificando os limites de serviço, garantindo a utilização da taxa de transferência provisionada e monitorando instâncias com uso excessivo.
3. **Segurança**: Aprimore a segurança do aplicativo e**liminando lacunas**, ativando recursos de segurança e analisando suas permissões.
4. **Tolerância a falhas**: Aumente a disponibilidade e a redundância do aplicativo aproveitando o auto scaling, verificações de integridade, as várias zonas de disponibilidade e os recursos de backup.
5. **Limites de serviço**: Verifica o uso do serviço **acima de 80% do limite**.

O status da verificação é mostrado usando codificação colorida na página do painel:

<img width="1409" height="384" alt="image" src="https://github.com/user-attachments/assets/7f74ef61-c00f-4e64-ae77-da078d3246ab" />


## Usando o Trusted Advisor

As seguintes verificações do Trusted Advisor estão disponíveis para todos os clientes sem nenhum custo:

1. Limites de serviço
2. Security groups: portas específicas sem restrição
3. Identity and Access Management (IAM)
4. Autenticação multifator (MFA) em conta raiz
5. Snapshots públicos do Amazon Elastic Block Store (Amazon EBS)
6. Snapshots públicos do Amazon Relational Database Service (Amazon RDS)

## Recursos do Trusted Advisor

1. **Notificações:** Relatórios semanais automatizados que o serviço gera com recomendações baseadas nas melhores práticas. Ele analisa sua infraestrutura e te informa onde você pode reduzir custos, melhorar a segurança ou otimizar performance. 
2. **Interface de programação de aplicativo (API) do AWS Support:**  recupere e atualize os resultados do Trusted Advisor programaticamente.
3. **Alterações recentes:** Monitore as alterações recentes do status da verificação no painel do console. 
4. **Atualizar tudo**: Atualize verificações individuais ou todas as verificações de uma só vez selecionando *Atualizar tudo.*
