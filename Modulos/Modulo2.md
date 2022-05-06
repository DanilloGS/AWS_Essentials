# Módulo 2
 
## Introdução
 
### Amazon Elastic Compute Cloud (Amazon EC2)
O Amazon EC2 fornece uma capacidade computacional redimensionável, o cliente escolhe quanto quer usar.
Um arquiteto responsável pelos recursos computacionais de uma empresa, sem o Amazon EC2, necessita para criar uma aplicação:
 
- Comprar de forma antecipada um hardware.
- Aguardar até que o hardware comprado seja entregue
- Instalar os servidores no data center
- Realizar configurações necessárias.
 
Já com o Amazon EC2, o mesmo arquiteto irá:
- Provisionar e executar os servidores em minutos.
- Parar de utilizar instâncias que não são mais necessárias para o app. Ou seja, não fica preso ao hardware.
- Pagar apenas pelo tempo de computação da instância que está executando.
- Economizar custo pagando somente pela capacidade necessária.
 
### Como Amazon EC2 funciona
 
### Execução
Para começar, deve-se primeiro executar uma instância. Começamos selecionando um modelo com configurações básicas (Sistema operacional, servidor de aplicativos ou os aplicativos). Podemos também selecionar uma instância específica (Configurações de Hardware). Com as configurações iniciais devemos especificar configurações de segurança para especificar o tráfego de rede que deve sair e entrar na instância.
 
### Conexão
Após realizarmos as configurações básicas em nossas instâncias, devemos conectar nossa aplicação ou usuários com a nuvem.
 
### Uso
Assim que a instância estiver conectada já é possível utilizá-la tranquilamente.
 
## Tipos de instância
O Amazon EC2 possui diversas instâncias distintas otimizadas para diferentes tarefas. Dentre as instâncias existentes estão
 
 
### Instâncias de uso geral
Instância equilibrada, ideal para aplicações que não exigem muito. Não possui nenhuma otimização. Exemplo:
- Servidor de apps
- Servidor de jogos
- Servidor de API's
- Bancos de dados pequenos e médios
 
### Otimizada para computação
Ideal para aplicações vinculadas a computação que necessitam de um processador de alto desempenho. Pode utilizar dessa instância assim como a geral.
Porém o seu uso é preferível para:
- Servidores web de alto desempenho
- Servidores de computação intensiva.
- Servidor dedicado a jogos.
- Processamento de trabalho em lote (Muitas transações em um único grupo)
 
### Otimizada para memória
Projetada para fornecer alto desempenho para cargas de trabalho que processam grandes conjuntos de dados na CPU. Realiza bem trabalhos com cargas que possuem alta necessidade de memória. Exemplo: Banco de dados com alta performance.
 
### Computação acelerada
Instâncias que utilizam aceleradores de hardware, ou como processadores, para executar tarefas de forma eficiente. Bastante utilizada para trabalhos que exigem realizar bastante cálculos.
Ideal para aplicativos gráficos e streaming de jogos e aplicativos.
 
### Otimizadas para armazenamento
Usada para cargas de trabalho que necessitam de um alto acesso sequencial de leitura e gravação de dados. Um exemplo de tecnologia utilizada é o Data Warehouse.
Ideal para tarefas que necessitam de um IOPS (In/Out per second) bastante alto. Essa instância é otimizada para consultas e leituras de banco de dados muito grandes.
 
## Precificação
 
### Sob demanda (0% de desconto) 
Ideais para cargas de trabalho irregulares de curto prazo e que não podem ser interrompidas. Paga somente o tempo que usar a instância.
Caso de uso ideal: Realizar desenvolvimento e testes de aplicativos e executar aplicativos com padrões imprevisíveis. Ideal para curto prazo de uso.
 
### Saving plans (Até 72% de desconto) 
É um plano com foco na economia. O cliente irá possuir um limite de uso dos recursos do Amazon EC2 com um preço X, mais barato que o normal, e assim que a sua taxa limite for excedida o preço para o uso da instância será o valor normal *Sob demanda*. Não depende da instância.
Caso de uso ideal: Quando o cliente possui um uso consistente dos recursos do EC2, mas sua aplicação não possui padrões previsíveis. Ideal para longo prazo quando se conhece o padrão de uso da aplicação.
 
### Instâncias reservadas (Até 75% de desconto)
O cliente reserva o uso de uma instância por um período longo de tempo e possui um desconto para o uso da mesma.
Caso de uso ideal: Cargas de trabalho de estado estacionário e uma aplicação com uso previsível.
 
### Instâncias Spot (Até 90% de desconto)
É ideal para tarefas que não tem tempo para acabar e tolera interrupções. As instâncias Spot utilizam a capacidade de computação que não está sendo utilizada no EC2. Porém a AWS pode recuperar o poder de processamento das instâncias ofertadas a qualquer momento e sem previsão de retorno.
Caso de uso ideal: Tarefas realizadas em segundo plano sem tempo para acabar.
 
### Host dedicado
Servidores físicos com capacidade de instância do Amazon EC2 dedicados ao cliente. Usado quando precisa atender um requisito muito específico do cliente. Opção mais cara ofertada.
 