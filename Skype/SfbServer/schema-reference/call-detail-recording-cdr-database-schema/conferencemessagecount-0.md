---
title: Exibição ConferenceMessageCount
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 1308b0e9aeb8954df8010d0c1d55036eff1a3dac
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856518"
---
# <a name="conferencemessagecount-view"></a>Exibição ConferenceMessageCount
 
A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
> [!NOTE]
> O exibição ConferenceMessageCount contém todas as colunas no [exibição ConferenceSessionDetails,](conferencesessiondetails.md) além das colunas listadas abaixo.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI do usuário que enviou a mensagem.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que enviou as mensagens. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Locatário do usuário que enviou as mensagens. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Número de mensagens enviadas pelo usuário durante a sessão de conferência.  <br/> |
   

