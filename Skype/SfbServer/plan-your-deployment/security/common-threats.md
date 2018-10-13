---
title: Ameaças de segurança comuns no Modern Day Computing
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: Como Skype para Business Server é um sistema de comunicação de classe empresarial, você deve estar ciente dos ataques de segurança comuns que podem afetar sua infraestrutura e comunicações.
ms.openlocfilehash: 594bde9b01a61586364034ba026db91aea49ef88
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546780"
---
# <a name="common-security-threats-in-modern-day-computing"></a>Ameaças de segurança comuns no Modern Day Computing
 
Como Skype para Business Server é um sistema de comunicação de classe empresarial, você deve estar ciente dos ataques de segurança comuns que podem afetar sua infraestrutura e comunicações.
  
## <a name="compromised-key-attack"></a>Chave de Ataque Comprometida

Uma chave é um código secreto ou um número que é usado para criptografar, descriptografar ou validar uma informação secreta. Existem duas chaves confidenciais em uso na infraestrutura de chave pública (PKI) que deve ser considerada: 
  
- A chave privada que cada titular do certificado tem
    
- A chave da sessão que é usada depois da identificação com sucesso e a chave da sessão alterada pelos parceiros de comunicação
    
Um ataque à chave comprometida acontece quando o atacante determina a chave de privacidade ou a chave da sessão. Quando o atacante é bem sucedido nesta determinação da chave, ele pode usá-la para descriptografar dados criptografados sem que o remetente.
  
Skype para Business Server usa os recursos PKI no sistema operacional Windows Server para proteger os dados da chave usados para criptografia para as conexões de segurança de camada de transporte (TLS). As chaves usadas para criptografar mídia são trocadas através de conexões TLS.
  
## <a name="network-denial-of-service-attack"></a>Rede de Ataque De Negação de Serviço

O ataque de negação de serviço ocorre quando o atacante impede o uso da rede normal e função pelos usuários válidos. Isso é feito quando o atacante inunda o serviço com pedidos legítimos que domina o uso do serviço pelos usuários legítimos. Usando um ataque de negação de serviço, o atacante pode fazer o seguinte:
  
- Enviar dados inválidos aos aplicativos e serviços que estão funcionando na rede atacada para interromper o funcionamento normal delel.
    
- Enviar uma grande quantidade de tráfego, sobrecarregando o sistema até que ele pare de responder ou responda devagar aos pedidos legítimos.
    
- Esconder a evidência dos ataques.
    
- Impedir os usuários de acessar os recursos de acesso a rede.
    
## <a name="eavesdropping-sniffing-snooping"></a>Espionagem (Bisbilhotar, Intrometer)

A Espionagem pode ocorrer quando um atacante ganha acesso ao caminho dos dados na rede e tem a habilidade para monitorar e ler o tráfego. Isso também é chamado de bisbilhotar ou falsificar. Se o tráfego está no texto plano, o atacante pode lê-lo quando o atacante ganha acesso ao caminho. Um exemplo é um ataque realizado no controle de um router no caminho dos dados. 
  
A configuração para o tráfego Skype para Business Server e uma recomendação padrão é usar o TLS mútuo (MTLS) entre servidores confiáveis e TLS do cliente para servidor. Essa medida protetora poderia dificultar e muito um ataque ou impossibilitar o alcance com o período de tempo no qual tal conversa ocorre. TLS autentica todas as partes e criptografa todo tráfego. Isso não impede a espionagem, mas o atacante não pode ler o tráfego, a não ser que quebre a criptografia.
  
