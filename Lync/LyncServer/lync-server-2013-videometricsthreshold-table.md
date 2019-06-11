---
title: 'Lync Server 2013: tabela VideoMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="9de4c-102">Tabela VideoMetricsThreshold no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9de4c-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9de4c-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9de4c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9de4c-104">A tabela VideoMetricsThreshold contém os valores ideais e aceitáveis para as métricas de qualidade da experiência usadas com chamadas com vídeo.</span><span class="sxs-lookup"><span data-stu-id="9de4c-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9de4c-105"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9de4c-106"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9de4c-107"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9de4c-108"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-110">int</span><span class="sxs-lookup"><span data-stu-id="9de4c-110">int</span></span></p></td>
<td><p><span data-ttu-id="9de4c-111">Primária</span><span class="sxs-lookup"><span data-stu-id="9de4c-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="9de4c-112">Tipo de chamada que foi feita.</span><span class="sxs-lookup"><span data-stu-id="9de4c-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de4c-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-114">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-115">O valor padrão é 0, 5.</span><span class="sxs-lookup"><span data-stu-id="9de4c-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-117">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-118">O valor padrão é 0,10.</span><span class="sxs-lookup"><span data-stu-id="9de4c-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de4c-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-120">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-121">O valor padrão é 5,0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-123">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-124">O valor padrão é 10,0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de4c-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-126">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9de4c-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-127">O valor padrão é 12, 0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-129">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="9de4c-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-130">O valor padrão é 7, 0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de4c-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-132">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-133">O valor padrão é 5,0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-135">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-136">O valor padrão é 10.0/</span><span class="sxs-lookup"><span data-stu-id="9de4c-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de4c-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-138">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-139">O valor padrão é 5,0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-141">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-142">O valor padrão é 10,0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de4c-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-144">foat</span><span class="sxs-lookup"><span data-stu-id="9de4c-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-145">O valor padrão é 0, 5.</span><span class="sxs-lookup"><span data-stu-id="9de4c-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-147">float</span><span class="sxs-lookup"><span data-stu-id="9de4c-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-148">O valor padrão é 0,10.</span><span class="sxs-lookup"><span data-stu-id="9de4c-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de4c-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-150">float</span><span class="sxs-lookup"><span data-stu-id="9de4c-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-151">O valor padrão é 12.</span><span class="sxs-lookup"><span data-stu-id="9de4c-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-153">float</span><span class="sxs-lookup"><span data-stu-id="9de4c-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-154">O valor padrão é 7.</span><span class="sxs-lookup"><span data-stu-id="9de4c-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de4c-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-156">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-157">O valor padrão é 5, 0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de4c-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9de4c-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9de4c-159">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="9de4c-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9de4c-160">O valor padrão é 10, 0.</span><span class="sxs-lookup"><span data-stu-id="9de4c-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

