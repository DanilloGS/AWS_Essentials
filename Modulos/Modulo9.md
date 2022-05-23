# Módulo 9
 
## AWS Cloud Adoption Framework (AWS CAF)
 
Organiza orientações em 6 áreas de foco chamadas perspectivas. Cada perspectiva aborda responsabilidades distintas. O processo de planejamento ajuda as pessoas certas em toda a organização a se prepararem para as mudanças futuras.
As perspectivas são:
 
### Negócio
 
A perspectiva de negócios garante que a TI esteja alinhada com as necessidades de negócio e que os investimentos em TI estejam vinculados aos principais resultados dos negócios.
Utilizada para criar um negócio sólido para adoção da nuvem e priorizar iniciativas de adoção de nuvem.
As funções comuns a perspectiva de negócio são:
- Gerentes de negócios.
- Gerentes financeiros.
- Proprietários de orçamento.
- Stakeholders de estratégia.
 
### Pessoas
 
Promove o desenvolvimento de uma estratégia de gerenciamento de alterações em toda a organização para a adoção bem sucedida da nuvem.
Utilizada para avaliar estruturas e funções organizacionais, novos requisitos de habilidades e processos e identificadores de lacunas. Ajuda a priorizar treinamento, pessoal e mudanças organizacionais.
Funções comuns da perspectiva de pessoas:
- RH
- Equipe
- Gerente de pessoas
 
### Governança
 
Utilizada para concentrar-se nas habilidades e nos processos para alinhar as estratégias de TI e de negócios. Isso maximiza o valor comercial e minimiza os riscos.
Usada para entender como atualizar as habilidades e os processos da equipe necessários para garantir a governança de negócios da nuvem.
Funções comuns:
- Diretor de informações (CIO)
- Gerentes do programa
- Arquitetos empresariais
- Analistas de negócio
- Gerentes de portfólio
 
### Plataforma
 
Inclui princípios e padrões para implementação de novas soluções na nuvem e migração de cargas de trabalho locais para a nuvem.
Use em uma variedade de modelos arquitetônicos para entender e comunicar a estrutura dos sistemas de TI e suas relações
Funções:
- Diretor de tecnologia (CTO)
- Gerentes de TI
- Arquitetos de solução
 
### Segurança
 
Garante que a organização atenda aos objetivos de segurança de visibilidade, auditoria, controle e agilidade.
Use o AWS CAF para estruturar a seleção e a implementação de controles de segurança que atendem às necessidades da organização.
Funções:
- Diretor de segurança de informação (CISO)
- Gerentes de segurança de TI
- Analistas de segurança de TI
 
### Operações
 
Ajuda a habilitar, executar, usar, operar e recuperar cargas de trabalho de TI para o nível definido com os Stakeholders da empresa.
O AWS CAF ajuda os stakeholders a definir os procedimentos operacionais atuais e identificar mudanças de processo e treinamento necessários para implementar a nuvem com sucesso.
Funções:
- Gerentes de operações de TI.
- Gerentes de suporte de TI.
 
## Estratégias de migração (Os 6 R's)
 
### Rehosting
 
Redefine o local onde o servidor está hospedado. É um lift-and-shift, que envolve a movimentação de aplicativos sem alterações.
 
### Platforming
 
Também funciona como um lift-and-shift, porém envolve algumas otimizações na nuvem para obter um benefício tangível. Não é necessário alterar a arquitetura central do app.
 
### Retire
 
Remoção de aplicações que não são mais necessárias.
 
### Retain
 
Consiste em manter os aplicativos essenciais para a empresa no ambiente de origem. Isso pode incluir apps que necessitam de refatoração importante antes de serem migrados ou trabalhos que podem ser adiados.
 
### Repurchasing
 
Envolve a mudança de uma licença tradicional para um modelo de software como serviço. Necessidade de comprar um produto diferente baseado em nuvem.
 
### Refactoring
 
Envolve reimaginar como um app é arquitetado e desenvolvido usando os recursos nativos da nuvem. A refatoração costuma ser orientada pela forte necessidade que a empresa tem em adicionar recursos, scaling ou desempenho.
 
## Snow Family
 
Coleção de dispositivos físicos para transporte de dados para dentro ou fora da AWS
 
### Snowcone
 
Dispositivo pequeno, robusto e seguro para a transferência de dados e computação de borda. Possui 2 CPUs, 4GB de memória e 8 TB de armazenamento.
 
### Snowball
 
#### Snowball Edge otimizado para armazenamento
 
Ideais para migração de dados de grande escala e fluxos de trabalho de transferência recorrentes.
- Armazenamento: 80 TB de capacidade de disco rígido (HDD) para volumes de blocos e armazenamento de objeto compatível com o Amazon S3, além de espaço para 1TB de SSD
- Computação: 40 vCPUs e 80 GB de memória para dar suporte a instâncias sbe1 do Amazon EC2.
 
#### Snowball Edge otimizado para computação
 
Fornece poder computacional para casos de uso como machine learning, análise de vídeo em movimento, análise e pilhas de computação locais.
- Armazenamento: 42 TB de armazenamento de objeto compatível com o Amazon S3 ou volumes de blocos compatíveis com o EBS e 7.68 TB de capacidade de SSD NVMe utilizável para volumes de blocos.
- Computação 52 vCPUs, 208 GB de memória e uma GPU NVIDIA Tesla V100. Executam instâncias do EC2.
 
### Snowmobile
 
É um serviço de transferência de dados na escala de exabytes usado para mover grandes quantidades de dados para a nuvem AWS. O Snowmobile é um caminhão que transporta um data center inteiro no seu reboque.
 
## Inovação com a AWS
 
A AWS possui diversos produtos diferentes para diversos tipos de problemas.
 
### Aplicações sem servidor
 
Significa que não é necessário administrar, fazer manutenção ou administrar servidores de aplicativos. Não é necessário lidar com tolerância a falhas ou disponibilidade.
O AWS Lambda é um exemplo de recurso serverless.
 
### Inteligencia artificial
 
AWS oferece uma infinidade de serviços para A.
 
- Converter fala em texto (Amazon Transcribe)
- Descobrir padrões em texto (Amazon Comprehend)
- Identificar atividade on-line potencialmente fraudulentas (Amazon Fraud Detector)
- Criar chatbots (Amazon Lex)
 
### Machine Learning
 
A AWS oferece o Amazon PageMaker, que remove o trabalho difícil do processo e ajuda o cliente a criar, treinar e implementar modelos de Machine Learning.
 

