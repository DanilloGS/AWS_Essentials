# Módulo 6
 
## Modelo de responsabilidade compartilhada
 
Tanto a AWS quanto o cliente têm a responsabilidade de manter a segurança de sua nuvem. Isso é o modelo de responsabilidade compartilhada. Um bom exemplo seria a construção de uma casa. A AWS representaria o engenheiro responsável por criar paredes fortes e portas resistentes e o cliente seria o morador que deveria garantir que as portas e janelas da casa estejam trancadas a visitantes indesejados.
 
### Segurança "da" nuvem (AWS)
 
A AWS é responsável por manter a segurança da nuvem.
A AWS opera, gerencia e controla os componentes em todas as camadas da infraestrutura. Isso inclui áreas como o SO do host, a camada de virtualização e a segurança física do data center no qual o serviço é operado.
Toda a infraestrutura global que executa os serviços da nuvem é feita pela AWS.
Os deveres da AWS são:
- Segurança física dos data center.
- Infraestrutura de hardware e software.
- Infraestrutura de redes.
- Infraestrutura de virtualização.
 
### Segurança "na" nuvem (Cliente)
 
O cliente tem total controle do conteúdo contratado da AWS e possuem a responsabilidade de manter seguro todo conteúdo que colocam na nuvem.
Os clientes são responsáveis por gerenciar os requisitos de segurança para o conteúdo e o nível de acesso de cada usuário a determinado conteúdo.
As etapas de segurança dependem de fatores de como o cliente utiliza os serviços, a complexidade de seus sistemas e a necessidade operacional de seguranças específicas da empresa.
A AWS não tem nenhum controle sobre a seleção, configuração e aplicação de patches no SO das instâncias EC2, configurações de segurança e gerenciamento de contas de usuários. Todas estas etapas de segurança ficam por conta do cliente.
 
## Permissões de usuário e acesso
 
### AWS Identity and Access Management (IAM)
 
Permite o gerenciamento aos serviços e recursos AWS com segurança.
Com o IAM é possível configurar o acesso com base nas necessidades operacionais de segurança específicas da empresa. É possível realizar com o IAM:
- Criação de usuários, grupos e funções do IAM.
- Políticas do IAM.
- Autenticação multifator
 
### Usuário root
 
Usuário que possui todos os privilégios da conta AWS. Pode fazer qualquer coisa sem restrição alguma. Seguindo o exemplo da cafeteria, seria como se fosse o dono do estabelecimento. Pode fazer qualquer coisa, por isso exige cautela ao utilizar o user root do AWS.
 
Nunca utilize o usuário root para tarefas cotidianas. É recomendado usá-lo para criar um novo usuários com permissões para criar usuários e então iniciar o desenvolvimento da nuvem.
Utilize o user root, apenas quando houver a necessidade de realizar uma tarefa somente limitada a ele, como por exemplo alterar o e-mail do usuário raíz e a alteração do plano do AWS Support.
 
### Usuários do IAM
 
Consiste em uma identidade dentro do AWS. Representa uma pessoa, consiste em um nome e uma credencial.
Por padrão, um novo usuário do IAM na AWS, não possui permissão alguma associadas a ele. Para que o usuário execute qualquer ação na AWS é necessário conhecê-lo uma permissão.
Recomendado criar um usuário distinto para cada pessoa que for utilizar os serviços.
 
### Políticas do IAM
 
É um documento que concede as permissões para serviços da AWS.
As políticas são um arquivo JSON, por exemplo, associado com um usuário que serve para especificar todas as permissões e restrições que aquele usuário terá na AWS.
É recomendado sempre seguir o princípio de mínimo privilégio ao conceder permissões. Dessa forma é possível impedir que usuários tenham acesso a serviços restritos.
Para não ser necessário toda vez ficar repetindo a mesma política várias vezes para diversos usuários a AWS fornece a possibilidade da criação de grupos do IAM.
 
### Grupos do IAM
 
