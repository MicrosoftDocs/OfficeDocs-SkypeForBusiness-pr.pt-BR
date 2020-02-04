---
title: 'Lync Server 2013: tabela AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a>Tabela AppSharingStream no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-21_

A tabela AppSharingStream contém métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos. Esta tabela foi introduzida no Microsoft Lync Server 2013.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dateTime</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Data e hora em que a sessão foi iniciada.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Identificador sequencial usado para distinguir entre as sessões iniciadas na mesma data e ao mesmo tempo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primário, estrangeiro</p></td>
<td><p>Representa o tipo de linha de vídeo usado na chamada. Os valores permitidos são:</p>
<ul>
<li><p>0 – áudio</p></li>
<li><p>1 – vídeo</p></li>
<li><p>2 – vídeo panorâmico</p></li>
<li><p>3 – compartilhamento de aplicativos/área de trabalho</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Streamid</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Identificador exclusivo do fluxo de compartilhamento de aplicativos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medida do &quot;shakiness&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Variação máxima detectada entre as entradas do pacote RTP. (Tremulação é uma medida do &quot;shakiness&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantidade média (em milissegundos) exigida para que um pacote de protocolo RTP viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</p>
<p>Os valores altos de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>A quantidade máxima de (em milissegundos) necessária para que um pacote de protocolo de transporte em tempo real vá para outro ponto de extremidade e, em seguida, retorne. Tempos de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</p>
<p>Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa máxima de perda de pacotes do protocolo de transporte em tempo real (RTP). (A perda de pacote ocorre quando pacotes RTP, um protocolo usado para a transmissão de áudio e vídeo pela Internet, não atinge seu destino.) Tarifas de alta perda são geralmente causadas por congestionamento; falta de largura de banda; congestionamento ou interferência sem fio; ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número de pacotes enviados.</p></td>
</tr>
<tr class="even">
<td><p><strong>Largura de banda</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largura de banda unidirecional estimada disponível no final da sessão. Relatado em bits por segundo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Descrição da carga de compartilhamento de aplicativos.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor total de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>À</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor médio de uma latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor máximo de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Total de ocorrências intermitentes unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Total de ocorrências de espaçamento unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade total do espaço unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração total unidirecional do espaço. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar (256)</p></td>
<td></td>
<td><p>Função do aplicativo (compartilhamento ou visualizador) e tipo de conteúdo.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tempo total de processamento para blocos RDP (protocolo de área de trabalho remota). Um total maior equivale a um atraso mais longo na experiência de visualização.</p></td>
</tr>
<tr class="odd">
<td><p><strong>À</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tempo médio de processamento de blocos RDP (protocolo de área de trabalho remota). Um total maior equivale a um atraso mais longo na experiência de visualização.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Tempo máximo de processamento de blocos RDP (protocolo de área de trabalho remota). Um total maior equivale a um atraso mais longo na experiência de visualização.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências intermitentes no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota). Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de intermitência no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota). Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração da intermitência no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota). Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de lacunas no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota).</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de espaço no bloco tempo de processamento de blocos RDP (protocolo de área de trabalho remota). A densidade de lacunas baixas equivale a uma melhor experiência de exibição.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração do espaço no bloco de tempo de processamento para blocos RDP (protocolo de área de trabalho remota). Durações de espaço curto equivalem a uma melhor experiência de exibição.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa total de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa média de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa máxima de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>em t</p></td>
<td></td>
<td><p>Ocorrências intermitentes na taxa de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de intermitência na taxa de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração da intermitência na taxa de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de lacunas na taxa de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade da lacuna na taxa de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração do espaçamento na taxa de blocos capturados (em blocos por segundo).</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>A porcentagem total do conteúdo que não chegou ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>A porcentagem média do conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>A porcentagem máxima do conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartada e sobrescrita pelo conteúdo novo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>As ocorrências de intermitência do conteúdo que não chegavam ao visualizador foram descartadas e sobrescritas pelo conteúdo novo.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de intermitência para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>A duração da intermitência para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>As ocorrências de lacunas do conteúdo que não chegavam ao visualizador foram descartadas e sobrescritas pelo conteúdo novo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de espaço para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração do espaço para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Número total de quadros recortedos da fonte de elementos gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Número médio de quadros recortes da fonte de elementos gráficos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Número máximo de quadros recortes da fonte de elementos gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências intermitentes nos quadros recortes da fonte gráfica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de intermitência nos quadros recapturada da fonte de elementos gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>A duração da intermitência nos quadros é recapturada da fonte de elementos gráficos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de lacunas nos quadros recortes da fonte gráfica.</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de lacunas nos quadros recortes da fonte gráfica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Intervalo de tempo nos quadros recortes da fonte de elementos gráficos.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa de quadro de entrada total conforme recebido pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa média de quadros recebidos, conforme recebido pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa máxima de bloco de entrada recebido pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de intermitência na taxa de peça de entrada recebidas pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de intermitência na taxa de peça de entrada como recebida pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração da intermitência na taxa de peça de entrada como recebida pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de lacunas na taxa de peça de entrada recebidas pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de espaço na taxa de peça de entrada como recebida pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração do espaçamento na taxa de peça de entrada como recebida pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa de quadro de entrada total conforme recebido pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa média de quadros recebidos, conforme recebido pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa máxima de quadros de entrada, conforme recebido pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de intermitência na taxa de quadros de entrada conforme recebidas pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de intermitência na taxa de quadros de entrada como recebida pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração da intermitência na taxa de quadros de entrada como recebida pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de lacunas na taxa de quadros de entrada recebidas pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de espaço na taxa de quadros de entrada como recebida pelo Visualizador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração do espaçamento na taxa de quadro de entrada como recebida pelo Visualizador.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa total de blocos de saída para o remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa média de peça de saída para o remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa máxima de bloco de saída para o remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de intermitência na taxa de bloco de saída para o remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de intermitência na taxa de peça de saída do remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração da intermitência na taxa de peça de saída do remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de lacunas na taxa de bloco de saída para o remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de espaço na taxa de bloco de saída para o remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração do espaçamento na taxa de peça de saída para o remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa de quadros de saída total para o remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>taxa média de quadros de saída para o remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa máxima de quadros de saída para o remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências intermitentes na taxa de quadros de saída do remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade de intermitência na taxa de quadros de saída do remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração da intermitência na taxa de quadros de saída do remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Ocorrências de lacunas na taxa de quadros de saída do remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade da lacuna na taxa de quadros de saída do remetente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração do espaçamento na taxa de quadros de saída do remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Altura média da resolução de vídeo em pixels.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largura média da resolução de vídeo em pixels.</p></td>
</tr>
<tr class="even">
<td><p><strong>Entrada</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Taxa média de quadros (em quadros por segundo) para transmissões de entrada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saída</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Taxa média de quadros (em quadros por segundo) para transmissões de saída.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>1 significa que a direção do fluxo é do chamador para o chamado.</p>
<p>0 significa que a direção do fluxo é do receptor para o chamador.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

