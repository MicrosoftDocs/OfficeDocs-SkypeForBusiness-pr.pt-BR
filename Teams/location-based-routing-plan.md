---
title: Planejar o Roteamento baseado na localização para o Roteamento direto
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Saiba como planejar o roteamento Location-Based roteamento direto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28dae01dd48537696aa140e07b947a03880b5307
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774561"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planejar o Roteamento baseado na localização para o Roteamento direto

## <a name="overview-of-location-based-routing"></a>Visão geral do Location-Based Routing

Em alguns países e regiões, é ilegal ignorar o provedor PSTN (Rede Telefônica Pública Comutado) para diminuir os custos de chamadas de longa distância. Este artigo descreve como usar o Location-Based roteamento para restringir o desvio de tarifa para usuários Microsoft Teams com base em sua localização geográfica. Este artigo se aplica somente a Sistema de Telefonia Roteamento Direto.

Aqui você obterá uma visão geral do Location-Based roteamento e orientações para ajudá-lo a planejar isso. Quando você estiver pronto para aplicar e habilitar Location-Based Roteamento, consulte:

- [Implantar configurações de rede para Location-Based Routing](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

> [!NOTE]
> Location-Based o roteamento não está disponível em implantações Microsoft 365 Nuvem da Comunidade Governamental (GCC) High ou DoD.

Location-Based Roteamento é um recurso que permite restringir o desvio de chamada com base na política e na localização geográfica do usuário no momento de uma chamada PSTN de entrada ou de saída. Location-Based Roteamento destina-se a fornecer um mecanismo para impedir o desvio de tarifa. Ele não deve ser usado como um mecanismo para rotear dinamicamente chamadas PSTN com base no local do usuário ou consequências não intencionais podem resultar.

Quando um Teams usuário está habilitado para roteamento Location-Based, o seguinte se aplica:

- Para fazer uma chamada PSTN de saída, um dos seguintes deve ser verdadeiro:
    - O ponto de extremidade do usuário está localizado em um site de rede habilitado para roteamento de Location-Based e chamadas egressam pelo gateway correspondente habilitado para roteamento Location-Based. 
    - O ponto de extremidade do usuário está localizado em um site de rede que não está habilitado para roteamento Location-Based e chama saída por meio de um gateway que não está habilitado para roteamento Location-Based.

    Chamadas de saída não são permitidas em nenhum outro cenário.

- Para receber uma chamada PSTN de entrada, o ponto de extremidade de atendimento do usuário deve estar localizado no mesmo site de rede em que a chamada entrar pelo gateway habilitado para roteamento Location-Based. Em qualquer outro cenário, como se o usuário estiver em roaming, a chamada não é permitida e é roteada para as configurações de encaminhamento de chamada do usuário (normalmente caixa postal).
- Para transferir uma chamada PSTN para outro usuário Teams, o ponto de extremidade do usuário de destino deve estar localizado no mesmo site de rede que o usuário que inicia a transferência. As transferências não são permitidas em nenhum outro cenário. 
- Para transferir outro usuário Teams para o PSTN, a chamada deve ser transferida por meio de um gateway habilitado para roteamento Location-Based localizado no mesmo site de rede do chamador inicial. As transferências não são permitidas em nenhum outro cenário.

Location-Based routing usa a mesma região de rede, site e definições de sub-rede que Skype for Business Server usa. Quando o desvio de tarifa é restrito para um local, um administrador associa cada sub-rede IP e cada gateway PSTN para esse local a um site de rede. A localização de um usuário é determinada pela sub-rede IP à Teams ponto de extremidade do usuário que estão conectados no momento de uma chamada PSTN. Um usuário pode ter vários clientes Teams localizados em sites diferentes, nesse caso, Location-Based Routing impõe o roteamento de cada cliente separadamente, dependendo do local de seu ponto de extremidade. 

Para se familiarizar com algumas das terminologias de rede usadas neste artigo, consulte Configurações de rede para recursos de voz na [nuvem em Teams](cloud-voice-network-settings.md).

## <a name="apply-location-based-routing"></a>Aplicar Location-Based roteamento

Você deve aplicar Location-Based roteamento a usuários, sites de rede e gateways PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar Location-Based roteamento no local do usuário

Como mencionado anteriormente, Location-Based Roteamento só se aplica a usuários que estão definidos para Roteamento Direto. Location-Based Roteamento não se aplica aos usuários que estão definidos para o Plano de Chamadas. Os usuários devem estar habilitados para roteamento Location-Based se eles estão sob restrição de desvio de chamada de chamada, que controla as condições em que podem fazer e receber chamadas PSTN e o gateway PSTN que pode ser usado. Quando um usuário habilitado para roteamento Location-Based está localizado em um site habilitado para roteamento Location-Based, o usuário deve fazer chamadas por meio de um gateway habilitado para roteamento de Location-Based conectado ao site. 

Location-Based o roteamento funciona determinando o local atual do usuário com base no endereço IP do ponto de extremidade Teams usuário e aplica as regras de acordo. O local de um usuário habilitado para roteamento Location-Based pode ser categorizado das seguintes maneiras: 
- **O usuário está localizado no mesmo local Location-Based site habilitado para Roteamento associado ao gateway PSTN em que seu DID é atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede conhecido habilitado para roteamento Location-Based e o número did (Discagem direta) do usuário termina em um gateway PSTN que está no mesmo site de rede. Por exemplo, o usuário está em seu escritório. 
- **O usuário está localizado em um site Location-Based roteamento não associado ao gateway PSTN em que seu DID é atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede conhecido habilitado para roteamento Location-Based e esse site não está associado ao gateway PSTN em que o número DID do usuário é atribuído. Por exemplo, o usuário viaja para outro escritório.  
- **O usuário está localizado em um site interno que não está habilitado para roteamento Location-Based.** <br>Nesse cenário, o usuário está localizado em um site de rede interna conhecido que não está habilitado para roteamento Location-Based. 
- **O usuário está localizado em um site desconhecido.** 
    - O usuário está localizado dentro da rede interna que não é definida como um site de rede. 
    - O usuário está localizado fora da rede interna. Por exemplo, o usuário está na Internet em casa ou em uma cafeteria. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar Location-Based roteamento no site de rede 
Os sites de rede devem estar habilitados para Location-Based roteamento para ajudar a determinar quais gateways encaminhar Location-Based usuários habilitados para roteamento durante o roaming. Se um usuário habilitado para roteamento de Location-Based estiver em um site habilitado para roteamento de Location-Based, somente o gateway PSTN habilitado para roteamento de Location-Based nesse site poderá ser usado para chamadas de saída. Se um usuário habilitado para roteamento de Location-Based roams para um site que não está habilitado para roteamento Location-Based, qualquer gateway que não está habilitado para roteamento Location-Based pode ser usado para chamadas de saída.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar Location-Based roteamento no gateway PSTN 

Os gateways são associados a sites para determinar onde um usuário habilitado para o roteamento Location-Based pode estar localizado quando faz ou recebe uma chamada PSTN. Os gateways devem ser habilitados para Location-Based Roteamento para garantir que ele está sob restrições de desvio de tarifa e não podem ser usados por usuários que não estão habilitados para roteamento Location-Based. O mesmo gateway pode estar associado a vários sites e pode ser configurado para ser habilitado para roteamento Location-Based ou não habilitado para roteamento Location-Based, dependendo do site.

## <a name="scenarios-for-location-based-routing"></a>Cenários do Roteamento Baseado na Localização

Esta seção descreve diferentes cenários para restringir o bypass de chamada de chamada usando o roteamento do Location-Based e compara como as chamadas são roteadas para usuários que não estão habilitados para roteamento de Location-Based com usuários habilitados para roteamento Location-Based.

- [Teams usuário coloca uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams usuário recebe uma chamada de entrada do PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams o usuário transfere ou encaminha chamada para outro Teams usuário](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams o usuário transfere ou encaminha chamada para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Toque simultâneo](#simultaneous-ringing)
- [Delegação](#delegation)

O diagrama a seguir mostra as restrições habilitadas Location-Based Roteamento em cada cenário. Usuários, sites de rede e gateways habilitados para Location-Based roteamento têm uma borda ao redor deles. Use o diagrama como um guia para ajudá-lo a entender como o roteamento Location-Based funciona em cada cenário.  

![Diagrama mostrando cenários para Location-Based Routing.](media/lbr-direct-routing.png "Diagrama mostrando cenários para roteamento Location-Based roteamento")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams usuário coloca uma chamada de saída para o PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para roteamento Location-Based pode fazer chamadas de saída usando qualquer gateway em qualquer site que não está habilitado para o roteamento de Location-Based por meio de sua política de roteamento de voz atribuída. No entanto, se um gateway estiver habilitado para roteamento de Location-Based, o usuário não poderá fazer chamadas de saída pelo gateway, mesmo que ele seja atribuído à política de roteamento de voz. Se o usuário estiver em roams para um site habilitado para roteamento Location-Based, ele só poderá fazer chamadas por meio de seus gateways de roteamento normais que não estão habilitados para roteamento Location-Based.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário
Em comparação, o roteamento de chamadas de saída para usuários habilitados para o roteamento Location-Based é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir mostra como Location-Based Roteamento afeta o roteamento de chamadas de saída de User1, dependendo do local de User1. 

|Local do ponto de extremidade user1  |Roteamento de chamadas de saída para User1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site1)      |Chamada roteada por gateway habilitado para o Location-Based De roteamento (GW1) no Site1, com base na política de roteamento de voz do usuário         |
|Site diferente de onde o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site2)    |Chamada roteada por gateway habilitado para o Location-Based de roteamento (GW2) em roam Site2, com base na política de roteamento de voz do usuário        |
|Site diferente de onde o DID do usuário é atribuído, site não habilitado para roteamento Location-Based (Site3)  |Chamada roteada por gateway que não está habilitado para roteamento de Location-Based no site que não está habilitado para o Location-Based Routing (GW3), com base na política de roteamento de voz do usuário       |
|Rede interna desconhecida (Location4)    |  Chamada PSTN não permitida       |
|Rede externa desconhecida (Location5)    | Chamada PSTN não permitida        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams usuário recebe uma chamada de entrada do PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para roteamento Location-Based pode receber uma chamada de entrada do gateway que não está habilitado para roteamento de Location-Based a partir do qual o número DID atribuído é atribuído. Se o usuário percorrer um site que não esteja habilitado para roteamento Location-Based, ele ainda poderá receber chamadas por meio de seus gateways PSTN normais.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

Em comparação, os usuários habilitados para Location-Based Roteamento só podem receber chamadas de entrada do gateway PSTN ao que seu DID é atribuído quando estão localizados no mesmo site. A tabela a seguir mostra como User1 recebe chamadas de entrada quando User1 se move para locais de rede diferentes. Se a chamada não for roteada para o ponto de extremidade do usuário, ela irá para as configurações de encaminhamento de chamada do usuário, se as configurações estão configuradas. Normalmente, isso é caixa postal.  

|Local do ponto de extremidade user1  |Roteamento de chamadas de entrada para User1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para roteamento Location-Based (Site1)   | Chamadas roteada para o ponto de extremidade do Usuário1 no Site1        |
|Site diferente de onde o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site2)    | Chamadas não roteada para pontos de extremidade no Site2        |
|Site diferente de onde o DID do usuário é atribuído, site não habilitado para roteamento Location-Based (Site3)    | Chamadas não roteada para pontos de extremidade no Site3        |
|Rede interna desconhecida (Location4)   | Chamadas não roteados para pontos de extremidade em Location4        |
|Rede externa desconhecida (Location5)     | Chamadas não roteada para pontos de extremidade em Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams o usuário transfere ou encaminha chamada para outro Teams usuário

