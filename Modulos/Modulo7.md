# Módulo 7
 
## Amazon CloudWatch
 
É um serviço de monitoramento da AWS. Com o CloudWatch é possível gerenciar várias métricas e configurar ações de alarme de acordo com os dados das métricas.
O CloudWatch utiliza as métricas para representar os pontos de dados para seus recursos. Os serviços do AWS enviam métricas ao CloudWatch. Em seguida, o CloudWatch utiliza as métricas para gerar gráficos de desempenho ao longo do tempo.
 
### Alarmes do CloudWatch
 
É possível criar alarmes que executam ações automáticas se o valor da métrica ultrapassar ou for inferior a um limite predefinido.
Por exemplo, se uma instância EC2 começar a chegar a 90% (Valor estabelecido pelo cliente) de toda sua capacidade computacional o CloudWatch irá executar um balanceador de carga de forma automática para abrir uma nova instância e dividir o fluxo de requisições.
 
### Painel do CloudWatch
 
É um recurso oferecido no qual é possível observar todas as métricas de seus recursos em um único local.
 
## AWS CloudTrail
 
É um serviço que registra todas as chamadas de API realizadas na conta do cliente. As informações gravadas são a identidade do chamador da API, hora da chamada da API, endereço IP de origem, do chamador e mais.
Todas as chamadas realizadas para ou da conta AWS são registradas no log do CloudTrail. Desde erros de erro do EC2 até criação de novos usuários do IAM.
 
### CloudTrails Insights
 
É um recurso opcional que permite que o CloudTrail detecte de forma automática atividades de API incomuns na conta AWS do cliente.
Por exemplo, ele pode reportar que mais instâncias que o usual foram ativadas.
 
## Trusted Advisor
 
É um serviço web que inspeciona seu ambiente AWS e faz recomendações em tempo real de acordo com as práticas recomendadas pela AWS.
O Trust Advisor compara suas descobertas com as práticas recomendadas da AWS em cinco categorias:
 
- Custo
- Desempenho
- Segurança
- tolerância a falhas
- Limites de serviço
 

