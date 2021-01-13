---
title: Exibição ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Esta exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813291"
---
# <a name="conferencemessagecount-view"></a>Exibição ConferenceMessageCount
 
A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> O visualização ConferenceMessageCount contém todas as colunas no visualização [ConferenceSessionDetails,](conferencesessiondetails.md) além das colunas listadas abaixo.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário que enviou a mensagem.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que enviou as mensagens. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Locatário do usuário que enviou as mensagens. Consulte a [tabela Tenants para](tenants.md) obter mais informações. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Número de mensagens enviadas pelo usuário durante a sessão de conferência.  <br/> |
   