O protocolo de Relay de Uso Traversal NAT (TURN) não exige o tráfego para ser criptografado e as informações que são enviadas são protegidas pela integridade da mensagem. Mesmo estando abertas apara a espionagem, as informações que são enviadas (o endereço do IP e a porta) podem ser extraídas diretamente dando uma simples olhada nos endereços de saída e de destino dos pacotes. O serviço A/V Edge certifica que os dados são válidos verificando a Integridade da Mensagem da mensagem, usando a chave derivada de poucos itens, incluindo uma senha do TURN, que nunca é enviada em um texto claro. Se o ProtocoIo (SRTP) é usado, o tráfego de mídia também é criptografado.
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>Falsificação de identidade (endereço IP e o chamador falsificação de Id)

Falsificação de identidade ocorre quando o invasor determina e usa um número de telefone de um usuário válido (id de chamador) ou um endereço IP de uma rede, o computador ou o componente de rede sem estar autorizado a fazer isso. Um ataque bem-sucedido permite que o invasor opere como se o invasor é a entidade normalmente identificada pelo número de telefone (id de chamador) ou o endereço IP.

Dentro do contexto do Skype para Business Server, falsificação de endereço IP entra em ação somente se um administrador tiver executado um dos seguintes procedimentos:
  
- Conexões configuradas que suportam apenas o Protocolo de Controle de Transmissão (TCP) (o que não é recomendado, porque as comunicações do TCP são descriptografadas).
    
- Marque os endereços de IP daquelas conexões como hosts confiáveis.
    
Este é o menor dos problemas para as conexões de Transport Layer Security (TLS), uma vez que a TLS autentica toda as partes e criptografa todo o tráfego. Usar a TLS impede que um atacante falsifique o endereço IP em uma conexão específica (por exemplo, conexões TLS mútuas). Mas o invasor ainda pode falsificar o endereço do servidor DNS, que usa Skype para Business Server. No entanto, como autenticação no Skype para negócios é realizada com certificados, um invasor não tem um certificado válido necessário para realizar a falsificação uma das partes na comunicação.

Por outro lado, falsificação de Id de chamador entra em ação depois de estabelecer um tronco SIP entre um provedor, gateway PSTN ou outro sistema PBX e Skype para Business Server. Nesses casos, Skype para Business Server não oferece nenhuma proteção para impedir contra falsificação de id do chamador. Isso significa que um Skype para o usuário de negócios pode receber uma chamada do tronco SIP com uma id de chamador falsificados exibindo o número de telefone do outro Skype para o usuário de negócios. Proteção ao seguinte deve ser aplicada no lado do provedor, gateway PSTN ou PBX.
  
## <a name="man-in-the-middle-attack"></a>Ataque a intermediário

Um ataque man-in-the-middle ocorre quando um invasor roteia novamente a comunicação entre dois usuários através do computador do invasor sem o conhecimento dos dois usuários estão se comunicando. O invasor pode monitorar e ler o tráfego antes de enviá-lo ao destinatário pretendido. Cada usuário presente na comunicação, sem saber, envia e recebe tráfego do invasor pensando estar se comunicando apenas com o usuário pretendido. Isso pode acontecer se um invasor conseguir modificar os Active Directory Domain Services para adicionar o servidor dele como um servidor confiável ou modificar o DNS (Sistema de Nome de Domínio) para fazer com que os clientes se conectem ao invasor no caminho para o servidor. Um ataque man-in-the-middle também pode ocorrer com o tráfego de mídia entre dois clientes. No entanto, Skype para Business Server ponto a ponto de áudio, vídeo e compartilhamento de aplicativos, fluxos são criptografados com o protocolo SRTP, usando as chaves de criptografia que são negociadas entre os pontos que estão usando o protocolo de iniciação de sessão (SIP) sobre TLS. Servidores como o Chat de grupo fazer uso de HTTPS para aprimorar a segurança do tráfego da web.
  
## <a name="rtp-replay-attack"></a>Ataque por Repetição RTP

Um ataque por repetição ocorre quando uma transmissão válida de mídia entre duas partes é interceptada e retransmitida de forma mal-intencionada. O SRTP usado em conexão com um protocolo de sinalização de segurança protege as transmissões contra ataques por repetição, habilitando o receptor a manter um índice de pacotes RTP já recebidos e a comparar cada novo pacote com aqueles já listados no índice.
  
