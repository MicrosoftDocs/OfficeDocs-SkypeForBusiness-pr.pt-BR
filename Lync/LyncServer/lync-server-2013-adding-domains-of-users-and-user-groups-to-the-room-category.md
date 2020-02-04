---
title: 'Lync Server 2013: Adicionando domínios de usuários e grupos de usuários à categoria da sala'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9fbbc7ad4fd5279cea1116607193817078a04e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a><span data-ttu-id="8bc01-102">Adicionando domínios de usuários e grupos de usuários à categoria da sala no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8bc01-102">Adding domains of users and user groups to the room category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bc01-103">_**Tópico da última modificação:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="8bc01-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="8bc01-104">Para adicionar grupos maiores de usuários a uma sala de chat, consulte [Configurar categorias no Lync Server 2013](lync-server-2013-configure-categories.md) e [gerenciar categorias](manage-categories.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="8bc01-104">To add larger groups of users to a chat room, see [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) and [Manage categories](manage-categories.md) in the Deployment documentation.</span></span> <span data-ttu-id="8bc01-105">Por exemplo, esse comando adiciona todos os usuários da NorthAmericaUsers OU no Active Directory à sala de chat do América do América do América do usuário:</span><span class="sxs-lookup"><span data-stu-id="8bc01-105">For example, this command adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

<span data-ttu-id="8bc01-106">Seu comando adiciona todos os membros do grupo de distribuição Finance à mesma sala de chat:</span><span class="sxs-lookup"><span data-stu-id="8bc01-106">His command adds all the members from the Finance distribution group to the same chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

