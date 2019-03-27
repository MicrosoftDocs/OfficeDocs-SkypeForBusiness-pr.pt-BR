---
title: Tabela VideoStream
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Cada registro representa um fluxo de vídeo. Normalmente, uma linha de mídia de vídeo contém dois fluxos de vídeo.
ms.openlocfilehash: d6eeeb96acc766859d6b57594bd11a5538593da3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881678"
---
# <a name="videostream-table"></a>Tabela VideoStream
 
Cada registro representa um fluxo de vídeo. Normalmente, uma linha de mídia de vídeo contém dois fluxos de vídeo.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |R referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primária  <br/> |ID exclusiva dentro de uma linha de mídia.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Externo, primário  <br/> |Descrição de carga. Consulte a [tabela PayloadDescription](payloaddescription.md) para obter mais informações. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Instabilidade média da rede estatísticas do protocolo de controle de Tempo Real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Tremulação máxima da rede durante a sessão de vídeo.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo de ida e volta de estatísticas RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo máximo de ida e volta do stream de vídeo.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Taxa de perda média de pacotes durante a chamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Perda máxima de pacotes observada durante a chamada.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Contagem de pacotes para o fluxo de vídeo (protocolo de transporte de Tempo Real, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Estimativas de largura de banda para o fluxo de vídeo.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Resolução do vídeo em pixels de largura multiplicado pelo pixels de altura. Relatado como uma cadeia de caracteres.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Taxa de bits média do fluxo de vídeo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |A taxa de quadros de vídeo recebida.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |A taxa de quadro de vídeo enviados.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |A taxa máxima de bits de vídeo durante a sessão de vídeo.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |A porcentagem do total de frames de vídeo perdidos.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Não disponível.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||A porcentagem do total de frames de vídeo perdidos.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava na resolução Common Interchange Format (CIF).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava na resolução VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava na resolução HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada com sem remoção de quadro.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada com remoção de quadro B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada com remoção de quadro BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada com remoção de quadro SP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada com o quadro bpsp.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Dados de fluxo no lado do receptor são recebidos.  <br/> |
|**Saída** <br/> |bit  <br/> | <br/> |Dados de fluxo no lado do remetente são recebidos.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que a direção do fluxo é do chamador para o receptor.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica a porcentagem de tempo em que a chamada esteve em um estado de congestionamento de perda.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica a porcentagem da chamada durante o qual um congestionamento causado pelo atraso na chegada de pacotes de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica a porcentagem de tempo quando uma chamada estava competindo por recursos de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantidade mínima de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantidade máxima de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desvio padrão da estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantidade média de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Porcentagem da chamada onde a extremidade determinou que a conexão de rede não pode suportar vídeos multiview.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantidade total de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantidade média de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantidade máxima de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densidade da intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duração da intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidade do intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duração do intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Taxa em que os pacotes de vídeo foram perdidos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Quantidade média de largura de banda alocada para vídeo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Externa  <br/> |Tipo de codecs de vídeo utilizados pelo remetente. Consulte a [tabela CodecDescription](codecdescription.md) para obter mais informações. <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Largura da resolução utilizada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Altura de resolução utilizada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Média de transmissão da taxa de quadro de vídeo utilizada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Taxa de bit máximo para o emissor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Taxa de bits média para o emissor.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Número máximo de fluxos de vídeo utilizada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Externa  <br/> |Códigos de vídeo utilizados pelo receptor. Consulte a [tabela CodecDescription](codecdescription.md) para obter mais informações. <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Largura da resolução utilizada pelo receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Altura de resolução utilizada pelo receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Taxa de quadros média de vídeo utilizada pelo receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Taxa de bit máximo para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Taxa de bits média para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Fluxos de vídeo máximos para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Fluxos de vídeo mínimos para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modo de vídeo (por exemplo, galeria ou fluxo único) para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Taxa de perda de pacotes após a correção de erro antecipada tiver sido aplicada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Porcentagem de tempo que o sinalizador de capacidade dinâmica esteve ativo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Resolução mínima medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Porcentagem da chamada abaixo do limiar da menor taxa de bits baixa (70 kilobits por segundo).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Porcentagem da chamada abaixo do limiar da taxa de quadros baixa (7.5 quadros por segundo, entrada).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Porcentagem da chamada que ocorreram na resolução mais baixa.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Comprimento da chamada em segundos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indica se os dados foram agregados a várias chamadas.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

