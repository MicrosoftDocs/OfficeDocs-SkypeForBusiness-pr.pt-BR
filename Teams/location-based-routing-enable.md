---
title: Habilitar o Roteamento baseado na localização para o Roteamento direto
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como habilitar o Location-Based roteamento direto, incluindo habilitá-lo para usuários, sites de rede, configurações de gateway e políticas de chamada.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: aadf5f4e4dff855d80c275be3d2027e767a732ad
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562190"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar o Roteamento baseado na localização para o Roteamento direto

Este artigo descreve como habilitar o Location-Based roteamento direto. Antes de seguir as etapas deste artigo, verifique se você leu o plano de [](location-based-routing-plan.md) Location-Based roteamento para roteamento direto e concluiu as etapas em Definir configurações de rede para Location-Based [Roteamento](location-based-routing-configure-network-settings.md).

 Depois de implantar o Roteamento Direto e configurar regiões de rede, sites e sub-redes, você estará pronto para habilitar o roteamento Location-Based rede. Para concluir as etapas neste artigo, você precisará de alguma familiaridade com cmdlets do PowerShell. Para saber mais, confira Visão [geral do Teams PowerShell](teams-powershell-overview.md)

 Você precisa habilitar o Location-Based roteamento para o seguinte:

- Usuários
- Sites de rede
- Configurações de gateway
- Políticas de chamadas

