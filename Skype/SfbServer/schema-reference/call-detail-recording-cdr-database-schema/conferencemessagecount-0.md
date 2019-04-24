---
title: Exibir ConferenceMessageCount
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: f2290eef7d2738831ed3ce72c794a36659858b8b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213708"
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
   

