---
title: Planejar o Roteamento baseado na localização para o Roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.service: msteams
ms.reviewer: roykuntz
search.appverid: MET150
description: Saiba como planejar o roteamento baseado no local para roteamento direto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8e6e8167dd6f543693638bed4fcbb467600364f0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461680"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planejar o Roteamento baseado na localização para o Roteamento direto

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>Visão geral do roteamento baseado no local

Em alguns países e regiões, não é possível ignorar o provedor de rede de telefônica pública comutada (PSTN) para diminuir os custos de chamada de longa distância. Este artigo descreve como usar o roteamento baseado no local para restringir o bypass de Chamada Tarifada para usuários do Microsoft Teams baseados em sua localização geográfica. Este artigo se aplica apenas ao roteamento direto de sistema do telefone.

Aqui, você obterá uma visão geral de roteamento baseado no local e orientações para ajudá-lo a planejar a ele. Quando você estiver pronto para aplicar e habilitar o roteamento baseado em local, consulte:
- [Implantar as configurações de rede para roteamento baseado no local](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

Roteamento baseado no local é um recurso que permite restringir o bypass de Chamada Tarifada com base em política e o local geográfico do usuário no momento de uma chamada PSTN de entrada ou de saída. 

Quando um usuário de equipes estiver habilitado para roteamento baseado em local, aplica o seguinte:
- Para fazer uma chamada de PSTN de saída, uma das opções a seguir deve ser verdadeira:
    - Ponto de extremidade do usuário está localizado em um site de rede que está habilitado para saída de chamadas e roteamento baseado no local através do gateway correspondente que está habilitado para roteamento baseado no local. 
    - Ponto de extremidade do usuário está localizado em um site de rede que não está habilitado para roteamento baseado no local e chamadas de saída por meio de um gateway que não está habilitado para roteamento baseado no local.

    Chamadas de saída não são permitidas em qualquer outro cenário.

- Para receber uma chamada de entrada de PSTN, o ponto de extremidade atendimento do usuário deve estar localizado no mesmo site de rede onde os ingresses chamada através do gateway que está habilitado para roteamento baseado no local. Em qualquer cenário, por exemplo, se o usuário é móveis, a chamada não é permitida e é roteada para (geralmente caixa postal) de configurações de encaminhamento de chamadas do usuário.
- Para transferir uma chamada PSTN para outro usuário de equipes, a meta de ponto de extremidade do usuário deve estar localizado no mesmo site do usuário que inicia a transferência. Transferências não são permitidas em qualquer outro cenário. 
- Para transferir o outro usuário equipes para a PSTN, a chamada deve ser transferida através de um gateway de roteamento baseados em local habilitado localizado no mesmo site de rede que o chamador inicial. Transferências não são permitidas em qualquer outro cenário.

Roteamento baseado em local usa as mesmas rede região, site e sub-rede definições que Skype para Business Server usa. Quando o desvio de Chamada Tarifada é restrito para um local, um administrador que associa cada sub-rede do IP e a cada gateway PSTN para esse local a um site de rede. Localização de um usuário é determinada pela sub-rede do IP conectados aos pontos de extremidade de equipes do usuário no momento de uma chamada PSTN. Um usuário pode ter vários clientes de equipes localizados em locais diferentes, nesse caso o roteamento baseado em local impõe a cada cliente roteamento separadamente, dependendo do local do seu ponto de extremidade. 

Para se familiarizar com a parte da rede terminologia usada neste artigo, consulte [terminologia de roteamento baseados em local](location-based-routing-terminology.md).

## <a name="apply-location-based-routing"></a>Aplicar o roteamento baseado no local

Você deve aplicar o roteamento baseado no local para usuários, sites de rede e gateways PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar o roteamento baseados em local no local do usuário

Conforme mencionado anteriormente, o roteamento baseado em local só se aplica aos usuários que estiverem configurados para roteamento direto. Roteamento baseado no local não se aplica aos usuários que estiverem configurados para planejar a chamada. Usuários devem ser habilitados para roteamento baseado em local, se eles estiverem em restrição de bypass de Chamada Tarifada, que controla as condições nas quais eles podem fazer e receber chamadas PSTN e o gateway PSTN que pode ser usado. Quando um usuário habilitado para roteamento baseado no local está localizado em um site que tenha habilitado para roteamento baseado em local, o usuário deve fazer chamadas através de um gateway de roteamento baseados em local habilitado conectados ao site. 

Roteamento baseado no local funciona, determinando o local atual do usuário, com base no endereço IP do ponto de extremidade de equipes do usuário e aplica as regras de acordo. O local de um usuário que esteja habilitado para roteamento baseado no local pode ser categorizado das seguintes maneiras: 
- **O usuário está localizado no mesmo roteamento baseados em local habilitado site associado ao gateway PSTN onde seu DID é atribuído.**<br>Neste cenário, o usuário está localizado em um site de rede conhecido que está habilitado para roteamento baseado no local e direto DID do usuário (discagem) termina de número em um gateway PSTN que está no mesmo site de rede. Por exemplo, o usuário está em seu escritório. 
- **O usuário está localizado em um roteamento baseados em local habilitado site diferente não associado ao gateway PSTN onde seu DID é atribuído.**<br>Neste cenário, o usuário está localizado em um site de rede conhecido que está habilitado para roteamento baseado em local, e esse site não está associado com o gateway PSTN onde o número DID do usuário é atribuído. Por exemplo, o usuário é encaminhado para outro escritório.  
- **O usuário está localizado em um site interno que não está habilitado para roteamento baseado no local.** <br>Neste cenário, o usuário está localizado em um site de rede interna conhecidas que não está habilitado para roteamento baseado no local. 
- **O usuário está localizado em um site desconhecido.** 
    - O usuário está localizado dentro da rede interna que não está definida como um site de rede. 
    - O usuário está localizado fora da rede interna. Por exemplo, o usuário está na Internet em casa ou em um cybercafé. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar o roteamento baseados em local no site de rede 
Sites de rede devem ser habilitados para roteamento baseado no local ajudar a determinar quais gateways para rotear os usuários de roteamento baseados em local habilitado quando estiver em roaming. Se um usuário que esteja habilitado para roteamento baseado em local passa para um site que está habilitado para roteamento baseado em local, apenas o gateway PSTN que está habilitado para roteamento baseados em local nesse site pode ser usado para chamadas de saída. Se um usuário que esteja habilitado para roteamento baseado em local passa para um site que não está habilitado para roteamento baseado em local, qualquer gateway que não está habilitado para roteamento baseado no local pode ser usado para chamadas de saída.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar o roteamento baseado no local em que o gateway PSTN 

Gateways associados aos sites para determinar onde um usuário habilitado para roteamento baseado no local pode ser localizado quando eles fazer ou recebem uma chamada PSTN. Gateways devem ser habilitados para roteamento baseado no local garantir que ele esteja sob restrições de bypass de Chamada Tarifada e não pode ser usado por usuários que não estão habilitados para roteamento baseado no local. O mesmo gateway pode ser associado a vários sites e pode ser configurado para ser habilitado para roteamento baseado no local ou não habilitado para roteamento baseado em local, dependendo do site. 

## <a name="scenarios-for-location-based-routing"></a>Cenários para Roteamento Baseado em Local

Esta seção descreve os diferentes cenários para restringir o bypass de Chamada Tarifada usando roteamento baseado no local e compara como as chamadas são roteadas para os usuários que não estão habilitados para roteamento baseado no local com usuários habilitados para roteamento baseado no local.

- [Usuário de equipes faz uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [Usuário de equipes recebe uma chamada de entrada do PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Usuário de equipes transfere ou encaminha a chamada para outro usuário de equipes](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Usuário de equipes transfere ou encaminha a chamada para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Toque simultâneo](#simultaneous-ringing)
- [Delegação](#delegation)

O diagrama a seguir mostra as restrições habilitadas por roteamento baseado no local em cada cenário. Usuários, sites de rede e gateways que estão habilitados para roteamento baseado em local têm uma borda ao redor deles. Use o diagrama como um guia para ajudá-lo a entender como baseados em local funciona de roteamento em cada cenário.  

![Diagrama mostrando cenários para roteamento baseado no local] (media/lbr-direct-routing.png "Diagrama mostrando cenários para roteamento baseado no local")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Usuário de equipes faz uma chamada de saída para o PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento baseado no local

Um usuário que não está habilitado para roteamento baseado no local pode fazer chamadas de saída usando qualquer gateway em qualquer site que não está habilitado para roteamento baseados em local por meio da política de roteamento de voz atribuída. No entanto, se um gateway estiver habilitado para roteamento baseado em local, o usuário não pode fazer chamadas de saída através do gateway, mesmo se ela estiver atribuída a política de roteamento de voz. Se o usuário passa para um site que está habilitado para roteamento baseado em local, eles só podem fazer chamadas por meio de seus gateways normais de roteamento que não estão habilitados para roteamento baseado no local.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento baseado no local
Em comparação, o roteamento de chamadas de saída para usuários habilitados para roteamento baseado em local é afetado por local da rede do ponto de extremidade do usuário. A tabela a seguir mostra como baseados em local roteamento afeta o roteamento de chamadas de saída de User1, dependendo do local do User1. 

|Local do ponto de extremidade User1  |Roteamento de chamadas de saída para o Usuário1  |
|---------|---------|
|Mesmo site onde DID do usuário é atribuído, site habilitado para roteamento baseados em local (Site1)      |Chamadas roteadas por meio do gateway está habilitado para roteamento baseado no local (GW1) em Site1, com base na política de roteamento de voz do usuário         |
|Site diferente de onde DID do usuário é atribuído, o site habilitado para roteamento baseados em local (Site2)    |Chamada roteada pelo gateway está habilitado para roteamento baseado em local (GW2) em roam Site2, com base na política de roteamento de voz do usuário        |
|Site diferente de onde DID do usuário é atribuído, o site não habilitado para roteamento baseados em local (downloads3)  |Chamadas roteadas por meio de gateway que não está habilitado para roteamento baseados em local no site que não tenha sido habilitado para baseados em local roteamento (GW3), com base na política de roteamento de voz do usuário       |
|Rede interna desconhecido (Location4)    |  PSTN chamar não permitidos       |
|Rede externa desconhecido (Location5)    | PSTN chamar não permitidos        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Usuário de equipes recebe uma chamada de entrada do PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento baseado no local

Um usuário que não está habilitado para roteamento baseado no local pode receber uma chamada de entrada do gateway que não está habilitado para roteamento baseados em local do qual seus atribuído número ingresses. Se o usuário passa para um site que não está habilitado para roteamento baseado em local, eles ainda poderá receber chamadas através de seus gateways PSTN normais.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento baseado no local

Em comparação, os usuários habilitados para roteamento baseado em local somente podem receber chamadas de entrada do gateway PSTN que seu DID é atribuída a quando eles estão localizados no mesmo site. A tabela a seguir mostra como User1 recebe as chamadas de entrada quando User1 é movido para locais de rede diferente. Se a chamada não é encaminhada ao ponto de extremidade do usuário, ela vai para configurações, de encaminhamento de chamadas do usuário se as configurações são definidas. Geralmente, isso é a caixa postal.  

|Local do ponto de extremidade User1  |Roteamento de chamadas de entrada para o Usuário1  |
|---------|---------|
|Mesmo site onde DID do usuário é atribuído, o site habilitado para roteamento baseados em local (Site1)   | Chamadas roteadas para o ponto de extremidade do Usuário1 em Site1        |
|Site diferente de onde DID do usuário é atribuído, o site habilitado para roteamento baseados em local (Site2)    | Chamadas não são roteadas para os pontos de extremidade Site2        |
|Site diferente de onde DID do usuário é atribuído, o site não habilitado para roteamento baseados em local (downloads3)    | Chamadas não são roteadas para os pontos de extremidade downloads3        |
|Rede interna desconhecido (Location4)   | Chamadas não são roteadas para os pontos de extremidade Location4        |
|Rede externa desconhecido (Location5)     | Chamadas não são roteadas para os pontos de extremidade Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Usuário de equipes transfere ou encaminha a chamada para outro usuário de equipes

Quando um ponto de extremidade PSTN está envolvido, roteamento baseado em local analisa se um ou ambos os usuários estão habilitados para roteamento baseado no local e determina se a chamada deve ser transferida ou encaminhada dependendo do local de ambos os pontos de extremidade. 
 
Transferência de chamada exige que o usuário inicial atender a chamada enquanto o encaminhamento de chamadas não exige a chamada inicial a ser atendido. Isso significa que as chamadas podem ser encaminhadas, mesmo se o Usuário1 não está em um local para receber entrada chama (consulte a tabela na seção [usuário equipes recebe uma chamada de entrada do PSTN](#teams-user-receives-an-inbound-call-from-the-pstn) ) e chamadas não poderão ser transferidas se User1 não puder receber a chamada de entrada. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento baseado no local

Um usuário que não está habilitado para roteamento baseado no local pode transferir ou PSTN encaminhar chamadas para outros usuários que não são habilitados para roteamento baseado no local. O usuário normalmente não poderão transferir ou encaminhar uma chamada PSTN para um usuário que esteja habilitado para roteamento baseado em local porque o roteamento baseado em local habilitado os usuários geralmente podem apenas ser colocado em gateways de roteamento baseados em local habilitado para PSTN chamadas. A exceção é quando um roteamento baseados em local habilitado o usuário estiver se movendo para um site que não está habilitado para roteamento baseado no local. Neste cenário, a chamada transferida é permitida.  

Da mesma forma, um usuário que não está habilitado para roteamento baseado em local só pode receber uma transferência ou encaminhou a chamada PSTN de outro usuário que não está habilitado para roteamento baseado no local. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento baseado no local

Geralmente, transferindo e encaminhando chamadas de PSTN de entrada de um gateway que está habilitado para roteamento baseado no local é permitida apenas se o usuário de destino está habilitado para roteamento baseado no local e está localizado no mesmo site. Caso contrário, não não permitido transferindo e encaminhando chamadas. 

A tabela a seguir mostra se transferências de chamada e o encaminhamento de chamada são permitidas, dependendo do local do usuário de destino. Nesta tabela, User1, localizado em Site1, inicia a transferência ou encaminhar para outros usuários de equipes que também são habilitados para roteamento baseado em local e que estão em diferentes locais.  

|Local de ponto de extremidade do usuário de destino|O Usuário1 inicia a transferência de chamada |O Usuário1 inicia encaminhar a chamada|
|---------|---------|---------|
|Mesmo site de rede como iniciador (User2)|Permitido|Permitido|
|Site de rede diferente, o site habilitado para roteamento baseado no local (User3)|Não permitido|Não permitido|
|Site de rede diferente, o site não habilitado para roteamento baseado no local (User4)|Não permitido|Não permitido|
|Rede interna desconhecido (User5)| Não permitido|Não permitido|
|Rede externa desconhecido (User6)| Não permitido|Não permitido|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Usuário de equipes transfere ou encaminha a chamada para o ponto de extremidade PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento baseado no local

- Transferindo e encaminhando uma chamada PSTN para outro número PSTN é permitido. 
- Transferindo e encaminhando uma chamada VOIP de entrada para a PSTN devem Respeitar restrições de bypass de Chamada Tarifada do chamador. 
    - Se o chamador não está habilitado para roteamento baseado em local, eles podem ser transferidos para qualquer gateway PSTN que não está habilitado para roteamento baseado no local.
    - Se o chamador estiver habilitado para roteamento baseado em local, eles só podem ser transferidos para um gateway de roteamento baseados em local habilitado localizado no mesmo local de rede. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento baseado no local

- Uma PSTN de entrada transferindo e o encaminhamento de chamada para outro número PSTN deve ser roteada check-out do gateway de roteamento baseados em local habilitado mesmo que a chamada de entrada chegou na. 
- Transferindo e encaminhando uma entrada VOIP chamada para a PSTN deve honram ambos o chamador e tarifas do usuário chamado ignorar restrições. 
    - Se o chamador não está habilitado para roteamento baseado em local, eles podem ser transferidos para qualquer gateway PSTN que não está habilitado para roteamento baseado no local.
    - Se o chamador estiver habilitado para roteamento baseado em local, eles podem apenas ser transferida para um gateway de roteamento baseados em local habilitado localizado no mesmo local de rede.
 
A tabela a seguir mostra como baseados em local roteamento afeta o roteamento de uma chamada VOIP de Usuário1 em Site1 aos usuários em diferentes locais que transferir ou encaminham a chamada para um ponto de extremidade PSTN.  

|Iniciando a transferência de chamada ou encaminhar do usuário  |Transferir para o PSTN  |Encaminhar para PSTN  |
|---------|---------|---------|
|Mesmo site de rede, sites habilitados para roteamento baseados em local (User2)   |Chamada transferência só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do Usuário2         |Pode encaminhar de chamada apenas roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do Usuário2         |
|Site de rede diferente, o site habilitado para roteamento baseado no local (User3)    |Chamada transferência só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do User3         |Encaminhar a chamada só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do User3         |
|Site de rede diferente, o site não habilitado para roteamento baseado no local (User4)    |Chamada transferência só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do User4         |Encaminhar a chamada só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do User4         |
|Rede interna desconhecido (User5)     |Chamada transferência só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do User5         |Encaminhar a chamada só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do User5         |
|Rede externa desconhecido (User6)   |Chamada transferência só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do User6        |Encaminhar a chamada só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do User6         |

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando um usuário habilitado para roteamento baseado em local recebe uma chamada e toque simultâneo habilitou, roteamento baseado em local analisa o local da parte chamada e os pontos de extremidade das partes chamados para determinar se a chamada deve ser roteada. Toque simultâneo segue as mesmas regras baseados em local como a chamada a transfere e encaminha. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Toque para outro usuário equipes simultâneo

A tabela a seguir mostra se o roteamento baseado em local permite toques aos diversos usuários para uma chamada de PSTN de entrada para o Usuário1 simultâneo.

|Local de ponto de extremidade do usuário de destino|Toque simultâneo  |
|---------|---------|
|Mesmo site de rede como iniciador (User2)   |Permitido         |
|Site de rede diferente transmitida habilitado para roteamento baseado no local (User3)   |Não permitido         |
|Site de rede transmitida não habilitado para roteamento baseado no local (User4)   |Não permitido        |
|Rede interna desconhecido (User5)    | Não permitido        |
|Rede externa desconhecido (User6)    |Não permitido        |
|Usuário de destino for um número PSTN    |Chamada só pode ser roteada por meio de roteamento baseados em local habilitado Gateway1 em Site1, com base na política de roteamento de voz do Usuário1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Toques para um ponto de extremidade PSTN simultâneos

A tabela a seguir mostra o comportamento de roteamento baseado no local para uma chamada VOIP de entrada de Usuário1 localizada em Site1 aos usuários em diferentes locais com o toque simultâneo definido como um número PSTN. 

|Local de ponto de extremidade do usuário chamado  |Destino de Toque simultâneo é o ponto de extremidade PSTN |
|---------|---------|
|Mesmo site de rede, sites habilitados para roteamento baseados em local (User2)    |Chamada ser só podem ser roteadas por meio de Gateway1 de roteamento baseados em local em Site1, com base na política de roteamento de voz do Usuário2       |
|Site de rede diferente habilitado para roteamento baseado no local (User3)    |Chamada só pode ser roteada por meio de Gateway1 de roteamento baseados em local em Site1, com base na política de roteamento de voz do User3        |
|Site de rede diferente não habilitado para roteamento baseado no local (User4)    |Chamada só pode ser roteada por meio de Gateway1 de roteamento baseados em local em Site1, com base na política de roteamento de voz do User4         |
|Rede interna desconhecido (User5)    |Chamada só pode ser roteada por meio de Gateway1 de roteamento baseados em local em Site1, com base na política de roteamento de voz do User5         |
|Rede externa desconhecido (User6)   |Chamada só pode ser roteada por meio de Gateway1 de roteamento baseados em local em Site1, com base na política de roteamento de voz do User6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Chamadas de entrada por meio de aplicativos de voz (atendedor automático ou chamada fila)

Chamadas de PSTN de entrada de um gateway de roteamento baseados em local habilitado têm permissão para se conectar a uma fila de chamada e atendente automático. Usuários habilitados para roteamento baseado em local só podem receber transferências de chamada de entrada desses aplicativos quando eles estão localizados no mesmo local em que a chamada PSTN de entrada se origina. 
 
Encaminhamento de chamadas e toque simultâneo aos usuários e PSTN é permitida para transferências de aplicativo de voz. Concluir a chamada para o destino está sujeito as mesmas regras de roteamento baseados em local mencionadas anteriormente.  
 
Encaminhar para caixa postal também é permitido.  

### <a name="delegation"></a>Delegação

Um usuário de equipes pode escolher representantes que podem fazer e receber chamadas em nome deles. Recursos de delegação em equipes são afetados pela roteamento baseado em local da seguinte maneira: 
- Para chamadas de saída de um representante de roteamento baseados em local habilitado em nome de um representante, as mesmas regras se aplicam. Roteamento de chamadas baseia-se na diretiva de autorização de chamada, política de roteamento de voz e local o delegado. Para obter mais informações, consulte o [usuário de equipes faz uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 
- Para chamadas PSTN de entrada para um delegator, as mesmas regras de roteamento baseado no local que se aplicam para encaminhamento de chamadas ou ligar simultaneamente para outros usuários também se aplicam ao representantes. Para obter mais informações, consulte [usuário equipes transfere ou encaminha a chamada para outro usuário de equipes](#teams-user-transfers-or-forwards-call-to-another-teams-user), [transferências de usuário de equipes ou encaminha a chamada para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)e [Toque simultâneo](#simultaneous-ringing). Quando um delegado define um ponto de extremidade PSTN como um destino de Toque simultâneo, a política de roteamento de voz do representante é usada para rotear a chamada para o PSTN. 
- Para delegação, é recomendável que os representantes associados e delegator estar localizado no mesmo site de rede. 

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Alterações de uma implantação de roteamento baseados em local no local

Política roteamento de voz de sites de rede não é mais usada. Em vez disso, podemos usar a política de roteamento de voz do usuário. Isso significa que, para permitir que os usuários se movimentem para outros sites, a política de roteamento de voz deve incluir os gateways dos sites roamed. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerações técnicas para Roteamento Baseado em Local

As sub-redes IPv4 e IPv6 são suportadas, no entanto, o IPv6 tem precedência quando a verificação de uma correspondência. Suporte a IPv6 em andamento e estará disponível por gerais disponibilidade (GA) para roteamento baseado no local. 

### <a name="client-support-for-location-based-routing"></a>Suporte ao cliente para roteamento baseado no local

Os clientes de equipes a seguir são suportados:
- Clientes de desktop de equipes (Windows e Mac)
- Clientes móveis de equipes (iOS e Android)
- Telefones IP de equipes

O cliente da web de equipes e Skype para clientes corporativos não são suportados.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

Roteamento baseado no local não se aplica aos seguintes tipos de interações. Roteamento baseado no local não é imposto quando os pontos de extremidade de equipes interagem com pontos de extremidade PSTN nos seguintes cenários: 
- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada 
- Skype um local para o usuário de negócios ou um Skype para Business Online usuário responde a um usuário de equipes  

### <a name="location-based-routing-for-conferencing"></a>Roteamento baseado no local para conferência

Um usuário de roteamento baseados em local habilitado em uma chamada PSTN não é permitido para iniciar uma conferência com outro usuário ou número PSTN. Conectando a atendedores automáticos ou filas de chamada é permitido. Se o usuário possui uma licença de conferência, o usuário deve iniciar uma conferência com os usuários relevantes e chamadas PSTN por meio de ponte de conferência para iniciar uma chamada em conferência.  

## <a name="next-steps"></a>Próximas etapas
Vá para [definir configurações de rede para roteamento baseado no local](location-based-routing-configure-network-settings.md).

### <a name="related-topics"></a>Tópicos relacionados
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Terminologia do Roteamento baseado na localização](location-based-routing-terminology.md)