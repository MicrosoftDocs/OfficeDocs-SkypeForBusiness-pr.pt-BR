---
title: 'Lync Server 2013: cmdlets de controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control cmdlets
ms:assetid: dd9d3912-b562-4839-a337-bfc5277cfb62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415676(v=OCS.15)
ms:contentKeyID: 48185602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3805a597cba993e8b50e006a198fdc693a1d595b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e42a8-102">Cmdlets do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e42a8-102">Call admission control cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e42a8-103">_**Tópico da última modificação:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="e42a8-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="e42a8-104">O controle de admissão de chamadas (CAC) determina se há largura de banda de rede suficiente para estabelecer uma sessão de áudio ou vídeo em tempo real de uma qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="e42a8-104">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time audio or video session of acceptable quality.</span></span> <span data-ttu-id="e42a8-105">Você gerencia o CAC por configuraing limitações e configurações de redes, sites e sub-redes e das interações entre elas.</span><span class="sxs-lookup"><span data-stu-id="e42a8-105">You manage CAC by configuraing limitations and settings for networks, sites, and subnets and the interactions between them.</span></span>

<div>

## <a name="call-admission-control-cmdlets"></a><span data-ttu-id="e42a8-106">Cmdlets de controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="e42a8-106">Call Admission Control Cmdlets</span></span>

<span data-ttu-id="e42a8-107">Use os cmdlets a seguir para gerenciar o CAC do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e42a8-107">Use the following cmdlets to manage CAC from the Lync Server Management Shell.</span></span>

<span data-ttu-id="e42a8-108">**Serviço de Controle de Admissão de Chamadas**</span><span class="sxs-lookup"><span data-stu-id="e42a8-108">**Call Admission Control**</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-130">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-130">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-131">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-131">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-133">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-133">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-138">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-138">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-139">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-139">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-140">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-140">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-141">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-141">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e42a8-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-143">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-143">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e42a8-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e42a8-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e42a8-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="e42a8-146">See Also</span></span>


[<span data-ttu-id="e42a8-147">Visão geral do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e42a8-147">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="e42a8-148">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="e42a8-148">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

