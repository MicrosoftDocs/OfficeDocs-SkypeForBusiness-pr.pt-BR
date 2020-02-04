---
title: 'Lync Server 2013: Excluindo sala de chat ou categoria'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74cf41679a21612e67c4a793c09ae3484377ef6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="3e291-102">Excluindo sala de chat ou categoria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e291-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e291-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3e291-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3e291-104">Salas de chat persistentes podem ser excluídas.</span><span class="sxs-lookup"><span data-stu-id="3e291-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="3e291-105">Se você tiver uma sala de chat que não está mais sendo usada, você pode desabilitá-la.</span><span class="sxs-lookup"><span data-stu-id="3e291-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="3e291-106">Para obter detalhes, consulte como [desabilitar ou habilitar uma sala de chat no Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span><span class="sxs-lookup"><span data-stu-id="3e291-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="3e291-107">Um administrador de chat persistente pode consultar salas de chat desabilitadas e, periodicamente, excluir e excluir permanentemente as salas de chat, usando o cmdlet do Windows PowerShell, **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="3e291-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="3e291-108">As categorias podem ser excluídas.</span><span class="sxs-lookup"><span data-stu-id="3e291-108">Categories can be deleted.</span></span> <span data-ttu-id="3e291-109">No entanto, para excluir uma categoria, você deve primeiro excluir todas as salas de chat dentro dela ou mover as salas de chat para uma nova categoria, deixando uma categoria vazia para exclusão.</span><span class="sxs-lookup"><span data-stu-id="3e291-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="3e291-110">O servidor de chat persistente não permite que você exclua uma categoria que contém salas de chat.</span><span class="sxs-lookup"><span data-stu-id="3e291-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="3e291-111">Para obter detalhes, consulte como [mover uma sala de chat de uma categoria para outra no Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span><span class="sxs-lookup"><span data-stu-id="3e291-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="3e291-112">Para obter detalhes sobre como excluir categorias vazias usando a interface de linha de comando do Windows PowerShell, consulte o "gerenciamento de sala" em [Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="3e291-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="3e291-113">Para obter detalhes sobre salas de chat e categorias, consulte [Configurar salas no Lync Server 2013](lync-server-2013-configure-rooms.md) e [Configurar categorias no Lync Server 2013](lync-server-2013-configure-categories.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="3e291-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

