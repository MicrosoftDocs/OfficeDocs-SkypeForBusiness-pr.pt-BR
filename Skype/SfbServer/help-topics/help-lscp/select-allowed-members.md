---
title: Selecionar Membros Permitidos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectAllowedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9e6df4a-e58a-4104-9f72-2f5c818353e1
description: Criar e gerenciar salas de chat persistente é muito mais fácil com o uso correto de categorias. Um administrador de chat persistente pode definir AllowedMembers e criadores para cada categoria e também pode definir as configurações e os comportamentos padrão da sala de chat que serão aplicados a todas as salas de chat criadas na categoria. Administradores de chat persistentes criam e gerenciam categorias usando o painel de controle ou cmdlets do Windows PowerShell.
ms.openlocfilehash: 916077fe25e1616888dd58dc40f0ef0f14c61e7a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699696"
---
# <a name="select-allowed-members"></a><span data-ttu-id="ce961-105">Selecionar Membros Permitidos</span><span class="sxs-lookup"><span data-stu-id="ce961-105">Select Allowed Members</span></span>

<span data-ttu-id="ce961-106">Criar e gerenciar salas de chat persistente é muito mais fácil com o uso correto de categorias.</span><span class="sxs-lookup"><span data-stu-id="ce961-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="ce961-107">Um administrador de chat persistente pode definir **AllowedMembers** e **criadores** para cada categoria e também pode definir as configurações e os comportamentos padrão da sala de chat que serão aplicados a todas as salas de chat criadas na categoria.</span><span class="sxs-lookup"><span data-stu-id="ce961-107">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="ce961-108">Administradores de chat persistentes criam e gerenciam categorias usando o painel de controle ou cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce961-108">Persistent Chat Administrators create and manage categories by using the control panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="ce961-109">Usuários, Unidades Organizacionais (OUs) e grupos de usuários identificados como Criadores da categoria são os únicos indivíduos e grupos que porem criar salas na categoria.</span><span class="sxs-lookup"><span data-stu-id="ce961-109">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="ce961-110">Após a criação da categoria, elas podem escolher usuários, UOs e grupos de usuários na lista **AllowedMembers** da categoria como gerentes e membros da sala de chat para gerenciar e participar da sala.</span><span class="sxs-lookup"><span data-stu-id="ce961-110">After the category is created, they can choose users, OUs, and user groups from the category's **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="ce961-111">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="ce961-111">Tasks that you can perform</span></span>

<span data-ttu-id="ce961-112">É possível executar as seguintes tarefas na página **Selecionar Membros Permitidos**:</span><span class="sxs-lookup"><span data-stu-id="ce961-112">You can perform the following tasks on the **Select Allowed Members** page:</span></span>

- [<span data-ttu-id="ce961-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="ce961-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="ce961-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="ce961-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="ce961-115">Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o painel de controle do Skype for Business Server, consulte [gerenciar o Skype for Business server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="ce961-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="ce961-116">Para configurar categorias salas de chat</span><span class="sxs-lookup"><span data-stu-id="ce961-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="ce961-117">Em **Associação**, na seção **Membros permitidos** , adicione ou remova usuários e outras entidades de segurança dos serviços de domínio Active Directory (usuários, grupos de distribuição, unidades organizacionais e assim por diante) que podem ser adicionados como membros de salas de chat pertencentes à categoria.</span><span class="sxs-lookup"><span data-stu-id="ce961-117">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="ce961-118">As entidades permitidas por uma categoria podem pesquisar por salas na categoria (a menos que uma sala esteja oculta, caso o qual apenas membros da sala podem pesquisar por ela no diretório).</span><span class="sxs-lookup"><span data-stu-id="ce961-118">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>


<span data-ttu-id="ce961-119">Para obter detalhes sobre recursos e recursos do servidor de chat persistente, consulte [visão geral do servidor de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ce961-119">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="ce961-120">Para obter detalhes sobre como trabalhar com configurações de servidor de chat persistente, consulte [Configurando o servidor de chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) na documentação de implantação e [Gerenciando o Lync Server 2013, servidor de chat persistente](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="ce961-120">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce961-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="ce961-121">See also</span></span>

[<span data-ttu-id="ce961-122">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="ce961-122">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
