---
title: Amostragem de consultas de banco de dados de Chat Persistente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Esta seção contém exemplos de consultas do banco de dados de Chat persistente.
ms.openlocfilehash: ab4db61e70108bb922646add050ddcf7f52951b1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025916"
---
# <a name="sample-persistent-chat-database-queries"></a>Amostragem de consultas de banco de dados de Chat Persistente
 
Esta seção contém exemplos de consultas do banco de dados de Chat persistente.
  
Use o exemplo a seguir para obter uma lista de suas salas de Chat persistente mais ativas após uma determinada data.
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

Use o exemplo a seguir para obter uma lista dos seus usuários mais ativas após uma determinada data.
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

Use o exemplo a seguir para obter uma lista de todos que já enviaram uma mensagem com "Olá mundo" nela.
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

Use o exemplo a seguir para obter uma lista de associações de grupo para uma determinada entidade.
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Use o exemplo a seguir para obter uma lista de cada sala de chat que um usuário, Jane Dow, é um membro direto.
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

Use o exemplo a seguir para obter uma lista dos convites recebidos por um usuário.
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```