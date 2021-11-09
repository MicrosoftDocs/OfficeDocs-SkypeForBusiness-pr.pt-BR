---
title: Tabela SessionCorrelation
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa um CorrelationID usado para correlacionar várias sessões.
ms.openlocfilehash: 706bd5c47d1a709712c7178562e535612f61332c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834899"
---
# <a name="sessioncorrelation-table"></a>Tabela SessionCorrelation
 
A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa um CorrelationID usado para correlacionar várias sessões. 
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Soma de verificação** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse Servidor de Conferência A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Unique  <br/> |As sessões correlacionadas terão a mesma ID de correlação.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Apenas para uso interno.  <br/> |
   

