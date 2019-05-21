---
title: Exibição ConferenceMessageCount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296487"
---
# <a name="conferencemessagecount-view"></a>Exibição ConferenceMessageCount
 
A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
> [!NOTE]
> A exibição ConferenceMessageCount contém todas as colunas na [exibição ConferenceSessionDetails](conferencesessiondetails.md) , além das colunas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |URL do usuário que enviou a mensagem.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que enviou as mensagens. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**Userlocatário** <br/> |identificador  <br/> |Locatário do usuário que enviou as mensagens. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Número de mensagens enviadas pelo usuário durante a sessão de conferência.  <br/> |
   

