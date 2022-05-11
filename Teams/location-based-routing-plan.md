---
title: Planejar o Roteamento baseado na localização para o Roteamento direto
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Saiba como planejar o roteamento Location-Based para Teams Telefone Roteamento Direto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f156b287969303edbf195c0054b3bb1eb631db2
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "65303993"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planejar o Roteamento baseado na localização para o Roteamento direto

Em alguns países e regiões, é ilegal ignorar o provedor PSTN (Rede Telefônica Pública Comuada) para diminuir os custos de chamadas de longa distância. 

Este artigo descreve o que você precisa saber para usar o Location-Based roteamento para restringir o bypass de chamada tarifada para Microsoft Teams usuários com base em sua localização geográfica. Este artigo se aplica somente ao Roteamento Direto. Location-Based roteamento não se aplica ao Plano de Chamadas ou Conexão do operador.

Quando estiver pronto para habilitar o Location-Based roteamento, confira:

- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Implantar configurações de rede para Location-Based roteamento](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)

> [!NOTE]
> Você não deve usar Location-Based roteamento dinâmico para rotear chamadas PSTN dinamicamente com base na localização do usuário. Fazer isso pode causar resultados não intencionais.

## <a name="overview"></a>Visão Geral

Location-Based roteamento permite restringir o bypass de chamada tarifada para um usuário com base na política e na localização geográfica do usuário no momento de uma chamada PSTN de entrada ou saída. 

Location-Based roteamento usa a topologia de rede que você define para região de rede, site e sub-rede. Quando o bypass de chamada tarifada é restrito para um local, você associa cada sub-rede IP e cada gateway PSTN para esse local a um site de rede. 

No momento de uma chamada PSTN, o local de um usuário é determinado pela sub-rede IP à qual os pontos de extremidade Teams usuário estão conectados. Se um usuário tiver vários clientes Teams localizados em sites diferentes, o roteamento do Location-Based imporá o roteamento de cada cliente separadamente, dependendo da localização dos pontos de extremidade Teams dados.

Para obter mais informações sobre configurações de rede, consulte [Configurações de rede para recursos de voz na nuvem Teams](cloud-voice-network-settings.md).

Este artigo pressupõe que um site de rede pode estar em um dos seguintes estados:

- **Habilitado –** um site configurado usando sub-redes de rede de locatário e sites e habilitado para Location-Based Roteamento.

- **Não habilitado –** um site configurado usando sub-redes e sites de rede de locatário, mas não habilitado para roteamento Location-Based locatário.

- **Desconhecido** – um site não configurado usando sites e sub-redes de rede de locatários. Normalmente, esses sites são internos da rede corporativa, mas por design não configurados ou externos à rede corporativa. De qualquer forma, esses sites não estão habilitados para o Location-Based Roteamento. 

### <a name="toll-bypass-evaluation-and-outcome"></a>Avaliação e resultado do bypass de chamada tarifada

Quando Location-Based roteamento é usado, uma chamada entre um usuário Teams e o PSTN é avaliada para determinar se o bypass de chamada tarifada é restrito. Dependendo dos resultados, a chamada será ou não concluída. 

Se um usuário estiver habilitado para o roteamento Location-Based e o usuário estiver localizado em um site em que as restrições de roteamento do Location-Based estão em vigor, o bypass de chamada tarifada será restrito para esse usuário. Teams usa as seguintes informações para determinar se o bypass de chamada tarifada é restrito: 

- Se o Teams usuário está habilitado para Location-Based roteamento conforme definido na política de Teams Chamada do usuário.

- O Teams local do site de rede do ponto de extremidade do usuário e se o site está habilitado ou não para Location-Based Roteamento.

- O local do site de rede do gateway PSTN que está sendo usado pela chamada.

- Se o gateway PSTN que está sendo usado pela chamada foi habilitado para Location-Based Roteamento.

- Para cenários de transferência, a rota da chamada PSTN se baseia nas configurações de roteamento da pessoa que está transferindo a chamada e nas configurações de Roteamento do Location-Based do usuário do Teams para o qual a chamada está sendo transferida.  

