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
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="67861-103">Implantando regiões de rede, sites e sub-redes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67861-103">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67861-104">_**Última modificação do tópico:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="67861-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="67861-105">Após a implantação do Enterprise Voice, você precisará configurar:</span><span class="sxs-lookup"><span data-stu-id="67861-105">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="67861-106">Regiões de rede</span><span class="sxs-lookup"><span data-stu-id="67861-106">Network regions</span></span>

  - <span data-ttu-id="67861-107">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="67861-107">Network sites</span></span>

  - <span data-ttu-id="67861-108">Sub-redes da rede</span><span class="sxs-lookup"><span data-stu-id="67861-108">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="67861-109">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="67861-109">Define Network Regions</span></span>

<span data-ttu-id="67861-110">Use o comando do Windows PowerShell do Lync Server, o New-CsNetworkRegion ou o painel de controle do Lync Server para definir as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="67861-110">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="67861-111">Para obter mais informações, consulte [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="67861-111">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="67861-112">Neste exemplo, o seguinte comando do Windows PowerShell ilustra a região de rede, a região 1 (Índia), definida neste cenário.</span><span class="sxs-lookup"><span data-stu-id="67861-112">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="67861-113">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="67861-113">Define Network Sites</span></span>

<span data-ttu-id="67861-114">Use o comando do Lync Server Windows PowerShell, New-CsNetworkSite ou o painel de controle do Lync Server para definir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="67861-114">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="67861-115">Para obter mais informações, consulte [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="67861-115">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="67861-116">Para este exemplo, a tabela a seguir e o comando do Windows PowerShell do Lync Server ilustram os sites de rede definidos neste cenário.</span><span class="sxs-lookup"><span data-stu-id="67861-116">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="67861-117">Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="67861-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="67861-118">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="67861-118">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="67861-119">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="67861-119">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67861-120">ID de site</span><span class="sxs-lookup"><span data-stu-id="67861-120">Site ID</span></span></p></td>
<td><p><span data-ttu-id="67861-121">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="67861-121">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="67861-122">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="67861-122">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67861-123">ID de região</span><span class="sxs-lookup"><span data-stu-id="67861-123">Region ID</span></span></p></td>
<td><p><span data-ttu-id="67861-124">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="67861-124">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="67861-125">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="67861-125">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="67861-126">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="67861-126">Define Network Subnets</span></span>

<span data-ttu-id="67861-127">Use o comando do Lync Server Windows PowerShell, New-CsNetworkSubnet ou o painel de controle do Lync Server para definir sub-redes de rede e atribuí-las aos sites de rede.</span><span class="sxs-lookup"><span data-stu-id="67861-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="67861-128">Para obter mais informações, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="67861-128">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="67861-129">Neste exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram a atribuição de sub-redes de rede para os sites de rede, Delhi e Hyderabad, definidas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="67861-129">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="67861-130">Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="67861-130">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="67861-131">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="67861-131">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="67861-132">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="67861-132">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67861-133">ID da sub-rede</span><span class="sxs-lookup"><span data-stu-id="67861-133">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="67861-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="67861-134">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="67861-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="67861-135">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67861-136">Máscara</span><span class="sxs-lookup"><span data-stu-id="67861-136">Mask</span></span></p></td>
<td><p><span data-ttu-id="67861-137">dia</span><span class="sxs-lookup"><span data-stu-id="67861-137">24</span></span></p></td>
<td><p><span data-ttu-id="67861-138">dia</span><span class="sxs-lookup"><span data-stu-id="67861-138">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67861-139">ID de site</span><span class="sxs-lookup"><span data-stu-id="67861-139">Site ID</span></span></p></td>
<td><p><span data-ttu-id="67861-140">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="67861-140">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="67861-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="67861-141">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67861-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="67861-142">See Also</span></span>


[<span data-ttu-id="67861-143">Configurando o roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67861-143">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

