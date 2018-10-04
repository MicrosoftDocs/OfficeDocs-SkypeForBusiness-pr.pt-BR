---
title: Tabela VideoMetricsThreshold
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: A tabela VideoMetricsThreshold contém valores ótimos e aceitáveis para as métricas de qualidade da experiência usadas com chamadas de vídeo.
ms.openlocfilehash: b5a62f15720779c7830e6b6bf097be7d045d8f7a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375664"
---
# <a name="videometricsthreshold-table"></a>Tabela VideoMetricsThreshold
 
A tabela VideoMetricsThreshold contém valores ótimos e aceitáveis para as métricas de qualidade da experiência usadas com chamadas de vídeo.
  

| **Coluna**                                               | **Tipo de dados**       | **Chave/índice**  | **Detalhes**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primária  <br/> | Tipo de chamada feita.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | O valor padrão é 0.05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | O valor padrão é 0.10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | O valor padrão é 5.0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | O valor padrão é 10.0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | O valor padrão é 12.0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | O valor padrão é 7.0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | O valor padrão é 5.0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | decimal(5,2)  <br/> |                | O valor padrão é 10.0 /  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | O valor padrão é 5.0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | O valor padrão é 10.0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | O valor padrão é 0.05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | O valor padrão é 0.10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | O valor padrão é 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | O valor padrão é 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | O valor padrão é 5.00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | O valor padrão é 10.00.  <br/>   |

