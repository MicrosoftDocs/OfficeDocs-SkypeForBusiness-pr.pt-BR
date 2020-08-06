---
title: Planejar o Roteamento baseado na localização para o Roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Saiba como planejar o roteamento baseado em localização para roteamento direto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab779c7b60ab702284c871ab6bd0ec08d051267
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572236"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planejar o Roteamento baseado na localização para o Roteamento direto

## <a name="overview-of-location-based-routing"></a>Visão geral do roteamento baseado em local

Em alguns países e regiões, é ilegal ignorar o provedor PSTN (rede telefônica pública comutada) para reduzir os custos de chamadas de longa distância. Este artigo descreve como usar o roteamento baseado em local para restringir o bypass de chamadas para usuários do Microsoft Teams com base em sua localização geográfica. Este artigo se aplica apenas ao encaminhamento direto do sistema telefônico.

Aqui você terá uma visão geral do roteamento e orientação baseado em local para ajudá-lo a planejar isso. Quando estiver pronto para aplicar e habilitar o roteamento baseado em localização, consulte:

- [Implantar configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

> [!NOTE]
> O roteamento baseado em local não está disponível nas implantações do Microsoft 365 governo Community Cloud (GCC) de alta ou DoD.

O roteamento baseado em local é um recurso que permite que você restrinja o desvio de chamada tarifada com base na política e na localização geográfica do usuário no momento de uma chamada PSTN de entrada ou saída. O roteamento baseado em local tem o objetivo de fornecer um mecanismo para impedir o bypass de chamadas. Ele não deve ser usado como um mecanismo para direcionar dinamicamente chamadas PSTN com base na localização do usuário ou podem resultar em conseqüências indesejadas.

Quando um usuário do teams estiver habilitado para roteamento baseado em local, o seguinte será aplicado:

- Para fazer uma chamada PSTN de saída, uma das seguintes opções deve ser verdadeira:
    - O ponto de extremidade do usuário está localizado em um site de rede habilitado para roteamento baseado em local e chama egresso por meio do gateway correspondente habilitado para roteamento baseado em local. 
    - O ponto de extremidade do usuário está localizado em um site de rede que não está habilitado para roteamento baseado em local e chama egresso por meio de um gateway que não está habilitado para roteamento baseado em local.

    Chamadas de saída não são permitidas em nenhum outro cenário.

- Para receber uma chamada PSTN de entrada, o ponto de extremidade de resposta do usuário deve estar localizado no mesmo site de rede em que a chamada ingresses o gateway habilitado para roteamento baseado em local. Em qualquer outro cenário, como se o usuário estiver em roaming, a chamada não será permitida e será roteada para as configurações de encaminhamento de chamadas do usuário (geralmente correio de voz).
- Para transferir uma chamada PSTN para outro usuário do Teams, o ponto de extremidade do usuário de destino deve estar localizado no mesmo site de rede que o usuário que inicia a transferência. As transferências não são permitidas em nenhum outro cenário. 
- Para transferir outro usuário de equipes para a PSTN, a chamada deve ser transferida por meio de um gateway habilitado para roteamento baseado em local localizado no mesmo local de rede que o chamador inicial. As transferências não são permitidas em nenhum outro cenário.

O roteamento baseado em local usa a mesma região de rede, site e definições de sub-rede que o Skype for Business Server usa. Quando a chamada tarifada é restrita para um local, um administrador associa cada sub-rede de IP e cada gateway PSTN desse local a um site de rede. A localização de um usuário é determinada pela sub-rede IP à qual os pontos de extremidade do usuário da equipe estão conectados no momento da chamada PSTN. Um usuário pode ter vários clientes do teams localizados em sites diferentes, e nesse caso, o roteamento baseado em localização impõe cada roteamento de cliente separadamente, dependendo da localização do seu ponto de extremidade. 

Para se familiarizar com algumas das terminologias de rede usadas neste artigo, consulte [configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md).

## <a name="apply-location-based-routing"></a>Aplicar roteamento baseado em local

Você deve aplicar o roteamento baseado em local a usuários, sites de rede e gateways PSTN.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar roteamento baseado em local no local do usuário

Conforme mencionado anteriormente, o roteamento baseado em local só se aplica a usuários que estão configurados para roteamento direto. O roteamento baseado em local não se aplica aos usuários que estão configurados para o plano de chamadas. Os usuários devem ser habilitados para roteamento baseado em local se estiverem em restrições de desvio de chamada, que controlam as condições em que podem fazer e receber chamadas PSTN e o gateway PSTN que podem ser usados. Quando um usuário habilitado para roteamento baseado em localização estiver localizado em um site habilitado para roteamento baseado em local, o usuário deverá fazer chamadas por meio de um gateway habilitado para roteamento baseado em local conectado ao site. 

O roteamento baseado em local funciona determinando a localização atual do usuário com base no endereço IP do ponto de extremidade do usuário da equipe e aplica as regras de acordo com isso. O local de um usuário habilitado para roteamento baseado em localização pode ser categorizado das seguintes maneiras: 
- **O usuário está localizado no mesmo site habilitado para roteamento baseado em localização associado ao gateway PSTN em que o seu foi atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede conhecido que está habilitado para roteamento baseado em localização, e o número do usuário do Direct Inward Dial (DID) termina em um gateway PSTN que está no mesmo local de rede. Por exemplo, o usuário está no escritório. 
- **O usuário está localizado em um site de roteamento baseado em local diferente, que não está associado ao gateway PSTN em que o seu foi atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede conhecido que está habilitado para roteamento baseado em local, e esse site não está associado ao gateway PSTN em que o número do usuário foi atribuído. Por exemplo, o usuário viaja para outro escritório.  
- **O usuário está localizado em um site interno que não está habilitado para roteamento baseado em local.** <br>Nesse cenário, o usuário está localizado em um site de rede interna conhecido que não está habilitado para roteamento baseado em local. 
- **O usuário está localizado em um site desconhecido.** 
    - O usuário está localizado na rede interna que não está definida como um site de rede. 
    - O usuário está localizado fora da rede interna. Por exemplo, o usuário está na Internet em casa ou em uma lanchonete. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar roteamento baseado em local no local de rede 
Os sites de rede devem ser habilitados para roteamento baseado em local para ajudar a determinar quais gateways para rotear usuários habilitados para roteamento baseado em locais quando estiverem em roaming. Se um usuário habilitado para roams de roteamento baseado em localização para um site habilitado para roteamento baseado em local, somente o gateway PSTN habilitado para roteamento baseado em local nesse site pode ser usado para chamadas de saída. Se um usuário habilitado para roams de roteamento baseado em localização para um site que não está habilitado para roteamento baseado em local, qualquer gateway que não esteja habilitado para roteamento baseado em localização poderá ser usado para chamadas de saída.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar roteamento baseado em local ao gateway PSTN 

Os gateways estão associados a sites para determinar onde um usuário habilitado para roteamento baseado em localização pode ser localizado quando eles fazem ou recebem uma chamada PSTN. Os gateways devem ser habilitados para roteamento baseado em local para garantir que ele esteja em restrições de desvios de chamada e não possa ser usado por usuários que não estão habilitados para roteamento baseado em localização. O mesmo gateway pode estar associado a vários sites, e ele pode ser configurado para ser habilitado para roteamento baseado em localização ou não habilitado para roteamento baseado em local, dependendo do site.

## <a name="scenarios-for-location-based-routing"></a>Cenários do Roteamento Baseado na Localização

Esta seção descreve diferentes cenários para restringir o bypass da chamada usando o roteamento baseado em localização e compara como as chamadas são roteadas para usuários que não estão habilitados para roteamento baseado em local com usuários habilitados para roteamento baseado em local.

- [O usuário do teams insere uma chamada de saída para a PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [O usuário do teams recebe uma chamada de entrada da PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [O usuário do teams transfere ou encaminha chamadas para outro usuário do teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [As transferências de usuários do teams ou encaminham chamadas para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Toque simultâneo](#simultaneous-ringing)
- [Delegação](#delegation)

O diagrama a seguir mostra as restrições habilitadas pelo roteamento baseado em local em cada cenário. Os usuários, os sites de rede e os gateways que são habilitados para o roteamento baseado em local têm uma borda ao seu. Use o diagrama como um guia para ajudá-lo a entender como o roteamento baseado em localização funciona em cada cenário.  

![Diagrama mostrando cenários para roteamento baseado em local](media/lbr-direct-routing.png "Diagrama mostrando cenários para roteamento baseado em local")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>O usuário do teams insere uma chamada de saída para a PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>O usuário não está habilitado para roteamento baseado em local

Um usuário que não está habilitado para roteamento baseado em localização pode fazer chamadas de saída usando qualquer gateway em qualquer site que não esteja habilitado para roteamento baseado em local por meio da política de roteamento de voz atribuída. No entanto, se um gateway estiver habilitado para roteamento baseado em local, o usuário não poderá fazer chamadas de saída pelo gateway mesmo se ele estiver atribuído à política de roteamento de voz. Se o usuário for móvel para um site habilitado para roteamento baseado em local, ele só poderá fazer chamadas por meio de seus gateways de roteamento normais que não estão habilitados para roteamento baseado em local.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento baseado em local
Em comparação, o roteamento de chamadas de saída para usuários que estão habilitados para roteamento baseado em local é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir mostra como o roteamento baseado em localização afeta o roteamento de chamadas de saída de Usuário1, dependendo da localização do Usuário1. 

|Localização do ponto de extremidade Usuário1  |Roteamento de chamadas de saída para user1  |
|---------|---------|
|Mesmo site em que o usuário fez a atribuição, site habilitado para roteamento baseado em local (site1)      |Chamada roteada por meio do gateway habilitada para roteamento baseado em local (GW1) em site1, com base na política de roteamento de voz do usuário         |
|Site diferente do qual o usuário fez a atribuição, site habilitado para roteamento baseado em local (site2)    |Chamada roteada por meio do gateway habilitada para roteamento baseado em local (GW2) no roam site2, com base na política de roteamento de voz do usuário        |
|Site diferente do qual o usuário fez a atribuição, site não habilitado para roteamento baseado em local (Site3)  |Chamada roteada por meio do gateway que não está habilitado para roteamento baseado em local no site que não está habilitado para roteamento baseado em local (GW3), com base na política de roteamento de voz do usuário       |
|Rede interna desconhecida (Location4)    |  Chamada PSTN não permitida       |
|Rede externa desconhecida (Location5)    | Chamada PSTN não permitida        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>O usuário do teams recebe uma chamada de entrada da PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>O usuário não está habilitado para roteamento baseado em local

Um usuário que não está habilitado para roteamento baseado em localização pode receber uma chamada de entrada do gateway que não está habilitado para roteamento baseado em local do qual o número atribuído ingresses. Se o usuário for móvel para um site que não está habilitado para roteamento baseado em local, ele ainda poderá receber chamadas por meio de seus gateways PSTN normais.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento baseado em local

Em comparação, os usuários habilitados para roteamento baseado em local só podem receber chamadas de entrada do gateway PSTN ao qual ele foi atribuído quando estiverem localizados no mesmo site. A tabela a seguir mostra como o Usuário1 recebe chamadas de entrada quando o Usuário1 se move para locais de rede diferentes. Se a chamada não for roteada para o ponto de extremidade do usuário, ela vai para as configurações de encaminhamento de chamadas do usuário, se as configurações estiverem definidas. Geralmente, esse é o correio de voz.  

|Localização do ponto de extremidade Usuário1  |Roteamento de chamadas recebidas para user1  |
|---------|---------|
|Mesmo site que o local do usuário foi atribuído, site habilitado para roteamento baseado em local (site1)   | Chamadas roteadas para o ponto de extremidade User1's no site1        |
|Site diferente do qual o usuário fez a atribuição, site habilitado para roteamento baseado em local (site2)    | Chamadas não encaminhadas para pontos de extremidade no site2        |
|Site diferente do qual o usuário fez a atribuição, site não habilitado para roteamento baseado em local (Site3)    | Chamadas não encaminhadas para pontos de extremidade no Site3        |
|Rede interna desconhecida (Location4)   | Chamadas não encaminhadas para pontos de extremidade no Location4        |
|Rede externa desconhecida (Location5)     | Chamadas não encaminhadas para pontos de extremidade no Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>O usuário do teams transfere ou encaminha chamadas para outro usuário do teams

Quando um ponto de extremidade PSTN está envolvido, o roteamento baseado em localização analisa se um ou ambos os usuários estão habilitados para roteamento baseado em localização e determina se a chamada deve ser transferida ou encaminhada dependendo do local de ambos os pontos de extremidade. 
 
A transferência de chamadas requer que o usuário inicial atenda a chamada enquanto o encaminhamento de chamadas não requer que a chamada inicial seja respondida. Isso significa que as chamadas podem ser encaminhadas mesmo que Usuário1 não esteja em um local para receber chamadas de entrada (veja se a tabela no [usuário do teams recebe uma chamada de entrada da seção PSTN](#teams-user-receives-an-inbound-call-from-the-pstn) ) e as chamadas não podem ser transferidas se user1 não puder receber a chamada de entrada. 

#### <a name="user-not-enabled-for-location-based-routing"></a>O usuário não está habilitado para roteamento baseado em local

Um usuário que não está habilitado para roteamento baseado em localização pode transferir ou encaminhar chamadas PSTN para outros usuários que não estão habilitados para roteamento baseado em local. Geralmente, o usuário não pode transferir ou encaminhar uma chamada PSTN para um usuário habilitado para roteamento baseado em local porque os usuários habilitados para roteamento baseado em localização, em geral, só podem ser colocados em conjunto em gateways habilitados para roteamento baseado em localização para chamadas PSTN. A exceção é quando um usuário habilitado para roteamento baseado em local faz roaming para um site que não está habilitado para roteamento baseado em local. Nesse cenário, a chamada transferida é permitida.  

Da mesma forma, um usuário que não está habilitado para roteamento baseado em local só pode receber uma transferência ou chamada PSTN encaminhada de outro usuário que não esteja habilitado para roteamento baseado em local. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento baseado em local

Geralmente, a transferência e encaminhamento de chamadas PSTN de entrada de um gateway habilitado para roteamento baseado em localização só é permitida se o usuário de destino estiver habilitado para roteamento baseado em localização e estiver localizado no mesmo site. Caso contrário, a transferência e encaminhamento de chamadas não é permitida. 

A tabela a seguir mostra se o encaminhamento de chamadas e transferências de chamadas são permitidos, dependendo da localização do usuário de destino. Nesta tabela, Usuário1, localizado em site1, inicia a transferência ou encaminhamento para outros usuários do teams que também estão habilitados para roteamento baseado em localização e que estão em locais diferentes.  

|Local de ponto de extremidade do usuário de destino|Usuário1 inicia a transferência de chamadas |Usuário1 inicia o encaminhamento de chamadas|
|---------|---------|---------|
|Mesmo local de rede que o iniciador (User2)|Autorizados|Autorizados|
|Site de rede diferente, site habilitado para roteamento baseado em local (Usuário3)|Não permitido|Não permitido|
|Site de rede diferente, site não habilitado para roteamento baseado em local (User4)|Não permitido|Não permitido|
|Rede interna desconhecida (User5)| Não permitido|Não permitido|
|Rede externa desconhecida (User6)| Não permitido|Não permitido|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>As transferências de usuários do teams ou encaminham chamadas para o ponto de extremidade PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>O usuário não está habilitado para roteamento baseado em local

- É permitido transferir e encaminhar uma chamada PSTN para outro número PSTN. 
- Transferir e encaminhar uma chamada VOIP de entrada para a PSTN deve respeitar as restrições de chamada tarifada do chamador. 
    - Se o chamador não estiver habilitado para roteamento baseado em local, ele poderá ser transferido para qualquer gateway PSTN que não esteja habilitado para roteamento baseado em local.
    - Se o chamador estiver habilitado para roteamento baseado em local, ele só poderá ser transferido para um gateway habilitado para roteamento baseado em local localizado no mesmo local de rede. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento baseado em local

- A transferência e encaminhamento de entrada de uma chamada PSTN para outro número PSTN deve ser roteado para o mesmo gateway habilitado para roteamento baseado em localização em que a chamada de entrada chegou. 
- A transferência e encaminhamento de uma chamada VOIP de entrada para a PSTN deve respeitar o chamador e as restrições de chamada tarifada do usuário chamadas. 
    - Se o chamador não estiver habilitado para roteamento baseado em local, ele poderá ser transferido para qualquer gateway PSTN que não esteja habilitado para roteamento baseado em local.
    - Se o chamador estiver habilitado para roteamento baseado em local, ele só poderá ser transferido para um gateway habilitado para roteamento baseado em local localizado no mesmo local de rede.
 
A tabela a seguir mostra como o roteamento baseado em localização afeta o roteamento de uma chamada de VOIP de Usuário1 em site1 para usuários em locais diferentes que transferem ou encaminham a chamada para um ponto de extremidade PSTN.  

|Usuário Iniciando transferência ou encaminhamento de chamadas  |Transferir para PSTN  |Encaminhar para PSTN  |
|---------|---------|---------|
|Mesmo site de rede, site habilitado para roteamento baseado em local (User2)   |A transferência de chamadas só pode ser roteada por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz User2's         |O encaminhamento de chamadas só pode ser roteado por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User2's         |
|Site de rede diferente, site habilitado para roteamento baseado em local (Usuário3)    |A transferência de chamadas só pode ser roteada por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz User3's         |O encaminhamento de chamadas só pode ser roteado por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User3's         |
|Site de rede diferente, site não habilitado para roteamento baseado em local (User4)    |A transferência de chamadas só pode ser roteada por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz User4's         |O encaminhamento de chamadas só pode ser roteado por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User4's         |
|Rede interna desconhecida (User5)     |A transferência de chamadas só pode ser roteada por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz User5's         |O encaminhamento de chamadas só pode ser roteado por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User5's         |
|Rede externa desconhecida (User6)   |A transferência de chamadas só pode ser roteada por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz User6's        |O encaminhamento de chamadas só pode ser roteado por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User6's         |

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando um usuário que está habilitado para o roteamento baseado em localização recebe uma chamada e tem o toque simultâneo habilitado, o roteamento baseado em local analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada. O toque simultâneo segue as mesmas regras baseadas em localização, como transferências e encaminhamentos de chamadas. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Toque simultâneo para outro usuário do teams

A tabela a seguir mostra se o roteamento baseado em localização permite o toque simultâneo para usuários diferentes para uma chamada PSTN de entrada para user1.

|Local de ponto de extremidade do usuário de destino|Toque simultâneo  |
|---------|---------|
|Mesmo local de rede que o iniciador (User2)   |Autorizados         |
|Site de rede móvel diferente habilitado para roteamento baseado em local (Usuário3)   |Não permitido         |
|Site de rede móvel não habilitado para roteamento baseado em local (User4)   |Não permitido        |
|Rede interna desconhecida (User5)    | Não permitido        |
|Rede externa desconhecida (User6)    |Não permitido        |
|O usuário de destino é um número PSTN    |A chamada só pode ser roteada por meio do roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User1's      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Tocando simultaneamente para um ponto de extremidade PSTN

A tabela a seguir mostra o comportamento de roteamento baseado em localização para uma chamada VOIP de entrada de Usuário1 localizada em site1 para usuários em locais diferentes com o toque simultâneo definido para um número PSTN. 

|Chamada local de ponto de extremidade do usuário  |O destino de toque simultâneo é um ponto de extremidade PSTN |
|---------|---------|
|Mesmo site de rede, site habilitado para roteamento baseado em local (User2)    |A chamada só pode ser roteada por meio de roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz User2's       |
|Site de rede diferente habilitado para roteamento baseado em local (Usuário3)    |A chamada só pode ser roteada por meio de roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User3's        |
|Site de rede diferente não habilitado para roteamento baseado em local (User4)    |A chamada só pode ser roteada por meio de roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User4's         |
|Rede interna desconhecida (User5)    |A chamada só pode ser roteada por meio de roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User5's         |
|Rede externa desconhecida (User6)   |A chamada só pode ser roteada por meio de roteamento baseado em local Gateway1 em site1, com base na política de roteamento de voz do User6's         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Chamadas recebidas por meio do aplicativo de voz (atendedor automático ou fila de chamadas)

As chamadas PSTN de entrada de um gateway habilitado para roteamento baseado em local têm permissão para se conectar a um atendedor automático ou fila de chamadas. Os usuários habilitados para roteamento baseado em local só podem receber transferências de chamadas de entrada desses aplicativos quando estiverem localizados no mesmo site em que a chamada PSTN de entrada for originada. 
 
O encaminhamento de chamadas e o toque simultâneo para os usuários e a PSTN são permitidos para transferências de aplicativos de voz. Concluir a chamada para o destino está sujeito às mesmas regras de roteamento baseadas em local listadas anteriormente.  
 
O encaminhamento para correio de voz também é permitido.  

### <a name="delegation"></a>Delegação

Um usuário do teams pode escolher os delegados que podem fazer e receber chamadas em nome deles. Os recursos de delegação no Teams são afetados pelo roteamento baseado em local da seguinte maneira: 
- Para chamadas de saída de um representante de roteamento baseado em local habilitado em nome de um delegador, as mesmas regras se aplicam. O roteamento de chamadas baseia-se na política de autorização de chamadas do representante, na política de roteamento de voz e no local. Para obter mais informações, consulte [Teams User colocam uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 
- Para chamadas PSTN de entrada para um delegador, as mesmas regras de roteamento baseadas em localização que se aplicam ao encaminhamento de chamadas ou ao toque simultâneo para outros usuários também se aplicam a representantes. Para obter mais informações, consulte [transferir usuários do teams ou encaminhar chamada para outro usuário](#teams-user-transfers-or-forwards-call-to-another-teams-user)do Teams, [transferir usuários do teams ou encaminhar chamada para ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)e [toque simultâneo](#simultaneous-ringing). Quando um representante define um ponto de extremidade PSTN como um alvo de toque simultâneo, a política de roteamento de voz do representante é usada para direcionar a chamada para a PSTN. 
- Para delegação, é recomendável que o delegante e os representantes associados estejam localizados no mesmo site de rede. 

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Alterações de uma implantação de roteamento baseada em locais locais

A política de roteamento de voz do site de rede não é mais usada. Em vez disso, usamos a política de roteamento de voz do usuário. Isso significa que para permitir que os usuários façam roaming para outros sites, a política de roteamento de voz deve incluir os gateways dos sites em roaming. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerações técnicas para Roteamento Baseado em Local

As sub-redes IPv4 e IPv6 são aceitas, no entanto, o IPv6 tem precedência quando verifica se há uma correspondência.

### <a name="client-support-for-location-based-routing"></a>Suporte do cliente para roteamento baseado em local

Há suporte para os seguintes clientes do teams:
- Clientes da área de trabalho do Teams (Windows e Mac)
- Clientes móveis do Microsoft Teams (iOS e Android)
- Telefones IP do teams

O cliente de equipes da Web e os clientes do Skype for Business não são compatíveis.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

O roteamento baseado em local não se aplica aos seguintes tipos de interações. O roteamento baseado em local não é imposto quando os pontos de extremidade da equipe interagem com pontos de extremidade PSTN nos seguintes cenários: 
- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada 
- Um usuário local do Skype for Business ou um usuário do Skype for Business online liga para um usuário do teams  

### <a name="location-based-routing-for-conferencing"></a>Roteamento baseado em local para conferência

Um usuário habilitado para roteamento baseado em local em uma chamada PSTN não pode iniciar uma conferência com outro usuário ou número PSTN. É permitido conectar-se a atendedores automáticos ou filas de chamadas. Se o usuário tiver uma licença de conferência, o usuário deverá iniciar uma conferência com os usuários relevantes e chamar a PSTN por meio da ponte de conferência para iniciar uma chamada em conferência.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de bypass de mídia para roteamento baseado em local

Se você estiver implantando o roteamento baseado em localização na Índia, será necessário configurar também o bypass de mídia. Para saber mais, consulte [planejar o bypass de mídia com o roteamento direto e a](direct-routing-plan-media-bypass.md) [otimização de mídia local para roteamento direto](direct-routing-media-optimization.md).

## <a name="next-steps"></a>Próximas etapas

Vá para [definir configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md)
