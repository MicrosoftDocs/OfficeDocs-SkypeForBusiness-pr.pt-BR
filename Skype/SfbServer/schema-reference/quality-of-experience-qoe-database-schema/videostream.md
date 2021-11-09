---
title: Tabela VideoStream
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Cada registro representa um fluxo de vídeo. Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.
ms.openlocfilehash: 5e1b566db7ee3f79219835055d6e617beeea6da6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863248"
---
# <a name="videostream-table"></a>Tabela VideoStream
 
Cada registro representa um fluxo de vídeo. Uma linha de mídia de vídeo geralmente contém dois fluxos de vídeo.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |R Referenciado da tabela [MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primário  <br/> |Identificação exclusiva em uma linha de mídia.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Foreign, Primary  <br/> |Descrição da carga. Consulte [a tabela PayloadDescription para](payloaddescription.md) obter mais informações. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Média de tremulação de rede a partir da estatística do protocolo RTCP.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Tremidação máxima da rede durante a sessão de vídeo.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo de ida e volta de estatísticas RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo máximo de viagem de ida e volta para o fluxo de vídeo.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Taxa média de perda de pacotes durante a chamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Perda máxima de pacotes observada durante a chamada.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Contagem de pacotes do stream de vídeo (Protocolo de Transporte em Tempo Real, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Estimativas de largura de banda para o fluxo de vídeo.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Resolução de vídeo obtida através da multiplicação dos pixel de altura e de largura. Relatada como uma sequência de caracteres.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Taxa de transmissão do stream de vídeo.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |A taxa de quadros de vídeo recebida.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |A taxa de quadros de vídeo enviada.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |A taxa máxima de bits de vídeo durante a sessão de vídeo.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |A porcentagem do total de quadros de vídeo perdidos.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Indisponível.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||A porcentagem do total de quadros de vídeo perdidos.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava na resolução CIF (Common Interchange Format).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava na resolução do VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||A porcentagem da chamada que estava na resolução HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada sem nenhuma queda de quadro.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada com a queda de quadro B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Porcentagem da duração da chamada com a queda do quadro BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Porcentagem da duração da chamada com a queda do quadro BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Porcentagem de duração da chamada com a queda do quadro BPSPI.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Os dados de fluxo no lado do receptor são recebidos.  <br/> |
|**Saída** <br/> |bit  <br/> | <br/> |Os dados de fluxo no lado do remetente são recebidos.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que a direção do fluxo é do chamador para o receptor.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
|**LossCongestionPercent** <br/> |flutuação  <br/> ||Indica a porcentagem do tempo em que a chamada estava em um estado de congestionamento de perda.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |flutuação  <br/> ||Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |flutuação  <br/> ||Indica a porcentagem do tempo em que a chamada estava competindo por recursos de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantidade mínima de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantidade máxima de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desvio padrão da estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantidade média de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |flutuação  <br/> ||Porcentagem da chamada em que o ponto de extremidade determinou que a conexão de rede não poderia suportar vídeo de multivisão.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |flutuação  <br/> ||Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |flutuação  <br/> ||Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |flutuação  <br/> ||Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de ocorrências de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Densidade total de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |flutuação  <br/> ||Duração total de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de ocorrências de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |flutuação  <br/> ||Densidade total de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |flutuação  <br/> ||Duração total de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||Taxa de perda dos pacotes de vídeo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Valor médio da largura de banda alocada para vídeo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Foreign  <br/> |Tipo de codecs de vídeo usados pelo remetente. Consulte a [tabela CodecDescription para](codecdescription.md) obter mais informações. <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Largura da resolução usada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Altura de resolução usada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |flutuação  <br/> ||Transmissão média da taxa de quadros de vídeo usada pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Taxa de bits máxima para o remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Taxa média de bits para o remetente.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Número máximo de fluxos de vídeo usados pelo remetente.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Foreign  <br/> |Códigos de vídeo usados pelo receptor. Consulte a [tabela CodecDescription para](codecdescription.md) obter mais informações. <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Largura de resolução usada pelo receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Altura de resolução usada pelo receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |flutuação  <br/> ||Taxa média de quadros de vídeo usada pelo receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Taxa de bits máxima para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Taxa média de bits para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Fluxos de vídeo máximos para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Fluxos mínimos de vídeo para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Modo de vídeo (por exemplo, galeria ou fluxo único) para o receptor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |flutuação  <br/> ||Taxa de perda de pacotes após a aplicação da correção de erro de encaminhamento.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |flutuação  <br/> ||Porcentagem de tempo em que o sinalizador de recurso dinâmico estava ativo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Resolução mínima medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |flutuação  <br/> ||Porcentagem da chamada abaixo do limite de taxa de bits baixo (70 quilobits por segundo).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |flutuação  <br/> ||Porcentagem da chamada abaixo do limite de taxa de quadros baixo (7,5 quadros por segundo, entrada).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |flutuação  <br/> ||Porcentagem da chamada que ocorreu na resolução mais baixa.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |flutuação  <br/> ||Comprimento da chamada em segundos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Indica se os dados foram agregados de várias chamadas.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

