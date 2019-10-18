---
title: Habilitar o Roteamento baseado na localização para o Roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como habilitar o roteamento baseado em local para roteamento direto.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4acd03dfff78d5aae329492014b24e55b2f92ec9
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572017"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar o Roteamento baseado na localização para o Roteamento direto

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Antes de seguir as etapas deste artigo, verifique se você leu o [roteamento baseado em local de plano para roteamento direto](location-based-routing-plan.md) e concluiu as etapas em [definir configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md).

Este artigo descreve como habilitar o roteamento baseado em localização para roteamento direto. Depois de implantar o roteamento direto do sistema telefônico e configurar regiões de rede, sites e sub-redes, você estará pronto para habilitar o roteamento baseado em localização. Para concluir as etapas deste artigo, você precisará de familiaridade com cmdlets do PowerShell. Para saber mais, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

 Você precisa ativar o roteamento baseado em local para o seguinte:
- Usuários
- Sites de rede
- Configurações de gateway
- Políticas de chamada

## <a name="enable-location-based-routing-for-users"></a>Habilitar roteamento baseado em local para usuários

1. Use o cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para definir usos de PSTN. Para vários usos, separe cada uso com uma vírgula.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Por exemplo:
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Use o cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para criar uma política de roteamento de voz para associar o usuário aos usos de PSTN apropriados.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Ao atribuir usos de PSTN a uma política de roteamento de voz, certifique-se de seguir um destes procedimentos:
    - Usar usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site
    - Use usos de PSTN associados a rotas de voz que usam um gateway PSTN localizado em uma região onde restrições de roteamento baseadas em localização não são necessárias.

    Neste exemplo, criamos duas novas políticas de roteamento de voz e atribuem usos de PSTN a elas. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    A tabela a seguir mostra as políticas de roteamento de voz definidas neste exemplo. 
    
    ||Política de roteamento de voz 1|Política de roteamento de voz 2|
    |---------|---------|---------|
    |ID da política de voz online   |Política de roteamento de voz online da Délhi   |Política de roteamento de voz do Hyderabad online    |
    |Usos de PSTN online  |Longa distância  |Longa distância, local, interna  |

3. Use o cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para associar políticas de roteamento de voz online aos usuários que precisam de restrições de roteamento para serem impostas.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Habilitar o roteamento baseado em local para sites de rede
1.  Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar o roteamento baseado em localização e associar políticas de roteamento de voz a seus sites de rede que precisam impor restrições de roteamento.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    Neste exemplo, habilitamos o roteamento baseado em local para o site de Delhi e o site do Hyderabad. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    A tabela a seguir mostra os sites habilitados para roteamento baseado em local neste exemplo.

    ||Site 1 (Déli)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
|Nome do site    |Site 1 (Déli)    |Site 2 (Hyderabad)   
    |EnableLocationBasedRouting    |Verdadeiro    |Verdadeiro    |
    |Sub-redes     |Sub-rede 1 (Déli)     |Sub-rede 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Habilitar roteamento baseado em local para gateways
1. Use o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para criar uma configuração de gateway para cada site de gateway ou de rede. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Se vários gateways estiverem associados a um sistema (por exemplo, gateway ou PBX), modifique cada gateway para habilitar as restrições de roteamento baseado em localização. 

    Neste exemplo, criamos uma configuração de gateway para cada gateway. 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md).
    
2. Use o cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar o roteamento baseado em localização para seus gateways que precisam impor restrições de roteamento. 

    Habilite o roteamento baseado em local para gateways que roteiam chamadas para gateways PSTN que roteiam chamadas para a PSTN e associe o site de rede onde o gateway está localizado.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    Neste exemplo, habilitamos o roteamento baseado em local para cada gateway associado a gateways PSTN nos sites Delhi e Hyderabad. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    Não habilite o roteamento baseado em localização para gateways que não roteiam chamadas para a PSTN. No entanto, você ainda precisa associar o gateway ao site de rede onde o sistema está localizado. Isso ocorre porque restrições de roteamento baseadas em local precisam ser impostas para que chamadas PSTN atinjam pontos de extremidade conectados por meio desse gateway. Neste exemplo, o roteamento baseado em localização não está habilitado para cada gateway associado a sistemas PBX nos sites Delhi e Hyderabad.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Os pontos de extremidade conectados a sistemas que não roteiam chamadas para a PSTN (por exemplo, um PBX) terão restrições semelhantes aos pontos de extremidade de usuários do teams habilitados para roteamento baseado em local. Isso significa que esses usuários podem fazer e receber chamadas para e de usuários do teams independentemente da localização do usuário. Eles também podem fazer e receber chamadas de e para outros sistemas que não roteiam chamadas para a rede PSTN (por exemplo, um ponto de extremidade conectado a um PBX diferente), independentemente do site de rede ao qual o sistema está associado. Todas as chamadas recebidas, chamadas de saída, transferências de chamadas e encaminhamento de chamadas que envolvem pontos de extremidade PSTN estarão sujeitas a imposição de roteamento baseado em localização. Essas chamadas devem usar somente gateways PSTN definidos como locais para tais sistemas. 

    A tabela a seguir mostra a configuração de gateway de quatro gateways em dois locais de rede diferentes: dois conectados a gateways PSTN e dois conectados a sistemas PBX. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway: gateway 1 DEL-GW    |    Verdadeiro     |   Site 1 (Déli)      |
    |PstnGateway: gateway 2 HYD-GW     |   Verdadeiro      |      Site 2 (Hyderabad)   |
    |PstnGateway: gateway 3 DEL-PBX    |    False     |     Site 1 (Déli)    |
    |PstnGateway: gateway 4 HYD-PBX    |    False     |    Site 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar roteamento baseado em local para políticas de chamadas

Para impor o roteamento baseado em localização para usuários específicos, configure a política de voz dos usuários para impedir o PTSN de chamada tarifada. 

Use o cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar o roteamento baseado em localização impedindo o bypass de chamada PSTN PSTN.

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
Neste exemplo, impedimos que a chamada em PSTN seja ignorada para políticas de chamada User1's. 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Tópicos relacionados
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Terminologia do Roteamento baseado na localização](location-based-routing-terminology.md)
