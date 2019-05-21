---
title: Tabela VideoStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Cada registro representa um fluxo de vídeo. Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.
ms.openlocfilehash: 678f8b14fb3746ddd50a83ebd68c3878237908e4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294520"
---
# <a name="videostream-table"></a>Tabela VideoStream
 
Cada registro representa um fluxo de vídeo. Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |R referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**Streamid** <br/> |int  <br/> |Primária  <br/> |ID exclusiva dentro de uma linha de mídia.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Estrangeiro, primário  <br/> |Descrição da carga. Consulte a [tabela PayloadDescription](payloaddescription.md) para obter mais informações. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maior tremulação de rede durante a sessão de vídeo.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo de ida e volta das estatísticas do RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo máximo de ida e volta do fluxo de vídeo.  <br/> |
|**PacketLossRate** <br/> |decimal (5, 4)  <br/> | <br/> |Taxa média de perda de pacotes durante a chamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal (5, 4)  <br/> | <br/> |Perda máxima de pacote observado durante a chamada.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Contagem de pacotes para o fluxo de vídeo (protocolo de transporte em tempo real, RTP).  <br/> |
|**Largura de banda** <br/> |int  <br/> | <br/> |Estimativas de largura de banda para o fluxo de vídeo.  <br/> |
|**VideoResolution** <br/> |caractere (9)  <br/> | <br/> |Resolução do vídeo em largura de pixels multiplicada pela altura de pixels. Relatado como uma cadeia de caracteres.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Taxa média de bits do fluxo de vídeo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal (9, 4)  <br/> | <br/> |A taxa de quadros de vídeo recebida.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal (9, 4)  <br/> | <br/> |A taxa de quadros de vídeo enviada.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |A taxa máxima de bits de vídeo durante a sessão de vídeo.  <br/> |
|**VideoFrameLossRate** <br/> |decimal (9, 4)  <br/> | <br/> |A porcentagem total de quadros de vídeo perdidos.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Não disponível.  <br/> |
|**À** <br/> |decimal (9, 4)  <br/> ||A porcentagem total de quadros de vídeo perdidos.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava na resolução de formato de intercâmbio (CIF) comum.  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava na resolução VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava a HD720 resolução.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada sem depósito de quadro.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada com B frame drop.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Porcentagem da duração da chamada com o depósito de quadros BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Porcentagem da duração da chamada com o BPSP frame drop.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Porcentagem da duração da chamada com o BPSPI frame drop.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Os dados de fluxo no lado do receptor são recebidos.  <br/> |
|**Saída** <br/> |bit  <br/> | <br/> |Dados de fluxo no lado do remetente são recebidos.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que a direção do fluxo é do chamador para o chamado.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica a porcentagem do tempo em que a chamada estava em um estado de congestionamento de perda.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada dos pacotes de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica a porcentagem do tempo quando a chamada estava competindo pelos recursos de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Valor mínimo de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Valor máximo de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||O desvio padrão da estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Valor médio da estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Porcentagem da chamada na qual o ponto de extremidade determinou que a conexão de rede não pôde dar suporte a vídeo MultiView.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Valor total de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**À** <br/> |float  <br/> ||Valor médio de uma latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Valor máximo de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de ocorrências intermitentes unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densidade total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duração total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de ocorrências de espaçamento unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidade total do espaço unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duração total unidirecional do espaço. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**À** <br/> |decimal (9, 4)  <br/> ||Taxa de perda de pacotes de vídeo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Quantidade média de largura de banda alocada para vídeo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Exterior  <br/> |Tipo de codecs de vídeo usados pelo remetente. Consulte a [tabela CodecDescription](codecdescription.md) para obter mais informações. <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Largura da resolução usada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Altura da resolução usada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Transmissão média de taxa de quadros de vídeo usada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Taxa máxima de bits do remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Taxa média de bits para o remetente.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Número máximo de fluxos de vídeo usados pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Exterior  <br/> |Códigos de vídeo usados pelo destinatário. Consulte a [tabela CodecDescription](codecdescription.md) para obter mais informações. <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Largura da resolução usada pelo destinatário.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Altura da resolução usada pelo destinatário.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**À** <br/> |float  <br/> ||Taxa média de quadros de vídeo usada pelo destinatário.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Taxa máxima de bits do destinatário.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Taxa média de bits para o destinatário.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Máximo de fluxos de vídeo para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Fluxos de vídeo mínimos para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modo de vídeo (por exemplo, galeria ou único fluxo) para o destinatário.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**À FEC PLR** <br/> |float  <br/> ||Taxa de perda de pacote após a aplicação da correção de erro de encaminhamento.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**À** <br/> |float  <br/> ||Porcentagem de tempo que o sinalizador de recurso dinâmico estava ativo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |caractere (9)  <br/> ||Resolução mínima medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Porcentagem da chamada abaixo do limite de baixa taxa de bits (70 quilobits por segundo).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**À** <br/> |float  <br/> ||Porcentagem da chamada abaixo do limite de baixa taxa de quadros (7,5 quadros por segundo, entrada).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**À** <br/> |float  <br/> ||Porcentagem da chamada ocorrida na resolução mais baixa.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Duração da chamada em segundos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indica se os dados foram agregados de várias chamadas.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

