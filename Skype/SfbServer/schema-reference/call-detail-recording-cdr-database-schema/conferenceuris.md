---
title: Tabela ConferenceUris Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: A tabela de ConfereneUris é uma tabela de suporte que armazena uma lista de uma conferência diversos URIs que tenham participado em sessões de conferência registradas no banco de dados. Cada registro na tabela representa um URI de conferência.
ms.openlocfilehash: 921bb448ffe50d62aa7680db0e8097c186eef8e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabela ConferenceUris Skype para Business Server 2015
 
A tabela de ConfereneUris é uma tabela de suporte que armazena uma lista de uma conferência diversos URIs que tenham participado em sessões de conferência registradas no banco de dados. Cada registro na tabela representa um URI de conferência.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primária  <br/> |Carimbo de hora, interno usado.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica o URI desta conferência.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI da conferência.  <br/> |
|**Soma de verificação** <br/> |int  <br/> ||Soma de verificação de ConferenceUri. Usado para aumenta a velocidade de pesquisas de banco de dados.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Externa  <br/> |Tipo de URI, como conf:chat para conferência de mensagem Instantânea ou conf:audio-vídeo para conferência de áudio/vídeo. Consulte a tabela de [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
   

