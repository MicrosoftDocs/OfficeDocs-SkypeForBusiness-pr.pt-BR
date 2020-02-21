---
title: 'Lync Server 2013: Criando ou editando uma nova sala'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5c6292b38bbc02eb2230b8746ec331b7bd1e6ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="2bdd4-102">Criando ou editando uma nova sala no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bdd4-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bdd4-103">_**Última modificação do tópico:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="2bdd4-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="2bdd4-104">A configuração de salas de chat persistente é normalmente tratada pelos usuários; um administrador de chat persistente normalmente não configura ou gerencia salas de chat.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="2bdd4-105">Os cmdlets do Windows PowerShell para gerenciar salas estão disponíveis somente para administradores do **CsPersistentChatAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="2bdd4-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="2bdd4-106">Os usuários que são **criadores** em qualquer categoria determinada podem usar o cliente Lync para criar e gerenciar salas.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="2bdd4-107">Os usuários que foram designados como gerentes de uma sala de chat específica também podem realizar gerenciamento contínuo da sala, como edição das propriedades ou associação das salas.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2bdd4-108">Os administradores de chat persistente também podem ser criadores e não estão sujeitos às restrições colocadas nos criadores.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="2bdd4-109">Opcionalmente, se você for um administrador de chat persistente, poderá empregar uma interface de usuário para criar e gerenciar salas de chat em vez de usar cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="2bdd4-110">Para fazer isso, habilite um administrador para servidor de chat persistente e use o cliente Lync para criar e gerenciar salas de chat.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="2bdd4-111">Se você deseja criar um fluxo de trabalho de gerenciamento de sala personalizado para seus usuários, você pode definir a propriedade **RoomManagementUrl** na sua configuração de servidor de chat persistente para redirecionar os usuários para sua solução personalizada do cliente Lync.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="2bdd4-112">Para obter detalhes sobre como configurar salas de chat usando a interface de linha de comando do Windows PowerShell, consulte "gerenciamento de sala" em [Configurando servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="2bdd4-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="2bdd4-113">Para obter detalhes sobre como configurar salas de chat, consulte [Configure Rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2bdd4-114">Servidor de chat persistente permite que os usuários criem e gerenciem a sala de chat de um site específico.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="2bdd4-115">No entanto, os usuários não podem criar ou gerenciar salas de chat em outros sites dentro da mesma topologia.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="2bdd4-116">Certifique-se de especificar os criadores e gerentes de sala de chat para todos os sites em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2bdd4-117">Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="2bdd4-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

