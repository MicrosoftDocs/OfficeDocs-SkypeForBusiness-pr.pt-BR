---
title: Tabela ConferenceUris no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816131"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabela ConferenceUris no Skype for Business Server 2015
 
A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primário  <br/> |Carimbo de hora, Interno usado.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo que identifica o URI desta conferência.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI da conferência.  <br/> |
|**Soma de verificação** <br/> |int  <br/> ||Soma de verificação do ConferenceUri. Usado para aumentar a velocidade de pesquisas no banco de dados.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Externo  <br/> |Tipo de URI, por exemplo, conf:chat para conferência IM ou conf:audio-video para conferência de áudio/vídeo. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