## <a name="spim"></a>Spim

Spim é uma mensagem instantânea comercial não solicitada ou pedidos de inscrição de presença. Embora não seja por si só um comprometimento da rede, é, no mínimo, irritante, pois pode reduzir a disponibilidade e a produção de recursos e levar a um comprometimento da rede. Um exemplo disso é quando os usuários fazem "spimming" uns para os outros, por meio de envios de solicitações. Os usuários podem bloquear uns aos outros para evitar isso, mas com a federação, se um ataque spim coordenado for estabelecido, isso poderá ser difícil de superar, a não ser que você desabilite a federação do parceiro.
  
## <a name="viruses-and-worms"></a>Vírus e Worms

Um vírus é uma unidade de código cujo propósito é reproduzir unidades de códigos adicionais e similares. Para funcionar, um vírus precisa de um host, como um arquivo, email ou programa. Aworm é uma unidade de código cuja finalidade é reproduzir unidades de código adicionais similares, mas ela não precisa ter um host. Os vírus e os worms aparecem principalmente durante transferências de arquivos entre clientes ou quando as URLs são enviadas por outros usuários. Um vírus no seu computador pode, por exemplo, usar sua identidade e enviar mensagens instantâneas em seu nome.
  
## <a name="personally-identifiable-information"></a>Informações de Identificação Pessoal

Skype para Business Server tem o potencial de divulgar informações em uma rede pública que poderia ser vinculados a um indivíduo. Os tipos de informações podem ser separados em duas categorias específicas:
  
- **Dados de presença avançada** Dados de presença avançada são informações que um usuário pode optar por compartilhar ou não em um vínculo a um parceiro federado ou com contatos dentro de uma organização. Esses dados não são compartilhados com usuários em uma rede IM pública. As políticas dos clientes e outras configurações de clientes podem dar um certo controle com o administrador do sistema. Skype para Business Server, o modo de privacidade de presença avançada pode ser configurado para um usuário individual evitar que Skype para usuários comerciais não na lista de contatos do usuário vejam as informações de presença do usuário. Modo de privacidade de presença avançada não impede que os usuários do Microsoft Office Communicator 2007 e Microsoft Office Communicator 2007 R2 ver informações de presença de um usuário. Para obter detalhes sobre como implantar o cliente e a presença, consulte [Deploy de clientes para o Skype para Business Server](../../deploy/deploy-clients/deploy-clients.md) e [Planejar a mensagens instantâneas e presença no Skype para Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
    
- **Dados obrigatórios** Dados obrigatórios é necessários para a operação adequada do servidor ou o cliente e não está sob o controle de administração do sistema ou do cliente. Essas informações são necessárias no nível do servidor ou no nível da rede para fins de roteamento, manutenção de estado e sinalização.
    
As seguintes listas tabelas de dados são exibidas para a rede pública.
  
**Dados de Presença Aumentados**

|**Dados Divulgados**|**Configurações Possíveis**|
|:-----|:-----|
|Dados Pessoais  <br/> |Nome, Título, empresa, Email, Fuso Horário  <br/> |
|Números de Telefone  <br/> |Comercial, Celular, Residencial  <br/> |
|Informações de Calendário  <br/> |Disponível/Ocupado, Aviso de Ausência, Detalhes da Reunião (para aqueles que têm acesso ao seu calendário)  <br/> |
|Status de Presença  <br/> |Ausente, Disponível, Ocupado, Não Perturbe, Offline  <br/> |
   
**Dados Obrigatórios**


| **Dados Divulgados** | **Exemplo de Informações**                            |
|:-------------------|:---------------------------------------------------|
| Endereço de IP  <br/>  | Endereço atual do computador ou endereço do NATed  <br/> |
| URI do SIP  <br/>     | jeremylos@litwareinc.com  <br/>                    |

