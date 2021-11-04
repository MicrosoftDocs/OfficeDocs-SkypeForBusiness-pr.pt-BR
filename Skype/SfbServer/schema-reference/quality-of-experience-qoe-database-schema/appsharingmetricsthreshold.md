---
title: Tabela AppSharingMetricsThreshold
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: A tabela AppSharingMetricsThreshold contém valores ideais e aceitáveis de métricas de Qualidade de Experiência usadas no compartilhamento de aplicativos. Esses limites são usado para determinar se a experiência de compartilhamento de aplicativos deve ser classificada como inadequada.
ms.openlocfilehash: d11c19886feebd77ff8b8dda262d969eb76c6434
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759353"
---
# <a name="appsharingmetricsthreshold-table"></a>Tabela AppSharingMetricsThreshold
 
A tabela AppSharingMetricsThreshold contém valores ideais e aceitáveis de métricas de Qualidade de Experiência usadas no compartilhamento de aplicativos. Esses limites são usado para determinar se a experiência de compartilhamento de aplicativos deve ser classificada como inadequada.
  
Esta tabela foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primário  <br/> |Tipo de chamada feita.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitação de largura de banda ideal para compartilhamento de aplicativos. O valor padrão é 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitação de largura de banda aceitável para compartilhamento de aplicativos. O valor padrão é 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||Taxa percentual ideal para blocos "estragados" para classificar uma qualidade de Compartilhamento de Aplicativos. Esse valor é o percentual de conteúdo do compartilhador que não alcançou o visualizador. O conteúdo pode ser descartado (ou danificado) quando o compartilhador descarta blocos da origem gráfica ou os blocos ASMCU descartam blocos do compartilhador, respectivamente. O valor padrão é 11%.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||Taxa percentual aceitável para blocos "estragados" para classificar uma qualidade de Compartilhamento de Aplicativos. Esse valor é o percentual de conteúdo do compartilhador que não alcançou o visualizador. O conteúdo pode ser descartado (ou danificado) quando o compartilhador descarta blocos da origem gráfica ou os blocos ASMCU descartam blocos do compartilhador, respectivamente. O valor padrão é 36%.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |flutuação  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |flutuação  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |flutuação  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |flutuação  <br/> ||Esta coluna não é usada no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |flutuação  <br/> ||Valor ideal do atraso unidirecional relativo entre dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,0 segundo.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |flutuação  <br/> ||Valor ideal do atraso unidirecional relativo entre dois pontos de extremidade de mídia envolvidos no compartilhamento de aplicativos. Esta é uma medida de latência de salto único. O valor padrão é 1,75 segundo.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |flutuação  <br/> ||Valor ideal da latência média de processamento de blocos RDP no Servidor de Conferência AS pelo tempo da sessão de visualização. Latência é a diferença de tempo entre quando o Quadro inicial é codificado no servidor (sharer ou MCU, dependendo do cenário) e o mesmo Quadro inicial é decodificado no visualizador.  <br/> Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode ter atrasos médios maiores. O valor padrão é 200 ms.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |flutuação  <br/> ||Valor aceitável da latência média de processamento de blocos RDP no Servidor de Conferência AS pelo tempo da sessão de visualização. Latência é a diferença de tempo entre quando o Quadro inicial é codificado no servidor (sharer ou MCU, dependendo do cenário) e o mesmo Quadro inicial é decodificado no visualizador.  <br/> Uma média alta reflete um atraso maior na experiência de visualização. Um servidor de conferência sobrecarregado pode ter atrasos médios maiores. O valor padrão é 200 ms.  <br/> A coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

