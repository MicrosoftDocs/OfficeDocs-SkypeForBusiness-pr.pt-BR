---
title: Tabela Users
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: A tabela de usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a>Tabela Users
 
A tabela de usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Carimbo de hora para uso interno.  <br/> |
|**UserId** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica este usuário.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI do usuário.  <br/> |
|**TenantId** <br/> |int  <br/> |Externa  <br/> |ID do locatário. do usuário Consulte a [tabela de inquilinos](tenants.md) para obter mais informações. <br/> |
|**UriTypeId** <br/> |int  <br/> |Externa  <br/> |Tipo de URI do usuário. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
   

