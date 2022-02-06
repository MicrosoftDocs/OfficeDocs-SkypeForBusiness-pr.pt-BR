---
title: Tabela SessionCorrelation
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
---

# <a name="sessioncorrelation-table"></a>Tabela SessionCorrelation
 
A tabela SessionCorrelation é uma tabela de suporte. Cada registro representa um CorrelationID usado para correlacionar várias sessões. 
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**Soma de verificação** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica esse Servidor de Conferência A/V.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Unique  <br/> |As sessões correlacionadas terão a mesma ID de correlação.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |Apenas para uso interno.  <br/> |
   

