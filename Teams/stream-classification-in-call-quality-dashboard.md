---
title: Classificação de fluxo no Painel de Qualidade de Chamadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Saiba como a qualidade do fluxo é classificada no Painel de Qualidade de Chamadas para o Microsoft Teams e o Skype for Business Online.
ms.openlocfilehash: a04843e45e444da34bf065c1cdfbf0a619be9406
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541716"
---
# <a name="stream-classification-in-call-quality-dashboard"></a>Classificação de fluxo no Painel de Qualidade de Chamadas

The Call Quality Dashboard (CQD) for Microsoft Teams and Skype for Business Online allows you to gain insights into the quality of calls made using Microsoft Teams and Skype for Business services. This topic provides detailed information about the quality classification of media streams. To learn more about CQD and how to enable it, see [Turning on and using Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md).

## <a name="classifier-definitions"></a>Definições do classificador

Streams in CQD are classified as good, poor, or unclassified based on the values of the available key quality metrics. The metrics and conditions used to classify stream are shown in the tables below. CQD's "Poor Due To" dimensions can be used to understand which metric is responsible for a poor classification. See [Dimensions and measures available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for more information on these dimensions.

### <a name="audio-classifier"></a>Classificador de áudio

Um fluxo de áudio é marcado como ruim se uma ou mais das seguintes condições forem atendidas:

|**Métrica**|**Condição**|**Explicação**|
|:-----|:-----|:-----|
|Audio Degradation Avg|> 1,0|Average Network Mean Opinion Score degradation for stream. Represents how much the network loss and jitter has impacted the quality of received audio.|
|Round Trip|> 500|Tempo médio de propagação da rede de ida e volta calculado conforme especificado em RFC3550 em milissegundos.|
|Packet Loss Rate|> 0,1|Taxa média de perda de pacote do stream.|
|Jitter|> 30|Média de tremulação para stream em milissegundos.|
|Ratio Concealed Samples Avg|> 0,07|Taxa média do número de quadros de áudio com amostras escondidas geradas pelo reparo para o número total de quadros de áudio de perda de pacotes.|

### <a name="video-classifier"></a>Classificador de Vídeo

Um fluxo de vídeo é marcado como bom ou ruim com base no valor da primeira métrica disponível na seguinte ordem:

|**Etapa Nº**|**Métrica**|**Condição**|**Classificação se a condição for verdadeira**|**Classificação se a condição for falsa**|**Classificação se a métrica não estiver disponível**|**Explicação**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|gt _ 50% |Poor|Good|Seguir para a Etapa 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|<7|Poor|Good|Seguir para a Etapa 3|Média de quadros por segundo recebidos para um stream de vídeo calculados durante a sessão.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Taxa de perda de pacotes após ter sido aplicado FEC agregados entre todos os fluxos de vídeo e codecs.|

### <a name="vbss-classifier"></a>Classificador VBSS

Um fluxo VBSS é marcado como bom ou ruim com base no valor da primeira métrica disponível na seguinte ordem:

|**Etapa Nº**|**Métrica**|**Condição**|**Classificação se a condição for verdadeira**|**Classificação se a condição for falsa**|**Classificação se a métrica não estiver disponível**|**Explicação**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1|Video Local Frame Loss Percentage Avg|gt _ 50% |Poor|Good|Seguir para a Etapa 2|Average percentage of video frames lost as displayed to the user. This includes frames recovered from network losses.|
|2|Video Frame Rate Avg|< 2|Poor|Good|Seguir para a Etapa 3|Média de quadros por segundo recebidos para um stream de vídeo calculados durante a sessão.|
|3|Video Post FECPLR|> 0,15|Poor|Good|Unclassified|Taxa de perda de pacotes após ter sido aplicado FEC agregados entre todos os fluxos de vídeo e codecs.|

### <a name="application-sharing-classifier"></a>Classificador de compartilhamento de aplicativos

Um fluxo de compartilhamento de aplicativo é marcado como ruim se uma ou mais das seguintes condições forem atendidas:


| **Métrica**                                     | **Condição** | **Explicação**                                                                                                                                                                                                        |
|:-----------------------------------------------|:--------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Spoiled Tile Percent Total                     | >36          | Percentage of tiles that are discarded instead of being sent to a remote peer (for example, from the MCU to a viewer). Discarded (or spoiled) tiles may be caused by bandwidth restrictions between client and server. |
| AppSharing RDP Tile Processing Latency Average | gt _ 400         | Média de latência de blocos de processamento em milissegundos na pilha RDP no servidor de conferência.                                                                                                                          |
| AppSharing Relative OneWay Average             | > 1,75        | Atraso unidirecional relativo médio entre os pontos de extremidade em segundos para fluxos de compartilhamento de aplicativos.                                                                                                                       |

## <a name="unclassified-streams"></a>Fluxos não classificados

No CQD, um fluxo é marcado como não classificado quando a conectividade do ICE falha ou quando todas as métricas necessárias para calcular a classificação do fluxo não são relatadas.

To check for ICE connectivity failures, examine the dimensions "First Connectivity Ice" and "Second Connectivity Ice" for a "FAILED" value. If either value indicates a failure, the stream will be marked as unclassified.

If ICE connectivity succeeded for an unclassified stream, the stream is likely considered unclassified because key stream metrics were not reported. There are a few reasons these metrics may not be reported:

- **QoE reports were not received** - The metrics used for classification are reported in a QoE report sent at the end of a call. If this report is not produced (e.g., because some third-party endpoints may not send QoE) or was not able to be sent (e.g., because of a network outage), CQD is unable to classify the stream.

> [!TIP]
> The "QoE Record Available" dimension can be used to determine whether a QoE report was received for a stream. Note that this dimension will have a value of "True" if a QoE report was received from either endpoint. A QoE report from both endpoints is required for the most accurate reporting of metrics.

- **Short calls** - Short calls may not have enough media activity to compute key stream metrics. Without these metrics, CQD is unable to classify the stream.

> [!TIP]
> The dimensions "Duration (Seconds)", "Duration (Minutes)", "Duration 5 seconds or less", and "Duration 60 seconds or more" can be used to determine the duration of a stream. The measurement "Avg Call Duration" can also be used to compute the average duration for a set of streams.

- **Low packet utilization** - Like the "short call" scenario, sufficient packet utilization is required for computation of key stream metrics. Without these metrics, CQD is unable to classify the stream.
    - A common low packet utilization scenario occurs when a user joins a meeting to listen to the presenter but never speaks (likely muting the microphone for most of the call). In such a scenario, one audio stream will have high packet utilization (inbound to the client) while the other will have little to no packet utilization (outbound from the client). In this scenario, the duration of the stream may be an hour or longer but the packet utilization on the stream from the client to the server will be extremely low due to the microphone being muted, resulting in an unclassified stream.

> [!TIP]
> A dimensão "Utilização de pacote" e a medida "Utilização média de pacote" podem ser usadas para determinar a atividade de pacote de um fluxo.


## <a name="related-topics"></a>Tópicos Relacionados
[Ativando e usando o painel de controle de qualidade de chamada (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Dimensões e medidas disponíveis no Painel de Qualidade de Chamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)
