---
title: Exibir ConferenceMessageCount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: ce94cd13637b70b87a92fd688ca8ce8aefd2c69e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901412"
---
# <a name="conferencemessagecount-view"></a>Exibir ConferenceMessageCount
 
A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
> [!NOTE]
> A exibição ConferenceMessageCount contém todas as colunas na [ConferenceSessionDetails view](conferencesessiondetails.md) além das colunas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário que enviou a mensagem.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que enviou as mensagens. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**UserTenant** <br/> |Identificador exclusivo  <br/> |Locatário do usuário que enviou as mensagens. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Número de mensagens enviadas pelo usuário durante a sessão de conferência.  <br/> |
   

