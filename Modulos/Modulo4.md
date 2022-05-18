# Módulo 4
 
## Conectividade com a AWS
 
### Amazon Virtual Private Cloud (Amazon VPC)
 
Serviço da AWS utilizado para o cliente criar sua própria rede privada. O Amazon VPC permite que o cliente providencie secções isoladas da nuvem do AWS. Assim é possível executar recursos em uma rede virtual. Em uma VPC, é possível organizar recursos e instâncias do EC2 em sub-redes. Seria como uma fortaleza protegida onde nada entra ou sai sem permissão explícita.
 
### Gateway de internet
 
Para que haja um tráfego público para acessar a VPN, é necessário anexar um Gateway da internet. Exemplo: Na cafeteria, o Gateway seria a porta de entrada para os clientes. Sem porta ninguém tem acesso a cafeteria.
 
### Gateway privado virtual
 
Somente alguns usuários terão acesso a rede (Usuários conectados a uma VPN) e seus dados de acesso são criptografados. Os dados privados trafegam pelo mesmo caminho que os públicos, porém com uma camada a mais de proteção (Criptografia). Exemplo: Utilizando o exemplo da cafeteria, seriam clientes que vão até o estabelecimento acompanhados de guarda costas e possuem acesso a uma sala VIP exclusiva para poucos clientes, porém o caminho até a cafeteria continua o mesmo é possível pegar engarrafamentos.
 
###  AWS Direct Connect
 
É uma conexão privada dedicada entre data center e VPC. Seria como uma via expressa, até a cafeteria, exclusiva para clientes VIP. Dessa forma os clientes da Vips não sofreram com o tráfego da rede pública. Ajuda a reduzir os custos da rede e a aumentar a quantidade de largura de banda.
 
 
## Sub-redes e listas de controle de acesso à rede
 
Para entender melhor a como funciona a sub rede iremos voltar à cafeteria.
Para que um pedido seja processado, os clientes devem pegar uma fila para falar com a atendente. Porém alguns clientes, apressados, tentam pedir diretamente ao barista. Isso interrompe o fluxo do tráfego e faz com que clientes acessem uma parte restrita da cafeteria.
Para sanar o problema de acesso em áreas restritas, dividimos o balcão para que os clientes não tenham acesso ao barista. O barista irá apenas receber os pedidos diretamente da caixa.
Na cafeteria, o balcão seria uma VPC. Uma área dividida que é dividida em 2, caixa e barista, que são nossas sub-redes.
 
### Sub-rede
 
Uma seção de uma VPC na qual são agrupados em necessidades operacionais ou de segurança. As sub-redes podem ser públicas (Caixa/Atendente), contém recursos que devem ser acessíveis ao público geral, ou privadas (Barista), recursos acessíveis apenas pela rede privada, como por exemplo o acesso a um banco de dados contendo informações sensíveis.
As sub-redes podem conversar entre si.
 
### Tráfego de rede VPC
 
Quando uma solicitação é realizada para a nuvem ela é enviada como um pacote.
Esse pacote entra na VPC pelo gateway. Antes desse pacote entrar na sub-rede, ele verifica se há permissões. Essas permissões indicam de onde ele veio e para onde ele vai. Os acessos são verificados a partir da lista de controle de acesso (ACL).
 
### Lista de controle de acesso (ACL) de rede
 
É um firewall virtual que tem o controle de entrada e saída da sub-rede.
Imagine um aeroporto. Em um aeroporto, quando vamos fazer uma viagem internacional, precisamos de um passaporte. Antes de realizarmos o embarque devemos passar por uma checagem se estamos aptos a sair do país de origem (Checagem na ACL), caso esteja tudo ok vamos para a próxima etapa. Assim que chegamos no país de destino passamos novamente por uma nova checagem que, por fim, aprova ou não nossa entrada.
As regras de ACL podem ser personalizadas.
 
### Filtragem de pacotes Stateless
 
Voltando ao exemplo anterior, a checagem stateless será o equivalente ao trabalhador da imigração e alfândega. Os trabalhadores não sabem quem tem permissão para entrar ou sair, por isso devem sempre realizar a checagem do passaporte na ACL, a fim de permitir ou recusar o viajante. O componente VPC que verifica as permissões para uma instância EC2 é um grupo de segurança.
 
### Grupos de segurança
 
É um firewall virtual que controla o tráfego de In/Out de uma instância EC2.
Por padrão, o grupo de segurança nega todo o tráfego de entrada e libera toda a saída. Regras personalizadas podem ser criadas para mudar esse comportamento.
Imagine o grupo de segurança como o porteiro de um prédio. O porteiro verifica todos que entram no prédio, mas não necessitam realizar a checagem novamente na saída.
 
### Filtragem de pacotes Stateful
 
Os grupos de segurança fazem parte da filtragem ``Stateful''. Eles se lembram das decisões tomadas anteriormente.
 
Imagine que uma instância na Sub-net envie um pacote para a subnet B. Este pacote irá sair da subnet A, será gravado pelo grupo de segurança A ao sair da instância e checado se pode sair da subnet no ACL. Após sair da subnet A, o pacote será checado pela ACL na entrada da subnet B e então será checado pelo grupo de segurança de B, para identificar se o pacote pode entrar na instância. Assim que o pacote entrar na instância, uma resposta deverá ser enviada à A passando por todos os ACL novamente e quando a resposta chegar no grupo de segurança A nenhuma checagem será realizada, pois o grupo de segurança A já sabe que a resposta é referente ao pacote enviado.
 
 
### Atenção
ACL - A princípio, libera todas as entradas e nega todas as saídas. (Stateless)
Grupo de segurança - A princípio, negou todas as entradas e libera todas as saídas. (Stateful)
 
## Redes globais
 
### Domain Name System (DNS)
 
O DNS seria como se fosse uma lista telefônica da internet. A resolução de DNS é o processo de converter nomes de um site para um endereço IP.
Suponha que queremos acessar o  site Any Company, hospedado na AWS.
 
- Ao digitar o nome do site na barra e pesquisar, esse nome é enviado para um resolvedor DNS do cliente.
- O resolvedor de DNS do cliente solicita o servidor DNS da empresa o endereço IP que corresponde ao site Any Company
- O servidor DNS responde com o endereço IP.
 
### Amazon Route 53
 
É um serviço de web de DNS. Conecta solicitações de usuários à infraestrutura em execução na AWS (Instâncias EC2 e balanceadores de carga) ou para infra estrutura fora da AWS.
Possui a capacidade de gerenciar registros DNS para nomes de domínio. Também é possível registrar novos nomes de domínio diretamente no Route 53. O cliente também é capaz de transferir registros DNS para nomes de domínios existentes gerenciados por outras empresas.
O Amazon CloudFront e Route 53 trabalham juntos.
 
#### Exemplo
 
Suponha que o site da Any Company esteja em execução em várias instâncias do EC2 através de um balanceador de carga.
- O cliente solicita os dados do site acessando AnyCompany
- O Amazon Route 52 usa o DNS para identificar o endereço IP correspondente com Any Company.com. O endereço de AnyCompany é enviado ao cliente.
- A solicitação do cliente é enviada para o local de borda mais próximo por intermédio do CloudFront.
- O CloudFront se conecta com o balanceador de carga que envia um pacote para as instâncias EC2.