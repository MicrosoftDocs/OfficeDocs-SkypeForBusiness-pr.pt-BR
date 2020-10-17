---
title: 'Lync Server 2013: Implantando regiões de rede, sites e sub-redes'
description: 'Lync Server 2013: Implantando regiões de rede, sites e sub-redes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1c4c08cd9b78b1439000cdb4a7bbe3ffc2f99d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561087"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Implantando regiões de rede, sites e sub-redes no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-12_

Após a implantação do Enterprise Voice, você precisará configurar:

  - Regiões de rede

  - Sites de rede

  - Sub-redes da rede

<div>

## <a name="define-network-regions"></a>Definir regiões de rede

Use o comando do Windows PowerShell do Lync Server, o New-CsNetworkRegion ou o painel de controle do Lync Server para definir as regiões de rede.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

Para obter mais informações, consulte [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).

Neste exemplo, o seguinte comando do Windows PowerShell ilustra a região de rede, a região 1 (Índia), definida neste cenário.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>Definir sites de rede

Use o comando do Lync Server Windows PowerShell, New-CsNetworkSite ou o painel de controle do Lync Server para definir sites de rede.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

Para obter mais informações, consulte [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).

Para este exemplo, a tabela a seguir e o comando do Windows PowerShell do Lync Server ilustram os sites de rede definidos neste cenário. Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site 1 (Déli)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID de site</p></td>
<td><p>Site 1 (Déli)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>ID de região</p></td>
<td><p>Região 1 (Índia)</p></td>
<td><p>Região 1 (Índia)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>Definir sub-redes de rede

Use o comando do Lync Server Windows PowerShell, New-CsNetworkSubnet ou o painel de controle do Lync Server para definir sub-redes de rede e atribuí-las aos sites de rede.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

Para obter mais informações, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

Neste exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram a atribuição de sub-redes de rede para os sites de rede, Delhi e Hyderabad, definidas neste cenário. Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site 1 (Déli)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID da sub-rede</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Máscara</p></td>
<td><p>dia</p></td>
<td><p>dia</p></td>
</tr>
<tr class="odd">
<td><p>ID de site</p></td>
<td><p>Site 1 (Déli)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando o roteamento de Location-Based no Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

