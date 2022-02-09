---
title: Tabela AppSharingStream
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: A tabela AppSharingStream contém medidas de qualidade da experiência dos fluxos de rede usados no compartilhamento de aplicativos. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 69313a2885f954245460963f119619fb2b91c8d6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398525"
---
# <a name="appsharingstream-table"></a>Tabela AppSharingStream
 
A tabela AppSharingStream contém medidas de qualidade da experiência dos fluxos de rede usados no compartilhamento de aplicativos. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primário, externo  <br/> |Data e hora de início da sessão.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário, externo  <br/> |Identificador sequencial usado para distinguir entre sessões que foram iniciadas na mesma data e na mesma hora.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário, externo  <br/> | Consulte [MediaLine Table](./medialine-0.md). <br/> |
|**StreamID** <br/> |int  <br/> |Primário  <br/> |Identificador exclusivo do fluxo de compartilhamento de aplicativos.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Tremulação máxima detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Quantidade média (em milissegundos) exigida para que um pacote de protocolo de transporte em tempo real viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||Quantidade máxima (em milissegundos) exigida para que um pacote de protocolo de transporte em tempo real viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**PacketLossRate** <br/> |flutuação  <br/> ||Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**PacketLossRateMax** <br/> |flutuação  <br/> ||Taxa máxima de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Número de pacotes enviados.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||Largura de banda unidirecional estimada disponível no final da sessão. Reportada em bits por segundo.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Descrição da carga do compartilhamento de aplicativos.  <br/> |
|**RelativeOneWayTotal** <br/> |flutuação  <br/> ||Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> |
|**RelativeOneWayAverage** <br/> |flutuação  <br/> ||Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> |
|**RelativeOneWayMax** <br/> |flutuação  <br/> ||Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de ocorrências de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |flutuação  <br/> ||Densidade total de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |flutuação  <br/> ||Duração total de intermitências unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de ocorrências de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapDensity** <br/> |flutuação  <br/> ||Densidade total de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapDuration** <br/> |flutuação  <br/> ||Duração total de intervalos unidirecionais. Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo; as lacunas indicam atrasos entre essas invasões. Esta medida avalia o fluxo de dados entre o cliente e o servidor.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||Função do aplicativo (participante do compartilhamento ou visualizador) e tipo de conteúdo.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |flutuação  <br/> ||O tempo total de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |flutuação  <br/> ||Tempo médio de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |flutuação  <br/> ||Tempo máximo de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |flutuação  <br/> ||Densidade da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |flutuação  <br/> ||Duração da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "estourada" é uma transmissão em que os dados fluem em intermediações imprevisíveis em vez de um fluxo contínuo.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalos no tempo de processamento de blocos de protocolo RDP (RDP).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |flutuação  <br/> ||Densidade do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Uma baixa densidade do intervalo significa uma melhor experiência de exibição.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |flutuação  <br/> ||Duração do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Uma baixa densidade de intervalo significa uma melhor experiência de exibição.  <br/> |
|**CaptureTileRateTotal** <br/> |flutuação  <br/> ||Taxa total de blocos capturados (em blocos por segundo)  <br/> |
|**CaptureTileRateAverage** <br/> |flutuação  <br/> ||Taxa média de blocos capturados (em blocos por segundo)  <br/> |
|**CaptureTileRateMax** <br/> |flutuação  <br/> ||Taxa máxima de blocos capturados (em blocos por segundo)  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)  <br/> |
|**CaptureTileRateBurstDensity** <br/> |flutuação  <br/> ||Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)  <br/> |
|**CaptureTileRateBurstDuration** <br/> |flutuação  <br/> ||Duração da intermitência na taxa de blocos capturados (em blocos por segundo)  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)  <br/> |
|**CaptureTileRateGapDensity** <br/> |flutuação  <br/> ||Densidade do intervalo na taxa de blocos capturados (em blocos por segundo)  <br/> |
|**CaptureTileRateGapDuration** <br/> |flutuação  <br/> ||Duração do intervalo na taxa de blocos capturados (em blocos por segundo)  <br/> |
|**SpoiledTilePercentTotal** <br/> |flutuação  <br/> ||Porcentagem total do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentAverage** <br/> |flutuação  <br/> ||Porcentagem média do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentMax** <br/> |flutuação  <br/> ||Porcentagem máxima do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |flutuação  <br/> ||Densidade da intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |flutuação  <br/> ||Duração da intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |flutuação  <br/> ||Densidade do intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |flutuação  <br/> ||Duração do intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.  <br/> |
|**ScrapingFrameRateTotal** <br/> |flutuação  <br/> ||Número total de quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateAverage** <br/> |flutuação  <br/> ||Número médio de quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateMax** <br/> |flutuação  <br/> ||Número máximo de quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |flutuação  <br/> ||Densidade da intermitência nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |flutuação  <br/> ||Duração da intermitência nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |flutuação  <br/> ||Densidade do intervalo nos quadros retirados da origem de gráficos.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |flutuação  <br/> ||Duração do intervalo nos quadros retirados da origem de gráficos.  <br/> |
|**IncomingTileRateTotal** <br/> |flutuação  <br/> ||Taxa de quadros total de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateAverage** <br/> |flutuação  <br/> ||Taxa de quadros média de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateMax** <br/> |flutuação  <br/> ||Taxa de blocos máxima de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |flutuação  <br/> ||Densidade da intermitência na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |flutuação  <br/> ||Duração da intermitência na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateGapDensity** <br/> |flutuação  <br/> ||Densidade do intervalo na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingTileRateGapDuration** <br/> |flutuação  <br/> ||Duração do intervalo na taxa de blocos de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateTotal** <br/> |flutuação  <br/> ||Taxa de quadros total de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateAverage** <br/> |flutuação  <br/> ||Taxa de quadros média de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateMax** <br/> |flutuação  <br/> ||Taxa de quadros média de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |flutuação  <br/> ||Densidade da intermitência na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |flutuação  <br/> ||Duração da intermitência na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |flutuação  <br/> ||Densidade do intervalo na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**IncomingFrameRateDuration** <br/> |flutuação  <br/> ||Duração do intervalo na taxa de quadros de entrada como recebida pelo visualizador.  <br/> |
|**OutgoingTileRateTotal** <br/> |flutuação  <br/> ||Taxa de blocos total de saída para o emissor.  <br/> |
|**OutgoingTileRateAverage** <br/> |flutuação  <br/> ||Taxa de blocos média de saída para o emissor.  <br/> |
|**OutgoingTileRateMax** <br/> |flutuação  <br/> ||Taxa de blocos máxima de saída para o emissor.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |flutuação  <br/> ||Densidade da intermitência na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |flutuação  <br/> ||Duração da intermitência na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |flutuação  <br/> ||Densidade do intervalo na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |flutuação  <br/> ||Duração do intervalo na taxa de blocos de saída para o emissor.  <br/> |
|**OutgoingFrameRateTotal** <br/> |flutuação  <br/> ||Taxa de quadros total de saída para o emissor.  <br/> |
|**OutgoingFrameRateAverage** <br/> |flutuação  <br/> ||Taxa de quadros média de saída para o emissor.  <br/> |
|**OutgoingFrameRateMax** <br/> |flutuação  <br/> ||Taxa de quadros máxima de saída para o emissor.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |flutuação  <br/> ||Densidade da intermitência na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |flutuação  <br/> ||Duração da intermitência na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de intervalo na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |flutuação  <br/> ||Densidade do intervalo na taxa de quadros de saída para o emissor.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |flutuação  <br/> ||Duração do intervalo na taxa de quadros de saída para o emissor.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Altura média da resolução de vídeo em pixels.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Largura média da resolução de vídeo em pixels.  <br/> |
|**Entrada** <br/> |bit  <br/> ||Taxa de quadros média (em quadros por segundo) para transmissões de entrada.  <br/> |
|**Saída** <br/> |bit  <br/> ||Taxa de quadros média (em quadros por segundo) para transmissões de saída.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 significa que a direção do fluxo é do chamador para o receptor.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
