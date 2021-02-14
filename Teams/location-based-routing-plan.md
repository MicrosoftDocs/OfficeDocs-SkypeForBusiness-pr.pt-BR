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

## <a name="overview-of-location-based-routing"></a>Visão geral do Location-Based Roteamento

Em alguns países e regiões, é ilegal ignorar o provedor de PSTN (Rede Telefônica Pública Comutado) para reduzir os custos de chamadas a longa distância. Este artigo descreve como usar o Location-Based roteamento para restringir o bypass de chamadas tarifadas para usuários do Microsoft Teams com base em sua localização geográfica. Este artigo se aplica somente ao Roteamento Direto do Sistema de Telefonia.

Aqui você terá uma visão geral do Location-Based roteamento e orientações para ajudá-lo a planejar. Quando estiver pronto para aplicar e habilitar Location-Based Roteamento, consulte:

- [Implantar configurações de rede para Location-Based Roteamento](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

> [!NOTE]
> Location-Based o roteamento não está disponível nas implantações do Microsoft 365 Government Community Cloud (GCC) High ou DoD.

Location-Based roteamento é um recurso que permite restringir o bypass de chamada tarifada com base na política e na localização geográfica do usuário no momento de uma chamada PSTN de entrada ou saída. Location-Based roteamento destina-se a fornecer um mecanismo para evitar o bypass de tarifas tarifadas. Ele não deve ser usado como um mecanismo para encaminhar dinamicamente chamadas PSTN com base na localização do usuário ou consequências não intencionais podem resultar.

Quando um usuário do Teams está habilitado para Location-Based Roteamento, aplica-se o seguinte:

- Para fazer uma chamada PSTN de saída, uma das seguintes coisas deve ser verdadeira:
    - O ponto de extremidade do usuário está localizado em um site de rede habilitado para Location-Based Roteamento e saída de chamadas por meio do gateway correspondente habilitado para Location-Based Roteamento. 
    - O ponto de extremidade do usuário está localizado em um site de rede que não está habilitado para o Location-Based Roteamento e saída de chamadas por meio de um gateway que não está habilitado para Location-Based Roteamento.

    As chamadas de saída não são permitidas em nenhum outro cenário.

- Para receber uma chamada PSTN de entrada, o ponto de extremidade de resposta do usuário deve estar localizado no mesmo site de rede em que a chamada se ingressa pelo gateway habilitado para Location-Based Roteamento. Em qualquer outro cenário, como se o usuário estiver em roaming, a chamada não é permitida e é roteada para as configurações de encaminhamento de chamada do usuário (geralmente caixa postal).
- Para transferir uma chamada PSTN para outro usuário do Teams, o ponto de extremidade do usuário de destino deve estar localizado no mesmo site de rede que o usuário que inicia a transferência. As transferências não são permitidas em nenhum outro cenário. 
- Para transferir outro usuário do Teams para o PSTN, a chamada deve ser transferida por meio de um gateway habilitado para roteamento Location-Based localizado no mesmo site de rede que o chamador inicial. As transferências não são permitidas em nenhum outro cenário.

Location-Based roteamento usa as mesmas definições de região de rede, site e sub-rede que o Skype for Business Server usa. Quando o bypass de tarifa é restrito para um local, um administrador associa cada sub-rede IP e cada gateway PSTN desse local a um site de rede. A localização de um usuário é determinada pela sub-rede IP a que os pontos de extremidade do Teams do usuário estão conectados no momento de uma chamada PSTN. Um usuário pode ter vários clientes do Teams localizados em sites diferentes, nesse caso, o Location-Based roteamento impõe o roteamento de cada cliente separadamente, dependendo da localização do ponto de extremidade. 

Para se familiarizar com algumas das terminologias de rede usadas neste artigo, consulte Configurações de rede [para recursos de voz na nuvem no Teams.](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>Aplicar Location-Based Roteamento

Você deve aplicar Location-Based roteamento a usuários, sites de rede e gateways PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar Location-Based roteamento no local do usuário

Conforme mencionado anteriormente, Location-Based roteamento aplica-se somente aos usuários que estão configuradas para Roteamento Direto. Location-Based o roteamento não se aplica aos usuários que estão definidos para o Plano de Chamada. Os usuários devem estar habilitados para Location-Based Roteamento se eles estão sob restrição de bypass de chamada tarifada, que controla as condições nas quais podem fazer e receber chamadas PSTN e o gateway PSTN que pode ser usado. Quando um usuário habilitado para o Location-Based Roteamento estiver localizado em um site habilitado para roteamento do Location-Based, o usuário deverá fazer chamadas por meio de um gateway habilitado para roteamento do Location-Based conectado ao site. 

Location-Based roteamento funciona determinando a localização atual do usuário com base no endereço IP do ponto de extremidade do Teams do usuário e aplica as regras de acordo. A localização de um usuário habilitado para o Location-Based roteamento pode ser categorizado das seguintes maneiras: 
- **O usuário está localizado na mesma página Location-Based site habilitado para roteamento associado ao gateway PSTN em que seu DID foi atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede conhecido habilitado para roteamento do Location-Based e o número DE (Direct Inward Dial) do usuário termina em um gateway PSTN que está no mesmo site de rede. Por exemplo, o usuário está em seu escritório. 
- **O usuário está localizado em outro Location-Based site habilitado para roteamento não associado ao gateway PSTN em que seu DID foi atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede conhecido habilitado para roteamento Location-Based e esse site não está associado ao gateway PSTN onde o número DID do usuário é atribuído. Por exemplo, o usuário viaja para outro escritório.  
- **O usuário está localizado em um site interno que não está habilitado para Location-Based Roteamento.** <br>Nesse cenário, o usuário está localizado em um site de rede interna conhecido que não está habilitado para Location-Based Roteamento. 
- **O usuário está localizado em um site desconhecido.** 
    - O usuário está localizado dentro da rede interna que não está definida como um site de rede. 
    - O usuário está localizado fora da rede interna. Por exemplo, o usuário está na Internet em casa ou em um café. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar Location-Based roteamento no site de rede 
Os sites de rede devem ser habilitados para Location-Based roteamento para ajudar a determinar quais gateways rotear Location-Based roteamento de usuários habilitados durante o roaming. Se um usuário habilitado para o Location-Based Roteamento for roteado para um site habilitado para roteamento de Location-Based, somente o gateway PSTN habilitado para o Location-Based Roteamento nesse site pode ser usado para chamadas de saída. Se um usuário habilitado para o Location-Based Roteamento for roteado para um site que não está habilitado para roteamento do Location-Based, qualquer gateway que não está habilitado para Location-Based Roteamento pode ser usado para chamadas de saída.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar Location-Based roteamento no gateway PSTN 

Os gateways são associados a sites para determinar onde um usuário habilitado para o Location-Based Roteamento pode ser localizado quando ele faz ou recebe uma chamada PSTN. Os gateways devem ser habilitados para Location-Based Roteamento para garantir que ele está sob restrições de bypass de tarifa e não pode ser usado por usuários que não estão habilitados para Location-Based Roteamento. O mesmo gateway pode estar associado a vários sites e pode ser configurado para ser habilitado para roteamento de Location-Based ou não habilitado para roteamento Location-Based, dependendo do site.

## <a name="scenarios-for-location-based-routing"></a>Cenários do Roteamento Baseado na Localização

Esta seção descreve diferentes cenários para restringir o bypass de chamada tarifada usando o Location-Based Roteamento e compara como as chamadas são roteadas para usuários que não estão habilitados para o roteamento de Location-Based com usuários habilitados para o roteamento Location-Based.

- [O usuário do Teams coloca uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [O usuário do Teams recebe uma chamada de entrada do PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Usuário do Teams transfere ou encaminha chamada para outro usuário do Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Usuário do Teams transfere ou encaminha chamada para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Toque simultâneo](#simultaneous-ringing)
- [Delegação](#delegation)

O diagrama a seguir mostra as restrições habilitadas Location-Based Roteamento em cada cenário. Os usuários, sites de rede e gateways habilitados para Location-Based roteamento têm uma borda ao redor deles. Use o diagrama como um guia para ajudá-lo a entender como o Location-Based roteamento funciona em cada cenário.  

![Diagrama mostrando cenários para Location-Based Roteamento](media/lbr-direct-routing.png "Diagrama mostrando cenários para Location-Based Roteamento")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>O usuário do Teams coloca uma chamada de saída para o PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para Location-Based Roteamento

Um usuário que não está habilitado para o Location-Based Roteamento pode fazer chamadas de saída usando qualquer gateway em qualquer site que não está habilitado para Location-Based Roteamento por meio de sua política de roteamento de voz atribuída. No entanto, se um gateway estiver habilitado para Location-Based Roteamento, o usuário não poderá fazer chamadas de saída pelo gateway mesmo que ele seja atribuído à política de roteamento de voz. Se o usuário estiver em roams para um site habilitado para roteamento de Location-Based, ele só poderá fazer chamadas por meio de seus gateways de roteamento normais que não estão habilitados para Location-Based Roteamento.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para Location-Based Roteamento
Em comparação, o roteamento de chamadas de saída para usuários habilitados para Location-Based roteamento é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir mostra como Location-Based roteamento afeta o roteamento de chamadas de saída do Usuário1, dependendo da localização do Usuário1. 

|Local do ponto de extremidade usuário1  |Roteamento de chamadas de saída para o Usuário1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site1)      |Chamada roteada pelo gateway habilitado para o Location-Based de roteamento (GW1) no Site1, com base na política de roteamento de voz do usuário         |
|Site diferente de onde o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site2)    |Chamada roteada pelo gateway habilitado para Location-Based roteamento (GW2) no Site de roam2, com base na política de roteamento de voz do usuário        |
|Site diferente de onde o DID do usuário está atribuído, site não habilitado para Location-Based Roteamento (Site3)  |Chamada roteada pelo gateway que não está habilitado para Location-Based Roteamento no site que não está habilitado para o roteamento de Location-Based (GW3), com base na política de roteamento de voz do usuário       |
|Rede interna desconhecida (Local4)    |  Chamada PSTN não permitida       |
|Rede externa desconhecida (Local5)    | Chamada PSTN não permitida        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>O usuário do Teams recebe uma chamada de entrada do PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para Location-Based Roteamento

Um usuário que não está habilitado para o Location-Based Roteamento pode receber uma chamada de entrada do gateway que não está habilitado para o Location-Based Roteamento a partir do qual o número DID atribuído é ingressado. Se o usuário estiver em roams para um site que não está habilitado para Location-Based Roteamento, ele ainda poderá receber chamadas por meio de seus gateways PSTN normais.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para Location-Based Roteamento

Em comparação, os usuários habilitados para o Location-Based Roteamento só podem receber chamadas de entrada do gateway PSTN ao que seu DID é atribuído quando estão localizados no mesmo site. A tabela a seguir mostra como o Usuário1 recebe chamadas de entrada quando o Usuário1 se move para locais de rede diferentes. Se a chamada não for roteada para o ponto de extremidade do usuário, ela irá para as configurações de encaminhamento de chamada do usuário, se as configurações estão configuradas. Normalmente, essa é a caixa postal.  

|Local do ponto de extremidade usuário1  |Roteamento de chamadas de entrada para o Usuário1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site1)   | Chamadas roteada para o ponto de extremidade do Usuário1 no Site1        |
|Site diferente de onde o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site2)    | Chamadas não roteada para pontos de extremidade no Site2        |
|Site diferente de onde o DID do usuário está atribuído, site não habilitado para Location-Based Roteamento (Site3)    | Chamadas não roteada para pontos de extremidade no Site3        |
|Rede interna desconhecida (Local4)   | Chamadas não roteada para pontos de extremidade em Local4        |
|Rede externa desconhecida (Local5)     | Chamadas não roteada para pontos de extremidade em Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Usuário do Teams transfere ou encaminha chamada para outro usuário do Teams

Quando um ponto de extremidade PSTN está envolvido, o Location-Based Roteamento analisa se um ou ambos os usuários estão habilitados para o roteamento do Location-Based e determina se a chamada deve ser transferida ou encaminhada dependendo da localização dos dois pontos de extremidade. 
 
A transferência de chamada exige que o usuário iniciador atenda a chamada enquanto o encaminhamento de chamada não exige que a chamada inicial seja atendida. Isso significa que as chamadas podem ser encaminhadas mesmo se o Usuário1 não estiver em um local para receber chamadas de entrada (veja a tabela no usuário do Teams que recebe uma chamada de entrada da seção [PSTN)](#teams-user-receives-an-inbound-call-from-the-pstn) e as chamadas não poderão ser transferidas se o Usuário1 não conseguir receber a chamada de entrada. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para Location-Based Roteamento

Um usuário que não está habilitado para o Location-Based Roteamento pode transferir ou encaminhar chamadas PSTN para outros usuários que não estão habilitados para Location-Based Roteamento. Normalmente, o usuário não terá permissão para transferir ou encaminhar uma chamada PSTN para um usuário habilitado para roteamento de Location-Based Location-Based porque os usuários habilitados para roteamento geralmente só têm permissão para serem co-localizados em Location-Based gateways habilitados para roteamento para chamadas PSTN. A exceção é quando um usuário Location-Based roteamento habilitado para roams para um site que não está habilitado para Location-Based Roteamento. Nesse cenário, a chamada transferida é permitida.  

Da mesma forma, um usuário que não está habilitado para o Location-Based Roteamento só pode receber uma chamada PSTN transferida ou encaminhada de outro usuário que não está habilitado para roteamento Location-Based. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para Location-Based Roteamento

Em geral, a transferência e o encaminhamento de chamadas PSTN de entrada de um gateway habilitado para o Location-Based Roteamento só será permitido se o usuário de destino estiver habilitado para o roteamento Location-Based e estiver localizado no mesmo site. Caso contrário, não é permitido transferir e encaminhar chamadas. 

A tabela a seguir mostra se o encaminhamento de chamada e transferências de chamada são permitidos, dependendo da localização do usuário de destino. Nesta tabela, o Usuário1, localizado no Site1, inicia a transferência ou encaminha para outros usuários do Teams que também estão habilitados para o Location-Based Roteamento e que estão em locais diferentes.  

|Local do ponto de extremidade do usuário de destino|Usuário1 inicia a transferência de chamada |O Usuário1 inicia o encaminhamento de chamada|
|---------|---------|---------|
|Mesmo site de rede que iniciador (Usuário2)|Permitido|Permitido|
|Site de rede diferente, site habilitado para Location-Based Roteamento (Usuário3)|Não permitido|Não permitido|
|Site de rede diferente, site não habilitado para Location-Based Roteamento (Usuário4)|Não permitido|Não permitido|
|Rede interna desconhecida (Usuário5)| Não permitido|Não permitido|
|Rede externa desconhecida (Usuário6)| Não permitido|Não permitido|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Usuário do Teams transfere ou encaminha chamada para o ponto de extremidade PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para Location-Based Roteamento

- Transferência e encaminhamento de uma chamada PSTN para outro número PSTN é permitido. 
- Transferir e encaminhar uma chamada VOIP de entrada para o PSTN deve seguir as restrições de bypass de chamada tarifada. 
    - Se o chamador não estiver habilitado para Location-Based Roteamento, ele poderá ser transferido para qualquer gateway PSTN que não está habilitado para Location-Based Roteamento.
    - Se o chamador estiver habilitado para Location-Based Roteamento, ele só poderá ser transferido para um gateway habilitado para roteamento Location-Based localizado no mesmo site de rede. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para Location-Based Roteamento

- Transferir e encaminhar uma chamada PSTN de entrada para outro número PSTN deve ser roteado para o mesmo gateway habilitado para roteamento do Location-Based em que a chamada de entrada chegou. 
- Transferir e encaminhar uma chamada VOIP de entrada para o PSTN deve honrar o chamador e as restrições de bypass de chamada do usuário. 
    - Se o chamador não estiver habilitado para Location-Based Roteamento, ele poderá ser transferido para qualquer gateway PSTN que não está habilitado para Location-Based Roteamento.
    - Se o chamador estiver habilitado para Location-Based Roteamento, ele só poderá ser transferido para um gateway habilitado para roteamento Location-Based localizado no mesmo site de rede.
 
A tabela a seguir mostra como Location-Based roteamento afeta o roteamento de uma chamada VOIP do Usuário1 no Site1 para usuários em locais diferentes que transferem ou encaminham a chamada para um ponto de extremidade PSTN.  

|Usuário iniciando a transferência de chamada ou encaminhando  |Transferir para PSTN  |Encaminhar para PSTN  |
|---------|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based Roteamento (Usuário2)   |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário2         |O encaminhamento de chamadas só pode ser roteado Location-Based Gateway1 habilitado para roteamento no Site1, com base na política de roteamento de voz do Usuário2         |
|Site de rede diferente, site habilitado para Location-Based Roteamento (Usuário3)    |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário3         |O encaminhamento de chamadas só pode ser roteado Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário3         |
|Site de rede diferente, site não habilitado para Location-Based Roteamento (Usuário4)    |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |O encaminhamento de chamadas só pode ser roteado Location-Based Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |
|Rede interna desconhecida (Usuário5)     |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário5         |O encaminhamento de chamadas só pode ser roteado Location-Based Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário5         |
|Rede externa desconhecida (Usuário6)   |A transferência de chamada só pode ser roteada Location-Based Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário6        |O encaminhamento de chamadas só pode ser roteado Location-Based gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário6         |

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando um usuário habilitado para o Location-Based Roteamento recebe uma chamada e tem o toque simultâneo habilitado, o Location-Based Roteamento analisa a localização da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada. O toque simultâneo segue as mesmas Location-Based regras que as transferências de chamada e encaminhamentos. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Toque simultâneo para outro usuário do Teams

A tabela a seguir mostra se Location-Based roteamento permite toque simultâneo para diferentes usuários para uma chamada PSTN de entrada para Usuário1.

|Local do ponto de extremidade do usuário de destino|Toque simultâneo  |
|---------|---------|
|Mesmo site de rede que iniciador (Usuário2)   |Permitido         |
|Site de rede em roamed diferente habilitado para Location-Based Roteamento (Usuário3)   |Não permitido         |
|Site de rede em roamed não habilitado para Location-Based Roteamento (Usuário4)   |Não permitido        |
|Rede interna desconhecida (Usuário5)    | Não permitido        |
|Rede externa desconhecida (Usuário6)    |Não permitido        |
|O usuário de destino é um número PSTN    |A chamada só pode ser roteada Location-Based Gateway habilitado para roteamento1 no Site1, com base na política de roteamento de voz do Usuário1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Toque simultâneo para um ponto de extremidade PSTN

A tabela a seguir mostra Location-Based comportamento de roteamento para uma chamada VOIP de entrada de Usuário1 localizada no Site1 para usuários em locais diferentes com toque simultâneo definido como um número PSTN. 

|Local do ponto de extremidade do usuário chamado  |O destino do anel simultâneo é o ponto de extremidade PSTN |
|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based Roteamento (Usuário2)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário2       |
|Site de rede diferente habilitado para Location-Based Roteamento (Usuário3)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário3        |
|Site de rede diferente não habilitado para Location-Based Roteamento (Usuário4)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário4         |
|Rede interna desconhecida (Usuário5)    |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do User5         |
|Rede externa desconhecida (Usuário6)   |A chamada só pode ser roteada Location-Based Gateway de Roteamento1 no Site1, com base na política de roteamento de voz do Usuário6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Chamadas de entrada pelo aplicativo de voz (Atendimento Automático ou Fila de Chamadas)

As chamadas PSTN de entrada de um gateway habilitado para Location-Based roteamento têm permissão para se conectar a um atender automático ou fila de chamadas. Os usuários habilitados para Location-Based roteamento só podem receber transferências de chamadas de entrada desses aplicativos quando estão localizados no mesmo site de onde a chamada PSTN de entrada se origina. 
 
O encaminhamento de chamadas e o toque simultâneo para usuários e PSTN são permitidos para transferências de aplicativos de voz. Concluir a chamada para o destino está sujeito à mesma Location-Based de roteamento listadas anteriormente.  
 
O encaminhamento para a caixa postal também é permitido.  

### <a name="delegation"></a>Delegação

Um usuário do Teams pode escolher representantes que podem fazer e receber chamadas em seu nome. Os recursos de delegação no Teams são afetados Location-Based roteamento da seguinte forma: 
- Para chamadas de saída de um representante Location-Based roteamento habilitado em nome de um delegador, as mesmas regras são aplicadas. O roteamento de chamadas se baseia na política de autorização de chamada do representante, na política de roteamento de voz e no local. Para obter mais informações, consulte o usuário do Teams para fazer uma [chamada de saída para o PSTN.](#teams-user-places-an-outbound-call-to-the-pstn) 
- Para chamadas PSTN de entrada para um delegador, as mesmas regras de roteamento de Location-Based que se aplicam ao encaminhamento de chamadas ou ao toque simultâneo a outros usuários também se aplicam aos representantes. Para obter mais informações, consulte Transferências de usuário do Teams ou encaminhamento de chamada para outro usuário do [Teams,](#teams-user-transfers-or-forwards-call-to-another-teams-user)transferências de usuário do Teams ou encaminhamento de chamada para o ponto de extremidade [PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)e toque [simultâneo.](#simultaneous-ringing) Quando um representante define um ponto de extremidade PSTN como um destino de toque simultâneo, a política de roteamento de voz do representante é usada para rotear a chamada para o PSTN. 
- Para delegação, é recomendável que o delegador e os representantes associados sejam localizados no mesmo site de rede. 

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Alterações de uma implantação local Location-Based roteamento

A política de roteamento de voz do site de rede não é mais usada. Em vez disso, usamos a política de roteamento de voz do usuário. Isso significa que, para permitir que os usuários percorram outros sites, a política de roteamento de voz deve incluir os gateways dos sites em roamed. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerações técnicas para Roteamento Baseado em Local

As sub-redes IPv4 e IPv6 têm suporte, no entanto, IPv6 tem precedência ao verificar uma combinação.

### <a name="client-support-for-location-based-routing"></a>Suporte do cliente para Location-Based Roteamento

Os seguintes clientes do Teams são suportados:
- Clientes da área de trabalho do Teams (Windows e Mac)
- Clientes móveis do Teams (iOS e Android)
- Telefones IP do Teams

O cliente Web do Teams e os clientes do Skype for Business não são suportados.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

Location-Based Roteamento não se aplica aos seguintes tipos de interações. Location-Based o roteamento não é imposto quando os pontos de extremidade do Teams interagem com pontos de extremidade PSTN nos seguintes cenários: 
- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada 
- Um usuário local do Skype for Business ou um usuário do Skype for Business Online liga para um usuário do Teams  

### <a name="location-based-routing-for-conferencing"></a>Location-Based roteamento para conferência

Um Location-Based usuário habilitado para roteamento em uma chamada PSTN não tem permissão para iniciar uma conferência com outro usuário ou número PSTN. A conexão com os participantes automáticos ou filas de chamada é permitida. Se o usuário tiver uma licença de conferência, o usuário deverá iniciar uma conferência com os usuários relevantes e ligar para o PSTN pela ponte de conferência para iniciar uma chamada em conferência.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de bypass de mídia para Location-Based Roteamento

Se você estiver implantando Location-Based roteamento na Índia, também é necessário configurar o bypass de mídia. Para saber mais, consulte Plano de bypass de [mídia com Roteamento](direct-routing-plan-media-bypass.md) Direto e [Otimização de Mídia Local para Roteamento Direto.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>Direct Voice sobre IP (VoIP)

O Direct Voice sobre IP (VoIP) não deve ser implantado com nenhum equipamento de telefonia na Índia.

## <a name="next-steps"></a>Próximas etapas

Vá para [Configurar configurações de rede para Location-Based Roteamento.](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md)
