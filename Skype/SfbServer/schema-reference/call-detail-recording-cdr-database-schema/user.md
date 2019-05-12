---
title: Modo de exibição do usuário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: O modo de exibição do usuário armazena informações sobre os usuários que tiverem sido envolvidos em chamadas ou sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: f4e255f2de8dd087308ee46c64ef301cc0e9d390
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930075"
---
# <a name="user-view"></a>Modo de exibição do usuário
 
O modo de exibição do usuário armazena informações sobre os usuários que tiverem sido envolvidos em chamadas ou sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Número exclusivo que identifica este usuário.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI do usuário.  <br/> |
|TenantKey  <br/> |Identificador exclusivo  <br/> |Locatário do usuário. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
   

