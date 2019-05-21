---
title: Tabela AudioStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: Cada registro representa um fluxo de áudio. Uma linha de mídia de áudio geralmente contém dois fluxos de áudio.
ms.openlocfilehash: eae96b08f3a365288f48b7a68c75d3fd9114107d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295045"
---
# <a name="audiostream-table"></a>Tabela AudioStream
 
Cada registro representa um fluxo de áudio. Uma linha de mídia de áudio geralmente contém dois fluxos de áudio.
  
|Coluna|Tipo de dados|Chave/índice|Detalhes|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**Streamid** <br/> |int  <br/> |Primária  <br/> |ID exclusiva dentro de uma linha de mídia.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Maior tremulação de rede durante a chamada.  <br/> |
|**PacketLossRate** <br/> |decimal (5, 4)  <br/> | <br/> |Taxa média de perda de pacotes durante a chamada.  <br/> |
|**PacketLossRateMax** <br/> |decimal (5, 4)  <br/> | <br/> |Perda máxima de pacote observado durante a chamada.  <br/> |
|**BurstDensity** <br/> |decimal (9, 4)  <br/> | <br/> |Densidade média de perda de pacote durante intermitências de perdas durante a chamada.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |Duração média da perda de pacote durante intermitências de perdas durante a chamada.  <br/> |
|**BurstGapDensity** <br/> |decimal (9, 4)  <br/> | <br/> |Densidade média de perda de pacote durante intervalos entre intermitências de perda de pacote.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |Duração média de lacunas entre intermitências de perda de pacote.  <br/> |
|**PacketUtilization** <br/> |Núm  <br/> | <br/> |Contagem de pacotes para o fluxo de áudio.  <br/> |
|**Largura de banda** <br/> |Núm  <br/> | <br/> |Estimativas de largura de banda para o fluxo de áudio.  <br/> |
|**DegradationAvg** <br/> |decimal (3; 2)  <br/> | <br/> |Degradação do MOS de rede para toda a chamada. O intervalo é de 0,0 a 5,0. Essa métrica mostra o valor que o MOS de rede foi reduzido devido à instabilidade e à perda de pacote. Para ter uma qualidade aceitável, ele deve ser menor do que 0,5.  <br/> |
|**DegradationMax** <br/> |decimal (3; 2)  <br/> | <br/> |Degradação do MOS de rede máxima durante a chamada.  <br/> |
|**DegradationJitterAvg** <br/> |decimal (3; 2)  <br/> | <br/> |Degradação de MOS de rede causada pela tremulação.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal (3; 2)  <br/> | <br/> |Degradação de MOS de rede causada por perda de pacote.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Exterior  <br/> |O codec de áudio usado para a chamada, referenciado pela tabela PayloadDescription.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |Taxa de amostragem do fluxo de áudio.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Tempo de ida e volta das estatísticas do RTCP. Para ter uma qualidade aceitável, isso deve ser menor que 100 milhões.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Tempo máximo de ida e volta do fluxo de áudio.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal (3; 2)  <br/> | <br/> |Banda larga médio de um MOS de rede para a chamada. Essa métrica depende da perda de pacotes, da tremulação e do codec usados. O intervalo é de [1,0 a 5,0].  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal (3; 2)  <br/> | <br/> |A banda larga de rede mínima para a chamada.  <br/> |
|**SendListenMOS** <br/> |decimal (3; 2)  <br/> | <br/> |A média de Pontuação estimada banda larga de escuta do MOS para áudio enviado, incluindo o nível de fala, o nível de ruído e as características do dispositivo de captura.  <br/> |
|**SendListenMOSMin** <br/> |decimal (3; 2)  <br/> | <br/> |A SendListenMOS mínima para a chamada.  <br/> |
|**RecvListenMOS** <br/> |decimal (3; 2)  <br/> | <br/> |A média de Pontuação estimada banda larga de escuta do MOS para áudio recebido da rede, incluindo o nível de fala, o nível de ruído, o codec, as condições de rede e as características do dispositivo de captura.  <br/> |
|**RecvListenMOSMin** <br/> |decimal (3; 2)  <br/> | <br/> |A RecvListenMOS mínima para a chamada.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||Sinalizador que indica se o FEC de áudio foi usado para a chamada.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal (5; 2)  <br/> ||Índice médio de amostras ocultas geradas pelo reparo de áudio para amostras típicas.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal (5; 2)  <br/> ||Índice médio de amostras ampliadas geradas pelo reparo de áudio para amostras típicas.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal (5; 2)  <br/> ||Índice médio de amostras compactadas geradas pelo reparo de áudio para amostras típicas.  <br/> |
|**Entrada** <br/> |bit  <br/> | <br/> |Os dados de fluxo no lado do receptor são recebidos.  <br/> |
|**Saída** <br/> |bit  <br/> | <br/> |Dados de fluxo no lado do remetente são recebidos.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 significa que a direção do fluxo é do chamador para o receptor.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||Desvio padrão de tempos de chegada de tremulação.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Índice máximo de pacotes ocultados pelo REO reparo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||Desvio padrão da taxa de pacotes ocultados pelo REO reparo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Taxa de pacotes removidos pelo REO reparo em comparação ao número total de pacotes recebidos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||Taxa de pacotes de correção de erro usados encaminhar em comparação com o número total de pacotes recebidos.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Número máximo de pacotes de áudio que foram compactados pelo REO reparo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Indica a porcentagem do tempo em que a chamada estava em um estado de congestionamento de perda.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Indica a porcentagem da chamada durante a qual o congestionamento foi causado pela chegada atrasada dos pacotes de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Indica a porcentagem do tempo quando a chamada estava competindo pelos recursos de rede.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Valor mínimo de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Valor máximo de estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||O desvio padrão da estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Valor médio da estimativa de largura de banda medida durante a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Valor total de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**À** <br/> |float  <br/> ||Valor médio de uma latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Valor máximo de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de ocorrências intermitentes unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidade total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duração total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de ocorrências de espaçamento unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidade total do espaço unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duração total unidirecional do espaço. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||Porcentagem da chamada decodificada como estéreo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||Porcentagem da chamada renderizada como estéreo pelo cancelador de eco acústico.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||Taxa de perda de pacote após a aplicação da correção de erro de encaminhamento.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||Porcentagem da chamada codificada como estéreo.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||Porcentagem da chamada capturada como estéreo pelo cancelador de eco acústico.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
