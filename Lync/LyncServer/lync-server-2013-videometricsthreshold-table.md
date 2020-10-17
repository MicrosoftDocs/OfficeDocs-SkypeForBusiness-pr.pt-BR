---
title: 'Lync Server 2013: tabela VideoMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f1f1fc7ca86c10fa9c409c73c2f4b54ee2777a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508508"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="ea394-102">Tabela VideoMetricsThreshold no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea394-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea394-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ea394-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ea394-104">A tabela VideoMetricsThreshold contém os melhores valores e aceitáveis para as métricas de Qualidade da Experiência usada com chamadas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="ea394-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea394-105"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ea394-106"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ea394-107"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ea394-108"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea394-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-110">int</span><span class="sxs-lookup"><span data-stu-id="ea394-110">int</span></span></p></td>
<td><p><span data-ttu-id="ea394-111">Primário</span><span class="sxs-lookup"><span data-stu-id="ea394-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="ea394-112">Tipo de chamada realizada.</span><span class="sxs-lookup"><span data-stu-id="ea394-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea394-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-114">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-115">O valor padrão é 0.05.</span><span class="sxs-lookup"><span data-stu-id="ea394-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea394-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-117">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-118">O valor padrão é 0.10.</span><span class="sxs-lookup"><span data-stu-id="ea394-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea394-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-120">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-121">O valor padrão é 5.0.</span><span class="sxs-lookup"><span data-stu-id="ea394-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea394-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-123">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-124">O valor padrão é 10.0.</span><span class="sxs-lookup"><span data-stu-id="ea394-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea394-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-126">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ea394-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-127">O valor padrão é 12.0000.</span><span class="sxs-lookup"><span data-stu-id="ea394-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea394-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-129">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ea394-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-130">O valor padrão é 7.0000.</span><span class="sxs-lookup"><span data-stu-id="ea394-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea394-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-132">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-133">O valor padrão é 5.0.</span><span class="sxs-lookup"><span data-stu-id="ea394-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea394-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-135">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-136">O valor padrão é 10.0/</span><span class="sxs-lookup"><span data-stu-id="ea394-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea394-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-138">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-139">O valor padrão é 5.0.</span><span class="sxs-lookup"><span data-stu-id="ea394-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea394-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-141">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-142">O valor padrão é 10.0.</span><span class="sxs-lookup"><span data-stu-id="ea394-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea394-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-144">foat</span><span class="sxs-lookup"><span data-stu-id="ea394-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-145">O valor padrão é 0.05.</span><span class="sxs-lookup"><span data-stu-id="ea394-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea394-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-147">flutuação</span><span class="sxs-lookup"><span data-stu-id="ea394-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-148">O valor padrão é 0.10.</span><span class="sxs-lookup"><span data-stu-id="ea394-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea394-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-150">flutuação</span><span class="sxs-lookup"><span data-stu-id="ea394-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-151">O valor padrão é 12.</span><span class="sxs-lookup"><span data-stu-id="ea394-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea394-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-153">flutuação</span><span class="sxs-lookup"><span data-stu-id="ea394-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-154">O valor padrão é 7.</span><span class="sxs-lookup"><span data-stu-id="ea394-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea394-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-156">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-157">O valor padrão é 5.00.</span><span class="sxs-lookup"><span data-stu-id="ea394-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea394-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ea394-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ea394-159">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ea394-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ea394-160">O valor padrão é 10.00.</span><span class="sxs-lookup"><span data-stu-id="ea394-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

