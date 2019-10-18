---
title: Configurar definições de rede para o Roteamento baseado na localização
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para roteamento baseado em local para roteamento direto.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240bbce48452edf505a61830891d0fcd6a6d199d
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570694"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurar definições de rede para o Roteamento baseado na localização

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Se ainda não tiver feito isso, leia [roteamento baseado em local de plano para roteamento direto](location-based-routing-plan.md) para revisar outras etapas que você precisará tomar antes de definir as configurações de rede para roteamento baseado em local.

Este artigo descreve como definir as configurações de rede para roteamento baseado em local. Depois de implantar o roteamento direto do sistema telefônico em sua organização, as próximas etapas são criar e configurar regiões de rede, sites de rede e sub-redes de rede. Para concluir as etapas deste artigo, você precisará de familiaridade com cmdlets do PowerShell. Para saber mais, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).

## <a name="define-network-regions"></a>Definir regiões de rede
 Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas. Use o cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) para definir regiões de rede. Observe que o parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições e o parâmetro &lt;de ID&gt; de site do CentralSite é opcional. 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

Neste exemplo, criamos uma região de rede chamada Índia. 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a>Definir sites de rede

Use o cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sites de rede. 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
Neste exemplo, criamos dois novos sites de rede, Delhi e Hyderabad, na região da Índia. 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
A tabela a seguir mostra os sites de rede definidos neste exemplo. 

||Site 1 |Site 2 |
|---------|---------|---------|
|ID do site    |    Site 1 (Déli)     |  Site 2 (Hyderabad)       |
|ID da região  |     Região 1 (Índia)    |   Região 1 (Índia)      |

## <a name="define-network-subnets"></a>Definir sub-redes de rede

Use o cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir sub-redes de rede e associá-las a sites de rede. Cada sub-rede interna só pode ser associada a um site. 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
Neste exemplo, criamos uma associação entre a sub-rede 192.168.0.0 e o site de rede de Délhi e entre a sub-rede 2001:4898: E8:25:844e: 926f: 85ad: dd8e e o site de rede do Hyderabad.
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
A tabela a seguir mostra as sub-redes definidas neste exemplo. 

||Site 1 |Site 2 |
|---------|---------|---------|
|ID de sub-rede   |    192.168.0.0     |  2001:4898: E8:25:844e: 926f: 85ad: dd8e     |
|Remoção  |     24    |   120      |
|ID do site  | Site (Delhi) | Site 2 (Hyderabad) |

Para várias sub-redes, você pode importar um arquivo CSV usando um script como o seguinte.
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
Neste exemplo, o arquivo CSV tem a seguinte aparência:
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a>Definir sub-redes externas
Use o cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir sub-redes externas e atribuí-las ao locatário. Você pode definir um número ilimitado de sub-redes para um locatário. 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
Por exemplo:
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a>Próximas etapas
Vá para [habilitar o roteamento baseado em local para roteamento direto](location-based-routing-enable.md).

### <a name="related-topics"></a>Tópicos relacionados
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Terminologia do Roteamento baseado na localização](location-based-routing-terminology.md)
