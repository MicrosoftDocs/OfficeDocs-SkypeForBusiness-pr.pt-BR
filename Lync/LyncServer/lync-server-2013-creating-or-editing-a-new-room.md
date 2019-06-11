---
title: 'Lync Server 2013: Criando ou editando uma nova sala'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1442454b2afb129fda50d98ed17ccdc2c7ba35c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="2a98a-102">Criando ou editando uma nova sala no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a98a-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a98a-103">_**Tópico da última modificação:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="2a98a-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="2a98a-104">A configuração de salas de chat persistente é comumente manipulada pelos usuários; Geralmente, um administrador de chat persistente não configura ou gerencia salas de chat.</span><span class="sxs-lookup"><span data-stu-id="2a98a-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="2a98a-105">Cmdlets do Windows PowerShell para gerenciar salas estão disponíveis somente para administradores do **CsPersistentChatAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="2a98a-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="2a98a-106">Os usuários que são **criadores** em qualquer categoria determinada podem usar o cliente do Lync para criar e gerenciar salas.</span><span class="sxs-lookup"><span data-stu-id="2a98a-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="2a98a-107">Os usuários que foram designados como gerentes de uma sala de chat específica também podem executar o gerenciamento contínuo da sala, como a edição de propriedades da sala ou associação.</span><span class="sxs-lookup"><span data-stu-id="2a98a-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="2a98a-108">Os administradores de chat persistente também podem ser criadores e não estão sujeitos às restrições colocadas em criadores.</span><span class="sxs-lookup"><span data-stu-id="2a98a-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="2a98a-109">Opcionalmente, se você for um administrador de chat persistente, poderá empregar uma interface de usuário para criar e gerenciar salas de chat em vez de usar cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a98a-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="2a98a-110">Para fazer isso, habilite um administrador para servidor de chat persistente e use o cliente do Lync para criar e gerenciar salas de chat.</span><span class="sxs-lookup"><span data-stu-id="2a98a-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="2a98a-111">Se quiser criar um fluxo de trabalho de gerenciamento de sala personalizado para seus usuários, você pode definir a propriedade **RoomManagementUrl** na configuração do seu servidor de chat persistente para redirecionar os usuários para sua solução personalizada do cliente do Lync.</span><span class="sxs-lookup"><span data-stu-id="2a98a-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="2a98a-112">Para obter detalhes sobre como configurar salas de chat usando a interface de linha de comando do Windows PowerShell, consulte o "gerenciamento de sala" em Configurando o [servidor de chat persistente usando cmdlets do Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="2a98a-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="2a98a-113">Para obter detalhes sobre como configurar salas de chat, consulte [Configurar salas no Lync Server 2013](lync-server-2013-configure-rooms.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="2a98a-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a98a-114">O servidor de chat persistente permite que os usuários criem e gerenciem a sala de chat para um site específico.</span><span class="sxs-lookup"><span data-stu-id="2a98a-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="2a98a-115">No entanto, os usuários não podem criar ou gerenciar salas de chat em outros sites na mesma topologia.</span><span class="sxs-lookup"><span data-stu-id="2a98a-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="2a98a-116">Certifique-se de especificar os criadores e gerentes da sala de chat para todos os sites da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2a98a-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2a98a-117">Os usuários que estiverem hospedados em um aparelho de ramificação de Lync do Lync Server não poderão criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="2a98a-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

