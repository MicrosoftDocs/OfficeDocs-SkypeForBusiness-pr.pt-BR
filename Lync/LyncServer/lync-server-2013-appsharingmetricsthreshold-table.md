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
ms.openlocfilehash: 89260bb2e854087ec1167ff0fd8039c58ac99300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="eff42-102">Tabela AppSharingMetricsThreshold no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eff42-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eff42-103">_**Última modificação do tópico:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="eff42-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="eff42-p101">A tabela AppSharingMetricsThreshold contém valores ideais e aceitáveis de métricas de Qualidade de Experiência usadas no compartilhamento de aplicativos. Esses limites são usado para determinar se a experiência de compartilhamento de aplicativos deve ser classificada como inadequada.</span><span class="sxs-lookup"><span data-stu-id="eff42-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="eff42-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eff42-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eff42-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eff42-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eff42-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eff42-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-112">int</span><span class="sxs-lookup"><span data-stu-id="eff42-112">int</span></span></p></td>
<td><p><span data-ttu-id="eff42-113">Primário</span><span class="sxs-lookup"><span data-stu-id="eff42-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff42-114">Tipo de chamada feita.</span><span class="sxs-lookup"><span data-stu-id="eff42-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff42-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-116">int</span><span class="sxs-lookup"><span data-stu-id="eff42-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-p102">Limitação de largura de banda ideal para compartilhamento de aplicativos. O valor padrão é 1000000.</span><span class="sxs-lookup"><span data-stu-id="eff42-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff42-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-120">int</span><span class="sxs-lookup"><span data-stu-id="eff42-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-p103">Limitação de largura de banda aceitável para compartilhamento de aplicativos. O valor padrão é 500000.</span><span class="sxs-lookup"><span data-stu-id="eff42-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff42-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-124">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eff42-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-p104">Percentual ideal de blocos "danificados" para classificação de qualidade de compartilhamento de aplicativos. Esse valor é o percentual de conteúdo do compartilhador que não alcançou o visualizador. O conteúdo pode ser descartado (ou danificado) quando o compartilhador descarta blocos da origem gráfica ou os blocos ASMCU descartam blocos do compartilhador, respectivamente. O valor padrão é 11%.</span><span class="sxs-lookup"><span data-stu-id="eff42-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff42-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-130">decimal (5, 2)</span><span class="sxs-lookup"><span data-stu-id="eff42-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-p105">Percentual aceitável de blocos "danificados" para classificação de qualidade de compartilhamento de aplicativos. Esse valor é o percentual de conteúdo do compartilhador que não alcançou o visualizador. O conteúdo pode ser descartado (ou danificado) quando o compartilhador descarta blocos da origem gráfica ou os blocos ASMCU descartam blocos do compartilhador, respectivamente. O valor padrão é 36%.</span><span class="sxs-lookup"><span data-stu-id="eff42-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff42-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-136">int</span><span class="sxs-lookup"><span data-stu-id="eff42-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-137">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff42-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-139">int</span><span class="sxs-lookup"><span data-stu-id="eff42-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-140">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff42-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-142">float</span><span class="sxs-lookup"><span data-stu-id="eff42-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-143">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff42-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-145">float</span><span class="sxs-lookup"><span data-stu-id="eff42-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-146">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff42-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-148">float</span><span class="sxs-lookup"><span data-stu-id="eff42-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-149">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff42-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-151">float</span><span class="sxs-lookup"><span data-stu-id="eff42-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-152">Esta coluna não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff42-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-154">float</span><span class="sxs-lookup"><span data-stu-id="eff42-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-p106">Valor ideal do atraso unidirecional relativo entre dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,0 segundo.</span><span class="sxs-lookup"><span data-stu-id="eff42-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="eff42-158">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff42-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-160">float</span><span class="sxs-lookup"><span data-stu-id="eff42-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-p107">Valor ideal do atraso unidirecional relativo entre dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,75 segundo.</span><span class="sxs-lookup"><span data-stu-id="eff42-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="eff42-164">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff42-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-166">float</span><span class="sxs-lookup"><span data-stu-id="eff42-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-167">Valor ideal da latência média de processamento de blocos RDP no Servidor de Conferência AS pelo tempo da sessão de visualização.</span><span class="sxs-lookup"><span data-stu-id="eff42-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="eff42-168">Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.</span><span class="sxs-lookup"><span data-stu-id="eff42-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="eff42-p109">Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode ter atrasos médios maiores. O valor padrão é 200 ms.</span><span class="sxs-lookup"><span data-stu-id="eff42-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="eff42-172">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff42-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="eff42-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="eff42-174">float</span><span class="sxs-lookup"><span data-stu-id="eff42-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff42-175">Valor aceitável da latência média de processamento de blocos RDP no Servidor de Conferência AS pelo tempo da sessão de visualização.</span><span class="sxs-lookup"><span data-stu-id="eff42-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="eff42-176">Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.</span><span class="sxs-lookup"><span data-stu-id="eff42-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="eff42-p111">Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode ter atrasos médios maiores. O valor padrão é 200 ms.</span><span class="sxs-lookup"><span data-stu-id="eff42-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="eff42-180">A coluna foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eff42-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