Grupos do IAM são um conjunto de usuários do IAM. Ao atribuir uma política a um grupo, todos os usuários pertencentes a aquele grupo receberam as permissões especificadas pelas políticas.
A criação de grupos torna mais fácil a gestão de permissões entre pessoas de uma empresa. Por exemplo, na cafeteria temos um grupo de operadores de caixa. Os operadores de caixa têm acesso somente a visualização ao Bucket do S3 X. Se um dos funcionários operadores de caixa foi promovido para o gestor do armazém, onde necessita de mais permissões, basta retirá-lo do grupo de caixas e adicioná-lo no grupo de gestores.
 
### Funções do IAM
 
Na cafeteria, um dos funcionários reveza entre diferentes estações de trabalho ao longo do dia, desempenhando assim diversas funções que necessitam de diferentes permissões. Para que esse funcionário utilize somente um usuário para desempenhar as diversas tarefas a AWS fornece as Funções do IAM.
Uma função do IAM é uma identidade que um usuário especial pode assumir para possuir acesso temporário a algumas permissões. Quando esse usuário muda suas permissões todas as anteriores são revogadas temporariamente e novas permissões serão concedidas.
 
### Autenticação multifator (MFA)
 
Um exemplo são aqueles sites que exigem informações distintas para verificar sua identidade. Uma validação em dois fatores é um excelente exemplo de autenticação multifator.
O MFA é uma segurança a mais para a conta AWS.
É recomendado ativar o MFA para todos os usuários da conta AWS.
 
## AWS Organizations
 
Suponha que uma empresa possua diversas contas AWS. É possível utilizar o AWS Organizations para consolidar e gerenciar múltiplas contas AS em um local central.
Ao criar uma organização, o AWS Organization cria automaticamente uma raiz, que é o container primário para todas as contas da organização.
Com o AWS Organizations é possível controlar de forma centralizada as permissões para as contas da organização utilizando as políticas de controle de serviço (SPCs). As SPCs permitem que você coloque restrições nos serviços da AWS, dessa forma é possível controlar o nível de permissão e acesso de cada conta.
 
### Unidades organizacionais (UO)
 
Na AWS Organizations, é possível agrupar contas em unidades organizacionais (UO) para facilitar o gerenciamento de contas com requisitos de negócios ou segurança semelhantes. Políticas aplicadas a uma ou são herdadas para todas as contas na organização de forma automática. Impede o acesso a quaisquer serviços ou recursos que não sejam necessários.
 
## Conformidade
 
### AWS Artifact
 
É um serviço que fornece, sob demanda, relatórios de segurança e conformidade da AWS e a contratos online selecionados.
 
### AWS Artifact Agreements
 
Suponha que a empresa precise assinar um contrato com a AWS em relação ao uso de determinados tipos de informações em todos os serviços da AWS. É possível fazer isso pelo AWS Artifact Agreements.
No AWS Artifact Agreements é possível revisar, aceitar e gerenciar contratos para uma conta individual ou para todas as contas de uma organização. Diferentes tipos de acordos são oferecidos para atender as necessidades dos clientes sujeitos a regulamentações específicas, como por exemplo a LGPD.
 
### AWS Artifact Reports
 
Suponha que um membro da equipe de dev da empresa do cliente esteja criando um app e precise de mais informações sobre a responsabilidade em cumprir determinados padrões regulatórios. O acesso a essas informações podem ser recomendados ao AWS Artifact Reports.
O AWS Artifact Reports fornece relatórios de conformidade por auditores terceirizados. Esses auditores testaram e verificaram se a AWS está em conformidade com as diversas normas e regulamentações de segurança globais, regionais e específicas do setor.
 
### Centro de conformidade para o cliente
 
Contém recursos que ajudam o cliente a saber mais sobre a conformidade da AWS.
No centro de conformidade para o cliente, é possível ler histórias de conformidade dos clientes para descobrir como as empresas de setores regulamentados resolveram vários desafios de conformidade, governança e auditoria.
Possui um plano de aprendizagem para auditores. Esse plano foi elaborado para indivíduos em funções jurídicas.
 
