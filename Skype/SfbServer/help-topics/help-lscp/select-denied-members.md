---
title: Selecionar Membros Negados
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
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Um Administrador de Chat Persistente pode criar e gerenciar categorias de sala de chat. Como parte da criação e gerenciamento de categorias de sala de chat, um Administrador de Chat Persistente pode configurar entidades (grupos de Serviços de Domínio Active Directory/contêineres/usuários) que têm acesso para serem membros/criadores de salas de chat de uma categoria específica. Um Administrador de Chat Persistente também pode adicionar DeniedMembers a uma categoria e eles se tornam exclusões explícitas à lista de permissão. DeniedMembers substitui o que está em AllowedMembers.
ms.openlocfilehash: c5f942723937fe2da28025fba5da1fc7ee121c83
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814571"
---
# <a name="select-denied-members"></a><span data-ttu-id="9e244-106">Selecionar Membros Negados</span><span class="sxs-lookup"><span data-stu-id="9e244-106">Select Denied Members</span></span>

<span data-ttu-id="9e244-107">Um Administrador de Chat Persistente pode criar e gerenciar categorias de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="9e244-107">A Persistent Chat Administrator can create and manage chat room categories.</span></span> <span data-ttu-id="9e244-108">Como parte da criação e gerenciamento de categorias de sala de chat, um Administrador de Chat Persistente pode configurar entidades (grupos de Serviços de Domínio Active Directory/contêineres/usuários) que têm acesso para serem membros/criadores de salas de chat de uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="9e244-108">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory Domain Services groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="9e244-109">Um Administrador de Chat Persistente também pode adicionar DeniedMembers a uma categoria e eles se tornam exclusões explícitas à lista de permissão.</span><span class="sxs-lookup"><span data-stu-id="9e244-109">A Persistent Chat Administrator can also add DeniedMembers to a category and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="9e244-110">DeniedMembers substitui o que está em AllowedMembers.</span><span class="sxs-lookup"><span data-stu-id="9e244-110">DeniedMembers override what's in AllowedMembers.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="9e244-111">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="9e244-111">Tasks that you can perform</span></span>

<span data-ttu-id="9e244-112">É possível executar as seguintes tarefas na página **Selecionar Membros Negados**:</span><span class="sxs-lookup"><span data-stu-id="9e244-112">You can perform the following tasks on the **Select Denied Members** page:</span></span>

- [<span data-ttu-id="9e244-113">Configurar Categorias</span><span class="sxs-lookup"><span data-stu-id="9e244-113">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="9e244-114">Novos recursos de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9e244-114">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="9e244-115">Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Painel de Controle do Skype for Business Server, consulte [Gerenciar o Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="9e244-115">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="9e244-116">Para configurar as categorias para salas de chat</span><span class="sxs-lookup"><span data-stu-id="9e244-116">To configure categories for chat rooms</span></span>

<span data-ttu-id="9e244-117">Em **Associação,** na **seção Membros** Negados, adicione ou remova usuários e outras entidades do Active Directory associadas aos membros que estão sendo negados da sala.</span><span class="sxs-lookup"><span data-stu-id="9e244-117">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>


<span data-ttu-id="9e244-118">Para obter detalhes sobre recursos do Servidor de Chat Persistente, consulte [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="9e244-118">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9e244-119">Para obter detalhes sobre como trabalhar com configurações de Servidor de Chat Persistente, consulte [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="9e244-119">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e244-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="9e244-120">See also</span></span>

[<span data-ttu-id="9e244-121">Noções básicas sobre associação ao chat persistente</span><span class="sxs-lookup"><span data-stu-id="9e244-121">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)
