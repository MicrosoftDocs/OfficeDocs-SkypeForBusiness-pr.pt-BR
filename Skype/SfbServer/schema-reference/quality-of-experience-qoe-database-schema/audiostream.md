---
title: Tabela AudioStream
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Cada registro representa um fluxo de áudio. Uma linha de mídia de áudio normalmente contém dois fluxos de áudio.
ms.openlocfilehash: 7c1e7ae70a04aabc7db704aaaad873bc5b2100c9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212345"
---
# <a name="audiostream-table"></a>Tabela AudioStream
 
Cada registro representa um fluxo de áudio. Uma linha de mídia de áudio normalmente contém dois fluxos de áudio.
  
|Coluna|Tipo de dados|Chave/índice|Detalhes|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primária  <br/> |ID exclusiva dentro de uma linha de mídia.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Instabilidade média da rede estatísticas do protocolo de controle de Tempo Real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Tremulação máxima da rede durante a chamada.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Taxa de perda média de pacotes durante a chamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Perda máxima de pacotes observada durante a chamada.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidade média de perda de pacote durante picos de perdas durante a chamada.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Duração média de perda de pacote durante picos de perdas durante a chamada.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Duração média de intervalos entre picos de perda de pacotes.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Contagem de pacotes para o fluxo de áudio.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Estimativas de largura de banda para o fluxo de áudio.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradação de MOS de rede para a chamada inteira. O intervalo é 0,0 para 5.0. Essa métrica mostra a quantidade que de MOS de rede foi reduzido devido a tremulação e perda de pacotes. Para qualidade aceitável deveria menos que 0,5.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Degradação de MOS de rede máxima durante a chamada.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradação de MOS de rede causada por tremulação.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradação de MOS de rede causada por perda de pacotes.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Externa  <br/> |O Codec de áudio usado para a chamada, referenciada de PayloadDescription Table.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Taxa de amostragem para o fluxo de áudio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo de ida e volta de estatísticas RTCP. Para qualidade aceitável este deve ser menor que 100ms.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo máximo de ida e volta para o fluxo de áudio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Média de banda larga MOS de rede para a chamada. Essa métrica depende de perda de pacotes, tremulação e codec usado. O intervalo é [1.0 para 5.0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Banda larga mínima MOS de rede para a chamada.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |O MOS de escuta média prevista de banda ampla pontuação para áudio enviado, incluindo nível de fala, nível de ruído e características do dispositivo de captura.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |SendListenMOS mínimo para a chamada.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |A pontuação de MOS de escuta média prevista de banda ampla para áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições de rede e características do dispositivo de captura.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |O RecvListenMOS mínimo para a chamada.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Sinalizador que indica se o FEC de áudio foi usado para a chamada.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Taxa média de amostras escondidas geradas pelo Reparo de áudio para exemplos típicos.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Taxa média de amostras corrigidas geradas pelo Reparo de áudio para exemplos típicos.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Taxa média de amostras compactadas geradas pelo Reparo de áudio para exemplos típicos.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Dados de fluxo no lado do receptor são recebidos.  <br/> |
|**Saída** <br/> |bit  <br/> | <br/> |Dados de fluxo no lado do remetente são recebidos.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que a direção do fluxo é do chamador para o receptor.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Desvio padrão para tempos de chegada de tremulação.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Taxa máxima de pacotes de correção oculta.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Desvio padrão para o índice de pacotes de correção oculta.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Índice de pacotes deixados pela correção comparados ao número total de pacotes recebidos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Taxa de correção de erro usado encaminhados comparado com o número total de pacotes recebidos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Número máximo de pacotes de áudio comprimidos pela correção.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica a porcentagem de tempo em que a chamada esteve em um estado de congestionamento de perda.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica a porcentagem da chamada durante o qual um congestionamento causado pelo atraso na chegada de pacotes de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica a porcentagem de tempo quando uma chamada estava competindo por recursos de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantidade mínima de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantidade máxima de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desvio padrão da estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantidade média de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantidade total de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantidade média de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantidade máxima de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidade da intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duração da intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidade do intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duração do intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Porcentagem da chamada decodificada como estéreo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Porcentagem da chamada renderizada como estéreo pelo acoustic echo canceller.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Taxa de perda de pacotes após a correção de erro antecipada tiver sido aplicada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Porcentagem de chamadas codificadas como estéreo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Porcentagem da chamada capturada como estéreo pelo acoustic echo canceller.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
