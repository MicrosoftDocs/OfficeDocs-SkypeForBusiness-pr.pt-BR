---
title: 'Lync Server 2013: Tabela AudioStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Tabela AudioStream no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

Cada registro representa um fluxo de áudio. Uma linha de mídia de áudio geralmente contém dois fluxos de áudio.


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
<td><p>datetime</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primária</p></td>
<td><p>Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Streamid</strong></p></td>
<td><p>int</p></td>
<td><p>Primária</p></td>
<td><p>ID exclusiva dentro de uma linha de mídia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maior tremulação de rede durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Taxa média de perda de pacotes durante a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Perda máxima de pacote observado durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Densidade média de perda de pacote durante intermitências de perdas durante a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Duração média da perda de pacote durante intermitências de perdas durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>Densidade média de perda de pacote durante intervalos entre intermitências de perda de pacote.</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Duração média de lacunas entre intermitências de perda de pacote.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Núm</p></td>
<td><p> </p></td>
<td><p>Contagem de pacotes para o fluxo de áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Largura de banda</strong></p></td>
<td><p>Núm</p></td>
<td><p> </p></td>
<td><p>Estimativas de largura de banda para o fluxo de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Degradação do MOS de rede para toda a chamada. O intervalo é de 0,0 a 5,0. Essa métrica mostra o valor que o MOS de rede foi reduzido devido à instabilidade e à perda de pacote. Para ter uma qualidade aceitável, ele deve ser menor do que 0,5.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Degradação do MOS de rede máxima durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Degradação de MOS de rede causada pela tremulação.</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Degradação de MOS de rede causada por perda de pacote.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>Exterior</p></td>
<td><p>O codec de áudio usado para a chamada, referenciado pela tabela PayloadDescription.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Taxa de amostragem do fluxo de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tempo de ida e volta das estatísticas do RTCP. Para ter uma qualidade aceitável, isso deve ser menor que 100 milhões.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tempo máximo de ida e volta do fluxo de áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>Banda larga médio de um MOS de rede para a chamada. Essa métrica depende da perda de pacotes, da tremulação e do codec usados. O intervalo é de [1,0 a 5,0].</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>A banda larga de rede mínima para a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>A média de Pontuação estimada banda larga de escuta do MOS para áudio enviado, incluindo o nível de fala, o nível de ruído e as características do dispositivo de captura.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>A SendListenMOS mínima para a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>A média de Pontuação estimada banda larga de escuta do MOS para áudio recebido da rede, incluindo o nível de fala, o nível de ruído, o codec, as condições de rede e as características do dispositivo de captura.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>decimal (3; 2)</p></td>
<td><p> </p></td>
<td><p>A RecvListenMOS mínima para a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Sinalizador que indica se o FEC de áudio foi usado para a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td></td>
<td><p>Índice médio de amostras ocultas geradas pelo reparo de áudio para amostras típicas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td></td>
<td><p>Índice médio de amostras ampliadas geradas pelo reparo de áudio para amostras típicas.</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>decimal (5; 2)</p></td>
<td></td>
<td><p>Índice médio de amostras compactadas geradas pelo reparo de áudio para amostras típicas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Entrada</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Os dados de fluxo no lado do receptor são recebidos.</p></td>
</tr>
<tr class="even">
<td><p><strong>Saída</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Dados de fluxo no lado do remetente são recebidos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que a direção do fluxo é do chamador para o receptor.</p>
<p>0 significa que a direção do fluxo é do receptor para o chamador.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Desvio padrão de tempos de chegada de tremulação.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Índice máximo de pacotes ocultados pelo REO reparo.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Desvio padrão da taxa de pacotes ocultados pelo REO reparo.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa de pacotes removidos pelo REO reparo em comparação ao número total de pacotes recebidos.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa de pacotes de correção de erro usados encaminhar em comparação com o número total de pacotes recebidos.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Número máximo de pacotes de áudio que foram compactados pelo REO reparo.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica a porcentagem do tempo em que a chamada estava em um estado de congestionamento de perda.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada dos pacotes de rede.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica a porcentagem do tempo quando a chamada estava competindo pelos recursos de rede.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Valor mínimo de estimativa de largura de banda medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Valor máximo de estimativa de largura de banda medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>O desvio padrão da estimativa de largura de banda medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Valor médio da estimativa de largura de banda medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor total de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor médio de uma latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valor máximo de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Total de ocorrências intermitentes unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Total de ocorrências de espaçamento unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Densidade total do espaço unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração total unidirecional do espaço. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem da chamada decodificada como estéreo.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem da chamada renderizada como estéreo pelo cancelador de eco acústico.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa de perda de pacote após a aplicação da correção de erro de encaminhamento.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem da chamada codificada como estéreo.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem da chamada capturada como estéreo pelo cancelador de eco acústico.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

