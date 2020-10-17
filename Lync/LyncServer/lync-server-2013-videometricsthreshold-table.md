---
title: 'Lync Server 2013: tabela VideoMetricsThreshold'
description: 'Lync Server 2013: tabela VideoMetricsThreshold.'
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
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567997"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="484c6-103">Tabela VideoMetricsThreshold no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="484c6-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="484c6-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="484c6-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="484c6-105">A tabela VideoMetricsThreshold contém os melhores valores e aceitáveis para as métricas de Qualidade da Experiência usada com chamadas de vídeo.</span><span class="sxs-lookup"><span data-stu-id="484c6-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="484c6-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="484c6-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="484c6-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="484c6-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="484c6-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-111">int</span><span class="sxs-lookup"><span data-stu-id="484c6-111">int</span></span></p></td>
<td><p><span data-ttu-id="484c6-112">Primário</span><span class="sxs-lookup"><span data-stu-id="484c6-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="484c6-113">Tipo de chamada realizada.</span><span class="sxs-lookup"><span data-stu-id="484c6-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484c6-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-115">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-116">O valor padrão é 0.05.</span><span class="sxs-lookup"><span data-stu-id="484c6-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484c6-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-118">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-119">O valor padrão é 0.10.</span><span class="sxs-lookup"><span data-stu-id="484c6-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484c6-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-121">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-122">O valor padrão é 5.0.</span><span class="sxs-lookup"><span data-stu-id="484c6-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484c6-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-124">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-125">O valor padrão é 10.0.</span><span class="sxs-lookup"><span data-stu-id="484c6-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484c6-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-127">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="484c6-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-128">O valor padrão é 12.0000.</span><span class="sxs-lookup"><span data-stu-id="484c6-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484c6-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-130">decimal (9, 4)</span><span class="sxs-lookup"><span data-stu-id="484c6-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-131">O valor padrão é 7.0000.</span><span class="sxs-lookup"><span data-stu-id="484c6-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484c6-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-133">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-134">O valor padrão é 5.0.</span><span class="sxs-lookup"><span data-stu-id="484c6-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484c6-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-136">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-137">O valor padrão é 10.0/</span><span class="sxs-lookup"><span data-stu-id="484c6-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484c6-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-139">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-140">O valor padrão é 5.0.</span><span class="sxs-lookup"><span data-stu-id="484c6-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484c6-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-142">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-143">O valor padrão é 10.0.</span><span class="sxs-lookup"><span data-stu-id="484c6-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484c6-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-145">foat</span><span class="sxs-lookup"><span data-stu-id="484c6-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-146">O valor padrão é 0.05.</span><span class="sxs-lookup"><span data-stu-id="484c6-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484c6-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-148">flutuação</span><span class="sxs-lookup"><span data-stu-id="484c6-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-149">O valor padrão é 0.10.</span><span class="sxs-lookup"><span data-stu-id="484c6-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484c6-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-151">flutuação</span><span class="sxs-lookup"><span data-stu-id="484c6-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-152">O valor padrão é 12.</span><span class="sxs-lookup"><span data-stu-id="484c6-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484c6-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-154">flutuação</span><span class="sxs-lookup"><span data-stu-id="484c6-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-155">O valor padrão é 7.</span><span class="sxs-lookup"><span data-stu-id="484c6-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="484c6-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-157">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-158">O valor padrão é 5.00.</span><span class="sxs-lookup"><span data-stu-id="484c6-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="484c6-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="484c6-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="484c6-160">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="484c6-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="484c6-161">O valor padrão é 10.00.</span><span class="sxs-lookup"><span data-stu-id="484c6-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

