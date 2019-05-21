---
title: Tabela Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: A tabela usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295696"
---
# <a name="users-table"></a>Tabela Users
 
A tabela usuários é uma tabela de suporte. Cada registro na tabela armazena informações sobre um usuário envolvido em chamadas ou sessões que têm registros no banco de dados.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Carimbo de data/hora para uso interno.  <br/> |
|**ID** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse usuário.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |URI de usuário.  <br/> |
|**Tenantid** <br/> |int  <br/> |Exterior  <br/> |A ID de locatário deste usuário. Consulte a [tabela locatários](tenants.md) para obter mais informações. <br/> |
|**UriTypeId** <br/> |int  <br/> |Exterior  <br/> |O tipo de URI deste usuário. Consulte a [tabela UriTypes](uritypes.md) para obter mais informações. <br/> |
   