Quando um ponto de extremidade PSTN está envolvido, o Location-Based Routing analisa se um ou ambos os usuários estão habilitados para roteamento Location-Based e determina se a chamada deve ser transferida ou encaminhada dependendo do local dos dois pontos de extremidade. 
 
A transferência de chamada exige que o usuário iniciador atenda a chamada enquanto o encaminhamento de chamada não exige que a chamada inicial seja atendida. Isso significa que as chamadas podem ser encaminhadas mesmo se User1 não estiver em um local para receber chamadas de entrada (consulte a tabela no Teams o usuário recebe uma chamada de entrada da seção [PSTN)](#teams-user-receives-an-inbound-call-from-the-pstn) e as chamadas não poderão ser transferidas se User1 não puder receber a chamada de entrada. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para roteamento Location-Based pode transferir ou encaminhar chamadas PSTN para outros usuários que não estão habilitados para roteamento Location-Based. Normalmente, o usuário não terá permissão para transferir ou encaminhar uma chamada PSTN para um usuário habilitado para roteamento de Location-Based porque os usuários habilitados para roteamento do Location-Based geralmente só têm permissão para serem co Location-Based-localizados em gateways habilitados para roteamento para chamadas PSTN. A exceção é quando um usuário Location-Based roteamento habilitado para roteamento para um site que não está habilitado para roteamento Location-Based. Nesse cenário, a chamada transferida é permitida.  

Da mesma forma, um usuário que não está habilitado para o Location-Based Routing só pode receber uma chamada PSTN transferida ou encaminhada de outro usuário que não está habilitado para roteamento Location-Based. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

Geralmente, a transferência e o encaminhamento de chamadas PSTN de entrada de um gateway habilitado para roteamento Location-Based só é permitido se o usuário de destino estiver habilitado para roteamento de Location-Based e estiver localizado no mesmo site. Caso contrário, não é permitido transferir e encaminhar chamadas. 

A tabela a seguir mostra se as transferências de chamada e encaminhamento de chamada são permitidas, dependendo do local do usuário de destino. Nesta tabela, User1, localizado no Site1, inicia a transferência ou encaminha para outros usuários Teams que também estão habilitados para roteamento Location-Based e que estão em locais diferentes.  

|Local de ponto de extremidade do usuário de destino|User1 inicia a transferência de chamada |User1 inicia o encaminhamento de chamada|
|---------|---------|---------|
|Mesmo site de rede do iniciador (User2)|Permitido|Permitido|
|Site de rede diferente, site habilitado para Location-Based Roteamento (User3)|Não permitido|Não permitido|
|Site de rede diferente, site não habilitado para Location-Based Roteamento (User4)|Não permitido|Não permitido|
|Rede interna desconhecida (User5)| Não permitido|Não permitido|
|Rede externa desconhecida (User6)| Não permitido|Não permitido|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams o usuário transfere ou encaminha chamada para o ponto de extremidade PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

- É permitido transferir e encaminhar uma chamada PSTN para outro número PSTN. 
- Transferir e encaminhar uma chamada VOIP de entrada para a PSTN deve honrar as restrições de desvio de chamada. 
    - Se o chamador não estiver habilitado para roteamento de Location-Based, ele poderá ser transferido para qualquer gateway PSTN que não está habilitado para roteamento Location-Based.
    - Se o chamador estiver habilitado para roteamento Location-Based, ele só poderá ser transferido para um gateway habilitado para roteamento Location-Based localizado no mesmo site de rede. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

- Transferir e encaminhar uma chamada PSTN de entrada para outro número PSTN deve ser roteado para fora do mesmo gateway habilitado para roteamento Location-Based que a chamada de entrada chegou. 
- Transferir e encaminhar uma chamada VOIP de entrada para a PSTN deve honrar o chamador e as restrições de desvio de chamada do usuário. 
    - Se o chamador não estiver habilitado para roteamento de Location-Based, ele poderá ser transferido para qualquer gateway PSTN que não está habilitado para roteamento Location-Based.
    - Se o chamador estiver habilitado para roteamento Location-Based, ele só poderá ser transferido para um gateway habilitado para roteamento Location-Based localizado no mesmo site de rede.
 
A tabela a seguir mostra como o roteamento de Location-Based afeta o roteamento de uma chamada VOIP de User1 no Site1 para usuários em locais diferentes que transferem ou encaminham a chamada para um ponto de extremidade PSTN.  

|Usuário iniciando a transferência ou encaminhamento de chamada  |Transferir para PSTN  |Encaminhar para PSTN  |
|---------|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based Roteamento (User2)   |A transferência de chamada só pode ser roteada Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário2         |O encaminhamento de chamadas só pode ser roteado Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário2         |
|Site de rede diferente, site habilitado para Location-Based Roteamento (User3)    |A transferência de chamadas só pode ser roteada por meio Location-Based de um Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário3         |O encaminhamento de chamadas só pode ser roteado por meio Location-Based de um Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário3         |
|Site de rede diferente, site não habilitado para Location-Based Roteamento (User4)    |A transferência de chamada só pode ser roteada Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |O encaminhamento de chamadas só pode ser roteado por meio Location-Based de um Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |
|Rede interna desconhecida (User5)     |A transferência de chamada só pode ser roteada Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do User5         |O encaminhamento de chamadas só pode ser roteado Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do User5         |
|Rede externa desconhecida (User6)   |A transferência de chamada só pode ser roteada Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário6        |O encaminhamento de chamadas só pode ser roteado por meio Location-Based de um Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário6         |

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando um usuário habilitado para o roteamento Location-Based recebe uma chamada e tem o toque simultâneo habilitado, o roteamento do Location-Based analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada. O toque simultâneo segue as mesmas regras Location-Based como transferências de chamada e encaminhamentos. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Toque simultâneo para outro Teams usuário

A tabela a seguir mostra se Location-Based roteamento permite toque simultâneo para usuários diferentes para uma chamada PSTN de entrada para User1.

|Local de ponto de extremidade do usuário de destino|Anel simultâneo  |
|---------|---------|
|Mesmo site de rede do iniciador (User2)   |Permitido         |
|Site de rede roamed diferente habilitado para roteamento Location-Based (User3)   |Não permitido         |
|Site de rede roamed não habilitado para roteamento Location-Based (User4)   |Não permitido        |
|Rede interna desconhecida (User5)    | Não permitido        |
|Rede externa desconhecida (User6)    |Não permitido        |
|O usuário de destino é um número PSTN    |A chamada só pode ser roteada Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Toque simultâneo para um ponto de extremidade PSTN

A tabela a seguir mostra Location-Based comportamento de roteamento para uma chamada VOIP de entrada de User1 localizada em Site1 para usuários em locais diferentes com toque simultâneo definido como um número PSTN. 

|Local do ponto de extremidade do usuário chamado  |O destino de anel simultâneo é o ponto de extremidade PSTN |
|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based Roteamento (User2)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário2       |
|Site de rede diferente habilitado para Location-Based Roteamento (User3)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário3        |
|Site de rede diferente não habilitado para roteamento Location-Based (User4)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |
|Rede interna desconhecida (User5)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário5         |
|Rede externa desconhecida (User6)   |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Chamadas de entrada por meio de aplicativo de voz (Atendedor Automático ou Fila de Chamadas)

Chamadas PSTN de entrada de Location-Based gateway habilitado para roteamento têm permissão para se conectar a um atendimento automático ou fila de chamadas. Os usuários habilitados para Location-Based Roteamento só podem receber transferências de chamada de entrada desses aplicativos quando eles estão localizados no mesmo site de onde a chamada PSTN de entrada é originada. 
 
O encaminhamento de chamadas e toque simultâneo para usuários e PSTN é permitido para transferências de aplicativos de voz. Concluir a chamada para o destino está sujeito às mesmas regras de roteamento Location-Based listadas anteriormente.  
 
O encaminhamento para a caixa postal também é permitido.  

### <a name="delegation"></a>Delegação

Um Teams usuário pode escolher representantes que podem fazer e receber chamadas em seu nome. Os recursos de delegação Teams são afetados pela Location-Based roteamento da seguinte forma: 
- Para chamadas de saída de um representante Location-Based roteamento habilitado em nome de um representante, as mesmas regras se aplicam. O roteamento de chamadas se baseia na política de autorização de chamada do representante, na política de roteamento de voz e no local. Para obter mais informações, consulte Teams usuário coloca uma chamada de [saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 
- Para chamadas PSTN de entrada para um delegator, as mesmas regras de roteamento Location-Based que se aplicam ao encaminhamento de chamadas ou ao toque simultâneo a outros usuários também se aplicam aos representantes. Para obter mais informações, consulte Teams user transfers or [forwards call to](#teams-user-transfers-or-forwards-call-to-another-teams-user)another Teams user , [Teams user transfers or forwards call to PSTN endpoint](#teams-user-transfers-or-forwards-call-to-pstn-endpoint), and [Simultaneous ringing](#simultaneous-ringing). Quando um representante define um ponto de extremidade PSTN como um destino de anel simultâneo, a política de roteamento de voz do representante é usada para rotear a chamada para a PSTN. 
- Para delegação, é recomendável que o representante e os delegados associados sejam localizados no mesmo site de rede. 

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Alterações de uma implantação de roteamento local Location-Based roteamento

A política de roteamento de voz do site de rede não é mais usada. Em vez disso, usamos a política de roteamento de voz do usuário. Isso significa que, para permitir que os usuários percorram para outros sites, a política de roteamento de voz deve incluir os gateways dos sites em roamed. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerações técnicas para Roteamento Baseado em Local

As sub-redes IPv4 e IPv6 são suportadas, no entanto, IPv6 tem precedência ao verificar uma match.

### <a name="client-support-for-location-based-routing"></a>Suporte para cliente para roteamento Location-Based cliente

Os seguintes Teams clientes são suportados:
- Teams clientes da área de trabalho (Windows e Mac)
- Teams clientes móveis (iOS e Android)
- Teams Telefones IP

Os Teams web e Skype for Business clientes não são suportados.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

Location-Based Routing não se aplica aos seguintes tipos de interações. Location-Based o roteamento não é imposto quando Teams pontos de extremidade interagem com pontos de extremidade PSTN nos seguintes cenários: 
- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada 
- Um usuário local Skype for Business usuário ou um usuário Skype for Business online chama um Teams usuário  

### <a name="location-based-routing-for-conferencing"></a>Location-Based roteamento para conferência

Um Location-Based usuário habilitado para roteamento em uma chamada PSTN não tem permissão para iniciar uma conferência com outro usuário ou número PSTN. A conexão com os atendimentos automáticos ou filas de chamada é permitida. Se o usuário tiver uma licença de conferência, o usuário deverá iniciar uma conferência com os usuários relevantes e chamar a PSTN por meio da ponte de conferência para iniciar uma chamada de conferência.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de bypass de mídia para Location-Based Routing

Se você estiver implantando Location-Based roteamento na Índia, é um requisito também configurar o bypass de mídia. Para saber mais, confira [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md) and Local Media Optimization for Direct [Routing](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>Direct Voice sobre IP (VoIP)

O Direct Voice sobre IP (VoIP) não deve ser implantado com nenhum equipamento de telefonia na Índia.

## <a name="next-steps"></a>Próximas etapas

Vá para [Configurar configurações de rede para Location-Based Roteamento](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Configurações de rede para recursos de voz na nuvem Teams](cloud-voice-network-settings.md)
