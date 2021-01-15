---
title: Planejar o Roteamento baseado na localização para o Roteamento direto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Saiba como planejar o roteamento Location-Based roteamento direto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: f05049cdc181aef72f9ed018f20cd8d2e3264909
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822921"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planejar o Roteamento baseado na localização para o Roteamento direto

## <a name="overview-of-location-based-routing"></a>Visão geral do Location-Based roteamento

Em alguns países e regiões, é ilegal ignorar o provedor PSTN (Rede Telefônica Pública Comucionária) para reduzir os custos de chamadas a longa distância. Este artigo descreve como usar o roteamento Location-Based para restringir o desvio de tarifa para usuários do Microsoft Teams com base em sua localização geográfica. Este artigo se aplica somente ao Roteamento Direto do Sistema de Telefonia.

Aqui você obterá uma visão geral do Location-Based roteamento e orientações para ajudá-lo a planejar. Quando você estiver pronto para aplicar e habilitar Location-Based Roteamento, confira:

- [Implantar configurações de rede para Location-Based Roteamento](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

> [!NOTE]
> Location-Based roteamento não está disponível em implantações do Microsoft 365 Government Community Cloud (GCC) High ou DoD.

Location-Based roteamento é um recurso que permite restringir o desvio de chamada tarifada com base na política e na localização geográfica do usuário no momento de uma chamada PSTN de entrada ou saída. Location-Based roteamento destina-se a fornecer um mecanismo para impedir o desvio de tarifa. Ele não deve ser usado como um mecanismo para rotear dinamicamente chamadas PSTN com base no local do usuário ou consequências não intencionais podem resultar.

Quando um usuário do Teams está habilitado para roteamento Location-Based, o seguinte se aplica:

- Para fazer uma chamada PSTN de saída, um dos seguintes deve ser verdadeiro:
    - O ponto de extremidade do usuário está localizado em um site de rede habilitado para Roteamento do Location-Based e chama saída por meio do gateway correspondente habilitado para Roteamento Location-Based. 
    - O ponto de extremidade do usuário está localizado em um site de rede que não está habilitado para Roteamento do Location-Based e chama saída por meio de um gateway que não está habilitado para roteamento Location-Based.

    As chamadas de saída não são permitidas em nenhum outro cenário.

- Para receber uma chamada PSTN de entrada, o ponto de extremidade de atendimento do usuário deve estar localizado no mesmo site de rede em que a chamada entrar pelo gateway habilitado para roteamento Location-Based. Em qualquer outro cenário, como se o usuário estiver em roaming, a chamada não é permitida e é roteada para as configurações de encaminhamento de chamada do usuário (normalmente caixa postal).
- Para transferir uma chamada PSTN para outro usuário do Teams, o ponto de extremidade do usuário de destino deve estar localizado no mesmo site de rede que o usuário que inicia a transferência. As transferências não são permitidas em nenhum outro cenário. 
- Para transferir outro usuário do Teams para o PSTN, a chamada deve ser transferida por meio de um gateway habilitado para Roteamento Location-Based localizado no mesmo local de rede do chamador inicial. As transferências não são permitidas em nenhum outro cenário.

Location-Based roteamento usa as mesmas definições de região de rede, site e sub-rede que o Skype for Business Server usa. Quando o desvio de tarifa é restrito para um local, um administrador associa cada sub-rede IP e cada gateway PSTN desse local a um local de rede. A localização de um usuário é determinada pela sub-rede IP à que os pontos de extremidade do Teams do usuário estão conectados no momento de uma chamada PSTN. Um usuário pode ter vários clientes do Teams localizados em sites diferentes; nesse caso, o roteamento de Location-Based impõe o roteamento de cada cliente separadamente, dependendo do local de seu ponto de extremidade. 

Para se familiarizar com algumas das terminologia de rede usadas neste artigo, consulte Configurações de rede para recursos de voz na nuvem [no Teams.](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>Aplicar Location-Based roteamento

Você deve aplicar Location-Based roteamento a usuários, sites de rede e gateways PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar Location-Based roteamento no local do usuário

Conforme mencionado anteriormente, Location-Based roteamento só se aplica a usuários que estão definidos para o Roteamento Direto. Location-Based Roteamento não se aplica a usuários que estão definidos para o Plano de Chamadas. Os usuários devem estar habilitados para o Roteamento Location-Based se eles estão sob restrição de desvio tarifado, que controla as condições nas quais eles podem fazer e receber chamadas PSTN e o gateway PSTN que pode ser usado. Quando um usuário habilitado para Roteamento Location-Based está localizado em um site habilitado para Roteamento Location-Based, o usuário deve fazer chamadas por meio de um gateway habilitado para Roteamento Location-Based conectado ao site. 

Location-Based roteamento funciona determinando a localização atual do usuário com base no endereço IP do ponto de extremidade do Teams do usuário e aplica as regras de acordo. O local de um usuário habilitado para o Location-Based Roteamento pode ser categorizado das seguintes maneiras: 
- **O usuário está localizado no mesmo site Location-Based roteamento habilitado associado ao gateway PSTN em que seu DID está atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede conhecido habilitado para Roteamento Location-Based e o número DID do usuário termina em um gateway PSTN que está no mesmo local de rede. Por exemplo, o usuário está em seu escritório. 
- **O usuário está localizado em um local Location-Based local habilitado para roteamento não associado ao gateway PSTN em que seu DID está atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede conhecido habilitado para Roteamento Location-Based e esse site não está associado ao gateway PSTN no qual o número DID do usuário é atribuído. Por exemplo, o usuário vai para outro escritório.  
- **O usuário está localizado em um site interno que não está habilitado para roteamento Location-Based local.** <br>Nesse cenário, o usuário está localizado em um site de rede interno conhecido que não está habilitado para roteamento Location-Based usuário. 
- **O usuário está localizado em um site desconhecido.** 
    - O usuário está localizado dentro da rede interna que não está definida como um site de rede. 
    - O usuário está localizado fora da rede interna. Por exemplo, o usuário está na Internet em casa ou em uma cafeteria. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar Location-Based roteamento no local de rede 
Os sites de rede devem ser habilitados para roteamento Location-Based para ajudar a determinar quais gateways rotear Location-Based usuários habilitados para roteamento durante o roaming. Se um usuário habilitado para Roteamento do Location-Based estiver em um site habilitado para Roteamento Location-Based, somente o gateway PSTN habilitado para roteamento Location-Based nesse site poderá ser usado para chamadas de saída. Se um usuário habilitado para Roteamento Location-Based estiver em roams para um site que não está habilitado para Roteamento Location-Based, qualquer gateway que não está habilitado para roteamento Location-Based pode ser usado para chamadas de saída.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar Location-Based roteamento no gateway PSTN 

Os gateways são associados a sites para determinar onde um usuário habilitado para roteamento Location-Based pode ser localizado quando faz ou recebe uma chamada PSTN. Os gateways devem ser habilitados para o Roteamento Location-Based para garantir que ele está sob restrições de desvio de tarifa e não podem ser usados por usuários que não estão habilitados para Roteamento Location-Based. O mesmo gateway pode estar associado a vários sites e pode ser configurado para ser habilitado para Roteamento Location-Based ou não habilitado para Roteamento Location-Based, dependendo do site.

## <a name="scenarios-for-location-based-routing"></a>Cenários do Roteamento Baseado na Localização

Esta seção descreve diferentes cenários para restringir o desvio de chamada tarifada usando o Roteamento do Location-Based e compara como as chamadas são roteadas para usuários que não estão habilitados para Roteamento Location-Based com usuários habilitados para Roteamento Location-Based.

- [O usuário do Teams coloca uma chamada de saída para a PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [O usuário do Teams recebe uma chamada de entrada da PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [O usuário do Teams transfere ou encaminha a chamada para outro usuário do Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [O usuário do Teams transfere ou encaminha chamada para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Toque simultâneo](#simultaneous-ringing)
- [Delegação](#delegation)

O diagrama a seguir mostra as restrições habilitadas Location-Based Roteamento em cada cenário. Usuários, sites de rede e gateways habilitados para o Location-Based roteamento têm uma borda ao redor deles. Use o diagrama como um guia para ajudá-lo a entender Location-Based roteamento funciona em cada cenário.  

![Diagrama mostrando cenários de roteamento Location-Based local](media/lbr-direct-routing.png "Diagrama mostrando cenários de roteamento Location-Based local")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>O usuário do Teams coloca uma chamada de saída para a PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para roteamento Location-Based pode fazer chamadas de saída usando qualquer gateway em qualquer site que não está habilitado para roteamento Location-Based por meio de sua política de roteamento de voz atribuída. No entanto, se um gateway estiver habilitado para roteamento Location-Based, o usuário não poderá fazer chamadas de saída através do gateway, mesmo que ele seja atribuído à política de roteamento de voz. Se o usuário fizer roams para um site habilitado para Roteamento Location-Based, ele só poderá fazer chamadas por meio de seus gateways de roteamento normais que não estão habilitados para roteamento Location-Based.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário
Em comparação, o roteamento de chamadas de saída para usuários habilitados para o roteamento Location-Based é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir mostra como Location-Based Roteamento afeta o roteamento de chamadas de saída do Usuário1, dependendo do local do Usuário1. 

|Local do ponto de extremidade User1  |Roteamento de chamadas de saída para User1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para roteamento Location-Based (Site1)      |Chamada roteada por meio do gateway habilitado para o gw1 (roteamento de Location-Based) no Site1, com base na política de roteamento de voz do usuário         |
|Site diferente de onde o DID do usuário está atribuído, site habilitado para roteamento Location-Based (Site2)    |Chamada roteada pelo gateway habilitado para o gw2 (roteamento de Location-Based) em roam site2, com base na política de roteamento de voz do usuário        |
|Site diferente de onde o DID do usuário está atribuído, site não habilitado para roteamento Location-Based (Site3)  |Chamada roteada por meio de gateway que não está habilitado para roteamento de Location-Based no local que não está habilitado para roteamento de Location-Based (GW3), com base na política de roteamento de voz do usuário       |
|Rede interna desconhecida (Location4)    |  Chamada PSTN não permitida       |
|Rede externa desconhecida (Location5)    | Chamada PSTN não permitida        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>O usuário do Teams recebe uma chamada de entrada da PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para Roteamento Location-Based pode receber uma chamada de entrada do gateway que não está habilitado para roteamento Location-Based do qual o número DID atribuído é atribuído. Se o usuário passar para um site que não esteja habilitado para roteamento Location-Based, ele ainda poderá receber chamadas por meio de seus gateways PSTN normais.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

Em comparação, os usuários habilitados para roteamento Location-Based podem receber chamadas de entrada apenas do gateway PSTN ao que seu DID é atribuído quando estão localizados no mesmo site. A tabela a seguir mostra como o Usuário1 recebe chamadas de entrada quando o Usuário1 se move para locais de rede diferentes. Se a chamada não for roteada para o ponto de extremidade do usuário, ela irá para as configurações de encaminhamento de chamada do usuário, se as configurações estão configuradas. Normalmente, essa é a caixa postal.  

|Local do ponto de extremidade User1  |Roteamento de chamadas de entrada para o Usuário1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para roteamento Location-Based (Site1)   | Chamadas roteados para o ponto de extremidade do Usuário1 no Site1        |
|Site diferente de onde o DID do usuário está atribuído, site habilitado para roteamento Location-Based (Site2)    | Chamadas não roteados para pontos de extremidade no Site2        |
|Site diferente de onde o DID do usuário está atribuído, site não habilitado para roteamento Location-Based (Site3)    | Chamadas não roteados para pontos de extremidade no Site3        |
|Rede interna desconhecida (Location4)   | Chamadas não roteados para pontos de extremidade em Location4        |
|Rede externa desconhecida (Location5)     | Chamadas não roteados para pontos de extremidade em Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>O usuário do Teams transfere ou encaminha a chamada para outro usuário do Teams

Quando um ponto de extremidade PSTN está envolvido, o roteamento do Location-Based analisa se um ou ambos os usuários estão habilitados para roteamento Location-Based e determina se a chamada deve ser transferida ou encaminhada, dependendo do local dos dois pontos de extremidade. 
 
A transferência de chamada exige que o usuário iniciador atenda à chamada enquanto o encaminhamento de chamada não exige que a chamada inicial seja atendida. Isso significa que as chamadas podem ser encaminhadas mesmo se o Usuário1 não estiver em um local para receber chamadas de entrada (consulte a tabela no usuário do Teams que recebe uma chamada de entrada da seção [PSTN)](#teams-user-receives-an-inbound-call-from-the-pstn) e as chamadas não poderão ser transferidas se o Usuário1 não puder receber a chamada de entrada. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para roteamento Location-Based pode transferir ou encaminhar chamadas PSTN para outros usuários que não estão habilitados para roteamento Location-Based. O usuário normalmente não terá permissão para transferir ou encaminhar uma chamada PSTN para um usuário habilitado para Roteamento Location-Based porque usuários habilitados para Roteamento do Location-Based geralmente só têm permissão para serem co-localizados em gateways habilitados para roteamento Location-Based para chamadas PSTN. A exceção é quando um Location-Based usuário habilitado para roteamento habilitada para um site que não está habilitado para roteamento Location-Based local. Nesse cenário, a chamada transferida é permitida.  

Da mesma forma, um usuário que não está habilitado para roteamento Location-Based pode receber apenas uma chamada PSTN transferida ou encaminhada de outro usuário que não está habilitado para Roteamento Location-Based. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

Geralmente, a transferência e o encaminhamento de chamadas PSTN de entrada de um gateway habilitado para Roteamento do Location-Based são permitidos somente se o usuário de destino estiver habilitado para roteamento Location-Based e estiver localizado no mesmo local. Caso contrário, a transferência e o encaminhamento de chamadas não são permitidos. 

A tabela a seguir mostra se o encaminhamento de chamada e transferências de chamada são permitidos, dependendo do local do usuário de destino. Nesta tabela, o Usuário1, localizado no Site1, inicia a transferência ou encaminhamento para outros usuários do Teams que também estão habilitados para o Roteamento Location-Based e que estão em locais diferentes.  

|Local do ponto de extremidade do usuário de destino|User1 inicia a transferência de chamada |User1 inicia o encaminhamento de chamada|
|---------|---------|---------|
|Mesmo site de rede do iniciador (Usuário2)|Permitido|Permitido|
|Site de rede diferente, site habilitado para roteamento Location-Based (Usuário3)|Não permitido|Não permitido|
|Site de rede diferente, site não habilitado para Location-Based Roteamento (Usuário4)|Não permitido|Não permitido|
|Rede interna desconhecida (User5)| Não permitido|Não permitido|
|Rede externa desconhecida (Usuário6)| Não permitido|Não permitido|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>O usuário do Teams transfere ou encaminha chamada para o ponto de extremidade PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

- É permitido transferir e encaminhar uma chamada PSTN para outro número PSTN. 
- Transferir e encaminhar uma chamada VOIP de entrada para a PSTN deve honrar as restrições de bypass de chamada tarifada do chamador. 
    - Se o chamador não estiver habilitado para roteamento Location-Based, ele poderá ser transferido para qualquer gateway PSTN que não está habilitado para roteamento Location-Based.
    - Se o chamador estiver habilitado para roteamento Location-Based, ele só poderá ser transferido para um gateway habilitado para roteamento Location-Based local no mesmo local de rede. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

- A transferência e o encaminhamento de entrada de uma chamada PSTN para outro número PSTN devem ser roteados para o mesmo gateway habilitado de roteamento Location-Based em que a chamada de entrada chegou. 
- Transferir e encaminhar uma chamada VOIP de entrada para o PSTN deve honrar as restrições de bypass de chamada e de chamada do usuário. 
    - Se o chamador não estiver habilitado para roteamento Location-Based, ele poderá ser transferido para qualquer gateway PSTN que não está habilitado para roteamento Location-Based.
    - Se o chamador estiver habilitado para roteamento Location-Based, ele só poderá ser transferido para um gateway habilitado para Roteamento Location-Based local no mesmo local de rede.
 
A tabela a seguir mostra como o roteamento Location-Based afeta o roteamento de uma chamada VOIP do Usuário1 no Site1 para usuários em locais diferentes que transferem ou encaminham a chamada para um ponto de extremidade PSTN.  

|Usuário iniciando transferência ou encaminhamento de chamada  |Transferir para pSTN  |Encaminhar para pSTN  |
|---------|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based Roteamento (Usuário2)   |A transferência de chamada só pode ser roteada por meio Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário2         |O encaminhamento de chamadas só pode ser roteado Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário2         |
|Site de rede diferente, site habilitado para roteamento Location-Based (Usuário3)    |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário3         |O encaminhamento de chamadas só pode ser roteado por meio Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário3         |
|Site de rede diferente, site não habilitado para Location-Based Roteamento (Usuário4)    |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |O encaminhamento de chamadas só pode ser roteado Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |
|Rede interna desconhecida (User5)     |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário5         |O encaminhamento de chamadas só pode ser roteado por meio Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário5         |
|Rede externa desconhecida (Usuário6)   |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário6        |O encaminhamento de chamadas só pode ser roteado Location-Based Gateway habilitado para Roteamento1 no Site1, com base na política de roteamento de voz do Usuário6         |

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando um usuário habilitado para Roteamento do Location-Based recebe uma chamada e tem toque simultâneo habilitado, o roteamento do Location-Based analisa o local do chamador e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada. O toque simultâneo segue as mesmas Location-Based como transferências e encaminhamentos de chamada. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Toque simultâneo para outro usuário do Teams

A tabela a seguir mostra se Location-Based Roteamento permite toque simultâneo para diferentes usuários para uma chamada PSTN de entrada para User1.

|Local do ponto de extremidade do usuário de destino|Toque simultâneo  |
|---------|---------|
|Mesmo site de rede do iniciador (Usuário2)   |Permitido         |
|Site de rede roamed diferente habilitado para roteamento Location-Based (Usuário3)   |Não permitido         |
|Site de rede em roamed não habilitado para roteamento Location-Based (Usuário4)   |Não permitido        |
|Rede interna desconhecida (User5)    | Não permitido        |
|Rede externa desconhecida (Usuário6)    |Não permitido        |
|O usuário de destino é um número PSTN    |A chamada só pode ser roteada Location-Based Gateway1 habilitado para Roteamento no Site1, com base na política de roteamento de voz do Usuário1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Toque simultâneo para um ponto de extremidade PSTN

A tabela a seguir mostra Location-Based de roteamento para uma chamada VOIP de entrada de Usuário1 localizada em Site1 para usuários em locais diferentes com toque simultâneo definido como um número PSTN. 

|Local do ponto de extremidade do usuário chamado  |O destino de anel simultâneo é o ponto de extremidade PSTN |
|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based Roteamento (Usuário2)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário2       |
|Site de rede diferente habilitado para Location-Based roteamento (Usuário3)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário3        |
|Site de rede diferente não habilitado para roteamento Location-Based (Usuário4)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |
|Rede interna desconhecida (User5)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário5         |
|Rede externa desconhecida (Usuário6)   |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Chamadas de entrada por meio do aplicativo de voz (Atendedor Automático ou Fila de Chamadas)

Chamadas PSTN de entrada de um gateway Location-Based de roteamento habilitado têm permissão para se conectar a um atendimento automático ou fila de chamadas. Os usuários habilitados para roteamento Location-Based podem receber transferências de chamadas de entrada desses aplicativos somente quando eles estão localizados no mesmo site de origem da chamada PSTN de entrada. 
 
O encaminhamento de chamadas e o toque simultâneo para usuários e PSTN são permitidos para transferências de aplicativos de voz. Concluir a chamada para o destino está sujeito às mesmas regras de roteamento Location-Based listadas anteriormente.  
 
O encaminhamento para a caixa postal também é permitido.  

### <a name="delegation"></a>Delegação

Um usuário do Teams pode escolher representantes que podem fazer e receber chamadas em seu nome. Os recursos de delegação no Teams são afetados Location-Based roteamento da seguinte forma: 
- Para chamadas de saída de um representante Location-Based roteamento habilitado em nome de um delegante, as mesmas regras se aplicam. O roteamento de chamadas baseia-se na política de autorização de chamada do representante, na política de roteamento de voz e no local. Para obter mais informações, consulte o usuário do Teams que fez [uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 
- Para chamadas PSTN de entrada para um delegante, as mesmas regras de roteamento Location-Based que se aplicam ao encaminhamento de chamadas ou toque simultâneo a outros usuários também se aplicam aos representantes. Para obter mais informações, consulte Transferências de usuário ou encaminhamentos de chamada para outro usuário do [Teams,](#teams-user-transfers-or-forwards-call-to-another-teams-user)transferências de usuários do Teams ou encaminhamento de chamada para o ponto de extremidade [PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)e toque [simultâneo.](#simultaneous-ringing) Quando um representante define um ponto de extremidade PSTN como um destino de toque simultâneo, a política de roteamento de voz do representante é usada para rotear a chamada para a PSTN. 
- Para delegação, é recomendável que o delegante e os delegados associados sejam localizados no mesmo local de rede. 

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Alterações de uma implantação de roteamento de Location-Based local

A política de roteamento de voz do site de rede não é mais usada. Em vez disso, usamos a política de roteamento de voz do usuário. Isso significa que, para permitir que os usuários transitem para outros sites, a política de roteamento de voz deve incluir os gateways dos sites em roamed. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerações técnicas para Roteamento Baseado em Local

As sub-redes IPv4 e IPv6 são suportadas, no entanto, o IPv6 tem precedência ao verificar uma combinação.

### <a name="client-support-for-location-based-routing"></a>Suporte ao cliente para roteamento Location-Based cliente

Há suporte para os seguintes clientes do Teams:
- Clientes da área de trabalho do Teams (Windows e Mac)
- Clientes móveis do Teams (iOS e Android)
- Telefones IP do Teams

O cliente Web do Teams e os clientes do Skype for Business não são suportados.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

Location-Based roteamento não se aplica aos seguintes tipos de interações. Location-Based roteamento não é imposto quando os pontos de extremidade do Teams interagem com pontos de extremidade PSTN nos seguintes cenários: 
- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada 
- Um usuário local do Skype for Business ou um usuário do Skype for Business Online liga para um usuário do Teams  

### <a name="location-based-routing-for-conferencing"></a>Location-Based roteamento para conferência

Um Location-Based usuário habilitado para Roteamento em uma chamada PSTN não tem permissão para iniciar uma conferência com outro usuário ou número PSTN. A conexão com os atendentes automáticos ou filas de chamada é permitida. Se o usuário tiver uma licença de conferência, o usuário deverá iniciar uma conferência com os usuários relevantes e chamar a PSTN por meio da ponte de conferência para iniciar uma chamada de conferência.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de bypass de mídia para Location-Based roteamento

Se você estiver implantando Location-Based roteamento na Índia, é um requisito também configurar o bypass de mídia. Para saber mais, consulte [Plano de bypass](direct-routing-plan-media-bypass.md) de mídia com Roteamento Direto e Otimização de Mídia Local para [Roteamento Direto.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>Direct Voice sobre IP (VoIP)

O Direct Voice sobre IP (VoIP) não deve ser implantado com nenhum equipamento de telefonia na Índia.

## <a name="next-steps"></a>Próximas etapas

Vá para [Definir configurações de rede para Location-Based Roteamento](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md)
