---
title: Selecionar Membros Permitidos
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Criar e gerenciar salas de Chat Persistente é muito mais fácil com o uso correto de categorias. Um Administrador de Chat Persistente pode definir AllowedMembers e Criadores para cada categoria e também pode definir as configurações e comportamentos padrão da sala de chat que serão aplicadas a todas as salas de chat criadas na categoria. Os administradores de Chat Persistente criam e gerenciam categorias usando o painel de controle ou Windows PowerShell cmdlets.
ms.openlocfilehash: 47abbec64f6799a85f3f6123a898eeae00becbdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107987"
---
# <a name="select-allowed-members"></a><span data-ttu-id="15987-105">Selecionar Membros Permitidos</span><span class="sxs-lookup"><span data-stu-id="15987-105">Select Allowed Members</span></span>

<span data-ttu-id="15987-106">Criar e gerenciar salas de Chat Persistente é muito mais fácil com o uso correto de categorias.</span><span class="sxs-lookup"><span data-stu-id="15987-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="15987-107">Um Administrador de Chat Persistente pode definir **AllowedMembers** e Criadores para cada categoria e também pode definir as configurações e comportamentos padrão da sala de chat que serão aplicadas a todas as salas de chat **criadas** na categoria.</span><span class="sxs-lookup"><span data-stu-id="15987-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="15987-108">Os administradores de Chat Persistente criam e gerenciam categorias usando o painel de controle ou Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="15987-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="15987-109">Usuários, Unidades Organizacionais (OUs) e grupos de usuário identificados como Creators da categoria são os únicos indivíduos e grupos que têm permissão para criar salas na categoria.</span><span class="sxs-lookup"><span data-stu-id="15987-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="15987-110">Após a criação da categoria, eles podem escolher usuários, OUs e grupos de usuários na lista **AllowedMembers** da categoria como gerentes e membros da sala de chat para gerenciar e participar da sala.</span><span class="sxs-lookup"><span data-stu-id="15987-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="15987-111">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="15987-111">Tasks that you can perform</span></span>

<span data-ttu-id="15987-112">É possível executar as seguintes tarefas na página **Selecionar Membros Permitidos**:</span><span class="sxs-lookup"><span data-stu-id="15987-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="15987-113">Configurar categorias</span><span class="sxs-lookup"><span data-stu-id="15987-113">Configure Categories</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [<span data-ttu-id="15987-114">Novos recursos de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="15987-114">New Persistent Chat Server Features</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

<span data-ttu-id="15987-115">Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Painel de Controle do Skype for Business Server, consulte [Manage Skype for Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="15987-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="15987-116">Para configurar as categorias para salas de chat</span><span class="sxs-lookup"><span data-stu-id="15987-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="15987-117">Em Associação , na seção **Membros** Permitidos, adicione ou remova usuários e outras entidades de Serviços de Domínio do Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que têm permissão para serem adicionados como membros de salas de chat pertencentes à categoria.</span><span class="sxs-lookup"><span data-stu-id="15987-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="15987-118">As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).</span><span class="sxs-lookup"><span data-stu-id="15987-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="15987-119">Para obter detalhes sobre recursos e recursos do Servidor de Chat Persistente, consulte [Visão geral do Servidor](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) de Chat Persistente na documentação planejamento.</span><span class="sxs-lookup"><span data-stu-id="15987-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) in the Planning documentation.</span></span> <span data-ttu-id="15987-120">Para obter detalhes sobre como trabalhar com configurações do Servidor de Chat Persistente, consulte [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) na documentação de Implantação e [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="15987-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="15987-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="15987-121">See also</span></span>

[<span data-ttu-id="15987-122">Noções básicas sobre associação ao chat persistente</span><span class="sxs-lookup"><span data-stu-id="15987-122">Understanding Persistent Chat Membership</span></span>](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)