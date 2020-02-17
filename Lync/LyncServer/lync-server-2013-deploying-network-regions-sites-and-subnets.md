---
title: 'Lync Server 2013: Implantando regiões de rede, sites e sub-redes'
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
ms.openlocfilehash: 46e4db701dc3d43ed30b8101ef2af5ff2e4a2ad0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="8be05-102">Implantando regiões de rede, sites e sub-redes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8be05-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8be05-103">_**Última modificação do tópico:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="8be05-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="8be05-104">Após a implantação do Enterprise Voice, você precisará configurar:</span><span class="sxs-lookup"><span data-stu-id="8be05-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="8be05-105">Regiões de rede</span><span class="sxs-lookup"><span data-stu-id="8be05-105">Network regions</span></span>

  - <span data-ttu-id="8be05-106">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="8be05-106">Network sites</span></span>

  - <span data-ttu-id="8be05-107">Sub-redes da rede</span><span class="sxs-lookup"><span data-stu-id="8be05-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="8be05-108">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="8be05-108">Define Network Regions</span></span>

<span data-ttu-id="8be05-109">Use o comando do Windows PowerShell do Lync Server, o New-CsNetworkRegion ou o painel de controle do Lync Server para definir as regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="8be05-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="8be05-110">Para obter mais informações, consulte [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="8be05-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="8be05-111">Neste exemplo, o seguinte comando do Windows PowerShell ilustra a região de rede, a região 1 (Índia), definida neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8be05-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="8be05-112">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="8be05-112">Define Network Sites</span></span>

<span data-ttu-id="8be05-113">Use o comando do Lync Server Windows PowerShell, New-CsNetworkSite ou o painel de controle do Lync Server para definir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="8be05-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="8be05-114">Para obter mais informações, consulte [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="8be05-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="8be05-115">Para este exemplo, a tabela a seguir e o comando do Windows PowerShell do Lync Server ilustram os sites de rede definidos neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8be05-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="8be05-116">Somente as configurações específicas do roteamento baseado em local são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="8be05-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="8be05-117">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8be05-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="8be05-118">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8be05-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8be05-119">ID de site</span><span class="sxs-lookup"><span data-stu-id="8be05-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="8be05-120">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8be05-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="8be05-121">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8be05-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be05-122">ID de região</span><span class="sxs-lookup"><span data-stu-id="8be05-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="8be05-123">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="8be05-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="8be05-124">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="8be05-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="8be05-125">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="8be05-125">Define Network Subnets</span></span>

<span data-ttu-id="8be05-126">Use o comando do Lync Server Windows PowerShell, New-CsNetworkSubnet ou o painel de controle do Lync Server para definir sub-redes de rede e atribuí-las aos sites de rede.</span><span class="sxs-lookup"><span data-stu-id="8be05-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="8be05-127">Para obter mais informações, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="8be05-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="8be05-128">Neste exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram a atribuição de sub-redes de rede para os sites de rede, Delhi e Hyderabad, definidas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8be05-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="8be05-129">Somente as configurações específicas do roteamento baseado em local são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="8be05-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="8be05-130">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8be05-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="8be05-131">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8be05-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8be05-132">ID da sub-rede</span><span class="sxs-lookup"><span data-stu-id="8be05-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="8be05-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="8be05-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="8be05-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="8be05-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be05-135">Máscara</span><span class="sxs-lookup"><span data-stu-id="8be05-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="8be05-136">dia</span><span class="sxs-lookup"><span data-stu-id="8be05-136">24</span></span></p></td>
<td><p><span data-ttu-id="8be05-137">dia</span><span class="sxs-lookup"><span data-stu-id="8be05-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be05-138">ID de site</span><span class="sxs-lookup"><span data-stu-id="8be05-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="8be05-139">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8be05-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="8be05-140">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8be05-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8be05-141">Confira Também</span><span class="sxs-lookup"><span data-stu-id="8be05-141">See Also</span></span>


[<span data-ttu-id="8be05-142">Configurando o roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8be05-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

