---
title: Tabela SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões.
ms.openlocfilehash: 4efd1aeba45fb12aee646c401f492450f375aa20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907077"
---
# <a name="sessioncorrelation-table"></a>Tabela SessionCorrelation
 
A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa uma CorrelationID que é utilizado para correlacionar múltiplas sessões. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Soma de verificação** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica A / V Conferencing Server.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Exclusivo  <br/> |Sessões que são correlacionadas terão o mesmo ID de correlação.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Somente para uso interno.  <br/> |
   

