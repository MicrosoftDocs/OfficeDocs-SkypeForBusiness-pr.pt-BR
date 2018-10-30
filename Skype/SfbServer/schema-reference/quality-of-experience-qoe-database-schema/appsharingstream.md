---
title: Tabela AppSharingStream
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: A tabela AppSharingStream contém as métricas de qualidade da experiência para os fluxos de rede usados para compartilhamento de aplicativos. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 3505467fd5e163fe2c26aca4b1ba13681c0d4ee6
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839709"
---
# <a name="appsharingstream-table"></a>Tabela AppSharingStream
 
A tabela AppSharingStream contém as métricas de qualidade da experiência para os fluxos de rede usados para compartilhamento de aplicativos. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primária, estrangeira  <br/> |Data e hora em que a sessão foi iniciada.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária, estrangeira  <br/> |Identificador sequencial usado para distinguir entre sessões que foram iniciadas na mesma data e ao mesmo tempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária, estrangeira  <br/> | Consulte a [Tabela MediaLine](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**StreamID** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo do fluxo de compartilhamento de aplicativo.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada "tremula".) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Tremulação máxima detectada entre entradas de pacotes RTP. (É uma medida de "shakiness" de uma chamada de tremulação.) Os valores de tremulação alta normalmente são causados por congestionamento ou um servidor de mídia sobrecarregado e resultam em áudio distorcido ou perdido.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Quantidade média (em milissegundos) exigida para que um pacote de protocolo RTP viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Quantidade máxima de (em milissegundos) necessária para um pacote de protocolo de transporte em tempo real para viajar para outro ponto de extremidade e, em seguida, novamente. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Taxa média de perda de pacotes de protocolo RTP. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, não chegam ao seu destino). As altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Taxa máxima de perda de pacote real-time Transport Protocol (RTP). (A perda de pacote ocorre quando há falha de pacotes RTP, um protocolo usado para transmitir áudio e vídeo através da Internet, para atingir seu destino.) Taxas de perda de alta são geralmente causadas por congestionamento; falta de largura de banda; congestionamento sem fio ou interferência; ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Número de pacotes enviados.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Estimado unidirecional largura de banda disponível no final da sessão. Relatado em bits por segundo.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Descrição da carga do compartilhamento de aplicativos.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Quantidade total de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Quantidade média de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Quantidade máxima de latência unidirecional. Latência de unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidade da intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duração da intermitência unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidade do intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duração do intervalo unidirecional total. Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo constante; lacunas indicam atrasos entre esses picos. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||Tipo de conteúdo e função de aplicativo (participante do compartilhamento ou visualizador).  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Tempo total de processamento de blocos de protocolo RDP (RDP). Um total de superior é igual a um atraso mais na experiência de visualização.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||Tempo médio de processamento de blocos de protocolo RDP (RDP). Um total de superior é igual a um atraso mais na experiência de visualização.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Tempo máximo de processamento de blocos de protocolo RDP (RDP). Um total de superior é igual a um atraso mais na experiência de visualização.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densidade da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Intermitência duração em que o tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão onde os fluxos de dados picos imprevisíveis em vez de um fluxo contínuo.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo no tempo de processamento de blocos de protocolo RDP (RDP).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densidade do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Densidade do intervalo baixa equivale a uma melhor experiência de exibição.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Duração do intervalo em que o tempo de processamento de blocos de protocolo RDP (RDP). Durações lacuna curto equiparar para uma melhor experiência de exibição.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Taxa total de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Taxa média de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Taxa máxima de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densidade da intermitência na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densidade do intervalo na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Duração do intervalo na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||Porcentagem total do conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||Porcentagem média do conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||Porcentagem máxima do conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Densidade da intermitência do conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Intermitência densidade para o conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||Duração do conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente da intermitência.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo do conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densidade do intervalo do conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Duração do intervalo do conteúdo que não chegou ao visualizador, mas foi em vez disso descartado e substituído por conteúdo recente.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Número total de quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Número médio de quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Número máximo de quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densidade da intermitência nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densidade do intervalo nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Duração do intervalo nos quadros retirados da origem de gráficos.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Total de taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Média de taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Taxa de blocos máxima de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densidade da intermitência na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densidade do intervalo na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Duração do intervalo na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Total de taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Média de taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Máximo taxa de quadros entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densidade da intermitência na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densidade do intervalo na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Duração do intervalo na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Taxa de blocos saída total para o emissor.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Taxa média de saída lado a lado para o emissor.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Taxa de blocos saída máximo para o emissor.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densidade da intermitência na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densidade do intervalo na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Duração do intervalo na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Taxa de quadros saída total para o emissor.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||taxa média de saída quadro para o emissor.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Taxa de quadros saída máximo para o emissor.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densidade da intermitência na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densidade do intervalo na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Duração do intervalo na taxa de quadros de saída para o emissor.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Média de altura de resolução de vídeo, em pixels.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Média de largura de resolução de vídeo, em pixels.  <br/> |
|**Entrada** <br/> |bit  <br/> ||Taxa de quadros média (em quadros por segundo) para transmissões de entrada.  <br/> |
|**Saída** <br/> |bit  <br/> ||Taxa de quadros média (em quadros por segundo) para transmissões de saída.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 significa que a direção do fluxo é do chamador para o receptor.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
   

