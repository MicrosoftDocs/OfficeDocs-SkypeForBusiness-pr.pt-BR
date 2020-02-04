---
title: 'Lync Server 2013: Habilitar política de Servidor de Chat Persistente'
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
ms.openlocfilehash: 27d87277c813c24ae36de14430bc711d991d7181
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="5d40c-102">Habilitar política de Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d40c-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d40c-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5d40c-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5d40c-104">No painel de controle do Lync Server 2013, você pode usar a página **política de chat persistente** do grupo de **chat persistente** para gerenciar políticas em um nível global, de pool, de site ou de usuário, incluindo a configuração da política global padrão e a criação de uma ou mais políticas de usuário e de site adicionais para a sua implantação.</span><span class="sxs-lookup"><span data-stu-id="5d40c-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="5d40c-105">Se um usuário estiver habilitado para o servidor de chat persistente por política, o ambiente do servidor de chat persistente aparecerá no cliente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5d40c-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d40c-106">Na topologia, as políticas de site do servidor de chat persistente se aplicam globalmente, o pool de cada usuário ou o site de cada usuário ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="5d40c-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="5d40c-107">A política global é criada automaticamente quando você implanta um servidor de chat persistente, e pode ser configurada, mas não excluída.</span><span class="sxs-lookup"><span data-stu-id="5d40c-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="5d40c-108">Como ela se aplica a todos os usuários, não é necessário defini-la por usuário.</span><span class="sxs-lookup"><span data-stu-id="5d40c-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="5d40c-109">Você pode criar e configurar várias políticas de site e de usuário, juntamente com a política global, habilitar usuários para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="5d40c-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="5d40c-110">As políticas de servidor de chat persistente do pool e do site substituem a política global de servidor de chat persistente, mas somente para os usuários desse site.</span><span class="sxs-lookup"><span data-stu-id="5d40c-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="5d40c-111">As políticas de usuário substituem as políticas globais, de pool e de site para os usuários aos quais são atribuídas.</span><span class="sxs-lookup"><span data-stu-id="5d40c-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5d40c-112">Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="5d40c-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="5d40c-113">Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="5d40c-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5d40c-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5d40c-114">In This Section</span></span>

  - [<span data-ttu-id="5d40c-115">Configurar a política global para Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d40c-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="5d40c-116">Criar uma política de site para chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d40c-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="5d40c-117">Criar uma política de usuário para Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d40c-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="5d40c-118">Aplicar uma política de Chat Persistente a um usuário ou grupo de usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d40c-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

