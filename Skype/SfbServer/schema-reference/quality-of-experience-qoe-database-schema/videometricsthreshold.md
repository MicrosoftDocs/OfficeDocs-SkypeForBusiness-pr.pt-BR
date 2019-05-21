---
title: Tabela VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: A tabela VideoMetricsThreshold contém os valores ideais e aceitáveis para as métricas de qualidade da experiência usadas com chamadas com vídeo.
ms.openlocfilehash: a923334596ea6b3e6b56c43682be0f0f6a640f15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294534"
---
# <a name="videometricsthreshold-table"></a>Tabela VideoMetricsThreshold
 
A tabela VideoMetricsThreshold contém os valores ideais e aceitáveis para as métricas de qualidade da experiência usadas com chamadas com vídeo.
  

| **Coluna**                                               | **Tipo de dados**       | **Chave/índice**  | **Detalhes**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primária  <br/> | Tipo de chamada que foi feita.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal (5; 2)  <br/> |                | O valor padrão é 0, 5.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal (5; 2)  <br/> |                | O valor padrão é 0,10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal (5; 2)  <br/> |                | O valor padrão é 5,0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal (5; 2)  <br/> |                | O valor padrão é 10,0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal (9, 4)  <br/> |                | O valor padrão é 12, 0.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal (9, 4)  <br/> |                | O valor padrão é 7, 0.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal (5; 2)  <br/> |                | O valor padrão é 5,0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | decimal (5; 2)  <br/> |                | O valor padrão é 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal (5; 2)  <br/> |                | O valor padrão é 5,0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal (5; 2)  <br/> |                | O valor padrão é 10,0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | O valor padrão é 0, 5.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | O valor padrão é 0,10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | O valor padrão é 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | O valor padrão é 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal (5; 2)  <br/> |                | O valor padrão é 5, 0.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal (5; 2)  <br/> |                | O valor padrão é 10, 0.  <br/>   |

