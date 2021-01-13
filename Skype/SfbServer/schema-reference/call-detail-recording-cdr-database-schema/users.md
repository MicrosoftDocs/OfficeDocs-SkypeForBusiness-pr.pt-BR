---
title: Tabela Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: A tabela Usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que tenham registros no banco de dados.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831611"
---
# <a name="users-table"></a>Tabela Users
 
A tabela Usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que tenham registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Carimbo de data/hora para uso interno.  <br/> |
|**UserId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo identificando este usuário.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI do Usuário.  <br/> |
|**TenantId** <br/> |int  <br/> |Externo  <br/> |A ID de locatário do usuário. Consulte a [tabela Tenants para](tenants.md) obter mais informações. <br/> |
|**UriTypeId** <br/> |int  <br/> |Externo  <br/> |Tipo de URI do usuário. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

