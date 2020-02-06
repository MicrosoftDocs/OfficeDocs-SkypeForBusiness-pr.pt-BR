---
title: Amostragem de consultas de banco de dados de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Esta seção contém exemplos de consultas para o banco de dados de chat persistente.
ms.openlocfilehash: f967e62ade8186bb2f0dae79c06af71e872808af
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814719"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="924be-103">Amostragem de consultas de banco de dados de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="924be-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="924be-104">Esta seção contém exemplos de consultas para o banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="924be-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="924be-105">Use o exemplo a seguir para obter uma lista de suas salas de chat persistente mais ativas após uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="924be-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="924be-106">Use o exemplo a seguir para obter uma lista dos seus usuários ativos após uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="924be-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="924be-107">Use o exemplo a seguir para obter uma lista de todos os participantes que já enviaram uma mensagem com "Olá mundo".</span><span class="sxs-lookup"><span data-stu-id="924be-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="924be-108">Use o exemplo a seguir para obter uma lista de associações de grupo para uma determinada entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="924be-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="924be-109">Use o exemplo a seguir para obter uma lista de cada sala de chat que um usuário, Jane Dow, é membro direto de.</span><span class="sxs-lookup"><span data-stu-id="924be-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="924be-110">Use o exemplo a seguir para obter uma lista de convites que um usuário recebeu.</span><span class="sxs-lookup"><span data-stu-id="924be-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