Você pode usar o Centro [de administração do Teams ou](#using-the-microsoft-teams-admin-center) [o PowerShell](#using-powershell) para habilitar o Location-Based Roteamento.

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

### <a name="enable-location-based-routing-for-users"></a>Habilitar Location-Based roteamento para usuários

1. Crie uma política de roteamento de voz e atribua usos de PSTN à política. Ao atribuir usos de PSTN a uma política, certifique-se de fazer um dos seguintes procedimentos:

    - Use os usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site.

    - Use os usos de PSTN associados a rotas de voz que usam um gateway PSTN localizado em uma região em que Location-Based restrições de roteamento não são necessárias.

2. Atribua a política de roteamento de voz aos usuários que exigem que as restrições de roteamento sejam impostas.

Para saber mais sobre como criar políticas de roteamento de voz e atribuí-las aos usuários, consulte Gerenciar políticas de roteamento [de voz no Microsoft Teams](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar Location-Based roteamento para sites de rede

Habilite Location-Based roteamento para seus sites que precisam impor restrições de roteamento. Para fazer isso, no painel de navegação esquerdo do centro de administração do Microsoft Teams,  >  vá para a **topologia** Rede de Locais, selecione um site de rede, clique em **Editar** e, em seguida, ative o roteamento baseado **em Localização**.  

Para saber mais, confira [Gerenciar sua topologia de rede](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>Habilitar Location-Based roteamento para gateways

Habilite Location-Based roteamento para gateways que roteiam chamadas para gateways PSTN que roteiam chamadas para o PSTN e associem o site de rede onde o gateway está localizado. 

1. No painel de navegação esquerdo, vá para **Roteamento Direto** > **de** Voz e clique na guia **SBCs** .

2. Selecione o SBC e clique em **Editar**. 

3. Em **Roteamento baseado em localização e otimização de mídia**, ative **Habilitar roteamento baseado em localização**.

4. Especifique a ID do site do gateway e defina o modo de bypass.

5. Clique em **Salvar**.

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar Location-Based roteamento para políticas de chamada

Para impor Location-Based roteamento para usuários específicos, configure a política de chamada do usuário para impedir o bypass de chamada tarifada PSTN. Para fazer isso, ative a **configuração Impedir bypass** de chamada na política de chamada.

Para saber mais, confira [Políticas de chamada no Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>Usando o Windows PowerShell

### <a name="enable-location-based-routing-for-users"></a>Habilitar Location-Based roteamento para usuários

1. Para definir usos de PSTN, use o cmdlet [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) . Para vários usos, separe cada uso com uma vírgula.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    Por exemplo:

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. Para criar uma política de roteamento de voz para associar o usuário ao uso PSTN apropriado, use o cmdlet [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Ao atribuir usos de PSTN a uma política de roteamento de voz, verifique se você fez um dos seguintes procedimentos:

    - Use os usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site.

    - Use os usos de PSTN associados a rotas de voz que usam um gateway PSTN localizado em uma região em que Location-Based restrições de roteamento não são necessárias.

    O exemplo a seguir cria duas novas políticas de roteamento de voz e atribui usos PSTN a elas. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    A tabela a seguir mostra as políticas de roteamento de voz definidas neste exemplo. 
    
    |&nbsp;|Política de roteamento de voz 1|Política de roteamento de voz 2|
    |---------|---------|---------|
    |ID da política de voz online   |Política de roteamento de voz online de Delhi   |Política de roteamento de voz online do Hyderabad    |
    |Usos de PSTN online  |Longa Distância  |Longa Distância, Local, Interno  |

3. Para associar políticas de roteamento de voz online a usuários que exigem que restrições de roteamento sejam impostas, use o cmdlet [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) .

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>Habilitar Location-Based roteamento para sites de rede

1. Para habilitar Location-Based roteamento de voz e associar políticas de roteamento de voz aos sites de rede que precisam impor restrições de roteamento, use o cmdlet [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) .

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    Este exemplo habilita Location-Based roteamento para o site de Delhi e o site do Hyderabad. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    A tabela a seguir mostra os sites habilitados para Location-Based roteamento neste exemplo.

    |&nbsp;|Site 1 (Delhi)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
    |Nome do site    |Site 1 (Delhi)    |Site 2 (Hyderabad)|
    |EnableLocationBasedRouting    |Verdadeiro    |Verdadeiro    |
    |Sub-redes     |Sub-rede 1 (Delhi)     |Sub-rede 2 (Hyderabad)     |


### <a name="enable-location-based-routing-for-gateways"></a>Habilitar Location-Based roteamento para gateways

1. Para criar uma configuração de gateway para cada gateway ou site de rede, use o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) . 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    Se vários gateways forem associados a um sistema (por exemplo, Gateway ou PBX), modifique cada gateway para habilitar Location-Based roteamento. 

    O exemplo a seguir cria uma configuração de gateway para cada gateway. 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    Para obter mais informações, consulte [Configurar Roteamento Direto](direct-routing-configure.md).
    
2. Para habilitar Location-Based roteamento para seus gateways que precisam impor restrições de roteamento, use o cmdlet [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) . 

    Habilite Location-Based roteamento para gateways que roteiam chamadas para gateways PSTN que roteiam chamadas para o PSTN e associem o site de rede onde o gateway está localizado.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   O exemplo a seguir permite Location-Based roteamento para cada gateway associado a gateways PSTN nos sites Delhi e Hyderabad. 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    Não habilite Location-Based roteamento para gateways que não roteiam chamadas para o PSTN. No entanto, você ainda precisa associar o gateway ao site de rede onde o sistema está localizado. Isso ocorre porque Location-Based restrições de roteamento precisam ser impostas para chamadas PSTN que atingem pontos de extremidade conectados por meio desse gateway. Neste exemplo, o Location-Based roteamento não está habilitado para cada gateway associado aos sistemas PBX nos sites Delhi e Hyderabad.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar Location-Based roteamento para políticas de chamada

Para impor Location-Based roteamento para usuários específicos, configure a política de voz dos usuários para impedir o bypass de chamada tarifada PTSN. 

Para habilitar Location-Based roteamento impedindo o bypass de chamada tarifada PSTN, use o cmdlet [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) .


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

Neste exemplo, evitamos o desvio de chamada PSTN para as políticas de chamada de User1. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>Tópicos relacionados

- [Configurações de rede para recursos de voz na nuvem no Teams](cloud-voice-network-settings.md)