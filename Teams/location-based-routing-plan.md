---
title: Planejar o Roteamento baseado na localização para o Roteamento direto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Saiba como planejar o roteamento de Location-Based para o roteamento direto do telefone do Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 354a3ae6ec4fb482b6ba0d5136597438c37acbe2
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727783"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planejar o Roteamento baseado na localização para o Roteamento direto

Em alguns países e regiões, é ilegal ignorar o provedor PSTN (Rede Telefônica Comutada Pública) para diminuir os custos de chamada de longa distância. 

Este artigo descreve o que você precisa saber para usar Location-Based Roteamento para restringir o bypass de pedágio para usuários do Microsoft Teams com base em sua localização geográfica. Este artigo se aplica apenas ao Roteamento Direto. Location-Based Roteamento não se aplica ao Plano de Chamada ou ao Operator Connect.

Quando estiver pronto para habilitar Location-Based Roteamento, confira:

- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

> [!NOTE]
> Você não deve usar Location-Based Roteamento para rotear dinamicamente chamadas PSTN com base na localização do usuário. Fazer isso pode causar resultados não intencionais.

## <a name="overview"></a>Visão geral

Location-Based Roteamento permite restringir o bypass de pedágio para um usuário com base na política e na localização geográfica do usuário no momento de uma chamada PSTN de entrada ou saída. 

Location-Based Roteamento usa a topologia de rede que você define para região de rede, site e sub-rede. Quando o bypass de pedágio é restrito para um local, você associa cada sub-rede IP e cada gateway PSTN para esse local a um site de rede. 

No momento de uma chamada PSTN, a localização de um usuário é determinada pela sub-rede IP à qual os pontos de extremidade do Teams do usuário estão conectados. Se um usuário tiver vários clientes do Teams localizados em sites diferentes, Location-Based Roteamento imporá o roteamento de cada cliente separadamente, dependendo do local dos pontos de extremidade do Teams.

Para obter mais informações sobre configurações de rede, consulte [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md).

Este artigo pressupõe que um site de rede possa estar em um dos seguintes estados:

- **Habilitado** – um site configurado usando sub-redes e sites de rede de locatário e habilitado para Location-Based Roteamento.

- **Não habilitado** – um site configurado usando sub-redes e sites de rede de locatário, mas não habilitado para Location-Based Roteamento.

- **Desconhecido** – um site não configurado usando sub-redes e sites de rede de locatário. Normalmente, esses sites são internos para a rede corporativa, mas por design não configurado ou externos à rede corporativa. De qualquer forma, esses sites não estão habilitados para Location-Based Roteamento. 

### <a name="toll-bypass-evaluation-and-outcome"></a>Avaliação e resultado do bypass de pedágio

Quando Location-Based Roteamento é usado, uma chamada entre um usuário do Teams e o PSTN é avaliada para determinar se o bypass de pedágio é restrito. Dependendo dos resultados, a chamada será ou não concluída. 

Se um usuário estiver habilitado para Location-Based Roteamento e o usuário estiver localizado em um site onde Location-Based restrições de roteamento estiverem em vigor, o bypass de pedágio será restrito para esse usuário. O Teams usa as seguintes informações para determinar se o bypass de pedágio é restrito: 

- Se o usuário do Teams está habilitado para Location-Based Roteamento conforme definido na política de Chamada do Teams do usuário.

- O local do site de rede do usuário do Teams e se o site está habilitado ou não para Location-Based Roteamento.

- O local do site de rede do gateway PSTN que está sendo usado pela chamada.

- Se o gateway PSTN que está sendo usado pela chamada foi habilitado para Location-Based Roteamento.

- Para cenários de transferência, a rota da chamada PSTN baseia-se nas configurações de roteamento da pessoa que está transferindo a chamada e nas configurações de roteamento Location-Based do usuário do Teams para o qual a chamada está sendo transferida.  

- Para cenários de conferência e chamada de grupo, se um usuário do Teams para o qual o bypass de pedágio é restrito é ou faz parte da chamada.

