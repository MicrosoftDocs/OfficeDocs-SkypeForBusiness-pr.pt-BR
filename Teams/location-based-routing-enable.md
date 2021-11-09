---
title: Habilitar o Roteamento baseado na localização para o Roteamento direto
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como habilitar Location-Based roteamento direto, incluindo habilita-lo para usuários, sites de rede, configurações de gateway e políticas de chamada.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 750c20367c5710054d2b19d266ff9dc70f46edd9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829615"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar o Roteamento baseado na localização para o Roteamento direto

Antes de seguir as etapas deste artigo, certifique-se de ler [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) e concluir as etapas em Configure network [settings for Location-Based Routing](location-based-routing-configure-network-settings.md).

Este artigo descreve como habilitar o roteamento Location-Based roteamento direto. Depois de implantar Sistema de Telefonia Roteamento Direto e configurar regiões de rede, sites e sub-redes, você estará pronto para habilitar Location-Based Roteamento. Para concluir as etapas deste artigo, você precisará de alguma familiaridade com cmdlets do PowerShell. Para saber mais, consulte [Teams Visão Geral do PowerShell.](teams-powershell-overview.md)

 Você precisa habilitar Location-Based roteamento para o seguinte:
- Usuários
- Sites de rede
- Configurações de gateway
- Políticas de chamadas

Você pode usar o Microsoft Teams [de administração](#using-the-microsoft-teams-admin-center) ou [o PowerShel](#using-powershell)l para habilitar Location-Based Routing.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Habilitar Location-Based roteamento para usuários

1. Crie uma política de roteamento de voz e atribua usos PSTN à política. Ao atribuir usos de PSTN a uma política, certifique-se de fazer um dos seguintes:

    - Use usos PSTN associados a rotas de voz que usam um gateway PSTN local para o site.
    - Use os usos PSTN associados Location-Based a rotas de voz que usam um gateway PSTN localizado em uma região onde as restrições de roteamento não são necessárias.
2. Atribua a política de roteamento de voz aos usuários que exigem que as restrições de roteamento sejam impostas.

Para saber mais sobre como criar políticas de roteamento de voz e atribuí-las aos usuários, consulte [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar Location-Based roteamento para sites de rede

Habilitar Location-Based roteamento para seus sites que precisam impor restrições de roteamento. Para fazer isso, na navegação à esquerda do centro de administração Microsoft Teams, vá para **Localizações** Topologia de rede, selecione um site de rede, clique em Editar e, em seguida, acionar o roteamento baseado em  >   **Local.**   

Para saber mais, confira [Gerenciar sua topologia de rede.](manage-your-network-topology.md)

### <a name="enable-location-based-routing-for-gateways"></a>Habilitar Location-Based roteamento para gateways

Habilita Location-Based roteamento para gateways que roteiam chamadas para gateways PSTN que roteiam chamadas para a PSTN e associem o site de rede onde o gateway está localizado. 

1. Na navegação à esquerda, vá para **Roteamento Direto** de  >  Voz e clique na guia **SBCs.**
2. Selecione o SBC e clique em **Editar**. 
3. Em **Roteamento baseado em local e otimização de mídia,** ative **Habilitar roteamento baseado em local.**
4. Especifique a ID do site do gateway e, em seguida, de definir o modo de bypass.
5. Clique em **Salvar**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar Location-Based roteamento para políticas de chamada

Para impor Location-Based roteamento para usuários específicos, configurar a política de chamada do usuário para impedir o desvio de chamada de PSTN. Para fazer isso, a turn on the **Prevent toll bypass** setting in the calling policy.

Para saber mais, confira [Políticas de chamada em Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Usando o Windows PowerShell

### <a name="enable-location-based-routing-for-users"></a>Habilitar Location-Based roteamento para usuários

1. Use o cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para definir usos PSTN. Para vários usos, separe cada uso com uma vírgula.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Por exemplo:
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Use o cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para criar uma política de roteamento de voz para associar o usuário aos usos PSTN apropriados.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Ao atribuir usos PSTN a uma política de roteamento de voz, certifique-se de fazer um dos seguintes:
    - Usar usos PSTN associados a rotas de voz que usam um gateway PSTN local para o site
    - Use os usos PSTN associados Location-Based a rotas de voz que usam um gateway PSTN localizado em uma região onde as restrições de roteamento não são necessárias.

    Neste exemplo, criamos duas novas políticas de roteamento de voz e atribuímos usos PSTN a elas. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    A tabela a seguir mostra as políticas de roteamento de voz definidas neste exemplo. 
    
    |&nbsp;|Política de roteamento de voz 1|Política de roteamento de voz 2|
    |---------|---------|---------|
    |ID da política de voz online   |Política de roteamento de voz online de Délhi   |Política de roteamento de voz online do Hyderabad    |
    |Usos de PSTN online  |Long Distance  |Long Distance, Local, Internal  |

3. Use o cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para associar políticas de roteamento de voz online aos usuários que exigem restrições de roteamento a serem impostas.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar Location-Based roteamento para sites de rede

1.  Use o cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar Location-Based roteamento de voz e associar políticas de roteamento de voz aos sites de rede que precisam impor restrições de roteamento.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    Neste exemplo, habilitamos Location-Based roteamento para o site de Deli e o site do Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    A tabela a seguir mostra os sites habilitados para Location-Based Roteamento neste exemplo.

    |&nbsp;|Site 1 (Deli)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
    |Nome do site    |Site 1 (Deli)    |Site 2 (Hyderabad)|
    |EnableLocationBasedRouting    |Verdadeiro    |Verdadeiro    |
    |Sub-redes     |Sub-rede 1 (Deli)     |Sub-rede 2 (Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>Habilitar Location-Based roteamento para gateways

1. Use o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para criar uma configuração de gateway para cada gateway ou site de rede. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    Se vários gateways estão associados a um sistema (por exemplo, Gateway ou PBX), modifique cada gateway para habilitar Location-Based restrições de roteamento. 

    Neste exemplo, criamos uma configuração de gateway para cada gateway. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Para obter mais informações, consulte [Configure Direct Routing](direct-routing-configure.md).
    
2. Use o cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar Location-Based roteamento para seus gateways que precisam impor restrições de roteamento. 

    Habilita Location-Based roteamento para gateways que roteiam chamadas para gateways PSTN que roteiam chamadas para a PSTN e associem o site de rede onde o gateway está localizado.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    Neste exemplo, habilitamos Location-Based roteamento para cada gateway associado a gateways PSTN nos sites Delhi e Delhi e Debad. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    Não habilita o Location-Based roteamento para gateways que não encaminham chamadas para a PSTN. No entanto, você ainda precisa associar o gateway ao site de rede onde o sistema está localizado. Isso porque Location-Based restrições de roteamento precisam ser impostas para chamadas PSTN atingindo pontos de extremidade que estão conectados por meio desse gateway. Neste exemplo, Location-Based Roteamento não está habilitado para cada gateway associado aos sistemas PBX nos sites Delhi e Delhi e Debad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar Location-Based roteamento para políticas de chamada

Para impor Location-Based roteamento para usuários específicos, configurar a política de voz dos usuários para impedir o desvio de tarifa de PTSN. 

Use o cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar Location-Based roteamento impedindo o desvio de chamada de PSTN.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
Neste exemplo, evitamos o desvio de chamada PSTN para as políticas de chamada do Usuário1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de rede para recursos de voz na nuvem Teams](cloud-voice-network-settings.md)