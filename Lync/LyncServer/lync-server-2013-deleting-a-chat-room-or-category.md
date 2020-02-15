---
title: 'Lync Server 2013: excluindo uma sala de chat ou categoria'
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
ms.openlocfilehash: 6e94068337747feee592ec25669e9d7b5fc10bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="7a415-102">Excluindo uma sala de chat ou categoria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a415-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a415-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7a415-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7a415-104">As salas de chat persistentes podem ser excluídas.</span><span class="sxs-lookup"><span data-stu-id="7a415-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="7a415-105">Se houver uma sala de chat que não esteja mais sendo usada, você poderá desabilitá-la.</span><span class="sxs-lookup"><span data-stu-id="7a415-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="7a415-106">Para obter detalhes, consulte [desabilitar ou habilitar uma sala de chat no Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span><span class="sxs-lookup"><span data-stu-id="7a415-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="7a415-107">Um administrador de chat persistente pode consultar salas de bate-papo desabilitadas e pode limpar e excluir periodicamente as salas de chat, usando o cmdlet do Windows PowerShell, **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="7a415-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="7a415-108">As categorias podem ser excluídas.</span><span class="sxs-lookup"><span data-stu-id="7a415-108">Categories can be deleted.</span></span> <span data-ttu-id="7a415-109">No entanto, para excluir uma categoria, você deve primeiro excluir todas as salas de bate-papo ou mover as salas de chat para uma nova categoria, deixando uma categoria vazia para exclusão.</span><span class="sxs-lookup"><span data-stu-id="7a415-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="7a415-110">O servidor de chat persistente não permite que você exclua uma categoria que contenha salas de chat.</span><span class="sxs-lookup"><span data-stu-id="7a415-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="7a415-111">Para obter detalhes, consulte [movendo uma sala de chat de uma categoria para outra no Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span><span class="sxs-lookup"><span data-stu-id="7a415-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="7a415-112">Para obter detalhes sobre como excluir categorias vazias usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="7a415-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="7a415-113">Para obter detalhes sobre salas e categorias de chat, consulte [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) e [Configure Categories in Lync Server 2013](lync-server-2013-configure-categories.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="7a415-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