Se uma chamada não puder ser concluída, o usuário do Teams será notificado da seguinte maneira:

- Para chamadas PSTN de saída, a seguinte mensagem aparece na janela de chamada: Chamada não permitida devido às configurações da sua organização.

- Para chamadas PSTN de entrada, a chamada é roteada com base nas configurações de encaminhamento de chamada sem resposta do usuário do Teams, normalmente para a caixa postal. Se o usuário do Teams não tiver configuradas configurações de chamada sem resposta, a chamada será desconectada.

## <a name="apply-location-based-routing"></a>Aplicar Location-Based Roteamento

Você deve aplicar Location-Based Roteamento ao seguinte:

- [Usuários](#apply-location-based-routing-at-the-user-location)
- [Sites de rede](#apply-location-based-routing-at-the-network-site)
- [Gateways PSTN](#apply-location-based-routing-at-the-pstn-gateway)

Tenha em mente as seguintes práticas recomendadas:

- O gateway PSTN e o site de rede associados ao gateway devem estar habilitados para Location-Based Roteamento.

- Para fazer chamadas por meio de um gateway PSTN habilitado para Location-Based Roteamento, os usuários também devem estar habilitados para Location-Based Roteamento.

- Para permitir que os usuários habilitados para Location-Based Roteamento coloquem chamadas PSTN de saída de um site de rede desconhecido, o seguinte deve ser verdadeiro:

  - A chamada precisa ser saída de um gateway PSTN habilitado para Location-Based Roteamento.
  - O gateway PSTN deve ser configurado com o sinalizador GatewayLbrEnabledUserOverride definido como True.


### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar Location-Based Roteamento no local do usuário

A restrição de bypass de pedágio controla as condições em que um usuário pode fazer e receber chamadas PSTN e o gateway PSTN que pode ser usado. 

Se um usuário estiver sob restrição de bypass de pedágio, esse usuário deverá ser habilitado para Location-Based Roteamento. Quando o usuário habilitado está localizado em um site habilitado para Location-Based Roteamento, o usuário deve fazer chamadas por meio de um gateway que esteja conectado ao site e habilitado para Location-Based Roteamento. 

Location-Based Roteamento funciona determinando o local atual do usuário com base no endereço IP do ponto de extremidade do Teams do usuário e aplica as regras de acordo. O local de um usuário habilitado para Location-Based Roteamento pode ser categorizado da seguinte maneira: 

- **O usuário está localizado no mesmo site habilitado para Roteamento Location-Based associado ao gateway PSTN em que o DID é atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede configurado habilitado para Location-Based Roteamento e o número did (Discagem Direta para Entrada) do usuário termina em um gateway PSTN que está no mesmo site de rede. Por exemplo, o usuário está em seu escritório. 

- **O usuário está localizado em um site habilitado para roteamento de Location-Based diferente não associado ao gateway PSTN em que o DID é atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede configurado habilitado para Location-Based Roteamento e esse site não está associado ao gateway PSTN em que o número DID do usuário é atribuído. Por exemplo, o usuário viaja para outro escritório.  

- **O usuário está localizado em um site interno que não está habilitado para Location-Based Roteamento.** <br>Nesse cenário, o usuário está localizado em um site de rede configurado que não está habilitado para Location-Based Roteamento. 

- **O usuário está localizado em um site desconhecido.** 
    - O usuário está localizado na rede interna que não é definida como um site de rede. 
    - O usuário está localizado fora da rede interna. Por exemplo, o usuário está na Internet em casa ou em uma cafeteria. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar Location-Based Roteamento no site de rede 

Quando os usuários habilitados para Location-Based Roteamento estiverem roaming, os sites de rede habilitados para Location-Based Roteamento ajudarão a determinar quais gateways devem ser usados. Por exemplo:

- Se um usuário habilitado para Location-Based Roteamento percorrer para um site habilitado para Location-Based Roteamento, somente o gateway PSTN habilitado para Location-Based Roteamento nesse site poderá ser usado para chamadas de saída. 

- Se um usuário habilitado para Location-Based Roteamento vagar para um site que não está habilitado para Location-Based Roteamento, qualquer gateway que não esteja habilitado para Location-Based Roteamento poderá ser usado para chamadas de saída.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar Location-Based Roteamento no gateway PSTN  

Para aplicar Location-Based Roteamento no gateway PSTN, você deve fazer o seguinte:

- Habilite o gateway para Location-Based Roteamento. (Os gateways devem ser habilitados para Location-Based Roteamento para garantir que eles não possam ser usados por usuários que não estão habilitados para Location-Based Roteamento.)

- Atribua um site de rede ao gateway.

Em seguida, o sistema determina se um determinado usuário em um determinado site tem permissão para usar o gateway. 

Além disso, se você definir o GatewayLbrEnabledUserOverride como True, usuários habilitados para roteamento baseado em localização em sites desconhecidos — por exemplo, usuários que trabalham em casa — poderão fazer chamadas PSTN de saída.


## <a name="restriction-rules"></a>Regras de restrição

As regras de restrição dependem se um usuário do Teams está ou não habilitado para Location-Based Roteamento.

### <a name="user-is-enabled-for-location-based-routing"></a>O usuário está habilitado para roteamento de Location-Based

Quando um usuário está habilitado para Location-Based Roteamento, o seguinte se aplica:

- **Para fazer uma chamada PSTN de saída**, um dos seguintes deve ser verdadeiro:

  - O ponto de extremidade do usuário está localizado em um site habilitado para Location-Based Roteamento e chama a saída por meio de um gateway PSTN habilitado para Location-Based Roteamento no mesmo site.  

  - O ponto de extremidade do usuário está localizado em um site desconhecido e chama a saída por meio de um gateway PSTN habilitado para Location-Based Roteamento. O gateway PSTN é configurado com o parâmetro GatewayLbrEnabledUserOverride definido como True.

  - O ponto de extremidade do usuário está localizado em um site que não está habilitado para Location-Based Roteamento e chama a saída por meio de um gateway PSTN que não está habilitado para Location-Based Roteamento.

- **Para receber uma chamada PSTN de entrada**, um dos seguintes deve ser verdadeiro: 

   - O ponto de extremidade de resposta do usuário e o gateway PSTN pelo qual a chamada foi ingressada devem estar localizados no mesmo site habilitado para Location-Based Roteamento. O gateway PSTN deve estar habilitado para Location-Based Roteamento.

   - O ponto de extremidade de resposta do usuário e o gateway PSTN pelo qual a chamada é ingressada devem estar localizados no mesmo site que não está habilitado para Location-Based Roteamento. O gateway PSTN não deve ser habilitado para Location-Based Roteamento.  (Esse cenário envolve o redirecionamento da chamada PSTN de entrada para entrada, embora outro gateway PSTN do que o normalmente usado para chamadas de entrada para o número de telefone do usuário.)

   - Em qualquer outro cenário, como se o usuário estiver vagando, a chamada não é permitida e é roteada para as configurações de encaminhamento de chamada sem resposta do usuário (normalmente caixa postal).  
   
- **Para uma chamada voIP do Teams 1:1 e transferência para PSTN**, observe o seguinte:

  - O roteamento da chamada - ou seja, qual gateway PSTN para egressar a chamada em - baseia-se nas configurações de roteamento do usuário que transfere a chamada.

  - Se a transferência será permitida é baseado no seguinte:
  
    - O Location-Based configurações de roteamento do usuário que está sendo transferido para o PSTN.
    - O local do site de rede do ponto de extremidade.
    - Se o local está habilitado para Location-Based Roteamento.

    A transferência será permitida se o usuário que está sendo transferido conseguir fazer essa chamada PSTN em seu local atual usando o mesmo gateway PSTN.

- **Para uma chamada PSTN de entrada ou saída e transferência para outro usuário do Teams**, se a transferência é permitida depende do seguinte:

   - As configurações de roteamento do usuário que está recebendo a chamada transferida. 
   - O local do site de rede do ponto de extremidade.
   - Se o local está habilitado para Location-Based Roteamento.

   A transferência será permitida se a pessoa que recebe a chamada transferida puder fazer ou receber essa chamada PSTN em seu local atual usando o gateway PSTN usado pela chamada PSTN em andamento.


### <a name="user-is-not-enabled-for-location-based-routing"></a>O usuário não está habilitado para roteamento de Location-Based

Quando um usuário do Teams não está habilitado para Location-Based Roteamento, todas as chamadas de e para esse usuário devem rotear por meio de um gateway PSTN que não está habilitado para Location-Based Roteamento. Uma chamada de entrada para esse usuário roteada por meio de um gateway PSTN habilitado para Location-Based Roteamento roteará para as configurações de encaminhamento de chamada sem resposta do usuário (normalmente caixa postal).

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>Fluxos de decisão para chamadas de entrada e saída

Os diagramas a seguir mostram os fluxos de decisão para chamadas de entrada e saída.

**Chamadas de entrada**

![Diagrama mostrando LBR para chamadas de entrada](media/lbr-routing-inbound1.png "Diagrama mostrando cenários para Location-Based Roteamento")

**Chamadas de saída**

![Diagrama mostrando LBR para chamadas de saída](media/lbr-routing-outbound1.png "Diagrama mostrando cenários para Location-Based Roteamento")


## <a name="scenarios-for-location-based-routing"></a>Cenários do Roteamento Baseado na Localização

Esta seção descreve diferentes cenários para restringir o bypass de pedágio usando Location-Based Roteamento. Os cenários comparam como as chamadas são roteadas para usuários que não estão habilitados para Location-Based Roteamento com usuários habilitados para Location-Based Roteamento.

- [O usuário do Teams coloca uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [O usuário do Teams recebe uma chamada de entrada do PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [O usuário do Teams transfere ou encaminha chamada para outro usuário do Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Transferências ou encaminhamentos de usuário do Teams chamam para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Toque simultâneo](#simultaneous-ringing)
- [Delegação](#delegation)

O diagrama a seguir mostra as restrições habilitadas por Location-Based Roteamento em cada cenário. Usuários, sites de rede e gateways habilitados para Location-Based Roteamento têm uma borda em torno deles. Use o diagrama como um guia para ajudá-lo a entender como Location-Based Roteamento funciona em cada cenário.  

![Diagrama mostrando cenários para Location-Based Roteamento.](media/lbr-direct-routing.png "Diagrama mostrando cenários para Location-Based Roteamento")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>O usuário do Teams coloca uma chamada de saída para o PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento de Location-Based

Um usuário que não está habilitado para Location-Based Roteamento pode fazer chamadas de saída usando qualquer gateway em qualquer site que não esteja habilitado para Location-Based Roteamento por meio de sua política de roteamento de voz atribuída. No entanto, se um gateway estiver habilitado para Location-Based Roteamento, o usuário não poderá fazer chamadas de saída por meio do gateway, mesmo que seja atribuído à política de roteamento de voz. Se o usuário percorrer um site habilitado para Location-Based Roteamento, ele só poderá fazer chamadas por meio de seus gateways de roteamento normais que não estão habilitados para Location-Based Roteamento.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento de Location-Based

Em comparação, o roteamento de chamadas de saída para usuários habilitados para Location-Based Roteamento é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir mostra como Location-Based Roteamento afeta o roteamento de chamadas de saída do User1, dependendo da localização do User1. 

|Local do ponto de extremidade user1  |Roteamento de chamadas de saída para User1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site1)      |Chamada roteada por meio do gateway habilitado para o GW1 (roteamento de Location-Based) no Site1, com base na política de roteamento de voz do usuário         |
|Site diferente de onde o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site2)    |Chamada roteada por meio do gateway habilitado para o GW2 (roteamento de Location-Based) no Site2 do roam, com base na política de roteamento de voz do usuário        |
|Site diferente de onde o DID do usuário é atribuído, site não habilitado para Location-Based Roteamento (Site3)  |Chamada roteada por meio do gateway que não está habilitado para Location-Based Roteamento no site que não está habilitado para o GW3 (roteamento de Location-Based), com base na política de roteamento de voz do usuário       |
|Rede interna desconhecida (Location4)    |  Chamada PSTN não permitida a menos que o gateway tenha GatewayLbrEnabledUserOverride definido como True       |
|Rede externa desconhecida (Location5)    | Chamada PSTN não permitida a menos que o gateway tenha GatewayLbrEnabledUserOverride definido como True       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>O usuário do Teams recebe uma chamada de entrada do PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento de Location-Based

Um usuário que não está habilitado para Location-Based Roteamento pode receber uma chamada de entrada do gateway que não está habilitada para Location-Based Roteamento do qual o número DID atribuído ingresse. Se o usuário percorre um site que não está habilitado para o Roteamento Location-Based, ele ainda poderá receber chamadas por meio de seus gateways PSTN normais.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento de Location-Based

Em comparação, os usuários habilitados para Location-Based Roteamento só podem receber chamadas de entrada do gateway PSTN ao qual o DID é atribuído quando estão localizados no mesmo site. A tabela a seguir mostra como o User1 recebe chamadas de entrada quando o User1 se move para diferentes locais de rede. Se a chamada não for roteada para o ponto de extremidade do usuário, ela irá para as configurações de encaminhamento de chamada sem resposta do usuário, se as configurações estiverem configuradas. Normalmente, as chamadas são encaminhadas para a caixa postal.  

|Local do ponto de extremidade user1  |Roteamento de chamadas de entrada para User1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site1)   | Chamadas roteadas para o ponto de extremidade do User1 no Site1        |
|Site diferente de onde o DID do usuário é atribuído, site habilitado para Location-Based Roteamento (Site2)    | Chamadas não roteadas para pontos de extremidade no Site2        |
|Site diferente de onde o DID do usuário é atribuído, site não habilitado para Location-Based Roteamento (Site3)    | Chamadas não roteadas para pontos de extremidade no Site3        |
|Rede interna desconhecida (Location4)   | Chamadas não roteadas para pontos de extremidade no Location4        |
|Rede externa desconhecida (Location5)     | Chamadas não roteadas para pontos de extremidade no Location5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>O usuário do Teams transfere ou encaminha chamada para outro usuário do Teams

Quando um ponto de extremidade PSTN está envolvido, Location-Based Roteamento analisa se um ou ambos os usuários estão habilitados para Location-Based Roteamento e determina se a chamada deve ser transferida ou encaminhada dependendo do local de ambos os pontos de extremidade. 
 
A transferência de chamada requer que o usuário iniciador atendeu a chamada enquanto o encaminhamento de chamadas não exige que a chamada inicial seja atendida. As chamadas podem ser encaminhadas mesmo que o User1 não esteja em um local para receber chamadas de entrada (consulte a tabela no [usuário do Teams recebe uma chamada de entrada da seção PSTN](#teams-user-receives-an-inbound-call-from-the-pstn) ) e as chamadas não poderão ser transferidas se o User1 não puder receber a chamada de entrada. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento de Location-Based

Um usuário que não está habilitado para Location-Based Roteamento pode transferir ou encaminhar chamadas PSTN para outros usuários que não estão habilitados para Location-Based Roteamento. Os usuários habilitados para Location-Based Roteamento geralmente estão co-localizados em gateways habilitados para roteamento de Location-Based para chamadas PSTN. Consequentemente, os usuários que não estão habilitados não podem transferir ou encaminhar uma chamada PSTN para um usuário habilitado para Location-Based Roteamento. A exceção é quando um usuário habilitado para roteamento de Location-Based percorre um site que não está habilitado para Location-Based Roteamento. Nesse cenário, a chamada transferida é permitida.  

Da mesma forma, um usuário que não está habilitado para Location-Based Roteamento só pode receber uma transferência ou uma chamada PSTN encaminhada de outro usuário que não está habilitado para Location-Based Roteamento. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento de Location-Based

A transferência e o encaminhamento de chamadas PSTN de entrada de um gateway habilitado para Location-Based Roteamento só serão permitidos se o usuário de destino estiver habilitado para Location-Based Roteamento e estiver localizado no mesmo site. Caso contrário, não é permitido transferir e encaminhar chamadas. 

A tabela a seguir mostra se as transferências de chamada e encaminhamento de chamadas são permitidas, dependendo da localização do usuário de destino. Nesta tabela, o User1, localizado no Site1, inicia a transferência ou encaminha para outros usuários do Teams que também estão habilitados para Location-Based Roteamento e que estão em locais diferentes.  

|Local do ponto de extremidade do usuário de destino|User1 inicia a transferência de chamada |User1 inicia a chamada para a frente|
|---------|---------|---------|
|Mesmo site de rede que o iniciador (User2)|Permitido|Permitido|
|Site de rede diferente, site habilitado para Location-Based Roteamento (User3)|Não permitido|Não permitido|
|Site de rede diferente, site não habilitado para roteamento de Location-Based (User4)|Não permitido|Não permitido|
|Rede interna desconhecida (User5)| Não permitido|Não permitido|
|Rede externa desconhecida (User6)| Não permitido|Não permitido|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Transferências ou encaminhamentos de usuário do Teams chamam para o ponto de extremidade PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento de Location-Based

- É permitido transferir e encaminhar uma chamada PSTN para outro número PSTN. 

- Transferir e encaminhar uma chamada VOIP de entrada para o PSTN deve honrar as restrições de bypass de pedágio do chamador. 

    - Se o chamador não estiver habilitado para Location-Based Roteamento, ele poderá ser transferido para qualquer gateway PSTN que não esteja habilitado para Location-Based Roteamento.
    - Se o chamador estiver habilitado para Location-Based Roteamento, ele só poderá ser transferido para um gateway habilitado para Roteamento Location-Based localizado no mesmo site de rede. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento de Location-Based

- A transferência e o encaminhamento de uma chamada PSTN para outro número PSTN devem ser roteados para fora do mesmo gateway habilitado para roteamento Location-Based em que a chamada de entrada chegou.

- Transferir e encaminhar uma chamada VOIP de entrada para o PSTN deve honrar tanto o chamador quanto as restrições de bypass de pedágio do usuário. 

    - Se o chamador não estiver habilitado para Location-Based Roteamento, ele poderá ser transferido para qualquer gateway PSTN que não esteja habilitado para Location-Based Roteamento.

    - Se o chamador estiver habilitado para Location-Based Roteamento, ele poderá ser transferido apenas para um gateway habilitado para roteamento de Location-Based localizado no mesmo site de rede.
 
A tabela a seguir mostra como Location-Based Roteamento afeta o roteamento de uma chamada VOIP de Location-Based User1 habilitado para Roteamento no Site1 para usuários em locais diferentes que transferem ou encaminham a chamada para um ponto de extremidade PSTN.  

|Usuário iniciando transferência de chamada ou encaminhamento  |Transferir ou encaminhar para PSTN  |
|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based Roteamento (User2)   |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User2 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1         |
|Site de rede diferente, site habilitado para Location-Based Roteamento (User3)    |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User3 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1 |
|Site de rede diferente, site não habilitado para roteamento de Location-Based (User4)    |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User4 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1          |
|Rede interna desconhecida (User5)     |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User5 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1          |
|Rede externa desconhecida (User6)   |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User6 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1          |

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando um usuário habilitado para Location-Based Roteamento recebe uma chamada e tem o toque simultâneo habilitado, Location-Based Roteamento analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada. O toque simultâneo segue as mesmas regras de Location-Based que transferências de chamada e encaminhamentos. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Toque simultâneo para outro usuário do Teams

A tabela a seguir mostra se Location-Based Roteamento permite o toque simultâneo para diferentes usuários para uma chamada PSTN de entrada para User1.

|Local do ponto de extremidade do usuário de destino|Anel simultâneo  |
|---------|---------|
|Mesmo site de rede que o iniciador (User2)   |Permitido         |
|Site de rede perambulado diferente habilitado para roteamento de Location-Based (User3)   |Não permitido         |
|Site de rede de roaming não habilitado para roteamento de Location-Based (User4)   |Não permitido        |
|Rede interna desconhecida (User5)    | Não permitido        |
|Rede externa desconhecida (User6)    |Não permitido        |
|O usuário de destino é um número PSTN    |A chamada só pode ser roteada por meio do Gateway1 habilitado para roteamento de Location-Based no Site1, com base na política de roteamento de voz do User1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Toque simultâneo em um ponto de extremidade PSTN

A tabela a seguir mostra Location-Based comportamento de roteamento para uma chamada VoIP de entrada de Location-Based User1 habilitado para roteamento localizado no Site1 para usuários em locais diferentes com anel simultâneo definido como um número PSTN. 

|Chamado local do ponto de extremidade do usuário  |O destino do anel simultâneo é o ponto de extremidade PSTN |
|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based Roteamento (User2)    |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User2 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1        |
|Site de rede diferente habilitado para roteamento de Location-Based (User3)    |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User3 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1         |
|Site de rede diferente não habilitado para roteamento de Location-Based (User4)    |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User4 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1          |
|Rede interna desconhecida (User5)    |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User5 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1          |
|Rede externa desconhecida (User6)   |A chamada PSTN resultante só será permitida se a rota calculada com base na política de roteamento de voz do User6 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento no Site1          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>Chamadas de entrada por meio de aplicativos de voz (Atendimento Automático ou Fila de Chamadas)

Chamadas PSTN de entrada de um gateway habilitado para roteamento de Location-Based podem se conectar a um atendente automático ou fila de chamadas. 

Os usuários habilitados para Location-Based Roteamento têm suporte para receber transferências de chamada de entrada para esses aplicativos quando estiverem localizados no mesmo site do qual a chamada PSTN de entrada se origina. Para dar suporte à Otimização de Mídia Local e Bypass de Mídia nesses cenários, as filas de chamadas devem ser configuradas para o modo de transferência (Modo de Conferência = OFF).
 
O encaminhamento de chamadas e o toque simultâneo para usuários e PSTN são permitidos para transferências de aplicativo de voz. A conclusão da chamada para o destino está sujeita às mesmas regras de roteamento Location-Based listadas anteriormente.  
 
O encaminhamento para a caixa postal também é permitido.  

### <a name="delegation"></a>Delegação

Um usuário do Teams pode escolher delegados que podem fazer e receber chamadas em seu nome. Os recursos de delegação no Teams são afetados pelo roteamento de Location-Based da seguinte maneira: 

- Para chamadas de saída de um delegado habilitado para roteamento de Location-Based em nome de um delegado, as mesmas regras se aplicam. O roteamento de chamadas baseia-se na política de autorização de chamada do delegado, na política de roteamento de voz e no local. Para obter mais informações, consulte [O usuário do Teams coloca uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 

- Para chamadas PSTN de entrada para um delegador, as mesmas regras de roteamento de Location-Based que se aplicam ao encaminhamento de chamadas ou ao toque simultâneo a outros usuários também se aplicam aos delegados. Para obter mais informações, consulte [Transferências ou encaminhamentos de usuário do Teams chamem para outro usuário do Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user), [transferências de usuários ou encaminhamentos do Teams chamem para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint) e [toque simultâneo](#simultaneous-ringing). Quando um delegado define um ponto de extremidade PSTN como um destino de anel simultâneo, a política de roteamento de voz do delegado é usada para rotear a chamada para o PSTN. 

- Para delegação, a Microsoft recomenda que o delegado e os delegados associados estejam localizados no mesmo site de rede. 

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Alterações de uma implantação de roteamento de Location-Based local

A política de roteamento de voz do site de rede não é mais usada. Em vez disso, usamos a política de roteamento de voz do usuário. Para permitir que os usuários percorram outros sites, a política de roteamento de voz deve incluir os gateways dos sites perambulados. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerações técnicas para Roteamento Baseado em Local

No entanto, há suporte para sub-redes IPv4 e IPv6, no entanto, o IPv6 tem precedência ao verificar se há uma correspondência.

### <a name="client-support-for-location-based-routing"></a>Suporte ao cliente para roteamento de Location-Based

Há suporte para os seguintes clientes do Teams:
- Clientes da área de trabalho do Teams (Windows e Mac)
- Clientes móveis do Teams (iOS e Android)
- Telefones IP do Teams

Não há suporte para o cliente Web do Teams e Skype for Business clientes.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

Location-Based Roteamento não se aplica aos seguintes tipos de interações. Location-Based o roteamento não é imposto quando os pontos de extremidade do Teams interagem com pontos de extremidade PSTN nos seguintes cenários: 

- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada 

- Um usuário Skype for Business local ou um usuário do Skype for Business Online chama um usuário do Teams  

### <a name="location-based-routing-for-conferencing"></a>Location-Based Roteamento para conferência

Um usuário habilitado para roteamento de Location-Based sem uma licença de conferência de áudio em uma chamada PSTN não tem permissão para iniciar uma conferência com outro usuário ou número PSTN. É permitido conectar-se a atendentes automáticos ou filas de chamadas.

Se o usuário tiver uma licença de conferência de áudio, o usuário deverá iniciar uma conferência com os usuários relevantes e chamar o PSTN por meio da ponte de conferência para iniciar uma teleconferência. Se o usuário já estiver em uma chamada PSTN, ele poderá adicionar outro usuário ou número PSTN à chamada por meio da escalada da chamada usando a ponte de conferência para discar para fora.

Em uma teleconferência iniciada por um usuário sem uma licença de conferência de áudio, a adição de participantes PSTN não é permitido se houver ou tiver havido pelo menos um usuário habilitado para Roteamento Location-Based na teleconferência. Se pelo menos um participante do PSTN fizer ou fizer parte dessa teleconferência antes de qualquer Location-Based participantes habilitados para roteamento foram convidados a participar da chamada, Location-Based os participantes habilitados para roteamento não poderão ser adicionados à chamada.

Se o usuário habilitado para Roteamento Location-Based estiver ingressando na chamada de conferência de um site interno que não está habilitado para Location-Based Roteamento, as restrições no parágrafo acima não serão impostas. 

A conferência na rede para Conferência de Áudio NÃO deve ser implantada com nenhum equipamento de telefonia na Índia.

Um usuário habilitado para roteamento de Location-Based em uma chamada PSTN não tem permissão para mesclar essa chamada com outra chamada. Não há suporte a seguir: gravação da chamada PSTN e da gravação de conformidade da chamada PSTN.

### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de bypass de mídia para roteamento de Location-Based

Se você estiver implantando Location-Based Roteamento na Índia, é necessário também configurar o bypass de mídia. Para saber mais, confira [Planejar bypass de mídia com Roteamento Direto](direct-routing-plan-media-bypass.md) e [Otimização de Mídia Local para Roteamento Direto](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>Ip de voz direta (VoIP)

O VOIP (Direct Voice over IP) não deve ser implantado com nenhum equipamento de telefonia na Índia.


## <a name="related-articles"></a>Artigos relacionados

- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md)
