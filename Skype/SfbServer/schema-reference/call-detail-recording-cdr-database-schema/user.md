---
title: Modo de exibição do usuário
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: O modo de exibição do usuário armazena informações sobre os usuários que tiverem sido envolvidos em chamadas ou sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a>Modo de exibição do usuário
 
O modo de exibição do usuário armazena informações sobre os usuários que tiverem sido envolvidos em chamadas ou sessões que têm registros no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Número exclusivo que identifica este usuário.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI do usuário.  <br/> |
|TenantKey  <br/> |Identificador exclusivo  <br/> |Locatário do usuário. Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Tipo de URI do usuário. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
   

