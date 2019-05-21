---
title: Tabela SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa um CorrelationId, que é usado para correlacionar várias sessões.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294653"
---
# <a name="sessioncorrelation-table"></a>Tabela SessionCorrelation
 
A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa um CorrelationId, que é usado para correlacionar várias sessões. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Prova** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse servidor de conferência A/V.  <br/> |
|**CorrelationId** <br/> |nvarchar(256)  <br/> |Exclusividade  <br/> |As sessões correlacionadas terão a mesma ID de correlação.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Somente para uso interno.  <br/> |
   

