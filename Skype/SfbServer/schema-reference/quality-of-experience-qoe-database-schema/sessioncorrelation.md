---
title: Tabela SessionCorrelation
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões.
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a>Tabela SessionCorrelation
 
A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões. 
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Soma de verificação** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica A / V Conferencing Server.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |Sessões que são correlacionadas terão o mesmo ID de correlação.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Somente para uso interno.  <br/> |
   

