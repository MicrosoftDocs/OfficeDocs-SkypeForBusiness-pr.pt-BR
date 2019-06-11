---
title: 'Lync Server 2013: cmdlets de controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control cmdlets
ms:assetid: dd9d3912-b562-4839-a337-bfc5277cfb62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415676(v=OCS.15)
ms:contentKeyID: 48185602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e192d30205a43d2bf13a347b7ee40f0ac424320
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a><span data-ttu-id="94d41-102">Cmdlets do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94d41-102">Call admission control cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94d41-103">_**Tópico da última modificação:** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="94d41-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="94d41-104">O controle de admissão de chamadas (CAC) determina se há largura de banda de rede suficiente para estabelecer uma sessão de áudio ou vídeo em tempo real de uma qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="94d41-104">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time audio or video session of acceptable quality.</span></span> <span data-ttu-id="94d41-105">Você gerencia o CAC por configuraing limitações e configurações de redes, sites e sub-redes e das interações entre elas.</span><span class="sxs-lookup"><span data-stu-id="94d41-105">You manage CAC by configuraing limitations and settings for networks, sites, and subnets and the interactions between them.</span></span>

<div>

## <a name="call-admission-control-cmdlets"></a><span data-ttu-id="94d41-106">Cmdlets de controle de admissão de chamadas</span><span class="sxs-lookup"><span data-stu-id="94d41-106">Call Admission Control Cmdlets</span></span>

<span data-ttu-id="94d41-107">Use os cmdlets a seguir para gerenciar o CAC do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94d41-107">Use the following cmdlets to manage CAC from the Lync Server Management Shell.</span></span>

<span data-ttu-id="94d41-108">**Serviço de Controle de Admissão de Chamadas**</span><span class="sxs-lookup"><span data-stu-id="94d41-108">**Call Admission Control**</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-130">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-130">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-131">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-131">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-133">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-133">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-138">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-138">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-139">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-139">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-140">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-140">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-141">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-141">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="94d41-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-143">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-143">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="94d41-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="94d41-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="94d41-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="94d41-146">See Also</span></span>


[<span data-ttu-id="94d41-147">Visão geral do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94d41-147">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="94d41-148">Blog do PowerShell do Lync Server</span><span class="sxs-lookup"><span data-stu-id="94d41-148">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

