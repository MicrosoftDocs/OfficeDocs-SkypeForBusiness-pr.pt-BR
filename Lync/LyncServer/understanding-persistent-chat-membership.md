---
title: Entendendo associações do Chat Persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e525d93e58e73304b9d3a26248418c88b5e9ea79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="d5a0a-102">Entendendo associações do Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="d5a0a-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5a0a-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d5a0a-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d5a0a-104">O acesso do usuário a salas de chat persistente é gerenciado por associação; os usuários devem ser membros de uma sala de chat para poder postar e ler mensagens.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="d5a0a-105">Somente \*\*\*\* os apresentadores que têm uma afiliação designada com salas de chat podem usar o **lançamento para salas Auditorium**.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="d5a0a-106">Um Auditorium é um tipo de sala de chat (a outra é **normal**), onde somente os apresentadores podem postar e todos podem ler.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="d5a0a-107">Além disso, as salas de chat persistente funcionam nas regras de uma categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="d5a0a-108">Para obter detalhes sobre categorias, consulte [Gerenciando categorias, salas e suplementos no Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)e também as seções "como o escopo da categoria funciona" e "estratégias de categoria da sala", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="d5a0a-109">Um administrador de chat persistente pode criar e gerenciar categorias de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="d5a0a-110">Como parte da criação e do gerenciamento de categorias de salas de chat, o administrador de chat persistente pode configurar entidades de segurança (grupos, contêineres e usuários dos serviços de domínio Active Directory) que têm acesso a membros ou criadores de salas de chat de uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="d5a0a-111">Serviços de domínio do Active Directory e chat persistente</span><span class="sxs-lookup"><span data-stu-id="d5a0a-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="d5a0a-112">O servidor de chat persistente depende do Active Directory para o pool de usuários de chat persistente internos.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="d5a0a-113">Depois de instalar o chat persistente (cliente), você pode adicionar domínios de usuários e grupos de usuários à categoria sala.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="d5a0a-114">Em seguida, você pode adicionar esses usuários e grupos à Associação das categorias da sala.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5a0a-115">Você deve certificar-se de que não haja nomes duplicados para os usuários que desejam fazer alterações em suas salas de chat persistente (s).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="d5a0a-116">Se houver nomes de usuário duplicados, altere-os para nomes diferentes para desbloquear os usuários de fazerem essas alterações.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="d5a0a-117">Se um usuário tiver nomes duplicados no Active Directory e tentar fazer alterações na (s) sala (s), uma mensagem de erro será exibida solicitando que o usuário entre em contato com o administrador para obter resolução.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="d5a0a-118">Como o escopo da categoria funciona</span><span class="sxs-lookup"><span data-stu-id="d5a0a-118">How Category Scoping Works</span></span>

<span data-ttu-id="d5a0a-119">Uma categoria especifica todos os usuários e grupos que podem ser membros de uma lista de membros de uma sala de chat persistente na categoria, com base em sua propriedade **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="d5a0a-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="d5a0a-120">Por exemplo, se você definir o **AllowedMembers** da categoria como contoso.com, poderá adicionar qualquer grupo ou usuário na *contoso* como membro para salas de chat nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="d5a0a-121">Se você definir o **AllowedMembers** em uma categoria para *vendas*, somente grupos e usuários nesta lista de distribuição poderão ser adicionados como membros a salas de chat nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="d5a0a-122">Da mesma forma \*\*\*\* , a propriedade Creators permite que você controle quem pode criar salas de chat nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="d5a0a-123">Após a criação da sala de chat, qualquer pessoa do grupo **AllowedMembers** pode ser designada como **gerente** para operações de gerenciamento contínuo nas salas (por exemplo, alterações de associação e aprovações).</span><span class="sxs-lookup"><span data-stu-id="d5a0a-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="d5a0a-124">A definição de **AllowedMembers** e **criadores** para uma categoria tem os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="d5a0a-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="d5a0a-125">Todas as salas de chat nesta categoria estão limitadas às restrições definidas no nível da categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="d5a0a-126">Você pode usar isso para segregar as salas de chat com base nas necessidades de negócios e políticas de acesso.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="d5a0a-127">Um usuário que está na lista de **criadores** pode criar novas salas de chat nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="d5a0a-128">Se você quiser implementar um sistema em que um número restrito de funcionários na organização possa criar salas de chat, esse controle poderá ser usado para atender a essa exigência.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="d5a0a-129">Estratégias de categoria da sala</span><span class="sxs-lookup"><span data-stu-id="d5a0a-129">Room Category Strategies</span></span>

<span data-ttu-id="d5a0a-130">O **AllowedMembers** de uma categoria deve incluir todos os usuários que usarão qualquer sala de chat persistente nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="d5a0a-131">Dependendo dos seus requisitos de proteção de dados corporativos e garantia do nível apropriado de acesso, talvez você queira definir uma ou mais categorias para especificar quem pode pesquisar e participar de salas.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="d5a0a-132">Se você deseja permitir apenas um conjunto específico de usuários (um helpdesk central ou somente funcionários em tempo integral) para criar salas, é possível fazer o escopo dos **criadores** de uma categoria para atender a essa exigência.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="d5a0a-133">As categorias também podem ser usadas para criar paredes éticas.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="d5a0a-134">As paredes éticas impedem qualquer conflito de interesse em uma organização.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="d5a0a-135">Por exemplo, um administrador pode criar salas de chat em uma categoria somente para os comerciantes, enquanto as salas de chat em outra categoria podem ser usadas somente por analistas.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5a0a-136">No Lync Server 2013, servidor de chat persistente, não oferecemos suporte ao acesso a usuários federados.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="d5a0a-137">Se houver chats de usuários federados nas versões anteriores do servidor de chat persistente, eles serão migrados.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="d5a0a-138">Os usuários federados são adicionados como entidades de segurança desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="d5a0a-139">Restringir os membros a grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="d5a0a-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="d5a0a-140">Quando você adiciona um domínio a uma categoria, os grupos de usuários cujos objetos de grupo estão contidos nesse domínio estão disponíveis para que você possa especificá-los como membros de salas na categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="d5a0a-141">Recomendamos, como regra geral, que você use contêineres do Active Directory, como domínios e unidades organizacionais, para definir a **AllowedMembers** e os **criadores**de uma categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="d5a0a-142">Você pode adicionar objetos de qualquer domínio a uma lista de **AllowedMembers** ou **criadores** .</span><span class="sxs-lookup"><span data-stu-id="d5a0a-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="d5a0a-143">Somente objetos na lista **AllowedMembers** ou **criadores** podem ser adicionados a salas sob essa categoria.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

