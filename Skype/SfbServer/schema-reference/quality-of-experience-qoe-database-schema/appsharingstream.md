---
title: Tabela AppSharingStream
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: A tabela AppSharingStream contém métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 1ebcfe16fe5863bcb3046e88ba5cdc2079f22a9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811099"
---
# <a name="appsharingstream-table"></a>Tabela AppSharingStream
 
A tabela AppSharingStream contém métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos. Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primário, estrangeiro  <br/> |Data e hora em que a sessão foi iniciada.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário, estrangeiro  <br/> |Identificador sequencial usado para distinguir entre as sessões iniciadas na mesma data e ao mesmo tempo.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário, estrangeiro  <br/> | Consulte [tabela de mídia](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0). <br/> |
|**Streamid** <br/> |int  <br/> |Primária  <br/> |Identificador exclusivo do fluxo de compartilhamento de aplicativos.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||Variação máxima detectada entre as entradas do pacote RTP. (Tremulação é uma medida do "shakiness" de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou um servidor de mídia sobrecarregado, resultando em áudio distorcido ou perdido.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||Quantidade média (em milissegundos) exigida para que um pacote de protocolo RTP viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||A quantidade máxima de (em milissegundos) necessária para que um pacote de protocolo de transporte em tempo real vá para outro ponto de extremidade e, em seguida, retorne. Tempos de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||Taxa máxima de perda de pacotes do protocolo de transporte em tempo real (RTP). (A perda de pacote ocorre quando pacotes RTP, um protocolo usado para a transmissão de áudio e vídeo pela Internet, não atinge seu destino.) Tarifas de alta perda são geralmente causadas por congestionamento; falta de largura de banda; congestionamento ou interferência sem fio; ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||Número de pacotes enviados.  <br/> |
|**Largura de banda** <br/> |int  <br/> ||Largura de banda unidirecional estimada disponível no final da sessão. Relatado em bits por segundo.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||Descrição da carga de compartilhamento de aplicativos.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Valor total de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> |
|**À** <br/> |float  <br/> ||Valor médio de uma latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Valor máximo de latência unidirecional. A latência unidirecional relativa mede o atraso entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Total de ocorrências intermitentes unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||Densidade total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Duração total de intermitência unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Total de ocorrências de espaçamento unidirecionais. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Densidade total do espaço unidirecional. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Duração total unidirecional do espaço. Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante; as lacunas indicam atrasos entre essas intermitências. Essa métrica mede o fluxo de dados entre o cliente e o servidor.  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)  <br/> ||Função do aplicativo (compartilhamento ou visualizador) e tipo de conteúdo.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||Tempo total de processamento para blocos RDP (protocolo de área de trabalho remota). Um total maior equivale a um atraso mais longo na experiência de visualização.  <br/> |
|**À** <br/> |float  <br/> ||Tempo médio de processamento de blocos RDP (protocolo de área de trabalho remota). Um total maior equivale a um atraso mais longo na experiência de visualização.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||Tempo máximo de processamento de blocos RDP (protocolo de área de trabalho remota). Um total maior equivale a um atraso mais longo na experiência de visualização.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||Ocorrências intermitentes no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota). Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||Densidade de intermitência no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota). Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||Duração da intermitência no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota). Uma transmissão "intermitente" é uma transmissão na qual os dados fluem em picos imprevisíveis em oposição a um fluxo constante.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||Ocorrências de lacunas no tempo de processamento dos blocos RDP (protocolo de área de trabalho remota).  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||Densidade de espaço no bloco tempo de processamento de blocos RDP (protocolo de área de trabalho remota). A densidade de lacunas baixas equivale a uma melhor experiência de exibição.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||Duração do espaço no bloco de tempo de processamento para blocos RDP (protocolo de área de trabalho remota). Durações de espaço curto equivalem a uma melhor experiência de exibição.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||Taxa total de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||Taxa média de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||Taxa máxima de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |em t  <br/> ||Ocorrências intermitentes na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||Densidade de intermitência na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de lacunas na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||Densidade da lacuna na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||Duração do espaçamento na taxa de blocos capturados (em blocos por segundo).  <br/> |
|**À** <br/> |float  <br/> ||A porcentagem total do conteúdo que não chegou ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||A porcentagem média do conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||A porcentagem máxima do conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartada e sobrescrita pelo conteúdo novo.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||As ocorrências de intermitência do conteúdo que não chegavam ao visualizador foram descartadas e sobrescritas pelo conteúdo novo.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||Densidade de intermitência para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||A duração da intermitência para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||As ocorrências de lacunas do conteúdo que não chegavam ao visualizador foram descartadas e sobrescritas pelo conteúdo novo.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||Densidade de espaço para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||Duração do espaço para o conteúdo que não tinha chegado ao visualizador, em vez disso, foi descartado e sobrescrito pelo novo conteúdo.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||Número total de quadros recortedos da fonte de elementos gráficos.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||Número médio de quadros recortes da fonte de elementos gráficos.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||Número máximo de quadros recortes da fonte de elementos gráficos.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências intermitentes nos quadros recortes da fonte gráfica.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||Densidade de intermitência nos quadros recapturada da fonte de elementos gráficos.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||A duração da intermitência nos quadros é recapturada da fonte de elementos gráficos.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de lacunas nos quadros recortes da fonte gráfica.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||Densidade de lacunas nos quadros recortes da fonte gráfica.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||Intervalo de tempo nos quadros recortes da fonte de elementos gráficos.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||Taxa de quadro de entrada total conforme recebido pelo Visualizador.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||Taxa média de quadros recebidos, conforme recebido pelo Visualizador.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||Taxa máxima de bloco de entrada recebido pelo Visualizador.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de peça de entrada recebidas pelo Visualizador.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||Densidade de intermitência na taxa de peça de entrada como recebida pelo Visualizador.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de peça de entrada como recebida pelo Visualizador.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de lacunas na taxa de peça de entrada recebidas pelo Visualizador.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||Densidade de espaço na taxa de peça de entrada como recebida pelo Visualizador.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||Duração do espaçamento na taxa de peça de entrada como recebida pelo Visualizador.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||Taxa de quadro de entrada total conforme recebido pelo Visualizador.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||Taxa média de quadros recebidos, conforme recebido pelo Visualizador.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||Taxa máxima de quadros de entrada, conforme recebido pelo Visualizador.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de quadros de entrada conforme recebidas pelo Visualizador.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||Densidade de intermitência na taxa de quadros de entrada como recebida pelo Visualizador.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de quadros de entrada como recebida pelo Visualizador.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de lacunas na taxa de quadros de entrada recebidas pelo Visualizador.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||Densidade de espaço na taxa de quadros de entrada como recebida pelo Visualizador.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||Duração do espaçamento na taxa de quadro de entrada como recebida pelo Visualizador.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||Taxa total de blocos de saída para o remetente.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||Taxa média de peça de saída para o remetente.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||Taxa máxima de bloco de saída para o remetente.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências de intermitência na taxa de bloco de saída para o remetente.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||Densidade de intermitência na taxa de peça de saída do remetente.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de peça de saída do remetente.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de lacunas na taxa de bloco de saída para o remetente.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||Densidade de espaço na taxa de bloco de saída para o remetente.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||Duração do espaçamento na taxa de peça de saída para o remetente.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||Taxa de quadros de saída total para o remetente.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||taxa média de quadros de saída para o remetente.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||Taxa máxima de quadros de saída para o remetente.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||Ocorrências intermitentes na taxa de quadros de saída do remetente.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||Densidade de intermitência na taxa de quadros de saída do remetente.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||Duração da intermitência na taxa de quadros de saída do remetente.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||Ocorrências de lacunas na taxa de quadros de saída do remetente.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||Densidade da lacuna na taxa de quadros de saída do remetente.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||Duração do espaçamento na taxa de quadros de saída do remetente.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||Altura média da resolução de vídeo em pixels.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||Largura média da resolução de vídeo em pixels.  <br/> |
|**Entrada** <br/> |bit  <br/> ||Taxa média de quadros (em quadros por segundo) para transmissões de entrada.  <br/> |
|**Saída** <br/> |bit  <br/> ||Taxa média de quadros (em quadros por segundo) para transmissões de saída.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 significa que a direção do fluxo é do chamador para o chamado.  <br/> 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
   

