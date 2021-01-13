---
title: Selecionar Criadores
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
- ms.lync.lscp.SelectCreators
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8d9ed6f-22ba-470e-b0b4-0da3cea5e961
description: Criar e gerenciar salas de Chat Persistente é muito mais fácil com o uso correto de categorias. Um administrador de Chat Persistente pode definir AllowedMembers e Criadores para cada categoria e também pode definir as configurações de sala de chat padrão e os comportamentos que serão aplicados a todas as salas de chat criadas na categoria. Os administradores de Chat Persistente criam e gerenciam categorias usando o Painel de Controle do Skype for Business Server ou cmdlets do Windows PowerShell.
ms.openlocfilehash: 9fc8bf615de02a4c9eefcd204c832c5c8691eb7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821951"
---
# <a name="select-creators"></a><span data-ttu-id="43ea6-105">Selecionar Criadores</span><span class="sxs-lookup"><span data-stu-id="43ea6-105">Select Creators</span></span>

<span data-ttu-id="43ea6-106">Criar e gerenciar salas de Chat Persistente é muito mais fácil com o uso correto de categorias.</span><span class="sxs-lookup"><span data-stu-id="43ea6-106">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="43ea6-107">Um administrador de Chat Persistente pode definir **AllowedMembers** e Criadores para cada categoria e também pode definir as configurações de sala de chat padrão e os comportamentos que serão aplicados a todas as salas de chat **criadas** na categoria.</span><span class="sxs-lookup"><span data-stu-id="43ea6-107">A Persistent Chat administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="43ea6-108">Os administradores de Chat Persistente criam e gerenciam categorias usando o Painel de Controle do Skype for Business Server ou cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43ea6-108">Persistent Chat administrators create and manage categories by using Skype for Business Server Control Panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="43ea6-109">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="43ea6-109">Tasks that you can perform</span></span>

<span data-ttu-id="43ea6-110">É possível executar as seguintes tarefas na página **Selecionar Criadores**:</span><span class="sxs-lookup"><span data-stu-id="43ea6-110">You can perform the following tasks on the **Select Creators** page:</span></span>

- [<span data-ttu-id="43ea6-111">Configurar Categorias</span><span class="sxs-lookup"><span data-stu-id="43ea6-111">Configure Categories</span></span>](https://technet.microsoft.com/library/4547f514-f0c0-404d-890f-092ddeeac852.aspx)

- [<span data-ttu-id="43ea6-112">Novos recursos de servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="43ea6-112">New Persistent Chat Server Features</span></span>](https://technet.microsoft.com/library/c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8.aspx)

<span data-ttu-id="43ea6-113">Para obter detalhes sobre os diferentes procedimentos que você pode executar usando o Painel de Controle do Skype for Business Server, consulte [Gerenciar o Skype for Business Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="43ea6-113">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="43ea6-114">Para configurar as categorias para salas de chat</span><span class="sxs-lookup"><span data-stu-id="43ea6-114">To configure categories for chat rooms</span></span>

<span data-ttu-id="43ea6-115">Em **Associação,** na seção **Criadores,** adicione ou remova usuários e outras entidades do Active Directory associadas aos criadores da categoria.</span><span class="sxs-lookup"><span data-stu-id="43ea6-115">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="43ea6-116">Um criador é um usuário com permissões para criar salas de chat e atribuir gerentes e membros de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="43ea6-116">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>



<span data-ttu-id="43ea6-117">Para obter detalhes sobre recursos do Servidor de Chat Persistente, consulte [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="43ea6-117">For details about Persistent Chat Server features and capabilities, see [Overview of Persistent Chat Server](https://technet.microsoft.com/library/23f7c886-304d-495a-ae70-3cbb44241acd.aspx) in the Planning documentation.</span></span> <span data-ttu-id="43ea6-118">Para obter detalhes sobre como trabalhar com configurações de Servidor de Chat Persistente, consulte [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="43ea6-118">For details about working with Persistent Chat Server configurations, see [Configuring Persistent Chat Server](https://technet.microsoft.com/library/d90a4049-b268-4e8e-9f24-0cef08c8d9ed.aspx) in the Deployment documentation and [Managing Lync Server 2013, Persistent Chat Server](https://technet.microsoft.com/library/82befdc6-5d32-45f1-bfd7-aaedffed1ab8.aspx) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="43ea6-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="43ea6-119">See also</span></span>

[<span data-ttu-id="43ea6-120">Noções básicas sobre associação ao chat persistente</span><span class="sxs-lookup"><span data-stu-id="43ea6-120">Understanding Persistent Chat Membership</span></span>](https://technet.microsoft.com/library/900392d6-6e9f-4dae-93d6-39d7474409ef.aspx)

[<span data-ttu-id="43ea6-121">Usando categorias para administrar o servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="43ea6-121">Using Categories to Administer Persistent Chat Server</span></span>](https://technet.microsoft.com/library/dfcb3ad1-da90-467e-b08c-f4e68673b7b5.aspx)

[<span data-ttu-id="43ea6-122">Movendo uma sala de chat para outra categoria</span><span class="sxs-lookup"><span data-stu-id="43ea6-122">Moving a Chat Room from One Category to Another</span></span>](https://technet.microsoft.com/library/7e93b8f6-5a18-4476-a432-3918e01bcfa6.aspx)

[<span data-ttu-id="43ea6-123">Criando ou editando uma nova sala</span><span class="sxs-lookup"><span data-stu-id="43ea6-123">Creating or Editing a New Room</span></span>](https://technet.microsoft.com/library/aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4.aspx)
