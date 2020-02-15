---
title: Noções básicas sobre associação de chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb9718267798a937f482b09d2752f9d47e5967f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="98de8-102">Noções básicas sobre associação de chat persistente</span><span class="sxs-lookup"><span data-stu-id="98de8-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98de8-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="98de8-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="98de8-104">O acesso do usuário a salas de chat persistente é gerenciado por associação; os usuários devem ser membros de uma sala de chat para poder postar e ler mensagens.</span><span class="sxs-lookup"><span data-stu-id="98de8-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="98de8-105">Apenas **Apresentadores** que projetaram a afiliação com salas de chat têm permissão para usar a **publicação às salas de auditório**.</span><span class="sxs-lookup"><span data-stu-id="98de8-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="98de8-106">Um auditório é um tipo de sala de chat (a outra é a **Normal**), onde apenas Apresentadores podem postar e todos podem ler.</span><span class="sxs-lookup"><span data-stu-id="98de8-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="98de8-107">Além disso, as salas de chat persistente operam sob as regras de uma categoria.</span><span class="sxs-lookup"><span data-stu-id="98de8-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="98de8-108">Para obter detalhes sobre categorias, consulte [Gerenciando categorias, salas e suplementos no Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)e também as seções "como o escopo da categoria funciona" e "estratégias de categoria de sala", mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="98de8-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="98de8-109">Um administrador de chat persistente pode criar e gerenciar categorias de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="98de8-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="98de8-110">Como parte da criação e do gerenciamento de categorias de sala de chat, o administrador de chat persistente pode configurar entidades (grupos, contêineres e usuários dos serviços de domínio Active Directory) que têm acesso a membros ou criadores de salas de chat de uma determinada categoria.</span><span class="sxs-lookup"><span data-stu-id="98de8-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="98de8-111">Serviços de domínio do Active Directory e chat persistente</span><span class="sxs-lookup"><span data-stu-id="98de8-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="98de8-112">O servidor de chat persistente utiliza o Active Directory para o pool de usuários de chat persistente internos.</span><span class="sxs-lookup"><span data-stu-id="98de8-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="98de8-113">Após instalar o chat persistente (cliente), você pode adicionar domínios de usuários e grupos de usuários à categoria de sala.</span><span class="sxs-lookup"><span data-stu-id="98de8-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="98de8-114">Você poderá depois adicionar esses usuários e grupos aos membros de suas categorias de salas.</span><span class="sxs-lookup"><span data-stu-id="98de8-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98de8-115">Você deve garantir que não haja nomes duplicados para os usuários que desejam fazer alterações na (s) sala (s) de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="98de8-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="98de8-116">Se nomes de usuários duplicados existirem, altere-os para nomes diferentes para desbloquear os usuários par fazer essas alterações.</span><span class="sxs-lookup"><span data-stu-id="98de8-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="98de8-117">Se um usuário tiver nomes duplicados no Active Directory e tentar fazer alterações na (s) sala (s), uma mensagem de erro será exibida solicitando que o usuário contate o administrador para resolução.</span><span class="sxs-lookup"><span data-stu-id="98de8-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="98de8-118">Como funciona a associação de categoria</span><span class="sxs-lookup"><span data-stu-id="98de8-118">How Category Scoping Works</span></span>

