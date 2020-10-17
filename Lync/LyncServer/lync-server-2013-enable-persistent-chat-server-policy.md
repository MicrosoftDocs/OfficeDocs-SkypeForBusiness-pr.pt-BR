---
title: 'Lync Server 2013: habilitar política de servidor de chat persistente'
description: 'Lync Server 2013: habilitar política de servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58da577679795f00492af72b43ca72106d40f4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547877"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="d6fc5-103">Habilitar política de servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6fc5-103">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6fc5-104">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d6fc5-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d6fc5-105">No painel de controle do Lync Server 2013, você pode usar a página **política de chat persistente** do grupo de **chat persistente** para gerenciar políticas em nível global, de pool, de site ou de usuário, incluindo a configuração da política global padrão e a criação de uma ou mais políticas de usuário e de site adicionais para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-105">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="d6fc5-106">Se um usuário estiver habilitado para o servidor de chat persistente por política, o ambiente do servidor de chat persistente aparecerá no cliente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6fc5-107">Na topologia, as políticas de site do servidor de chat persistente são aplicadas globalmente, por pool do usuário ou por site do usuário ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-107">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="d6fc5-108">A política global é criada automaticamente quando você implanta o servidor de chat persistente, e pode ser configurada, mas não excluída.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="d6fc5-109">Como a política global se aplica a todos os usuários, não é necessário defini-la para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-109">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="d6fc5-110">Você pode criar e configurar várias políticas de site e de usuário, juntamente com a política global, habilitar usuários para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="d6fc5-111">As políticas de servidor de chat persistente de pool e de site substituem a política global de servidor de chat persistente, mas apenas para os usuários desse site.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="d6fc5-112">As políticas de usuário substituem as políticas global, de pool e de site para os usuários aos quais a política de usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6fc5-113">Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à topologia e, em seguida, publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="d6fc5-114">Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="d6fc5-114">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6fc5-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d6fc5-115">In This Section</span></span>

  - [<span data-ttu-id="d6fc5-116">Configurar a política global para chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6fc5-116">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="d6fc5-117">Criar uma política de site para chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6fc5-117">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="d6fc5-118">Criar uma política de usuário para chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6fc5-118">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="d6fc5-119">Aplicar uma política de chat persistente a um usuário ou grupo de usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6fc5-119">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

