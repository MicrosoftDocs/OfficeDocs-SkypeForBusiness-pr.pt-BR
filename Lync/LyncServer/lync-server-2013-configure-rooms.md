---
title: 'Lync Server 2013: configurar salas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6d5fabe5b465fd2ecab3cfee7474aa64160210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="e31c3-102">Configurar salas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e31c3-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e31c3-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e31c3-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e31c3-104">A configuração de salas de chat persistente é normalmente tratada por usuários ou outras equipes centrais usando a interface de linha de comando do Windows PowerShell; Normalmente, um administrador não gerencia as salas de chat.</span><span class="sxs-lookup"><span data-stu-id="e31c3-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="e31c3-105">No entanto, se você tiver que criar e gerenciar salas de chat, poderá usar a interface de linha de comando do Windows PowerShell ou adicionar a si mesmo como um membro para uma sala de chat e usar o cliente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e31c3-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="e31c3-106">Para obter detalhes sobre como configurar salas de chat usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="e31c3-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="e31c3-107">Gerenciando dados em salas de chat</span><span class="sxs-lookup"><span data-stu-id="e31c3-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="e31c3-108">O servidor de chat persistente permite que os usuários colaborem postando mensagens em salas de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e31c3-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="e31c3-109">Os dados persistem no servidor e os membros da sala podem ter acesso a eles, inclusive ao histório de dados.</span><span class="sxs-lookup"><span data-stu-id="e31c3-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="e31c3-110">No entanto, os usuários que têm funções diferentes têm acesso diferente aos dados persistentes conforme descrito na lista a seguir.</span><span class="sxs-lookup"><span data-stu-id="e31c3-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="e31c3-p103">Os administradores podem excluir qualquer conteúdo (por exemplo, conteúdo postado antes de determinada data) de qualquer sala de char para impedir que o banco de dados assuma proporções muito grandesm. Eles também podem remover ou substituir mensagens consideradas impróprias para uma sala de chat específica.</span><span class="sxs-lookup"><span data-stu-id="e31c3-p103">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large. Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="e31c3-113">Os usuários finais, incluisive os autores das mensagens, não podem excluir conteúdo de nenhuma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e31c3-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="e31c3-p104">Os gerentes das salas de chat podem desabilitar salas, mas não excluí-las. Somente os administradores podem excluir salas de chat após a criação.</span><span class="sxs-lookup"><span data-stu-id="e31c3-p104">Chat room managers can disable rooms, but cannot delete rooms. Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="e31c3-116">Quando a mensagem é excluída, não é possível desfazer a ação.</span><span class="sxs-lookup"><span data-stu-id="e31c3-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="e31c3-117">No entanto, as mensagens excluídas podem ser restauradas caso exista um backup.</span><span class="sxs-lookup"><span data-stu-id="e31c3-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="e31c3-118">Se um servidor de conformidade de chat persistente estiver habilitado, as mensagens antigas serão mantidas no banco de dados de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e31c3-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e31c3-119">Este uso de dados da sala de chat se aplica ao aplicativo de API do servidor de chat persistente do Lync Server 2013, exceto no caso em que a função de administrador está envolvida.</span><span class="sxs-lookup"><span data-stu-id="e31c3-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="e31c3-120">A API do servidor de chat persistente não pode ser usada para fazer qualquer uma das operações do administrador.</span><span class="sxs-lookup"><span data-stu-id="e31c3-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="e31c3-121">Você deve executar essas operações no Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e31c3-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

