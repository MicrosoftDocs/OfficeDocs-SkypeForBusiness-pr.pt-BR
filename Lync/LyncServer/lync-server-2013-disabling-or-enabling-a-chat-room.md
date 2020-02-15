---
title: 'Lync Server 2013: desabilitar ou habilitar uma sala de chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d9c706c0ea5afcff4f249a9c00a2355667f221
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="92703-102">Desabilitar ou habilitar uma sala de chat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92703-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92703-103">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="92703-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="92703-104">Se o tópico de uma sala de chat persistente não for mais relevante, você poderá tornar a sala de chat indisponível para os usuários desabilitando-a.</span><span class="sxs-lookup"><span data-stu-id="92703-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="92703-105">Quando uma sala de chat está desabilitada, todos os membros são desconectados imediatamente da sala.</span><span class="sxs-lookup"><span data-stu-id="92703-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="92703-106">Após uma sala de chat é desabilitada, os usuários não podem participar novamente ou encontrar nas pesquisas de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="92703-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="92703-107">Uma sala de chat desabilitada pode ser habilitada mais tarde por um administrador de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="92703-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="92703-108">Se uma sala de chat é desabilitada, sua lista de associação e outras configurações são preservadas.</span><span class="sxs-lookup"><span data-stu-id="92703-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="92703-109">Se você habilitar a sala novamente, não é necessário recriar manualmente as configurações.</span><span class="sxs-lookup"><span data-stu-id="92703-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="92703-p103">Se o histórico da sala de chat persistir (persistência da histórico da sala de chat é a melhor configuração em uma categoria aplicável a todas as salas dentro da categoria; o padrão é que é persistente, mas pode ser desativado configurando **Habilitar histórico de chat** da categoria para falso), o conteúdo é preservado quando a sala de chat é desabilitada. No entanto, este conteúdo não será exibido nas pesquisas durante o momento que a sala de chat permanece em um estado desabilitado. Se você posteriormente habilitar a sala de chat, os usuários podem pesquisar por mensagens publicadas antes da sala de chat ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="92703-p103">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled. However, that content will not appear in searches during the time that the chat room remains in a disabled state. If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="92703-113">Para obter detalhes sobre como desabilitar e habilitar salas de chat usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="92703-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="92703-114">Para desabilitar uma sala de chat, use um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="92703-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="92703-115">Para habilitar uma sala de chat, defina a propriedade disabled como false:</span><span class="sxs-lookup"><span data-stu-id="92703-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="92703-116">Observe que as salas de chat não podem ser habilitadas ou desabilitadas usando o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92703-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="92703-117">Para obter detalhes sobre como configurar salas de chat, consulte [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="92703-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

