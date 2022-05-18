# Módulo 5
 
## Armazenamento de instâncias e Amazon Elastic Block Store (Amazon EBS)
 
### O que é armazenamento em bloco
Local para armazenar arquivos em blocos no disco. Quando um arquivo do bloco é alterado, não há a necessidade de atualizar todo o bloco, somente os arquivos afetados. HDD seria um exemplo de armazenamento em bloco
 
### Armazenamento de instâncias (Instance Store)
Fornece um armazenamento temporário a nível de bloco para uma instância do EC2. Um armazenamento de instância é o armazenamento em disco fisicamente anexo ao host para uma instância EC2. Tem o mesmo tempo de vida de uma instância. Quando uma instância é encerrada, todos os dados no armazenamento são perdidos.
Isso ocorre, por que as instâncias EC2 são virtuais e são iniciadas em hosts aleatórios, por isso os volumes devem estar sempre vazios.
 
### Amazon Elastic Block Store (Amazon EBS)
 
É um serviço que fornece armazenamento a nível de bloco que pode ser usado junto com instâncias EC2. Se a instância parar, os dados da mesma serão armazenados no volume do EBS anexo à instância.
Para criar um volume EBS deve definir as configurações e provisões da mesma. Assim que estiver configurada a mesma pode ser anexada a qualquer instância.
É sempre importante fazer backup dos dados EBS, pois diferentemente do armazenamento comum de instâncias os dados do EBS devem perdurar por longos períodos. Os backups são Snapshots do EBS.
 
### Snapshot do EBS
 
É um backup incremental. Ou seja, um backup que irá adicionar dados em cima de imagens de Snapshots anteriores, os dados não se perdem ou são escritos de novo são somente incrementados dados novos.
 
## Amazon Simple Storage Service (Amazon S3)
 
### Armazenamento de objetos
 
No armazenamento de objetos cada objeto consiste em dados, metadados e uma chave.
Os dados podem ser de qualquer formato de arquivo. Os metadados contêm informações dos dados, como por exemplo tamanho. A chave é o id exclusivo do objeto no armazém.
 
### O que é o S3
 
Um serviço que fornece armazenamento a nível do objeto. Todos os objetos são armazenados como bucket.
É possível transferir qualquer tipo de arquivo para o S3. Além disso, o tamanho máximo suportado para um **único** O arquivo é de 5 TB. O bucket em si possui armazenamento ilimitado para o cliente.
É possível definir permissões de controle e acesso para esse bucket. Há também a possibilidade de criar um recurso de versionamento do Amazon S3 para rastrear as mudanças dos objetos no bucket.
 
### Classes de armazenamento do S3
 
#### S3 Standard
 
É a classe mais geral de armazenamento. Ideal para a maioria dos casos de uso.
 
- Projetado para dados acessados com frequência
- Armazenado em, pelo menos, 3 zonas de disponibilidade.
 
#### S3 Standard-Infrequent Access (S3 Standard-IA)
 
Armazenamento de baixo custo em relação ao Standard ideal para dados que não serão acessados com muita frequência, como por exemplo backups.
- Projetados para dados acessados com pouca frequência
- Armazenado em, pelo menos, 3 zonas de disponibilidade.
- Preço de serviço mais baixo, porém o preço de recuperação é mais alto.
 
#### S3 One-Zone-Infrequent Access (S3 One Zone-IA)
 
Similar ao S3 Standard-IA, porém os dados são armazenados somente em uma zona de disponibilidade. Ideal para clientes que querem economizar.
 
- Disponível em apenas uma zona de acesso.
- Opção mais barata que o S3 Standard-IA
- Pode reproduzir facilmente os dados em caso de uma falha na Zona de disponibilidade
 
#### S3 Intelligent Tiring
 
Monitora padrões de acessos dos dados e os classificam em um período de 30 dias. Utiliza uma inteligência artificial para mover, de forma automática, os objetos entre buckets para muitos acessos (S3 Standard) e buckets para poucos acessos (S3 Standard-IA).
 
- Ideal para dados com padrões de acesso desconhecidos
- Requer uma taxa mensal de monitoramento e automação por objeto.
 
#### S3 Glacier
 
S3 Glacier é um armazenamento de baixo custo, ideal para arquivar dados. Pode ser usada como o Google Drive
 
- Armazenamento de baixo custo projetado para arquivar dados.
- Capaz de recuperar objetos em poucos minutos ou horas
 
#### S3 Glacier Deep Archive
 
É a opção mais barata oferecida pela a AWS. A diferença do S3 Glacier Deep Archive é a prontidão com que os arquivos serão recuperados. Essa opção pode recuperar objetos armazenados em até 12h.
 
- Opção mais barata
- Ideal para arquivamento.
- Capaz de recuperar arquivos em até 12h.
 
 
## Amazon Elastic File System (Amazon EFS)
 
