---
title: 'Lync Server 2013: tabela AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f8dc1dac3dc7a9ec362473221d36191dd7dd0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Tabela AppSharingMetricsThreshold no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-12-08_

A tabela AppSharingMetricsThreshold contém os valores ideais e aceitáveis para as métricas de qualidade da experiência usadas com o compartilhamento de aplicativos. Esses limiares são usados para determinar se a experiência de compartilhamento de aplicativos deve ser classificada como ruim.

Esta tabela foi introduzida no Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Coluna</strong></th>
<th><strong>Tipo de dados</strong></th>
<th><strong>Chave/índice</strong></th>
<th><strong>Detalhes</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Tipo de chamada que foi feita.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitação de largura de banda ideal para compartilhamento de aplicativos. O valor padrão é 1 milhão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitação de largura de banda aceitável para compartilhamento de aplicativos. O valor padrão é 500000.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td></td>
<td><p>A taxa de porcentagem ideal para blocos "danificados" para classificar uma qualidade de compartilhamento de aplicativos. Esse valor é a porcentagem do conteúdo do participante do compartilhamento que não tinha chegado ao visualizador. O conteúdo pode ser descartado (ou danificados) quando o participante do compartilhamento descarta blocos da fonte gráfica ou os blocos do ASMCU descartam os blocos do participante do compartilhamento, respectivamente. O valor padrão é 11%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td></td>
<td><p>cceptable a taxa de porcentagem para blocos "danificados" para classificar uma qualidade de compartilhamento de aplicativos. Esse valor é a porcentagem do conteúdo do participante do compartilhamento que não tinha chegado ao visualizador. O conteúdo pode ser descartado (ou danificados) quando o participante do compartilhamento descarta blocos da fonte gráfica ou os blocos do ASMCU descartam os blocos do participante do compartilhamento, respectivamente. O valor padrão é 36%.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Esta coluna não é usada no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Esta coluna não é usada no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Esta coluna não é usada no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Esta coluna não é usada no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Esta coluna não é usada no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Esta coluna não é usada no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor ideal para o atraso unidirecional relativo entre os dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,0 segundos.</p>
<p>A coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor ideal para o atraso unidirecional relativo entre os dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,75 segundos.</p>
<p>A coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>O valor ideal da latência média de processamento de bloco RDP no servidor de conferência as na duração da sessão de exibição. Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.</p>
<p>Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores. O valor padrão é 200ms.</p>
<p>A coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor aceitável da latência média de processamento de bloco RDP no servidor de conferência as na duração da sessão de exibição. Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.</p>
<p>Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores. O valor padrão é 200ms.</p>
<p>A coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

