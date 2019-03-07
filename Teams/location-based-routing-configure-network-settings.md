---
title: Configurar definições de rede para o Roteamento baseado na localização
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para roteamento baseado no local para roteamento direto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67202207b5668022f4e0b33acc2d20f3c4abd7aa
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462704"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurar definições de rede para o Roteamento baseado na localização

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Se você ainda não tiver feito isso, leia [Plan_Location-Based roteamento para roteamento direto](location-based-routing-plan.md) para revisar outras etapas que você precisará levar antes de implantar as configurações de rede para roteamento baseado no local.

Este artigo descreve como definir as configurações de rede para roteamento baseado no local. Depois de implantar roteamento direto de sistema do telefone na sua organização, as próximas etapas são para criar e configurar as regiões de rede, sites de rede e sub-redes da rede. Para concluir as etapas neste artigo, você precisará de familiaridade com os cmdlets do PowerShell. Para saber mais, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Definir regiões de rede
 Uma região de rede interconexão várias partes de uma rede de várias áreas geográficas. Use o ``New-CsTenantNetworkRegion`` cmdlet do PowerShell para definir regiões de rede. Observe que o ``RegionID`` parâmetro é um nome lógico que representa a geografia da região e não tem dependências ou restrições e o ``CentralSite <site ID>`` parâmetro é opcional. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Neste exemplo, criamos uma região de rede denominada Índia. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Definir os sites de rede

Use o ``New-CsTenantNetworkSite`` cmdlet do PowerShell para definir os sites de rede. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
Neste exemplo, criamos dois novos sites de rede, Délhi e Hyderabad, na região Índia. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
A tabela a seguir mostra os sites de rede definidos neste exemplo. 

||Site 1 |Site 2 |
|---------|---------|---------|
|ID do site    |    1 (Délhi) do site     |  Site 2 (Hyderabad)       |
|ID de região  |     Região 1 (Índia)    |   Região 1 (Índia)      |

## <a name="define-network-subnets"></a>Definir subredes

Use o ``New-CsTenantNetworkSubnet`` cmdlet para definir subredes e associá-los aos sites de rede. Cada sub-rede interna só pode ser associado um site. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
Neste exemplo, criamos uma associação entre a sub-rede 192.168.0.0 e o site de rede Délhi e entre sub-rede 192.168.1.0 e o site de rede de Hyderabad.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
A tabela a seguir mostra as sub-redes definidas neste exemplo. 

||Site 1 |Site 2 |
|---------|---------|---------|
|ID de sub-rede   |    192.168.0.0     |  192.168.1.0     |
|Máscara  |     24    |   24      |
|ID do site  | Site (Délhi) | Site 2 (Hyderabad) |

Para várias sub-redes, você pode importar um arquivo CSV usando um script como o seguinte.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
Neste exemplo, o arquivo CSV é parecido com isto:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Definir as sub-redes externas
Use o ``New-CsTenantTrustedIPAddress`` cmdlet para definir as sub-redes externas e atribuí-las ao inquilino. Você pode definir um número ilimitado de sub-redes para um inquilino. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Por exemplo:
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Próximas etapas
Vá para [Habilitar o roteamento baseado no local para roteamento direto](location-based-routing-enable.md).

### <a name="related-topics"></a>Tópicos relacionados
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Terminologia do Roteamento baseado na localização](location-based-routing-terminology.md)
