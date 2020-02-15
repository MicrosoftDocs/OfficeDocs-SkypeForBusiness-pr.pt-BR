---
title: 'Lync Server 2013: movendo uma sala de chat de uma categoria para outra'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40077d8092f8b0b78b6e9ce78cd16c6f1e0812f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="1fc9f-102">Mover uma sala de chat de uma categoria para outra no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fc9f-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fc9f-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1fc9f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1fc9f-104">Recomendamos que você não altere a categoria de uma sala de chat persistente após a criação da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="1fc9f-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="1fc9f-105">Contudo, se a o gerente da sala tiver privilégios de **Criador** em outra categoria, ele pode mover a sala de uma categoria a outra.</span><span class="sxs-lookup"><span data-stu-id="1fc9f-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="1fc9f-106">A sala não é excluída e recriada.</span><span class="sxs-lookup"><span data-stu-id="1fc9f-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="1fc9f-107">É uma mudança de associação no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1fc9f-107">It is a change of association within the database.</span></span>

<span data-ttu-id="1fc9f-p102">Muda a categoria de uma sala de chat deve ser feito raramente. Uma categoria determina o membro permitido para a sala de chat, por isso, quando uma sala de chat muda de categoria, todas as listas de controle de acesso ao sistema (SACLs) não mais suportados pela nova categoria são purgadas. Por exemplo, se um usuário for membro da sala e não mais um **AllowedMember** na nova categoria, a filiação da sala será modificada e o usuário será removido da sala.</span><span class="sxs-lookup"><span data-stu-id="1fc9f-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="1fc9f-111">Para obter detalhes sobre como mover uma sala de chat usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="1fc9f-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="1fc9f-112">Para obter detalhes sobre como configurar salas de chat, consulte [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="1fc9f-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

