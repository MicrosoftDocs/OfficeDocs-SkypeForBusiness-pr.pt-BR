---
title: Tabela VideoMetricsThreshold
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: A tabela VideoMetricsThreshold contém os melhores valores e aceitáveis para as métricas de Qualidade da Experiência usada com chamadas de vídeo.
ms.openlocfilehash: 1885e1d5bfbea10ffed518aaedcc8bf47a2b5217c333c187eaf2a2ee0dc7b0d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339997"
---
# <a name="videometricsthreshold-table"></a>Tabela VideoMetricsThreshold
 
A tabela VideoMetricsThreshold contém os melhores valores e aceitáveis para as métricas de Qualidade da Experiência usada com chamadas de vídeo.
  

| **Coluna**                                               | **Tipo de dados**       | **Chave/Índice**  | **Detalhes**                          |
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

