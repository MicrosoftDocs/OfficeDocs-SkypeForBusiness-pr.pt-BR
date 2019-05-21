---
title: Tabela User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: A tabela do usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um usuário.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294611"
---
# <a name="user-table"></a>Tabela User
 
A tabela do usuário é uma tabela de suporte que armazena uma lista de vários usuários que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um usuário.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primária  <br/> |Número exclusivo que identifica esse usuário.  <br/> |
|**SOLICITAÇÃO** <br/> |nvarchar (450)  <br/> |Exclusividade  <br/> |Cadeia de caracteres de URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 é um tipo de URI desconhecido.  <br/> 2 é o URI do usuário.  <br/> 4 é o URI da conferência.  <br/> 8 é o URI do telefone.  <br/> |
|**TenantKey** <br/> |int  <br/> |Exterior  <br/> |Locatário do usuário, referenciado da tabela de locatários.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Carimbo de data/hora mais recente quando o usuário tiver uma chamada de áudio ruim.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Somente para uso interno.  <br/> |
   