Os dados podem ser acessados em pastas de arquivos compartilhadas. Um servidor de armazenamento utiliza armazenamento em bloco com um sistema de arquivos local para organizar arquivos. Os dados são acessados através de caminhos de arquivo.
O armazenamento de arquivos é ideal para casos de uso em que um grande número de serviços e recursos precisam acessar os mesmos dados ao mesmo tempo.
É um sistema de arquivos escalável, ou seja, aumenta ou diminui de acordo com a necessidade do cliente. Não é necessário interromper aplicações para redimensioná-lo
 
### Diferença entre UBS e ESF
 
|EBS|EFS|
|:---:|:---:|
|Dados são armazenados em uma única zona de disponibilidade|Serviço regional, os dados podem estar presentes entre diversas zonas de disponibilidade|
|Para conectar o EBS à uma instância EC2, ambos deve estar hospedados na mesma zona|Dados podem ser acessados a partir de qualquer zona de disponibilidade em que o sistema de arquivos está hospedado|
||Pode ser acessado com o AWS Direct Connect|
 
 
## Amazon Relational Database Service (Amazon RDS)
 
Serviço que permite a execução de bancos de dados relacionais na nuvem.
O RDS automatiza tarefas como provisionamento de hardware, configuração do banco, patches e backups. O serviço pode ser integrado a outros serviços do AWS, como por exemplo o AWS Lambda para consultar tabelas no banco sem a necessidade de um servidor.
Possui bastante opções de seguranças para os dados que são armazenados.
 
### Disponibilidade
O RDS está disponível para os seguintes SGBD.
 
- Amazon Aurora
- MySQL
- PostgreSQL
- Oracle
- Microsoft SQL Server
- MariaDB
 
### Amazon Aurora
 
É um SGBD comparável com as outras opções do mercado.
Reduz os custos do banco de dados reduzindo a quantidade de operações desnecessárias.
Ideal para cargas de trabalho que exigem alta disponibilidade. Replica seis cópias de seus dados em 3 zonas de disponibilidade e faz backup contínuo de seus dados para o Amazon S3.
 
## Amazon DynamoDB (Serviço chave-valor)
 
É um banco de dados não relacional, assim como o MongoDB.
O DynamoDB é um serviço de bancos de dados de chaves-valor. Ele oferece um desempenho de um dígito de desempenho em qualquer scaling.
 
### Serverless
 
Não é necessário provisionar, aplicar patches ou gerenciar servidores. Não é necessário instalar, manter ou operar o software.
 
### Auto-Scaling
 
À medida que o tamanho do banco expande ou retrai, o DynamoDB é dimensionado automaticamente para ajustar as alterações na capacidade e manter o desempenho consistente.
 
## Amazon Redshift
 
É um serviço de Data Warehouse que pode ser usado para realizar a análise de big data. Ele oferece a capacidade de coletar dados de muitas fontes além de ajudar a entender relações e tendências em todos os dados.
Ideal para realizar análise de grandes volumes de dados de uma forma ágil. É até 10x mais veloz que o RDS
 
## AWS Database Migration Service (AWS DMS)
 
Permite realizar a migração de bancos de dados on premise para os serviços de nuvem do AWS.
Com o AWS DMS é possível mover dados entre origem e destino, mesmo que o banco de dados da origem não seja compatível com o destino. Durante a migração, o banco de dados de origem permanece operacional.
Suponha que o cliente tenha um banco de dados MySQL armazenado localmente em uma instância EC2 ou no RDS. Com o AWS DMS é possível migrar essa arquitetura do banco para o Amazon Aurora, por exemplo.
 
### Exemplos de uso
 
- *Desenvolvimento e teste de migração de dados*Os devs podem testar a aplicação com os dados de produção sem afetar os usuários em produção.
- *Consolidação de banco de dados*Combinar bancos distintos em um só local.
- *Replicação contínua*Envio de cópias contínuas de seus dados para outras fontes de destino ao invés de fazer só uma migração única.
 
## Outros serviços de banco de dados
 
### Amazon DocumentDB
 
É um serviço de banco de dados de documentos compatível com as cargas de trabalho do MongoDB
 
### Amazon Neptune
 
Banco de dados baseado em grafos. Criar e executar aplicações nas quais os dados devem estar altamente conectados, como por exemplo em uma rede social. Ideal para mecanismos de recomendação, detecção de fraudes e gráficos de reconhecimento.
 
### Amazon Quantum Ledger Database (Amazon QLDB)
 
É um serviço de bancos de dados Ledger. Um sistema imutável de registros onde nenhum dado inserido pode ser removido das auditorias.
 
### Amazon Managed Blockchain
 
É um serviço para criar e gerenciar redes de blockchain com estruturas de código aberto. Blockchain é um sistema de registro distribuído que permite que várias partes executam, transações e compartilhem dados sem uma autoridade central.
 
### Amazon ElastiCache
 
Serviço que adiciona camadas de cache nos bancos de dados para melhorar os tempos de leitura de solicitações comuns.
 
### Amazon DynamoDB Accelerator
 
É um cache de memória para o DynamoDB. Melhora os tempos de resposta do banco.
 

