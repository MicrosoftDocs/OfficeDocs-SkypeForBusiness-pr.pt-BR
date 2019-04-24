---
title: Tabela AppSharingMetricsThreshold
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: A tabela AppSharingMetricsThreshold contém valores ótimos e aceitáveis para as métricas de qualidade da experiência usadas com compartilhamento de aplicativos. Esses limites são usados para determinar se a experiência de compartilhamento de aplicativo deve ser classificado como insatisfatória.
ms.openlocfilehash: bddad99803ab6683985b0f44ed5df509b84344f3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212324"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabela AppSharingMetricsThreshold
 
A tabela AppSharingMetricsThreshold contém valores ótimos e aceitáveis para as métricas de qualidade da experiência usadas com compartilhamento de aplicativos. Esses limites são usados para determinar se a experiência de compartilhamento de aplicativo deve ser classificado como insatisfatória.
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primária  <br/> |Tipo de chamada feita.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitação de largura de banda otimizado para compartilhamento de aplicativos. O valor padrão é 1.000.000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitação de largura de banda aceitável para compartilhamento de aplicativos. O valor padrão é 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||Taxa de porcentagem ideal para blocos "estragados" para a classificação de uma qualidade de compartilhamento de aplicativos. Esse valor é a porcentagem do conteúdo do que o participante do compartilhamento que não chegou ao visualizador. Conteúdo pode ser descartado (ou estragado) quando o participante do compartilhamento descarta blocos da origem de gráficos ou o ASMCU organiza descarta organiza do compartilhador respectivamente. O valor padrão é % 11.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||Taxa de porcentagem aceitável para blocos "estragados" para a classificação de uma qualidade de compartilhamento de aplicativos. Esse valor é a porcentagem do conteúdo do que o participante do compartilhamento que não chegou ao visualizador. Conteúdo pode ser descartado (ou estragado) quando o participante do compartilhamento descarta blocos da origem de gráficos ou o ASMCU organiza descarta organiza do compartilhador respectivamente. O valor padrão é 36%.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valor ideal para o atraso unidirecional relativo entre os pontos de extremidade de duas mídias envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,0 segundos.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valor ideal para o atraso unidirecional relativo entre os pontos de extremidade de duas mídias envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,75 segundos.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valor ideal da média peça RDP processamento latência no servidor de conferência como em toda a duração da sessão de visualização. Latência é a diferença de horário entre quando o quadro Iniciar é codificado no servidor (participante do compartilhamento ou MCU dependendo do cenário) e o mesmo quadro iniciar está decodificado no Visualizador do.  <br/> Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores. O valor padrão é 200 ms.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valor aceitável da média peça RDP processamento latência no servidor de conferência como em toda a duração da sessão de visualização. Latência é a diferença de horário entre quando o quadro Iniciar é codificado no servidor (participante do compartilhamento ou MCU dependendo do cenário) e o mesmo quadro iniciar está decodificado no Visualizador do.  <br/> Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores. O valor padrão é 200 ms.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

