---
title: Tabela ConferenceUris no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: A tabela ConfereneUris é uma tabela de suporte que armazena uma lista de vários URIs de conferência que participaram de sessões de conferência registradas no banco de dados. Cada registro na tabela representa um URI de conferência.
ms.openlocfilehash: 60f9952fa1fcc5b1a1a651c44beaed894a387b81
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296389"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabela ConferenceUris no Skype for Business Server 2015
 
A tabela ConfereneUris é uma tabela de suporte que armazena uma lista de vários URIs de conferência que participaram de sessões de conferência registradas no banco de dados. Cada registro na tabela representa um URI de conferência.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primária  <br/> |Carimbo de data/hora, usado internamente.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse URI de conferência.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||URL da conferência.  <br/> |
|**Prova** <br/> |int  <br/> ||Soma de verificação de ConferenceUri. Usado para aumentar a velocidade das pesquisas do banco de dados.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Exterior  <br/> |Tipo de URI, como conf: chat para conferência de IM ou conf: áudio-vídeo para videoconferência/videoconferência. Consulte a tabela da [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
   

