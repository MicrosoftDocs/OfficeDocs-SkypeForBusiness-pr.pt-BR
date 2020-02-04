---
title: 'Lync Server 2013: tabela AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="c8d81-102">Tabela AppSharingMetricsThreshold no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8d81-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8d81-103">_**Tópico da última modificação:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="c8d81-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="c8d81-104">A tabela AppSharingMetricsThreshold contém os valores ideais e aceitáveis para as métricas de qualidade da experiência usadas com o compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="c8d81-105">Esses limiares são usados para determinar se a experiência de compartilhamento de aplicativos deve ser classificada como ruim.</span><span class="sxs-lookup"><span data-stu-id="c8d81-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="c8d81-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8d81-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c8d81-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c8d81-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c8d81-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8d81-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-112">int</span><span class="sxs-lookup"><span data-stu-id="c8d81-112">int</span></span></p></td>
<td><p><span data-ttu-id="c8d81-113">Primária</span><span class="sxs-lookup"><span data-stu-id="c8d81-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c8d81-114">Tipo de chamada que foi feita.</span><span class="sxs-lookup"><span data-stu-id="c8d81-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d81-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-116">int</span><span class="sxs-lookup"><span data-stu-id="c8d81-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-117">Limitação de largura de banda ideal para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="c8d81-118">O valor padrão é 1 milhão.</span><span class="sxs-lookup"><span data-stu-id="c8d81-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d81-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-120">int</span><span class="sxs-lookup"><span data-stu-id="c8d81-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-121">Limitação de largura de banda aceitável para compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="c8d81-122">O valor padrão é 500000.</span><span class="sxs-lookup"><span data-stu-id="c8d81-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d81-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-124">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="c8d81-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-125">A taxa de porcentagem ideal para blocos "danificados" para classificar uma qualidade de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="c8d81-126">Esse valor é a porcentagem do conteúdo do participante do compartilhamento que não tinha chegado ao visualizador.</span><span class="sxs-lookup"><span data-stu-id="c8d81-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="c8d81-127">O conteúdo pode ser descartado (ou danificados) quando o participante do compartilhamento descarta blocos da fonte gráfica ou os blocos do ASMCU descartam os blocos do participante do compartilhamento, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c8d81-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="c8d81-128">O valor padrão é 11%.</span><span class="sxs-lookup"><span data-stu-id="c8d81-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d81-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-130">decimal (5; 2)</span><span class="sxs-lookup"><span data-stu-id="c8d81-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-131">cceptable a taxa de porcentagem para blocos "danificados" para classificar uma qualidade de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="c8d81-132">Esse valor é a porcentagem do conteúdo do participante do compartilhamento que não tinha chegado ao visualizador.</span><span class="sxs-lookup"><span data-stu-id="c8d81-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="c8d81-133">O conteúdo pode ser descartado (ou danificados) quando o participante do compartilhamento descarta blocos da fonte gráfica ou os blocos do ASMCU descartam os blocos do participante do compartilhamento, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c8d81-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="c8d81-134">O valor padrão é 36%.</span><span class="sxs-lookup"><span data-stu-id="c8d81-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d81-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-136">int</span><span class="sxs-lookup"><span data-stu-id="c8d81-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-137">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d81-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-139">int</span><span class="sxs-lookup"><span data-stu-id="c8d81-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-140">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d81-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-142">float</span><span class="sxs-lookup"><span data-stu-id="c8d81-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-143">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d81-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-145">float</span><span class="sxs-lookup"><span data-stu-id="c8d81-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-146">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d81-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-148">float</span><span class="sxs-lookup"><span data-stu-id="c8d81-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-149">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d81-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-151">float</span><span class="sxs-lookup"><span data-stu-id="c8d81-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-152">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d81-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-154">float</span><span class="sxs-lookup"><span data-stu-id="c8d81-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-155">Valor ideal para o atraso unidirecional relativo entre os dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="c8d81-156">Esta é uma medida de latência de salto único.</span><span class="sxs-lookup"><span data-stu-id="c8d81-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="c8d81-157">O valor padrão é 1,0 segundos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="c8d81-158">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d81-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-160">float</span><span class="sxs-lookup"><span data-stu-id="c8d81-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-161">Valor ideal para o atraso unidirecional relativo entre os dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="c8d81-162">Esta é uma medida de latência de salto único.</span><span class="sxs-lookup"><span data-stu-id="c8d81-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="c8d81-163">O valor padrão é 1,75 segundos.</span><span class="sxs-lookup"><span data-stu-id="c8d81-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="c8d81-164">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8d81-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-166">float</span><span class="sxs-lookup"><span data-stu-id="c8d81-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-167">O valor ideal da latência média de processamento de bloco RDP no servidor de conferência as na duração da sessão de exibição.</span><span class="sxs-lookup"><span data-stu-id="c8d81-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="c8d81-168">Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.</span><span class="sxs-lookup"><span data-stu-id="c8d81-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="c8d81-169">Uma média alta reflete um atraso maior na experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="c8d81-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="c8d81-170">Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores.</span><span class="sxs-lookup"><span data-stu-id="c8d81-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="c8d81-171">O valor padrão é 200ms.</span><span class="sxs-lookup"><span data-stu-id="c8d81-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="c8d81-172">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8d81-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="c8d81-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="c8d81-174">float</span><span class="sxs-lookup"><span data-stu-id="c8d81-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c8d81-175">Valor aceitável da latência média de processamento de bloco RDP no servidor de conferência as na duração da sessão de exibição.</span><span class="sxs-lookup"><span data-stu-id="c8d81-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="c8d81-176">Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.</span><span class="sxs-lookup"><span data-stu-id="c8d81-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="c8d81-177">Uma média alta reflete um atraso maior na experiência de visualização.</span><span class="sxs-lookup"><span data-stu-id="c8d81-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="c8d81-178">Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores.</span><span class="sxs-lookup"><span data-stu-id="c8d81-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="c8d81-179">O valor padrão é 200ms.</span><span class="sxs-lookup"><span data-stu-id="c8d81-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="c8d81-180">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8d81-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

