---
title: Tabela ConferenceUris no Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.
ms.openlocfilehash: b9d9903a90717043a6e86f9efcbfdeb4adc073a4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417484"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabela ConferenceUris no Skype for Business Server 2015
 
A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primário  <br/> |Carimbo de hora, Interno usado.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o URI desta conferência.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI da conferência.  <br/> |
|**Soma de verificação** <br/> |int  <br/> ||Soma de verificação do ConferenceUri. Usado para aumentar a velocidade de pesquisas no banco de dados.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Tipo de URI, por exemplo, conf:chat para conferência IM ou conf:audio-video para conferência de áudio/vídeo. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

