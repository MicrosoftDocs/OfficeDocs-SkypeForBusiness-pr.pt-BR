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
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="2a3f6-102">Implantando regiões de rede, sites e sub-redes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a3f6-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a3f6-103">_**Tópico da última modificação:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="2a3f6-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="2a3f6-104">Depois que o Enterprise Voice for implantado, você precisará configurar:</span><span class="sxs-lookup"><span data-stu-id="2a3f6-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="2a3f6-105">Regiões de rede</span><span class="sxs-lookup"><span data-stu-id="2a3f6-105">Network regions</span></span>

  - <span data-ttu-id="2a3f6-106">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="2a3f6-106">Network sites</span></span>

  - <span data-ttu-id="2a3f6-107">Sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="2a3f6-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="2a3f6-108">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="2a3f6-108">Define Network Regions</span></span>

<span data-ttu-id="2a3f6-109">Use o comando do Windows PowerShell do Lync Server, novo-CsNetworkRegion ou o painel de controle do Lync Server para definir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="2a3f6-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="2a3f6-110">Para obter mais informações, consulte [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span><span class="sxs-lookup"><span data-stu-id="2a3f6-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="2a3f6-111">Para este exemplo, o seguinte comando do Windows PowerShell ilustra a região de rede, região 1 (Índia), definida nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="2a3f6-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="2a3f6-112">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="2a3f6-112">Define Network Sites</span></span>

<span data-ttu-id="2a3f6-113">Use o comando do Windows PowerShell do Lync Server, novo-CsNetworkSite ou o painel de controle do Lync Server para definir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="2a3f6-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="2a3f6-114">Para obter mais informações, consulte [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="2a3f6-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="2a3f6-115">Para este exemplo, a tabela a seguir e o comando do Windows PowerShell do Lync Server ilustram os sites de rede definidos neste cenário.</span><span class="sxs-lookup"><span data-stu-id="2a3f6-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="2a3f6-116">Somente as configurações específicas do roteamento baseado em localização são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="2a3f6-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="2a3f6-117">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="2a3f6-118">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a3f6-119">ID do site</span><span class="sxs-lookup"><span data-stu-id="2a3f6-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-120">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-121">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a3f6-122">ID da região</span><span class="sxs-lookup"><span data-stu-id="2a3f6-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-123">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-124">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="2a3f6-125">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="2a3f6-125">Define Network Subnets</span></span>

<span data-ttu-id="2a3f6-126">Use o comando do Windows PowerShell do Lync Server, novo-CsNetworkSubnet ou o painel de controle do Lync Server para definir sub-redes de rede e atribuí-las a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="2a3f6-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="2a3f6-127">Para obter mais informações, consulte [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="2a3f6-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="2a3f6-128">Para este exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram a atribuição de sub-redes de rede para os sites de rede, Delhi e Hyderabad, definidas nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="2a3f6-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="2a3f6-129">Somente as configurações específicas do roteamento baseado em localização são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="2a3f6-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="2a3f6-130">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="2a3f6-131">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a3f6-132">ID de sub-rede</span><span class="sxs-lookup"><span data-stu-id="2a3f6-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="2a3f6-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="2a3f6-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a3f6-135">Remoção</span><span class="sxs-lookup"><span data-stu-id="2a3f6-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-136">24</span><span class="sxs-lookup"><span data-stu-id="2a3f6-136">24</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-137">24</span><span class="sxs-lookup"><span data-stu-id="2a3f6-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a3f6-138">ID do site</span><span class="sxs-lookup"><span data-stu-id="2a3f6-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-139">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="2a3f6-140">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="2a3f6-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a3f6-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="2a3f6-141">See Also</span></span>


[<span data-ttu-id="2a3f6-142">Configurando o Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a3f6-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

