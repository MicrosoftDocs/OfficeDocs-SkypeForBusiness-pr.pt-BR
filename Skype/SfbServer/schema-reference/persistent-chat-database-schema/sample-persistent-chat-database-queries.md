---
title: Amostragem de consultas de banco de dados de Chat Persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Esta seção contém consultas de exemplo para o banco de dados de Chat Persistente.
ms.openlocfilehash: 9ae2f99817cae9eb892bf7c43d68900495878abf
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756434"
---
# <a name="sample-persistent-chat-database-queries"></a>Amostragem de consultas de banco de dados de Chat Persistente
 
Esta seção contém consultas de exemplo para o banco de dados de Chat Persistente.
  
Use o exemplo a seguir para obter uma lista das salas de Chat Persistente mais ativas após uma determinada data.
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

Use o exemplo a seguir para obter uma lista de seus usuários mais ativos após uma determinada data.
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

Use o seguinte exemplo para obter uma lista de todos que já enviaram uma mensagem com a frase "Olá Mundo".
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

Use o exemplo a seguir para obter uma lista de membros do grupo de uma determinada entidade.
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Use o exemplo a seguir para obter uma lista de todas as salas de chat das quais um usuário, Maria da Silva, é um membro direto.
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

Use o exemplo a seguir para obter uma lista dos convites recebidos por um usuário.
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
