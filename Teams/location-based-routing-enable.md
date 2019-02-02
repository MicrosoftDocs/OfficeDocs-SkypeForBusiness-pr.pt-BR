---
title: Habilitar o roteamento baseado no local para roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Aprenda a habilitar o roteamento baseado no local para roteamento direto.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3468b413fedc5d3e24871a632f50b5d58c7c5467
ms.sourcegitcommit: 9f767b48e5f0eaf43869cba9c42ba3ba3225bcf6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2019
ms.locfileid: "29715449"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>Habilitar o roteamento baseado no local para roteamento direto

Antes de seguir as etapas neste artigo, verifique se você tiver ler [Plan Location-Based roteamento para roteamento direto](location-based-routing-plan.md) e concluir as etapas em [definir configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md).

Este artigo descreve como habilitar o roteamento baseado no local para roteamento direto. Depois de implantar o roteamento direto de sistema do telefone e configurar regiões de rede, sites e sub-redes, você está pronto para habilitar o roteamento baseado no local. Para concluir as etapas neste artigo, você precisará de familiaridade com os cmdlets do PowerShell. Para saber mais, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).

 Você precisa habilitar o roteamento baseado no local para o seguinte:
- Usuários
- Sites de rede
- Configurações de gateway
- Políticas de chamada

## <a name="enable-location-based-routing-for-users"></a>Habilitar o roteamento baseado no local para usuários

1. Use o ``Set-CsOnlinPstnUsages`` cmdlet para definir os usos da PSTN. Para vários usos, separe cada uso com uma vírgula.

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    Por exemplo:
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. Use o ``New-CsOnlineVoiceRoutingPolicy`` cmdlet para criar uma política de roteamento de voz para associar o usuário os usos da PSTN apropriados.

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    Quando você atribui usos da PSTN a uma política de roteamento de voz, não deixe de que fazer um destes procedimentos:
    - Use os usos de PSTN associados às rotas de voz que usam um gateway PSTN local para o site
    - Use os usos de PSTN associados às rotas de voz que usam um gateway PSTN localizado em uma área onde as restrições de roteamento baseado no local não são necessários.

    Neste exemplo, criamos duas novas políticas de roteamento de voz e atribuir os usos da PSTN a eles. 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    A tabela a seguir mostra as políticas de roteamento de voz definidas neste exemplo. 
    
    ||1 política de roteamento de voz|2 de política de roteamento de voz|
    |---------|---------|---------|
    |ID da política de voz   |Política de roteamento de voz Délhi   |Política de roteamento de voz de Hyderabad    |
    |Usos da PSTN online  |Interurbano  |Interurbano, Local, interno  |

    Para obter mais informações, consulte [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).
3. Use o ``Grant-CsOnlineVoiceRoutingPolicy`` políticas de roteamento aos usuários que precisam ser impostas restrições de roteamento de voz de cmdlet para associar online.
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>Habilitar o roteamento baseado no local para sites de rede
1.  Use o ``Set-CsTenantNetworkSite`` cmdlet para habilitar o roteamento baseado no local e associar as políticas de roteamento para os locais de rede que precisam para impor restrições de roteamento de voz.
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -OnlineVoiceRoutingPolicy <voice routing policy ID> 
    ```

    Neste exemplo, podemos habilitar roteamento baseado no local para o site de Délhi e local de Hyderabad. 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "DelhiVoiceRoutingPolicy" 
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "HyderabadVoiceRoutingPolicy" 
    ```
    A tabela a seguir mostra os sites habilitados para roteamento baseados em local neste exemplo.

    ||1 (Délhi) do site  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
    |EnableLocationBasedRouting    |True    |True    |
    |Política de roteamento de voz    | Política de roteamento de voz Délhi       |Política de roteamento de voz de Hyderabad    |
    |Sub-redes     |Subrede 1 (Délhi)     |Subrede 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>Habilitar o roteamento baseado no local para gateways
1. Use o ``New-CsOnlinePstnGateway`` cmdlet para criar uma configuração de gateway para cada site de rede ou gateway. 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    Se vários gateways são associados um sistema (por exemplo, o Gateway ou PBX), modifique cada gateway para habilitar as restrições de roteamento baseados em local. 

    Neste exemplo, criamos uma configuração de gateway para cada gateway. 
    ```
    New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md).
    
2. Use o ``Set-CSOnlinePSTNGateway`` cmdlet para habilitar o roteamento baseado no local para seus gateways que precisam para impor restrições de roteamento. 

    Habilitar o roteamento baseado no local para os gateways que roteiem as chamadas para os gateways PSTN que rotear as chamadas para a PSTN e associe o site de rede onde se encontra o gateway.

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    Neste exemplo, podemos habilitar roteamento baseado no local para cada gateway associado aos gateways PSTN nos sites Délhi e Hyderabad. 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    Não habilite o roteamento baseado no local para gateways que não encaminhar chamadas para o PSTN. No entanto, você ainda precisará associe o gateway para o site de rede em que o sistema está localizado. Isso ocorre porque as restrições de roteamento baseados em local precisam ser impostas para chamadas PSTN está atingindo pontos de extremidade que estão conectados por meio deste gateway. Neste exemplo, roteamento baseado no local não está habilitado para cada gateway associado aos sistemas de PBX nos sites Délhi e Hyderabad.

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    Pontos de extremidade conectados aos sistemas que não encaminhar chamadas para a PSTN (por exemplo, um PBX) terá restrições semelhantes como pontos de extremidade dos usuários de equipes habilitados para roteamento baseado no local. Isso significa que esses usuários podem fazer e receber chamadas de e para usuários de equipes, independentemente do local do usuário. Eles também podem fazer e receber chamadas de outros sistemas que não rotear as chamadas para a rede PSTN (por exemplo, um ponto de extremidade conectado a um PBX diferente) independentemente do site de rede aos quais o sistema está associado. Todas as chamadas de entrada, chamadas de saída, transferências de chamada e o encaminhamento de chamadas que envolvem pontos de extremidade PSTN estará sujeito aplicações de roteamento baseados em local. Essas chamadas devem usar somente os gateways PSTN que são definidos como local para tais sistemas. 

    A tabela a seguir mostra a configuração do gateway de quatro gateways em dois sites de rede diferente: dois conectados aos gateways PSTN e dois conectados aos sistemas de PBX. 

    ||GatewaySiteLbrEnabled   |NetworkSiteID  |
    |---------|---------|---------|
    |DEL PstnGateway:Gateway 1-GW    |    True     |   1 (Délhi) do site      |
    |PstnGateway:Gateway 2 HYD-GW     |   True      |      Site 2 (Hyderabad)   |
    |PBX DEL PstnGateway:Gateway 3    |    True     |     1 (Délhi) do site    |
    |PBX HYD PstnGateway:Gateway 4    |    True     |    Site 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>Habilitar o roteamento baseado no local para chamar políticas

Para impor o roteamento baseado no local para usuários específicos, configurar a política de voz dos usuários para evitar que as tarifas PTSN desvio. 

Use o ``Grant-TeamsCallingPolicy`` o desvio de cmdlet para habilitar o roteamento baseado em local, impedindo a execução de tarifas PSTN.

```
Grant-TeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
Neste exemplo, podemos impedir PSTN Chamada Tarifada desvio do Usuário1 chamar políticas. 

```
Grant-TeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a>Tópicos relacionados
- [Planejar o roteamento baseado no local para roteamento direto](location-based-routing-plan.md)
- [Definir configurações de rede para roteamento baseado no local](location-based-routing-configure-network-settings.md)
- [Terminologia de roteamento baseados em local](location-based-routing-terminology.md)