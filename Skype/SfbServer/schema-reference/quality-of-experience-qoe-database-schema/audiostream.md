---
title: Tabela AudioStream
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Cada registro representa um fluxo de áudio. Uma linha de mídia de áudio geralmente contém dois fluxos de áudio.
ms.openlocfilehash: 0ca913e042b988d20aad644af65fed7970d2afa8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763249"
---
# <a name="audiostream-table"></a>Tabela AudioStream
 
Cada registro representa um fluxo de áudio. Uma linha de mídia de áudio geralmente contém dois fluxos de áudio.
  
|Coluna|Tipo de dados|Chave/Índice|Detalhes|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primário  <br/> |Identificação exclusiva em uma linha de mídia.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Média de tremulação de rede a partir da estatística do protocolo RTCP.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Tremulação máxima da rede durante a chamada.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |Taxa média de perda de pacotes durante a chamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |Perda máxima de pacotes observada durante a chamada.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidade média de perda de pacotes durante as estouros de perdas durante a chamada.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Duração média de perda de pacote durante picos de perdas durante a chamada.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Duração média de intervalos entre picos de perda de pacotes.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |Contagem de pacotes para o fluxo de áudio.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |Estimativas de largura de banda para o fluxo de áudio.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradação de MOS de rede para a chamada completa. O intervalo vai de 0,0 a 5,0. Essa métrica mostra o quanto o MOS de rede foi reduzido por causa de tremulação e perda de pacote. Para obter a qualidade aceitável, o MOS da rede deve ser menor que 0,5.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |Degradação máxima de MOS de rede durante a chamada.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradação de MOS de rede causada por tremulação.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |Degradação de MOS de rede causada por perda de pacote.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Foreign  <br/> |O codec de áudio usado para a chamada, referenciado da Tabela PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Taxa de amostragem para o fluxo de áudio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo de ida e volta de estatísticas RTCP. Para uma qualidade aceitável, isso deve ser menor do que 100ms.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo máximo de ida e volta para o fluxo de áudio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |Média de MOS de rede de banda ampla para a chamada. Essa métrica depende da perda de pacote, da tremulação e do codec usado. O intervalo é [1,0 a 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |O MOS de rede de banda larga mínima para a chamada.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |A pontuação média de MOS de escuta de banda larga prevista para áudio enviado, incluindo o nível de fala, o nível de ruído e as características do dispositivo de captura.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |O mínimo SendListenMOS para a chamada.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |A pontuação média prevista de MOS de escuta de banda larga para áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições de rede e características do dispositivo de captura.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |O recvListenMOS mínimo para a chamada.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Sinalizador indicando se o FEC de áudio foi usado para a chamada.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Taxa média de amostras escondidas geradas pelo reparo de áudio para exemplos típicos.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Taxa média de amostras corrigidas geradas pelo reparo de áudio para exemplos típicos.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||Taxa média de amostras compactadas geradas pelo reparo de áudio para exemplos típicos.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Os dados de fluxo no lado do receptor são recebidos.  <br/> |
|**Saída** <br/> |bit  <br/> | <br/> |Os dados de fluxo no lado do remetente são recebidos.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que a direção do fluxo é do chamador para o chamador.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
|**JitterInterArrivalSD** <br/> |flutuação  <br/> ||Desvio padrão para tempos de chegada de tremidos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |flutuação  <br/> ||Taxa máxima de pacotes ocultos pelo curador.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |flutuação  <br/> ||Desvio padrão para a proporção de pacotes ocultos pelo curador.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |flutuação  <br/> ||Taxa de pacotes descartados pelo curador em comparação com o número total de pacotes recebidos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |flutuação  <br/> ||Taxa de pacotes de correção de erro de encaminhamento usados em comparação com o número total de pacotes recebidos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |flutuação  <br/> ||Número máximo de pacotes de áudio que foram compactados pelo curador.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |flutuação  <br/> ||Indica a porcentagem do tempo em que a chamada estava em um estado de congestionamento de perda.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |flutuação  <br/> ||Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada de pacotes de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |flutuação  <br/> ||Indica a porcentagem do tempo em que a chamada estava competindo por recursos de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Quantidade mínima de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Quantidade máxima de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Desvio padrão da estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Quantidade média de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |flutuação  <br/> ||Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |flutuação  <br/> ||Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |flutuação  <br/> ||Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de ocorrências de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |flutuação  <br/> ||Densidade total de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |flutuação  <br/> ||Duração total de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de ocorrências de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |flutuação  <br/> ||Densidade total de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |flutuação  <br/> ||Duração total de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |flutuação  <br/> ||Porcentagem da chamada decodificada como estéreo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |flutuação  <br/> ||Porcentagem da chamada renderizada como estéreo pelo cancelador de eco acústico.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |flutuação  <br/> ||Taxa de perda de pacotes após a aplicação da correção de erro de encaminhamento.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |flutuação  <br/> ||Porcentagem da chamada codificada como estéreo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |flutuação  <br/> ||Porcentagem da chamada capturada como estéreo pelo cancelador de eco acústico.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
