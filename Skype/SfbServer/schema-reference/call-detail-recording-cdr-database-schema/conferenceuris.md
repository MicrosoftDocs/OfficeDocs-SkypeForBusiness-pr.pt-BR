---
title: Tabela ConferenceUris no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 7d7f0ea8504faa3e23d981a74e65062fdb6d5836
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744017"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabela ConferenceUris no Skype for Business Server 2015
 
A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primário  <br/> |Carimbo de hora, Interno usado.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o URI desta conferência.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI da conferência.  <br/> |
|**Soma de verificação** <br/> |int  <br/> ||Soma de verificação do ConferenceUri. Usado para aumentar a velocidade de pesquisas no banco de dados.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Tipo de URI, por exemplo, conf:chat para conferência IM ou conf:audio-video para conferência de áudio/vídeo. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