<span data-ttu-id="98de8-119">Uma categoria especifica todos os usuários e grupos que podem ser membros de uma lista de membros de uma sala de chat persistente nessa categoria, com base em sua propriedade **Membros permitidos** .</span><span class="sxs-lookup"><span data-stu-id="98de8-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="98de8-120">Por exemplo, se você definir o **Membros permitidos** da categoria como contoso.com, poderá adicionar qualquer grupo ou usuário na *contoso* como membro para salas de chat nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="98de8-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="98de8-121">Se você definir o **Membros permitidos** em uma categoria como *vendas*, somente os grupos e usuários dessa lista de distribuição poderão ser adicionados como membros às salas de chat nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="98de8-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="98de8-122">Da mesma forma, a propriedade **Creators** permite que você controle quem pode criar salas de chat nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="98de8-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="98de8-123">Depois que a sala de chat é criada, qualquer pessoa do grupo **Membros permitidos** pode ser designada como **gerente** para operações de gerenciamento contínuo nas salas (por exemplo, alterações de associação e aprovações).</span><span class="sxs-lookup"><span data-stu-id="98de8-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="98de8-124">Definir uma lista de membros para uma categoria oferece os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="98de8-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="98de8-p107">Todas as salas de chat nesta categoria estão sujeitas às restrições definidas no nível da categoria. Você pode usar isso para segregar as salas de chat baseando-se nas necessidades de negócios e políticas de acesso.</span><span class="sxs-lookup"><span data-stu-id="98de8-p107">All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="98de8-p108">Um usuário membro na lista \*\*Criadores \*\* pode criar novas salas de chat naquela categoria. Se você desejar implantar um sistema onde um número restrito de pessoas na organização possa criar salas de chat, este controle pode ser usado para atender a essa exigência.</span><span class="sxs-lookup"><span data-stu-id="98de8-p108">A user who is in the **Creators** list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="98de8-129">Estratégias de categoria de salas</span><span class="sxs-lookup"><span data-stu-id="98de8-129">Room Category Strategies</span></span>

<span data-ttu-id="98de8-130">O **Membros permitidos** de uma categoria deve incluir todos os usuários que usarão qualquer sala de chat persistente nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="98de8-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="98de8-131">Dependendo dos seus requisitos para proteger dados empresariais e garantir o nível correto de acesso, você poderá definir uma ou mais categorias para especificar quem pode pesquisar e participar das salas.</span><span class="sxs-lookup"><span data-stu-id="98de8-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="98de8-132">Se desejar permitir apenas um conjunto específico de usuários (um helpdesk central ou apenas funcionários de tempo integral) para criar salas, você pode fazer o escopo dos **Criadores** de uma categoria para satisfazer esse requisito.</span><span class="sxs-lookup"><span data-stu-id="98de8-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="98de8-p110">As categorias podem ser também usadas para criar barreiras éticas. As barreiras éticas evitam qualquer conflito de interesses em uma organização. Por exemplo, um administrador pode criar salas de chat em uma categoria apenas para comerciantes, ao passo que as salas de chat em outra categoria podem ser usadas somente por analistas.</span><span class="sxs-lookup"><span data-stu-id="98de8-p110">Categories can also be used to create ethical walls. Ethical walls prevent any conflict of interest in an organization. For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98de8-136">No Lync Server 2013, servidor de chat persistente, não há suporte para acesso a usuários federados.</span><span class="sxs-lookup"><span data-stu-id="98de8-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="98de8-137">Se houver chats de usuários federados em versões anteriores do servidor de chat persistente, eles serão migrados.</span><span class="sxs-lookup"><span data-stu-id="98de8-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="98de8-138">Os usuários federados são adicionados como princípios desativados.</span><span class="sxs-lookup"><span data-stu-id="98de8-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="98de8-139">Como estreitar o escopo para grupos de usuário</span><span class="sxs-lookup"><span data-stu-id="98de8-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="98de8-140">Ao adicionar um domínio ao escopo da categoria raiz, os grupos de usuários cujos objetos de grupo estão contidos nesse domínio serão disponibilizados a você para serem especificados como membros das categorias e salas de chat no servidor.</span><span class="sxs-lookup"><span data-stu-id="98de8-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="98de8-141">Recomendamos, como regra geral, que você use contêineres do Active Directory, como domínios e unidades organizacionais, para definir os **Membros permitidos** e **criadores**de uma categoria.</span><span class="sxs-lookup"><span data-stu-id="98de8-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="98de8-142">Você pode adicionar objetos de qualquer domínio a uma lista de  **Membros Permitidos** ou **Criadores**.</span><span class="sxs-lookup"><span data-stu-id="98de8-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="98de8-143">Apenas objetos dentro da lista de **Membros Permitidos** ou **Criadores** pode ser adicionada a salas sob esta categoria.</span><span class="sxs-lookup"><span data-stu-id="98de8-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

