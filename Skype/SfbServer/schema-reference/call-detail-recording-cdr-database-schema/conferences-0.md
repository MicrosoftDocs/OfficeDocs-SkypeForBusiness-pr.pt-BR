---
title: Exibição de conferências
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
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: A Exibição de Conferências armazena informações sobre as conferências. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 500a03e85a3339d28227a5b65d5a3c206fc34723
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828624"
---
# <a name="conferences-view"></a>Exibição de conferências
 
A Exibição de Conferências armazena informações sobre as conferências. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação da sessão. Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão. Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI da conferência.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo da URI de conferência. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Usado para conferências recorrentes. Cada instância de uma conferência recorrente possui o mesmo ConferenceUri, mas um ConfInstance diferente.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Hora inicial da conferência.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Hora final da conferência.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI do usuário que organizou a conferência.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que organizou a conferência. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Inquilino do usuário que organizou a conferência. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nome de domínio totalmente qualificado do pool que hospeda a conferência.  <br/> |
|**Flag** <br/> |smallint  <br/> |Máscara de bits que contém os Atributos de Conferência. Os possíveis valores são:  <br/> 0X01 - Transação Sintética  <br/> |
   

