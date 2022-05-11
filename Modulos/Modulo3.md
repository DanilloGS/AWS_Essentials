# Módulo 3
 
## Infraestrutura Global da AWS
A Amazon possui diversas regiões para manter sua arquitetura do AWS e cada região possui sua peculiaridade. As características que devem ser levadas em conta ao escolher uma região são:
 
### Conformidade com a governança de dados e requisitos legais.
 
Algumas empresas exigem que os dados sejam executados em uma região específica do mundo. Por exemplo, uma empresa que reside no Reino Unido, pode exigir que todos os dados do Reino Unido sejam processados no Reino Unido, seguindo as leis do local.
 
### Proximidade com os clientes
 
Selecionar uma região levando em conta onde a maioria dos usuários que irão utilizar o aplicativo então, isso diminui a latência. Por exemplo, um app que tem foco majoritariamente no Brasil seria ideal que a região escolhida fosse São Paulo.
 
### Serviços disponíveis por região
 
Nem todos os recursos oferecidos pela AWS estão disponíveis em todas as regiões. Por conta desse problema, se o cliente necessitar de utilizar um recurso muito específico da AWS o mesmo terá que checar quais regiões têm oferecem esse recurso.
 
### Preço
 
Cada região possui uma carga tributária referente ao local onde está hospedada, isso influencia diretamente no preço do serviço. Por exemplo, manter uma região em São Paulo pode custar até 50% mais que manter no Oregon.
 
## Zonas de disponibilidade
 
As regiões não possuem somente 1 Data Center. Na verdade, regiões possuem uma Zona de disponibilidade que são representadas por diversos data centers do AWS espalhados e distantes uns dos outros pela região. Por exemplo, na região do Norte da Califórnia existem  3 zonas de disponibilidade na região. A zona de disponibilidade evita que a aplicação para de funcionar em caso de desastre em um Data Center.
 
### Importante
 
É sempre recomendado que o cliente possua mais de uma única instância do EC2 rodando em várias zonas de disponibilidade. Por exemplo, se o cliente possuir sua aplicação somente na zona A e ocorra uma falha no data center, a aplicação de todos os usuários irão parar. Porém, se o cliente possuir sua aplicação na zona A e B, caso ocorra algum desastre em alguma das zonas, o cliente não terá prejuízo algum.
 
## Pontos de presença
 
### Edge Location (Amazon CloudFront)
 
Local de borda é um site que o Amazon CloudFront utiliza para armazenar cópias em cache do seu conteúdo mais próximo dos seus clientes para uma entrega mais rápida.
 
Exemplo:
 
- Uma região hospedada no Brasil precisa enviar dados para a China. O que deve ser feito?
- Os dados são levados para um local de borda perto da China e ficam salvos em uma espécie de Cache.
- Quando os clientes Chineses solicitarem o dado X esse dado será fornecido pelo local de borda, mais rápido do que solicitar ao Brasil.

#### AWS Outposts

São mini clusters on-premises ou em locais de borda que possuem alguns recursos do AWS para os clientes.

## Provisionando recursos AWS
 
### Maneiras de interagir como AWS
 
#### Console de gerenciamento
 
Interface Web para acessar e gerenciar os serviços do AWS. Por aqui se pode executar tarefas, monitorar recursos, visualizar alarmes e acesso às informações de cobrança.
Vantagem: Todas as informações dos recursos da AWS estão presentes lá
Desvantagem: Muito manual, requer muitos cliques e é muito suscetível a erro humano.
 
#### Linha de comando
 
Comandos que podem ser executados em qualquer Shell. O AWS CLI está disponível para Windows, Mac e Linux.
Vantagem: Ótimo para utilizar em Scripts de automação.
Desvantagem: Fornece poucas informações sobre as instâncias.
 
#### SKD
 
Kits de desenvolvimento que facilitam o uso do serviço do AWS por uma API projetada para a linguagem ou plataforma.
Vantagem: Permite conectar aplicativos existentes ou criar novos que serão executados totalmente no AWS.
Desvantagem: Assim como o Firebase, é limitado a linguagem de programação.
 
### AWS Elastic Beanstalk
 
Serviço que ajuda a provisionar ambientes baseados no EC2. Não é necessário clicar no console ou criar comandos no Shell para criar a rede. Basta fornecer no Beanstalk as configurações desejadas e então o ambiente estará pronto para deploy. Também há a possibilidade de salvar as configurações do ambiente para que sejam usadas novamente em outros contextos. O foco ficará na aplicação e não na infraestrutura.
 
### AWS CloudFormation
 
Cria um ambiente escrevendo linhas de código em vez de utilizar o Management Console para provisionar recursos individualmente. Define os recursos do AWS usando um JSON ou YAML. Com o CloudFormation o cliente só se preocupa em definir o que for desejado e o AWS faz o resto.
 

