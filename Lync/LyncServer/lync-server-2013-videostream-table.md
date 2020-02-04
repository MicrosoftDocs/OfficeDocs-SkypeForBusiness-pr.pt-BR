---
title: 'Lync Server 2013: Tabela VideoStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Tabela VideoStream no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-12-13_

Cada registro representa um fluxo de vídeo. Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.


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
<td><p>R referenciada na <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</p></td>
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
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>Estrangeiro, primário</p></td>
<td><p>Descrição da carga. Consulte a <a href="lync-server-2013-payloaddescription-table.md">tabela PayloadDescription no Lync Server 2013</a> para obter mais informações.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Maior tremulação de rede durante a sessão de vídeo.</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tempo de ida e volta das estatísticas do RTCP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Tempo máximo de ida e volta do fluxo de vídeo.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Taxa média de perda de pacotes durante a chamada.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal (5, 4)</p></td>
<td><p> </p></td>
<td><p>Perda máxima de pacote observado durante a chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Contagem de pacotes para o fluxo de vídeo (protocolo de transporte em tempo real, RTP).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Largura de banda</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Estimativas de largura de banda para o fluxo de vídeo.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>caractere (9)</p></td>
<td><p> </p></td>
<td><p>Resolução do vídeo em largura de pixels multiplicada pela altura de pixels. Relatado como uma cadeia de caracteres.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Taxa média de bits do fluxo de vídeo.</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>A taxa de quadros de vídeo recebida.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>A taxa de quadros de vídeo enviada.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>A taxa máxima de bits de vídeo durante a sessão de vídeo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td><p> </p></td>
<td><p>A porcentagem total de quadros de vídeo perdidos.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Não disponível.</p></td>
</tr>
<tr class="odd">
<td><p><strong>À</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td></td>
<td><p>A porcentagem total de quadros de vídeo perdidos.</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>A porcentagem da chamada que estava na resolução de formato de intercâmbio (CIF) comum.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>A porcentagem da chamada que estava na resolução VGA.</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>A porcentagem da chamada que estava a HD720 resolução.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Porcentagem de duração da chamada sem depósito de quadro.</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Porcentagem de duração da chamada com B frame drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Porcentagem da duração da chamada com o depósito de quadros BP.</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Porcentagem da duração da chamada com o BPSP frame drop.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>Porcentagem da duração da chamada com o BPSPI frame drop.</p></td>
</tr>
<tr class="even">
<td><p><strong>Entrada</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Os dados de fluxo no lado do receptor são recebidos.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Saída</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Dados de fluxo no lado do remetente são recebidos.</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 significa que a direção do fluxo é do chamador para o chamado.</p>
<p>0 significa que a direção do fluxo é do receptor para o chamador.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica a porcentagem do tempo em que a chamada estava em um estado de congestionamento de perda.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada dos pacotes de rede.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Indica a porcentagem do tempo quando a chamada estava competindo pelos recursos de rede.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Valor mínimo de estimativa de largura de banda medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Valor máximo de estimativa de largura de banda medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>O desvio padrão da estimativa de largura de banda medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Valor médio da estimativa de largura de banda medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem da chamada na qual o ponto de extremidade determinou que a conexão de rede não pôde dar suporte a vídeo MultiView.</p>
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
<td><p>int</p></td>
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
<td><p><strong>À</strong></p></td>
<td><p>decimal (9, 4)</p></td>
<td></td>
<td><p>Taxa de perda de pacotes de vídeo.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Quantidade média de largura de banda alocada para vídeo.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Exterior</p></td>
<td><p>Tipo de codecs de vídeo usados pelo remetente. Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largura da resolução usada pelo remetente.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Altura da resolução usada pelo remetente.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Transmissão média de taxa de quadros de vídeo usada pelo remetente.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Taxa máxima de bits do remetente.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Taxa média de bits para o remetente.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Número máximo de fluxos de vídeo usados pelo remetente.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>Exterior</p></td>
<td><p>Códigos de vídeo usados pelo destinatário. Consulte a <a href="lync-server-2013-codecdescription-table.md">tabela CodecDescription no Lync Server 2013</a> para obter mais informações.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Largura da resolução usada pelo destinatário.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Altura da resolução usada pelo destinatário.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa média de quadros de vídeo usada pelo destinatário.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Taxa máxima de bits do destinatário.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Taxa média de bits para o destinatário.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Máximo de fluxos de vídeo para o receptor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Fluxos de vídeo mínimos para o receptor.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Modo de vídeo (por exemplo, galeria ou único fluxo) para o destinatário.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>À FEC PLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Taxa de perda de pacote após a aplicação da correção de erro de encaminhamento.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>À</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem de tempo que o sinalizador de recurso dinâmico estava ativo.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>caractere (9)</p></td>
<td></td>
<td><p>Resolução mínima medida durante a chamada.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem da chamada abaixo do limite de baixa taxa de bits (70 quilobits por segundo).</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem da chamada abaixo do limite de baixa taxa de quadros (7,5 quadros por segundo, entrada).</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>À</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Porcentagem da chamada ocorrida na resolução mais baixa.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Duração da chamada em segundos.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indica se os dados foram agregados de várias chamadas.</p>
<p>Esta coluna foi introduzida no Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

