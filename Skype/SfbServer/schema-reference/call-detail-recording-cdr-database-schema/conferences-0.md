---
title: Exibir conferências
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: O modo de exibição de conferências armazena informações sobre as conferências. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 42bdbed9cceb8d50e2de8ddbe29ba406e4a0a2f5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213267"
---
# <a name="conferences-view"></a>Exibir conferências
 
O modo de exibição de conferências armazena informações sobre as conferências. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Hora da solicitação de sessão. Usado em conjunto com SessionIdSeq para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Número de identificação para identificar a sessão. Usado em conjunto com SessionIdTime para identificar exclusivamente uma sessão. Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI da conferência.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Tipo de URI da conferência. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**ConfInstance** <br/> |Identificador exclusivo  <br/> |Usada para conferências recorrentes. Cada instância de uma conferência recorrente tem o mesmo ConferenceUri, mas um ConfInstance diferente.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Hora de início para a conferência.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Hora da conferência final.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI do usuário que organizou a conferência.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário que organizou a conferência. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Locatário do usuário que organizou a conferência. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nome de domínio totalmente qualificado do pool que hospeda a conferência.  <br/> |
|**Sinalizador** <br/> |smallint  <br/> |Máscara de bits que contém os atributos de conferência. Valores possíveis são:  <br/> 0X01 - transação sintética  <br/> |
   

