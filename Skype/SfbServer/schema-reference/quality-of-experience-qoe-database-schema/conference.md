---
title: Tabela Conference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: A tabela de conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a>Tabela Conference
 
A tabela de conferência é uma tabela de suporte. Cada registro representa uma conferência ou sessão ponto a ponto.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o registro desta conferência.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |exclusivo  <br/> |Caso se trate de uma conferência ou DialogID se este de URI de conferência é uma sessão ponto a ponto.  <br/> |
|**Soma de verificação** <br/> |int  <br/> |índice  <br/> |Soma de verificação o URI de conferência. Isso é usado internamente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Somente para uso interno.  <br/> |
   