- Para cenários de conferência e chamada em grupo, se um Teams usuário para o qual o bypass de chamada tarifada está restrito é ou se fez parte da chamada.

Se uma chamada não puder ser concluída, o Teams usuário será notificado da seguinte maneira:

- Para chamadas PSTN de saída, a seguinte mensagem aparece na janela de chamada: chamada não permitida devido às configurações da sua organização.

- Para chamadas PSTN de entrada, a chamada é roteada com base nas chamadas Teams configurações de encaminhamento de chamadas não respondidas do usuário, normalmente para a caixa postal. Se o Teams usuário não tiver configurações de chamada não respondidas definidas, a chamada será desconectada.

## <a name="apply-location-based-routing"></a>Aplicar Location-Based roteamento

Você deve aplicar Location-Based roteamento ao seguinte:

- [Usuários](#apply-location-based-routing-at-the-user-location)
- [Sites de rede](#apply-location-based-routing-at-the-network-site)
- [Gateways PSTN](#apply-location-based-routing-at-the-pstn-gateway)

Lembre-se das seguintes práticas recomendadas:

- O gateway PSTN e o site de rede associados ao gateway devem ser habilitados para Location-Based roteamento.

- Para fazer chamadas por meio de um gateway PSTN habilitado para roteamento Location-Based, os usuários também devem ser habilitados para Location-Based roteamento.

- Para permitir que os usuários habilitados para o roteamento Location-Based localizem chamadas PSTN de saída de um site de rede desconhecido, o seguinte deve ser verdadeiro:

  - A chamada precisa ser saída de um gateway PSTN habilitado para Location-Based Roteamento.
  - O gateway PSTN deve ser configurado com o sinalizador GatewayLbrEnabledUserOverride definido como True.


### <a name="apply-location-based-routing-at-the-user-location"></a>Aplicar Location-Based roteamento no local do usuário

A restrição de bypass de chamada tarifada controla as condições nas quais um usuário pode fazer e receber chamadas PSTN e o gateway PSTN que pode ser usado. 

Se um usuário estiver sob restrição de bypass de chamada tarifada, esse usuário deverá ser habilitado para Location-Based Roteamento. Quando o usuário habilitado está localizado em um site habilitado para roteamento do Location-Based, o usuário deve fazer chamadas por meio de um gateway que esteja conectado ao site e habilitado para roteamento Location-Based. 

Location-Based roteamento funciona determinando o local atual do usuário com base no endereço IP do ponto de extremidade Teams usuário e aplica as regras adequadamente. O local de um usuário que está habilitado para Location-Based roteamento pode ser categorizado da seguinte maneira: 

- **O usuário está localizado no mesmo site Location-Based roteamento habilitado associado ao gateway PSTN em que seu DID é atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede configurado habilitado para roteamento do Location-Based e o número DID (Direct Inward Dial) do usuário é encerrado em um gateway PSTN que está no mesmo site de rede. Por exemplo, o usuário está em seu escritório. 

- **O usuário está localizado em outro site Location-Based roteamento habilitado não associado ao gateway PSTN em que seu DID é atribuído.**<br>Nesse cenário, o usuário está localizado em um site de rede configurado habilitado para roteamento do Location-Based e esse site não está associado ao gateway PSTN em que o número DID do usuário é atribuído. Por exemplo, o usuário viaja para outro escritório.  

- **O usuário está localizado em um site interno que não está habilitado para Location-Based Roteamento.** <br>Nesse cenário, o usuário está localizado em um site de rede configurado que não está habilitado para Location-Based Roteamento. 

- **O usuário está localizado em um site desconhecido.** 
    - O usuário está localizado dentro da rede interna que não está definida como um site de rede. 
    - O usuário está localizado fora da rede interna. Por exemplo, o usuário está na Internet em casa ou em uma cafeteria. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Aplicar Location-Based roteamento no site de rede 

Quando os usuários habilitados para o Location-Based roteamento estão em roaming, os sites de rede habilitados para o roteamento Location-Based ajudarão a determinar quais gateways usar. Por exemplo:

- Se um usuário habilitado para o roteamento do Location-Based for movido para um site habilitado para roteamento do Location-Based, somente o gateway PSTN habilitado para roteamento do Location-Based nesse site poderá ser usado para chamadas de saída. 

- Se um usuário habilitado para o roteamento do Location-Based for movido para um site que não esteja habilitado para roteamento do Location-Based, qualquer gateway que não esteja habilitado para roteamento do Location-Based poderá ser usado para chamadas de saída.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Aplicar Location-Based roteamento no gateway PSTN  

Para aplicar Location-Based roteamento no gateway PSTN, você deve fazer o seguinte:

- Habilite o gateway para Location-Based roteamento. (Os gateways devem ser habilitados para Location-Based roteamento para garantir que eles não possam ser usados por usuários que não estão habilitados para Location-Based Roteamento.)

- Atribua um site de rede ao gateway.

Em seguida, o sistema determina se um determinado usuário em um determinado site tem permissão para usar o gateway. 

Além disso, se você definir o GatewayLbrEnabledUserOverride como True, os usuários habilitados para roteamento baseado em localização em sites desconhecidos, por exemplo, os usuários que trabalham em casa, poderão fazer chamadas PSTN de saída.


## <a name="restriction-rules"></a>Regras de restrição

As regras de restrição dependem se um Teams usuário está ou não habilitado para Location-Based roteamento.

### <a name="user-is-enabled-for-location-based-routing"></a>O usuário está habilitado para roteamento Location-Based usuário

Quando um usuário está habilitado para Location-Based roteamento, o seguinte se aplica:

- **Para fazer uma chamada PSTN** de saída, uma das seguintes ações deve ser verdadeira:

  - O ponto de extremidade do usuário está localizado em um site habilitado para Roteamento do Location-Based e chama a saída por meio de um gateway PSTN habilitado para roteamento Location-Based no mesmo site.  

  - O ponto de extremidade do usuário está localizado em um site desconhecido e chama a saída por meio de um gateway PSTN habilitado para Location-Based Roteamento. O gateway PSTN é configurado com o parâmetro GatewayLbrEnabledUserOverride definido como True.

  - O ponto de extremidade do usuário está localizado em um site que não está habilitado para Roteamento do Location-Based e chama a saída por meio de um gateway PSTN que não está habilitado para roteamento Location-Based.

- **Para receber uma chamada PSTN de entrada**, uma das seguintes ações deve ser verdadeira: 

   - O ponto de extremidade de resposta do usuário e o gateway PSTN pelo qual a entrada de chamada deve estar localizado no mesmo site que está habilitado para Location-Based Roteamento. O gateway PSTN deve ser habilitado para Location-Based Roteamento.

   - O ponto de extremidade de atendimento do usuário e o gateway PSTN pelo qual a chamada é feita devem estar localizados no mesmo site que não está habilitado para o Location-Based Roteamento. O gateway PSTN não deve ser habilitado para o Location-Based Roteamento.  (Esse cenário envolve rotear novamente a chamada PSTN de entrada para entrada, embora outro gateway PSTN que normalmente seja usado para chamadas de entrada para o número de telefone do usuário.)

   - Em qualquer outro cenário, como se o usuário estiver em roaming, a chamada não é permitida e é roteada para as configurações de encaminhamento de chamadas não respondidas do usuário (normalmente caixa postal).  
   
- **Para uma chamada VoIP 1:1 Teams transferência para PSTN**, observe o seguinte:

  - O roteamento da chamada, ou seja, qual gateway PSTN para saída da chamada é baseado nas configurações de roteamento do usuário que está transferindo a chamada.

  - Se a transferência será permitida se baseia no seguinte:
  
    - As Location-Based de roteamento do usuário que está sendo transferido para o PSTN.
    - O local do site de rede do ponto de extremidade.
    - Se a localização está habilitada para Location-Based Roteamento.

    A transferência será permitida se o usuário que está sendo transferido for capaz de fazer essa chamada PSTN em seu local atual usando o mesmo gateway PSTN.

- **Para uma chamada PSTN** de entrada ou saída e transferência para outro Teams usuário, se a transferência é permitida depende do seguinte:

   - As configurações de roteamento do usuário que está recebendo a chamada transferida. 
   - O local do site de rede do ponto de extremidade.
   - Se a localização está habilitada para Location-Based Roteamento.

   A transferência será permitida se a pessoa que recebe a chamada transferida for capaz de fazer ou receber essa chamada PSTN em seu local atual usando o gateway PSTN usado pela chamada PSTN em andamento.


### <a name="user-is-not-enabled-for-location-based-routing"></a>O usuário não está habilitado para roteamento Location-Based usuário

Quando um usuário Teams não está habilitado para roteamento do Location-Based, todas as chamadas desse usuário devem rotear por meio de um gateway PSTN que não esteja habilitado para roteamento Location-Based. Uma chamada de entrada para esse usuário roteada por meio de um gateway PSTN habilitado para Location-Based Roteamento será roteada para as configurações de encaminhamento de chamadas não respondidas do usuário (normalmente caixa postal).

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>Fluxos de decisão para chamadas de entrada e saída

Os diagramas a seguir mostram os fluxos de decisão para chamadas de entrada e saída.

**Chamadas de entrada**

![Diagrama mostrando LBR para chamadas de entrada](media/lbr-routing-inbound1.png "Diagrama mostrando cenários para o Location-Based Roteamento")

**Chamadas de saída**

![Diagrama mostrando LBR para chamadas de saída](media/lbr-routing-outbound1.png "Diagrama mostrando cenários para o Location-Based Roteamento")


## <a name="scenarios-for-location-based-routing"></a>Cenários do Roteamento Baseado na Localização

Esta seção descreve diferentes cenários para restringir o bypass de chamada tarifada usando o Location-Based Roteamento. Os cenários comparam como as chamadas são roteados para usuários que não estão habilitados para roteamento de Location-Based com usuários habilitados para Location-Based Roteamento.

- [Teams usuário faz uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams usuário recebe uma chamada de entrada do PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams usuário transfere ou encaminha a chamada para outro Teams usuário](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams usuário transfere ou encaminha a chamada para o ponto de extremidade PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Toque simultâneo](#simultaneous-ringing)
- [Delegação](#delegation)

O diagrama a seguir mostra as restrições habilitadas pelo Location-Based roteamento em cada cenário. Usuários, sites de rede e gateways habilitados para o Location-Based roteamento têm uma borda ao redor deles. Use o diagrama como um guia para ajudá-lo a entender como Location-Based roteamento funciona em cada cenário.  

![Diagrama mostrando cenários de Location-Based Roteamento.](media/lbr-direct-routing.png "Diagrama mostrando cenários para o Location-Based Roteamento")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams usuário faz uma chamada de saída para o PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para roteamento de Location-Based pode fazer chamadas de saída usando qualquer gateway em qualquer site que não está habilitado para roteamento de Location-Based por meio de sua política de roteamento de voz atribuída. No entanto, se um gateway estiver habilitado para roteamento de Location-Based, o usuário não poderá fazer chamadas de saída por meio do gateway, mesmo se ele estiver atribuído à política de roteamento de voz. Se o usuário fizer roaming para um site habilitado para roteamento do Location-Based, ele só poderá fazer chamadas por meio de seus gateways de roteamento normais que não estão habilitados para roteamento Location-Based.
 
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

Em comparação, o roteamento de chamadas de saída para usuários habilitados para Location-Based roteamento é afetado pelo local de rede do ponto de extremidade do usuário. A tabela a seguir mostra como Location-Based roteamento afeta o roteamento de chamadas de saída de User1, dependendo da localização de User1. 

|Local do ponto de extremidade User1  |Roteamento de chamadas de saída para User1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para Location-Based roteamento (Site1)      |Chamada roteada por meio do gateway habilitado para o GW1 (roteamento de Location-Based) no Site1, com base na política de roteamento de voz do usuário         |
|Site diferente do local em que o DID do usuário é atribuído, site habilitado para Location-Based roteamento (Site2)    |Chamada roteada por meio do gateway que está habilitado para o GW2 (roteamento de Location-Based) em roam site2, com base na política de roteamento de voz do usuário        |
|Site diferente do local em que o DID do usuário é atribuído, o site não está habilitado para roteamento de Location-Based (Site3)  |Chamada roteada por meio do gateway que não está habilitada para o roteamento de Location-Based no site que não está habilitado para o GW3 (roteamento de Location-Based), com base na política de roteamento de voz do usuário       |
|Rede interna desconhecida (Local4)    |  A chamada PSTN não é permitida, a menos que o gateway tenha GatewayLbrEnabledUserOverride definido como True       |
|Rede externa desconhecida (Local5)    | A chamada PSTN não é permitida, a menos que o gateway tenha GatewayLbrEnabledUserOverride definido como True       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams usuário recebe uma chamada de entrada do PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para o roteamento do Location-Based pode receber uma chamada de entrada do gateway que não está habilitado para o roteamento Location-Based do qual suas ingresses de número DID atribuídas. Se o usuário faz roaming para um site que não está habilitado para roteamento Location-Based, ele ainda poderá receber chamadas por meio de seus gateways PSTN normais.
  
#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

Em comparação, os usuários habilitados para Location-Based Roteamento só podem receber chamadas de entrada do gateway PSTN ao qual seu DID é atribuído quando estão localizados no mesmo site. A tabela a seguir mostra como User1 recebe chamadas de entrada quando User1 é movido para locais de rede diferentes. Se a chamada não for roteada para o ponto de extremidade do usuário, ela irá para as configurações de encaminhamento de chamadas não respondidas do usuário, se as configurações forem definidas. Normalmente, as chamadas são encaminhadas para a caixa postal.  

|Local do ponto de extremidade User1  |Roteamento de chamadas de entrada para User1  |
|---------|---------|
|Mesmo site em que o DID do usuário é atribuído, site habilitado para Location-Based roteamento (Site1)   | Chamadas roteados para o ponto de extremidade de User1 no Site1        |
|Site diferente do local em que o DID do usuário é atribuído, site habilitado para Location-Based roteamento (Site2)    | Chamadas não roteados para pontos de extremidade no Site2        |
|Site diferente do local em que o DID do usuário é atribuído, o site não está habilitado para roteamento de Location-Based (Site3)    | Chamadas não roteados para pontos de extremidade no Site3        |
|Rede interna desconhecida (Local4)   | Chamadas não roteados para pontos de extremidade na Localização4        |
|Rede externa desconhecida (Local5)     | Chamadas não roteados para pontos de extremidade na Localização5        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams usuário transfere ou encaminha a chamada para outro Teams usuário

Quando um ponto de extremidade PSTN está envolvido, o roteamento do Location-Based analisa se um ou ambos os usuários estão habilitados para roteamento do Location-Based e determina se a chamada deve ser transferida ou encaminhada dependendo da localização de ambos os pontos de extremidade. 
 
A transferência de chamada exige que o usuário iniciador atenda a chamada enquanto o encaminhamento de chamadas não exige que a chamada inicial seja atendida. As chamadas podem ser encaminhadas mesmo que User1 não esteja em um local para receber chamadas de entrada (consulte a tabela no Teams o usuário recebe uma chamada de entrada da seção [PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)) e as chamadas não poderão ser transferidas se User1 não puder receber a chamada de entrada. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

Um usuário que não está habilitado para o Location-Based roteamento pode transferir ou encaminhar chamadas PSTN para outros usuários que não estão habilitados para o Location-Based Roteamento. Os usuários habilitados para Location-Based roteamento geralmente são colocalizados em gateways habilitados para Location-Based roteamento para chamadas PSTN. Consequentemente, os usuários que não estão habilitados não têm permissão para transferir ou encaminhar uma chamada PSTN para um usuário habilitado para Location-Based Roteamento. A exceção é quando um Location-Based usuário habilitado para Roteamento móvel para um site que não está habilitado para Location-Based Roteamento. Nesse cenário, a chamada transferida é permitida.  

Da mesma forma, um usuário que não está habilitado para o Location-Based Routing só pode receber uma transferência ou chamada PSTN encaminhada de outro usuário que não está habilitado para roteamento Location-Based. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

A transferência e o encaminhamento de chamadas PSTN de entrada de um gateway habilitado para o roteamento do Location-Based só será permitido se o usuário de destino estiver habilitado para roteamento Location-Based e estiver localizado no mesmo site. Caso contrário, a transferência e o encaminhamento de chamadas não são permitidos. 

A tabela a seguir mostra se o encaminhamento de chamadas e transferências de chamada são permitidos, dependendo do local do usuário de destino. Nesta tabela, User1, localizado no Site1, inicia a transferência ou encaminha para outros usuários do Teams que também estão habilitados para o roteamento Location-Based e que estão em locais diferentes.  

|Localização do ponto de extremidade do usuário de destino|User1 inicia a transferência de chamada |User1 inicia o encaminhamento de chamadas|
|---------|---------|---------|
|Mesmo site de rede que o iniciador (User2)|Permitido|Permitido|
|Site de rede diferente, site habilitado para Location-Based roteamento (Usuário3)|Não permitido|Não permitido|
|Site de rede diferente, site não habilitado para Location-Based roteamento (Usuário4)|Não permitido|Não permitido|
|Rede interna desconhecida (User5)| Não permitido|Não permitido|
|Rede externa desconhecida (User6)| Não permitido|Não permitido|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams usuário transfere ou encaminha a chamada para o ponto de extremidade PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Usuário não habilitado para roteamento Location-Based usuário

- É permitido transferir e encaminhar uma chamada PSTN para outro número PSTN. 

- Transferir e encaminhar uma chamada VOIP de entrada para o PSTN deve respeitar as restrições de bypass de chamada. 

    - Se o chamador não estiver habilitado para roteamento de Location-Based, ele poderá ser transferido para qualquer gateway PSTN que não esteja habilitado para Location-Based Roteamento.
    - Se o chamador estiver habilitado para roteamento Location-Based, ele só poderá ser transferido para um gateway habilitado para roteamento Location-Based localizado no mesmo site de rede. 

#### <a name="user-enabled-for-location-based-routing"></a>Usuário habilitado para roteamento Location-Based usuário

- Transferir e encaminhar uma chamada PSTN de entrada para outro número PSTN deve ser roteado para o mesmo gateway habilitado para roteamento Location-Based no qual a chamada de entrada chegou.

- Transferir e encaminhar uma chamada VOIP de entrada para o PSTN deve respeitar o chamador e as restrições de bypass de chamada do usuário. 

    - Se o chamador não estiver habilitado para roteamento de Location-Based, ele poderá ser transferido para qualquer gateway PSTN que não esteja habilitado para Location-Based Roteamento.

    - Se o chamador estiver habilitado para Location-Based roteamento, ele poderá ser transferido somente para um gateway habilitado para roteamento Location-Based localizado no mesmo site de rede.
 
A tabela a seguir mostra como o roteamento de Location-Based afeta o roteamento de uma chamada VOIP do Location-Based Routing habilitado para User1 no Site1 para usuários em locais diferentes que transferem ou encaminham a chamada para um ponto de extremidade PSTN.  

|Usuário iniciando a transferência ou encaminhamento de chamadas  |Transferir ou encaminhar para pSTN  |
|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based roteamento (User2)   |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User2 resultar em uma rota por meio do gateway1 habilitado para roteamento de Location-Based no Site1         |
|Site de rede diferente, site habilitado para Location-Based roteamento (Usuário3)    |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User3 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento1 no Site1 |
|Site de rede diferente, site não habilitado para Location-Based roteamento (Usuário4)    |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User4 resultar em uma rota por meio do gateway1 habilitado para roteamento Location-Based no Site1          |
|Rede interna desconhecida (User5)     |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User5 resultar em uma rota por meio do gateway1 habilitado para roteamento de Location-Based no Site1          |
|Rede externa desconhecida (User6)   |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User6 resultar em uma rota por meio do gateway1 habilitado para roteamento Location-Based no Site1          |

### <a name="simultaneous-ringing"></a>Toque simultâneo

Quando um usuário habilitado para o roteamento do Location-Based recebe uma chamada e tem toque simultâneo habilitado, o roteamento do Location-Based analisa o local da parte de chamada e os pontos de extremidade das partes chamadas para determinar se a chamada deve ser roteada. O toque simultâneo segue as mesmas Location-Based que as transferências de chamadas e encaminhamentos. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Toque simultâneo para outro Teams usuário

A tabela a seguir mostra se Location-Based roteamento permite toque simultâneo para diferentes usuários para uma chamada PSTN de entrada para User1.

|Localização do ponto de extremidade do usuário de destino|Anel simultâneo  |
|---------|---------|
|Mesmo site de rede que o iniciador (User2)   |Permitido         |
|Site de rede móvel diferente habilitado para Location-Based Roteamento (Usuário3)   |Não permitido         |
|Site de rede móvel não habilitado para roteamento Location-Based móvel (Usuário4)   |Não permitido        |
|Rede interna desconhecida (User5)    | Não permitido        |
|Rede externa desconhecida (User6)    |Não permitido        |
|O usuário de destino é um número PSTN    |A chamada só pode ser roteada por meio Location-Based Gateway1 habilitado para Roteamento no Site1, com base na política de roteamento de voz do User1      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Toque simultâneo para um ponto de extremidade PSTN

A tabela a seguir mostra Location-Based de roteamento para uma chamada VoIP de entrada do Location-Based Routing habilitado user1 localizado no Site1 para usuários em locais diferentes com anel simultâneo definido como um número PSTN. 

|Local do ponto de extremidade do usuário chamado  |O destino de anel simultâneo é o ponto de extremidade PSTN |
|---------|---------|
|Mesmo site de rede, site habilitado para Location-Based roteamento (User2)    |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User2 resultar em uma rota por meio do gateway1 habilitado para roteamento de Location-Based no Site1        |
|Site de rede diferente habilitado para Location-Based roteamento (Usuário3)    |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User3 resultar em uma rota por meio de Location-Based Gateway1 habilitado para Roteamento1 no Site1         |
|Site de rede diferente não habilitado para Location-Based roteamento (User4)    |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User4 resultar em uma rota por meio do gateway1 habilitado para roteamento Location-Based no Site1          |
|Rede interna desconhecida (User5)    |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User5 resultar em uma rota por meio do gateway1 habilitado para roteamento de Location-Based no Site1          |
|Rede externa desconhecida (User6)   |A chamada PSTN resultante será permitida somente se a rota calculada com base na política de roteamento de voz do User6 resultar em uma rota por meio do gateway1 habilitado para roteamento Location-Based no Site1          |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>Chamadas de entrada por meio de aplicativos de voz (Atendedor Automático ou Fila de Chamadas)

Chamadas PSTN de entrada de um gateway habilitado para roteamento Location-Based podem se conectar a um atendedor automático ou fila de chamadas. 

Os usuários habilitados para Location-Based Roteamento têm suporte para receber transferências de chamada de entrada para esses aplicativos quando estiverem localizados no mesmo site do qual a chamada PSTN de entrada se origina.
 
O encaminhamento de chamadas e toque simultâneo para usuários e PSTN são permitidos para transferências de aplicativo de voz. Concluir a chamada para o destino está sujeito às mesmas regras de Location-Based roteamento listadas anteriormente.  
 
O encaminhamento para a caixa postal também é permitido.  

### <a name="delegation"></a>Delegação

Um Teams usuário pode escolher representantes que podem fazer e receber chamadas em seu nome. Os recursos de delegação Teams são afetados pelo Location-Based roteamento da seguinte maneira: 

- Para chamadas de saída de Location-Based delegado habilitado para Roteamento em nome de um delegador, as mesmas regras se aplicam. O roteamento de chamadas é baseado na política de autorização de chamada do delegado, na política de roteamento de voz e no local. Para obter mais informações, [Teams usuário faz uma chamada de saída para o PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 

- Para chamadas PSTN de entrada para um delegador, as mesmas regras de roteamento Location-Based que se aplicam ao encaminhamento de chamadas ou ao toque simultâneo a outros usuários também se aplicam a delegados. Para obter mais informações, Teams usuário transfere ou encaminha [a chamada para](#teams-user-transfers-or-forwards-call-to-another-teams-user) outro usuário do Teams, o usuário do Teams transfere ou encaminha a chamada para o ponto de extremidade [PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint) e toque [simultâneo.](#simultaneous-ringing) Quando um delegado define um ponto de extremidade PSTN como um destino de anel simultâneo, a política de roteamento de voz do delegado é usada para rotear a chamada para o PSTN. 

- Para delegação, a Microsoft recomenda que o delegador e os delegados associados estejam localizados no mesmo site de rede. 

## <a name="other-planning-considerations"></a>Outras considerações de planejamento

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Alterações de uma implantação de roteamento Location-Based local

A política de roteamento de voz do site de rede não é mais usada. Em vez disso, usamos a política de roteamento de voz do usuário. Para permitir que os usuários usem roaming para outros sites, a política de roteamento de voz deve incluir os gateways dos sites móveis. 

### <a name="technical-considerations-for-location-based-routing"></a>Considerações técnicas para Roteamento Baseado em Local

As sub-redes IPv4 e IPv6 têm suporte, no entanto, o IPv6 tem precedência ao verificar uma correspondência.

### <a name="client-support-for-location-based-routing"></a>Suporte ao cliente para roteamento Location-Based cliente

Os seguintes Teams clientes têm suporte:
- Teams de área de trabalho (Windows e Mac)
- Teams clientes móveis (iOS e Android)
- Teams IP

Não há suporte Teams cliente Web Skype for Business clientes web.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Recursos não suportados pelo Roteamento Baseado em Local

Location-Based roteamento não se aplica aos seguintes tipos de interações. Location-Based roteamento não é imposto quando Teams de extremidade interagem com pontos de extremidade PSTN nos seguintes cenários: 

- Estacionamento de chamada ou recuperação de chamadas PSTN por meio do estacionamento de chamada 

- Um usuário de Skype for Business local ou um Skype for Business online chama um Teams usuário  

### <a name="location-based-routing-for-conferencing"></a>Location-Based roteamento para conferência

Um Location-Based usuário habilitado para Roteamento em uma chamada PSTN não tem permissão para iniciar uma conferência com outro usuário ou número PSTN. A conexão com atendedores automáticos ou filas de chamadas é permitida.

Se o usuário tiver uma licença de audioconferência, o usuário deverá iniciar uma conferência com os usuários relevantes e chamar o PSTN por meio da ponte de conferência para iniciar uma chamada em conferência.

Em uma chamada em conferência iniciada por um usuário sem uma licença de audioconferência, a adição de participantes PSTN não será permitida se houver ou tiver sido pelo menos um usuário habilitado para Roteamento Location-Based na chamada em conferência. Se pelo menos um participante PSTN fizer parte dessa chamada em conferência antes de qualquer participante habilitado para Roteamento do Location-Based ser convidado a ingressar na chamada, esses participantes habilitados para Roteamento do Location-Based não poderão ser adicionados à chamada.

Se o usuário habilitado para roteamento de Location-Based estiver ingressando na chamada de conferência de um site interno que não está habilitado para roteamento Location-Based, as restrições no parágrafo acima não serão impostas. 

A conferência em rede para Audioconferência não deve ser implantada com nenhum equipamento de telefonia na Índia.


### <a name="media-bypass-requirement-for-location-based-routing"></a>Requisito de bypass de mídia para Location-Based roteamento

Se você estiver implantando o Location-Based roteamento na Índia, também será necessário configurar o bypass de mídia. Para saber mais, confira Planejar o bypass [de mídia com Roteamento](direct-routing-plan-media-bypass.md) Direto e Otimização [de Mídia Local para Roteamento Direto](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>VoIP (Direct Voice over IP)

O VoIP (Direct Voice over IP) não deve ser implantado com nenhum equipamento de telefonia na Índia.


## <a name="related-articles"></a>Artigos relacionados

- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Configurações de rede para recursos de voz na nuvem Teams](cloud-voice-network-settings.md)
