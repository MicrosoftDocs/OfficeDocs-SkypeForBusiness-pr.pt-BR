---
title: 'Lync Server 2013: Gerenciando categorias, salas e suplementos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f9281b7987bea7425589efc649c1c29a8482770
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505868"
---
# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="18e2d-102">Gerenciando categorias, salas e suplementos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18e2d-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="18e2d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="18e2d-104">No painel de controle do Lync Server 2013, ou usando os cmdlets do Windows PowerShell, os administradores de chat persistente podem usar a página de **chat persistente** para criar categorias e suplementos. Para gerenciar salas de chat persistente, os administradores podem usar cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18e2d-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="18e2d-105">Como alternativa, se o administrador de chat persistente também estiver habilitado para SIP, ele poderá usar o cliente Lync para iniciar uma página da Web para criar e gerenciar salas de chat.</span><span class="sxs-lookup"><span data-stu-id="18e2d-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="18e2d-106">Os tópicos a seguir descrevem como criar e trabalhar com categorias e salas de chat.</span><span class="sxs-lookup"><span data-stu-id="18e2d-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="18e2d-107">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="18e2d-107">In This Section</span></span>

  - [<span data-ttu-id="18e2d-108">Criando ou editando uma nova categoria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="18e2d-109">Criando ou editando uma nova sala no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="18e2d-110">Criando novos suplementos para salas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="18e2d-111">Configuração que pode postar mensagens em uma sala de chat do auditório no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="18e2d-112">Desabilitar ou habilitar uma sala de chat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="18e2d-113">Mover uma sala de chat de uma categoria para outra no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="18e2d-114">Excluindo uma sala de chat ou categoria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="18e2d-115">Excluindo uma mensagem ou limpando mensagens obsoletas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18e2d-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

