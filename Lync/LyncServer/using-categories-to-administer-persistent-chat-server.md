---
title: Usando categorias para administrar o servidor de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eecae8ff3c84861df7c624e8ca5b958c4fb53696
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="e8204-102">Usando categorias para administrar o servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e8204-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8204-103">_**Última modificação do tópico:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="e8204-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="e8204-104">Sua implantação de servidor de chat persistente pode hospedar várias salas de chat persistentes simultâneas.</span><span class="sxs-lookup"><span data-stu-id="e8204-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="e8204-105">As salas de chat podem ser organizadas em um conjunto de categorias no servidor.</span><span class="sxs-lookup"><span data-stu-id="e8204-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="e8204-106">Cada sala de chat pertence a uma categoria, e herda algumas configurações dessa categoria.</span><span class="sxs-lookup"><span data-stu-id="e8204-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="e8204-107">Essa organização cria uma estrutura útil para identificar conversas, com base em suas finalidades de negócio e facilita a administração delegada e o gerenciamento simplificado.</span><span class="sxs-lookup"><span data-stu-id="e8204-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8204-108">Embora muitos dos recursos de gerenciamento de salas de chat estejam disponíveis em computadores que executam o chat persistente (Lync Client) para o usuário, os administradores de chat persistente (na função <STRONG>cspersistentchatadministrator</STRONG> ) devem usar o painel de controle do Lync Server ou cmdlets do Windows PowerShell para criar ou gerenciar categorias.</span><span class="sxs-lookup"><span data-stu-id="e8204-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="e8204-109">Os administradores de chat persistente usam o painel de controle do Lync Server ou cmdlets do Windows PowerShell para criar e gerenciar categorias e para projetar o acesso de salas de chat para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8204-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="e8204-110">Gerentes de sala de chat persistente, que têm a capacidade de gerenciar uma ou mais salas de chat, podem usar o cliente Lync para iniciar um aplicativo Web de gerenciamento de salas para criar e gerenciar salas (ou os clientes podem criar soluções e fluxos de trabalho personalizados para serem invocados).</span><span class="sxs-lookup"><span data-stu-id="e8204-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="e8204-111">Os administradores de chat persistente também podem usar o painel de controle do Lync Server ou cmdlets do Windows PowerShell para criar e gerenciar salas.</span><span class="sxs-lookup"><span data-stu-id="e8204-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8204-112">Uma sala de chat persistente não pode ter o mesmo nome de uma categoria de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e8204-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="e8204-p103">Os gerentes de sala de chat podem fazer alterações em todas as propriedades de sala de chat, exceto alterar a categoria da sala. Não é possível impedi-los de executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e8204-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="e8204-115">Desabilitar uma sala de chat</span><span class="sxs-lookup"><span data-stu-id="e8204-115">Disabling a chat room</span></span>

  - <span data-ttu-id="e8204-116">Alterar o nome de uma sala de chat</span><span class="sxs-lookup"><span data-stu-id="e8204-116">Changing a chat room name</span></span>

  - <span data-ttu-id="e8204-117">Alterar a descrição de uma sala de chat</span><span class="sxs-lookup"><span data-stu-id="e8204-117">Changing a chat room description</span></span>

  - <span data-ttu-id="e8204-118">Alterar um tipo de sala de chat (Auditório versus Normal)</span><span class="sxs-lookup"><span data-stu-id="e8204-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="e8204-119">Alterar a privacidade de uma sala (aberta versus fechada versus segredo)</span><span class="sxs-lookup"><span data-stu-id="e8204-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="e8204-120">Adicionar ou remover membros</span><span class="sxs-lookup"><span data-stu-id="e8204-120">Adding or removing members</span></span>

  - <span data-ttu-id="e8204-121">Adicionar ou remover gerentes de sala de chat</span><span class="sxs-lookup"><span data-stu-id="e8204-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="e8204-122">Adicionar ou remover um suplemento</span><span class="sxs-lookup"><span data-stu-id="e8204-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="e8204-123">Alterar configurações como convites (de acordo com o que é permitido pela categoria)</span><span class="sxs-lookup"><span data-stu-id="e8204-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="e8204-124">Administração delegada</span><span class="sxs-lookup"><span data-stu-id="e8204-124">Delegated Administration</span></span>

<span data-ttu-id="e8204-125">Criar e gerenciar salas de chat persistente é muito mais fácil com o uso correto de categorias.</span><span class="sxs-lookup"><span data-stu-id="e8204-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="e8204-126">Um administrador de chat persistente pode definir **Membros permitidos** e **criadores** para cada categoria e também pode definir as configurações e os comportamentos de sala de chat padrão que serão aplicados a todas as salas de chat criadas na categoria.</span><span class="sxs-lookup"><span data-stu-id="e8204-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="e8204-127">Administradores de chat persistente criam e gerenciam categorias usando o painel de controle do Lync Server ou cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8204-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="e8204-p105">Usuários, Unidades Organizacionais (OUs) e grupos de usuário identificados como Creators da categoria são os únicos indivíduos e grupos que têm permissão para criar salas na categoria. Após a criação da categoria, eles podem escolher usuários, OUs e grupos de usuário na lista **AllowedMembers** da categoria como gerentes de sala de chat e membros para gerenciar e participar na sala.</span><span class="sxs-lookup"><span data-stu-id="e8204-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="e8204-130">As salas de chat criadas em uma categoria aderem às políticas e configurações aplicadas pela categoria (por exemplo, quem pode estar na associação da sala, quem pode gerenciar a sala, se os carregamentos de arquivo são permitidos, se os convites são enviados e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="e8204-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