## Ataques DoS e DDOS
 
A AWS foi arquitetada de uma forma que previne diversos tipos de ataques que tentem sobrecarregar sua estrutura.
 
### Ataques de negação de serviço (DoS)
 
Um ataque DoS é uma tentativa deliberada de tornar um site ou app indisponível para os usuários.
Por exemplo, um usuário mal intencionado pode sobrecarregar um host até que não seja mais capaz de responder a outros usuários. Impedindo solicitações de serviço legítimas.
O ELB consegue barrar esse tipo de ataque.
 
### Ataques distribuídos de negação de serviço (DDoS)
 
Várias fontes são usadas para realizar um ataque. Por exemplo, o hacker pode criar diversos bots que fiquem realizando solicitações infinitas até que o site ou app de uma empresa fique indisponível.
O ELB consegue barrar esse tipo de ataque.
 
### AWS Shield
 
O AWS Shield é um serviço que protege aplicativos contra ataques DDoS. Há 2 tipos de serviços distintos.
 
#### AWS Shield Standard
 
Protege automaticamente todos os clientes AWS sem nenhum custo. Protege os clientes contra os ataques DDoS mais comuns e frequentes.
Utiliza técnicas de análise para detectar o tráfego mal-intencionado em tempo real e tentar mitigá-lo.
 
#### AWS Shield Advanced
 
Serviço pago de proteção que fornece diagnósticos detalhados dos ataques e a capacidade de detectar e mitigar ataques elaborados de DDoS.
Se integra a outros serviços, como Amazon CloudFront, Amazon Route 53 e o ELB. Além disso, pode ser integrado ao AWS WAF escrevendo regras personalizadas para mitigar ataques.
 
## Serviços de segurança
 
### AWS Key Management Service (AWS KMS)
 
É um serviço que permite ao cliente gerenciar e executar operações de criptografia pelo uso de chaves de criptografia. Uma chave é uma cadeia de números aleatórios gerada para bloquear e desbloquear dados. O WMS permite o uso de chaves criptográficas em diversos serviços da AWS.
Com o AWS KMS, o cliente pode escolher os níveis específicos de controle de acessos necessários para cada uma das chaves. Por exemplo, especificar níveis de acesso para usuários e funções do IAM.
 
### AWS WAF
 
É um firewall de aplicação web que permite monitorar solicitações que acessam os serviços do host.
Trabalha em conjunto com o Amazon CloudFront e um balanceador de carga. O WAF funciona de uma forma semelhante ao ACL para proteger os recursos da AWS.
Requisições de IP 's mal intencionados são adicionadas na ACL da web e todas as requisições feitas são checadas pelo WAF. Se o IP não estiver na lista de bloqueados a requisição irá prosseguir normalmente.
 
### Amazon Inspector
 
É um serviço que mapeia, de forma automática, possíveis vulnerabilidades nos aplicativos do cliente e soluções de como resolver esses problemas encontrados.
Corrigir os erros apontados pelo Amazon Inspector não é uma garantia de que o aplicativo está 100% seguro. Por conta da responsabilidade compartilhada de segurança o cliente também é responsável pela segurança dos serviços contratados.
 
### Amazon Guard Duty
 
É um serviço de detecção inteligente de ameaças à infraestrutura e recursos do cliente. Ele identifica ameaças monitorando continuamente a atividade da rede e o comportamento da conta no ambiente da AWS.
O Guard Duty analisa continuamente dados de várias fontes da AWS, incluindo logs de fluxo de VPC e logs de DNS.
Se o serviço detectar ameaças é possível revisá-las pelo AWS Management Console. As descobertas possuem etapas de correção. Além disso, é possivel vincular o Guard Duty com o AWS Lambda para executar etapas de correção automaticamente.
 

