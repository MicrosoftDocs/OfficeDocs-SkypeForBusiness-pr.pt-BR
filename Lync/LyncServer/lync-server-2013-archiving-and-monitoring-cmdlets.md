---
title: 'Lync Server 2013: cmdlets de arquivamento e monitoramento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Archiving and Monitoring cmdlets
ms:assetid: 04e1d0f6-d00e-4d8f-b969-daf092b2cdb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415629(v=OCS.15)
ms:contentKeyID: 48183281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06f4968e9897b63c4819be0b403b3d0d2a0c2136
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="archiving-and-monitoring-cmdlets-in-lync-server-2013"></a><span data-ttu-id="4e442-102">Cmdlets de arquivamento e monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e442-102">Archiving and Monitoring cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e442-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="4e442-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="4e442-104">Os cmdlets de arquivamento e monitoramento permitem que os administradores gerenciem a mensagem instantânea e o arquivamento da sessão de conferência; para registrar informações de detalhes da chamada; e monitorar o Microsoft Lync Server 2013 usando o QoE (qualidade da experiência).</span><span class="sxs-lookup"><span data-stu-id="4e442-104">The archiving and monitoring cmdlets enable administrators to manage instant message and conference session archiving; to record call detail information; and to monitor Microsoft Lync Server 2013 using Quality of Experience (QoE).</span></span>


> [!NOTE]
> <span data-ttu-id="4e442-105">Para obter informações adicionais sobre cmdlets, consulte o blog&nbsp;do Lync Server Windows <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>PowerShell em.</span><span class="sxs-lookup"><span data-stu-id="4e442-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="4e442-106">O conteúdo de cada blog e sua URL estão sujeitos a alterações sem aviso prévio.</span><span class="sxs-lookup"><span data-stu-id="4e442-106">The content of each blog and its URL are subject to change without notice.</span></span>



<div>

## <a name="archiving-and-monitoring-cmdlets"></a><span data-ttu-id="4e442-107">Cmdlets de arquivamento e monitoramento</span><span class="sxs-lookup"><span data-stu-id="4e442-107">Archiving and Monitoring Cmdlets</span></span>

<span data-ttu-id="4e442-108">A seguir, encontra-se uma lista de cmdlets relacionados diretamente ao gerenciamento de arquivamento e monitoramento:</span><span class="sxs-lookup"><span data-stu-id="4e442-108">The following is a list of cmdlets that relate directly to managing archiving and monitoring:</span></span>

<span data-ttu-id="4e442-109">**Arquivamento e Monitoramento**</span><span class="sxs-lookup"><span data-stu-id="4e442-109">**Archiving and Monitoring**</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-110">[Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-110">[Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-111">[New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-111">[New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-112">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-112">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-113">[Set-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-113">[Set-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-114">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-114">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-115">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-115">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-116">[Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-116">[Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-117">[Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-117">[Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-118">[New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-118">[New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-119">[Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-119">[Remove-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-120">[Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-120">[Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-121">[Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-121">[Set-CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-122">[Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-122">[Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-123">[New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-123">[New-CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-124">[Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-124">[Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-125">[Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-125">[Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-126">[Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-126">[Set-CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-127">[Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-127">[Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-128">[New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-128">[New-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-129">[Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-129">[Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-130">[Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-130">[Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))</span></span>

<span data-ttu-id="4e442-131">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-131">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-132">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-132">[Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-133">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-133">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-134">[Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-134">[Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-135">[New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-135">[New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-136">[Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-136">[Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-137">[Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-137">[Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-138">[Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-138">[Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-139">[Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-139">[Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-140">[Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-140">[Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-141">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-141">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-142">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-142">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-143">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-143">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-144">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-144">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4e442-145">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-145">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4e442-146">[New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4e442-146">[New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

