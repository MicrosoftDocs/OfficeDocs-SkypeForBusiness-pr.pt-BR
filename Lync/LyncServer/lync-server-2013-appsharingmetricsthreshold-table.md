---
title: 'Lync Server 2013: tabela AppSharingMetricsThreshold'
description: 'Lync Server 2013: tabela AppSharingMetricsThreshold.'
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
ms.openlocfilehash: 092c7d08026e6b736b81043a71b4ecaabc4d5f1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546807"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="72dd6-103">Tabela AppSharingMetricsThreshold no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72dd6-103">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72dd6-104">_**Última modificação do tópico:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="72dd6-104">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="72dd6-p101">A tabela AppSharingMetricsThreshold contém valores ideais e aceitáveis de métricas de Qualidade de Experiência usadas no compartilhamento de aplicativos. Esses limites são usado para determinar se a experiência de compartilhamento de aplicativos deve ser classificada como inadequada.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="72dd6-107">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72dd6-108"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="72dd6-109"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="72dd6-110"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="72dd6-111"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72dd6-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-113">int</span><span class="sxs-lookup"><span data-stu-id="72dd6-113">int</span></span></p></td>
<td><p><span data-ttu-id="72dd6-114">Primário</span><span class="sxs-lookup"><span data-stu-id="72dd6-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="72dd6-115">Tipo de chamada feita.</span><span class="sxs-lookup"><span data-stu-id="72dd6-115">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72dd6-116"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-116"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-117">int</span><span class="sxs-lookup"><span data-stu-id="72dd6-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-p102">Limitação de largura de banda ideal para compartilhamento de aplicativos. O valor padrão é 1000000.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72dd6-120"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-120"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-121">int</span><span class="sxs-lookup"><span data-stu-id="72dd6-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-p103">Limitação de largura de banda aceitável para compartilhamento de aplicativos. O valor padrão é 500000.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72dd6-124"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-124"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-125">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72dd6-125">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-p104">Percentual ideal de blocos "danificados" para classificação de qualidade de compartilhamento de aplicativos. Esse valor é o percentual de conteúdo do compartilhador que não alcançou o visualizador. O conteúdo pode ser descartado (ou danificado) quando o compartilhador descarta blocos da origem gráfica ou os blocos ASMCU descartam blocos do compartilhador, respectivamente. O valor padrão é 11%.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72dd6-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-131">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="72dd6-131">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-p105">Percentual aceitável de blocos "danificados" para classificação de qualidade de compartilhamento de aplicativos. Esse valor é o percentual de conteúdo do compartilhador que não alcançou o visualizador. O conteúdo pode ser descartado (ou danificado) quando o compartilhador descarta blocos da origem gráfica ou os blocos ASMCU descartam blocos do compartilhador, respectivamente. O valor padrão é 36%.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72dd6-136"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-136"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-137">int</span><span class="sxs-lookup"><span data-stu-id="72dd6-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-138">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-138">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72dd6-139"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-139"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-140">int</span><span class="sxs-lookup"><span data-stu-id="72dd6-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-141">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-141">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72dd6-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-143">flutuação</span><span class="sxs-lookup"><span data-stu-id="72dd6-143">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-144">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-144">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72dd6-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-146">flutuação</span><span class="sxs-lookup"><span data-stu-id="72dd6-146">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-147">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-147">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72dd6-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-149">flutuação</span><span class="sxs-lookup"><span data-stu-id="72dd6-149">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-150">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-150">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72dd6-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-152">flutuação</span><span class="sxs-lookup"><span data-stu-id="72dd6-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-153">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-153">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72dd6-154"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-154"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-155">flutuação</span><span class="sxs-lookup"><span data-stu-id="72dd6-155">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-p106">Valor ideal do atraso unidirecional relativo entre dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,0 segundo.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="72dd6-159">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-159">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72dd6-160"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-160"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-161">flutuação</span><span class="sxs-lookup"><span data-stu-id="72dd6-161">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-p107">Valor ideal do atraso unidirecional relativo entre dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,75 segundo.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="72dd6-165">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-165">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72dd6-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-167">flutuação</span><span class="sxs-lookup"><span data-stu-id="72dd6-167">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-168">Valor ideal da latência média de processamento de blocos RDP no Servidor de Conferência AS pelo tempo da sessão de visualização.</span><span class="sxs-lookup"><span data-stu-id="72dd6-168">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="72dd6-169">Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.</span><span class="sxs-lookup"><span data-stu-id="72dd6-169">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="72dd6-p109">Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode ter atrasos médios maiores. O valor padrão é 200 ms.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="72dd6-173">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-173">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72dd6-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="72dd6-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="72dd6-175">flutuação</span><span class="sxs-lookup"><span data-stu-id="72dd6-175">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="72dd6-176">Valor aceitável da latência média de processamento de blocos RDP no Servidor de Conferência AS pelo tempo da sessão de visualização.</span><span class="sxs-lookup"><span data-stu-id="72dd6-176">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="72dd6-177">Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.</span><span class="sxs-lookup"><span data-stu-id="72dd6-177">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="72dd6-p111">Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode ter atrasos médios maiores. O valor padrão é 200 ms.</span><span class="sxs-lookup"><span data-stu-id="72dd6-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="72dd6-181">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72dd6-181">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

