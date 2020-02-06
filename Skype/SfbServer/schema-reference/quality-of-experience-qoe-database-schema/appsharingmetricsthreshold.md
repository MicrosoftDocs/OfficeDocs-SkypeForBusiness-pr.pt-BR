---
title: Tabela AppSharingMetricsThreshold
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
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: A tabela AppSharingMetricsThreshold contém os valores ideais e aceitáveis para as métricas de qualidade da experiência usadas com o compartilhamento de aplicativos. Esses limiares são usados para determinar se a experiência de compartilhamento de aplicativos deve ser classificada como ruim.
ms.openlocfilehash: 3639d9f2783b6433353f23d15e6ce063fb8ec49f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811379"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabela AppSharingMetricsThreshold
 
A tabela AppSharingMetricsThreshold contém os valores ideais e aceitáveis para as métricas de qualidade da experiência usadas com o compartilhamento de aplicativos. Esses limiares são usados para determinar se a experiência de compartilhamento de aplicativos deve ser classificada como ruim.
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primária  <br/> |Tipo de chamada que foi feita.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitação de largura de banda ideal para compartilhamento de aplicativos. O valor padrão é 1 milhão.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitação de largura de banda aceitável para compartilhamento de aplicativos. O valor padrão é 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal (5; 2)  <br/> ||A taxa de porcentagem ideal para blocos "danificados" para classificar uma qualidade de compartilhamento de aplicativos. Esse valor é a porcentagem do conteúdo do participante do compartilhamento que não tinha chegado ao visualizador. O conteúdo pode ser descartado (ou danificados) quando o participante do compartilhamento descarta blocos da fonte gráfica ou os blocos do ASMCU descartam os blocos do participante do compartilhamento, respectivamente. O valor padrão é 11%.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal (5; 2)  <br/> ||Taxa de porcentagem aceitável para blocos "danificados" para classificar uma qualidade de compartilhamento de aplicativos. Esse valor é a porcentagem do conteúdo do participante do compartilhamento que não tinha chegado ao visualizador. O conteúdo pode ser descartado (ou danificados) quando o participante do compartilhamento descarta blocos da fonte gráfica ou os blocos do ASMCU descartam os blocos do participante do compartilhamento, respectivamente. O valor padrão é 36%.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valor ideal para o atraso unidirecional relativo entre os dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,0 segundos.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valor ideal para o atraso unidirecional relativo entre os dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,75 segundos.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||O valor ideal da latência média de processamento de bloco RDP no servidor de conferência as na duração da sessão de exibição. Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.  <br/> Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores. O valor padrão é 200ms.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valor aceitável da latência média de processamento de bloco RDP no servidor de conferência as na duração da sessão de exibição. Latência é a diferença de tempo entre o momento em que o quadro inicial é codificado no servidor (participante do compartilhamento ou MCU, dependendo do cenário) e o mesmo quadro inicial é decodificado no visualizador.  <br/> Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores. O valor padrão é 200ms.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

