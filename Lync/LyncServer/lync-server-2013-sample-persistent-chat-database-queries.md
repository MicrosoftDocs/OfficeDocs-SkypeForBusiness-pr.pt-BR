---
title: 'Lync Server 2013: exemplo de consultas de banco de dados persistente de chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sample Persistent Chat database queries
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558649(v=OCS.15)
ms:contentKeyID: 48184133
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfbe31844e0ca78a3f9b133bde96f2a6f625f759
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511028"
---
# <a name="sample-persistent-chat-database-queries-for-lync-server-2013"></a><span data-ttu-id="212bf-102">Exemplo de consultas de banco de dados de chat persistente para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="212bf-102">Sample Persistent Chat database queries for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="212bf-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="212bf-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="212bf-104">Esta seção contém exemplos de consultas para o banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="212bf-104">This section contains sample queries for the Persistent Chat database.</span></span>

<span data-ttu-id="212bf-105">Use o exemplo a seguir para obter uma lista de suas salas de chat persistente mais ativas após uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="212bf-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

<span data-ttu-id="212bf-106">Use o exemplo a seguir para obter uma lista de seus usuários mais ativos após uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="212bf-106">Use the following example to get a list of your most active users after a certain date.</span></span>

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

<span data-ttu-id="212bf-107">Use o seguinte exemplo para obter uma lista de todos que já enviaram uma mensagem com a frase "Olá Mundo".</span><span class="sxs-lookup"><span data-stu-id="212bf-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

<span data-ttu-id="212bf-108">Use o exemplo a seguir para obter uma lista de membros do grupo de uma determinada entidade.</span><span class="sxs-lookup"><span data-stu-id="212bf-108">Use the following example to get a list of group memberships for a certain principal.</span></span>

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

<span data-ttu-id="212bf-109">Use o exemplo a seguir para obter uma lista de todas as salas de chat das quais um usuário, Maria da Silva, é um membro direto.</span><span class="sxs-lookup"><span data-stu-id="212bf-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

<span data-ttu-id="212bf-110">Use o exemplo a seguir para obter uma lista dos convites recebidos por um usuário.</span><span class="sxs-lookup"><span data-stu-id="212bf-110">Use the following example to get a list of invitations that a user has received.</span></span>

    SELECT prinName
          ,nodeName
          ,invID   
          ,createdOn
      FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
      where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
      ORDER BY invID DESC

</div>

<span> </span>

</div>

</div>

</div>

