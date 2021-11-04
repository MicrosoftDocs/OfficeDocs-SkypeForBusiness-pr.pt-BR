---
title: Tabela VideoMetricsThreshold
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
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: A tabela VideoMetricsThreshold contém os melhores valores e aceitáveis para as métricas de Qualidade da Experiência usada com chamadas de vídeo.
ms.openlocfilehash: 08ebc41fd49fc29583059aa03601f9acc384c822
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741777"
---
# <a name="videometricsthreshold-table"></a>Tabela VideoMetricsThreshold
 
A tabela VideoMetricsThreshold contém os melhores valores e aceitáveis para as métricas de Qualidade da Experiência usada com chamadas de vídeo.
  

| **Column**                                               | **Tipo de dados**       | **Chave/Índice**  | **Detalhes**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primário  <br/> | Tipo de chamada realizada.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | O valor padrão é 0.05.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | O valor padrão é 0.10.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | O valor padrão é 5.0.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | O valor padrão é 10.0.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | O valor padrão é 12.0000.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | O valor padrão é 7.0000.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | O valor padrão é 5.0.  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | decimal(5,2)  <br/> |                | O valor padrão é 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | O valor padrão é 5.0.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | O valor padrão é 10.0.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | O valor padrão é 0.05.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | flutuação  <br/>        |                | O valor padrão é 0.10.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | flutuação  <br/>        |                | O valor padrão é 12.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | flutuação  <br/>        |                | O valor padrão é 7.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | O valor padrão é 5.00.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | O valor padrão é 10.00.  <br/>   |

