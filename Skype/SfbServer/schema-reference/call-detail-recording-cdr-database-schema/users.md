---
title: Tabela Usuários
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: A tabela Usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que tenham registros no banco de dados.
ms.openlocfilehash: 66f3e1247d29969ecef36a5d6247510b5eae022c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389773"
---
# <a name="users-table"></a>Tabela Usuários
 
A tabela Usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que tenham registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Carimbo de data/hora para uso interno.  <br/> |
|**UserId** <br/> |int  <br/> |Primário  <br/> |Número exclusivo identificando este usuário.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI do Usuário.  <br/> |
|**TenantId** <br/> |int  <br/> |Foreign  <br/> |ID de locatário desse usuário. Consulte a [tabela Locatários](tenants.md) para obter mais informações. <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Tipo de URI desse usuário. Consulte a [tabela UriTypes para](uritypes.md) obter mais informações. <br/> |
   

