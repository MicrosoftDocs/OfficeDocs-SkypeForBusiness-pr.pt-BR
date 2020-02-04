---
title: Selecionar Membros Negados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Um administrador de chat persistente pode criar e gerenciar categorias de sala de chat. Como parte da criação e do gerenciamento de categorias de salas de chat, um administrador de chat persistente pode configurar entidades de segurança (grupos/contêineres/usuários dos serviços de domínio Active Directory) que têm acesso a membros/criadores de salas de chat de uma categoria específica. Um administrador de chat persistente também pode adicionar DeniedMembers a uma categoria e essas são exclusões explícitas da lista de permissões. DeniedMembers substitui o que está no AllowedMembers.
ms.openlocfilehash: c8b357abe49d794283b7165d9c5decdffaece275
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685874"
---
# <a name="select-denied-members"></a><span data-ttu-id="af2f6-106">Selecionar Membros Negados</span><span class="sxs-lookup"><span data-stu-id="af2f6-106">Select Denied Members</span></span>

<span data-ttu-id="af2f6-107">Um administrador de chat persistente pode criar e gerenciar categorias de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af2f6-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="af2f6-108">Como parte da criação e do gerenciamento de categorias de salas de chat, um administrador de chat persistente pode configurar entidades de segurança (grupos/contêineres/usuários dos serviços de domínio Active Directory) que têm acesso a membros/criadores de salas de chat de uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="af2f6-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="af2f6-109">Um administrador de chat persistente também pode adicionar DeniedMembers a uma categoria e essas são exclusões explícitas da lista de permissões.</span><span class="sxs-lookup"><span data-stu-id="af2f6-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="af2f6-110">DeniedMembers substitui o que está no AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="af2f6-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="af2f6-111">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="af2f6-111">Tasks that you can perform</span></span>

<span data-ttu-id="af2f6-112">É possível executar as seguintes tarefas na página **Selecionar Membros Negados**:</span><span class="sxs-lookup"><span data-stu-id="af2f6-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="af2f6-113">Configure Categories</span><span class="sxs-lookup"><span data-stu-id="af2f6-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="af2f6-114">New Persistent Chat Server Features</span><span class="sxs-lookup"><span data-stu-id="af2f6-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="af2f6-115">Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o painel de controle do Skype for Business Server, consulte [gerenciar o Skype for Business server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="af2f6-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="af2f6-116">Para configurar categorias salas de chat</span><span class="sxs-lookup"><span data-stu-id="af2f6-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="af2f6-117">Em **Associação**, na seção **Membros negados** , adicione ou remova usuários e outras entidades de segurança do Active Directory associadas a membros sendo negados da sala.</span><span class="sxs-lookup"><span data-stu-id="af2f6-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="af2f6-118">Para obter detalhes sobre recursos e recursos do servidor de chat persistente, consulte [visão geral do servidor de chat persistente](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="af2f6-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="af2f6-119">Para obter detalhes sobre como trabalhar com configurações de servidor de chat persistente, consulte [Configurando o servidor de chat persistente](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) na documentação de implantação e [Gerenciando o Lync Server 2013, servidor de chat persistente](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="af2f6-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="af2f6-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="af2f6-120">See also</span></span>

[<span data-ttu-id="af2f6-121">Understanding Persistent Chat Membership</span><span class="sxs-lookup"><span data-stu-id="af2f6-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
