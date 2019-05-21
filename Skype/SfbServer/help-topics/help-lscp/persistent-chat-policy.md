---
title: Política de Chat Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Você pode usar a página Política de Chat Persistente do grupo Chat Persistente para gerenciar políticas no nível global, de pool, de site ou de usuário, inclusive para configurar a política global padrão e criar uma ou mais políticas de usuário e de site para sua implantação. Se o servidor de chat persistente estiver habilitado para um usuário por política, o ambiente do servidor de chat persistente aparecerá no cliente.
ms.openlocfilehash: f08f0af3c2f553f1acc980c64be1602519ffa898
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291057"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="8dcfc-104">Política de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="8dcfc-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="8dcfc-105">Você pode usar a página **Política de Chat Persistente** do grupo **Chat Persistente** para gerenciar políticas no nível global, de pool, de site ou de usuário, inclusive para configurar a política global padrão e criar uma ou mais políticas de usuário e de site para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="8dcfc-106">Se o servidor de chat persistente estiver habilitado para um usuário por política, o ambiente do servidor de chat persistente aparecerá no cliente.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="8dcfc-107">A política global é criada automaticamente quando você implanta um servidor de chat persistente, e pode ser configurada, mas não excluída.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="8dcfc-108">Como a política global se aplica a todos os usuários, ela não precisa ser definida por usuário.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="8dcfc-109">Você pode criar e configurar várias políticas de site e de usuário, juntamente com a política global, habilitar usuários para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="8dcfc-110">As políticas de servidor de chat persistente do pool e do site substituem a política global de servidor de chat persistente, mas somente para os usuários desse site.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="8dcfc-111">As políticas de usuário substituem as políticas globais, de pool e de site para os usuários aos quais são atribuídas.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8dcfc-112">Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="8dcfc-113">Para obter detalhes, consulte [Adicionar servidor de chat persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="8dcfc-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="8dcfc-114">Tarefas que você pode executar</span><span class="sxs-lookup"><span data-stu-id="8dcfc-114">Tasks that you can perform</span></span>

<span data-ttu-id="8dcfc-115">Você pode executar as seguintes tarefas na página **Política de Chat Persistente**: habilitar e gerenciar a política de Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="8dcfc-116">Para configurar a política global para chats persistentes</span><span class="sxs-lookup"><span data-stu-id="8dcfc-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="8dcfc-117">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8dcfc-118">No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8dcfc-119">No painel de controle do Skype for Business Server, clique em **chat persistente**e, em seguida, clique em **política de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="8dcfc-120">Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8dcfc-121">Em **Editar Política de Chat Persistent - Global**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="8dcfc-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="8dcfc-122">Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="8dcfc-123">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política global para _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="8dcfc-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="8dcfc-124">Para controlar o chat persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="8dcfc-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="8dcfc-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="8dcfc-126">Para criar uma política de chat persistente para um site</span><span class="sxs-lookup"><span data-stu-id="8dcfc-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="8dcfc-127">Para cada site que você implantou, é possível criar uma política de chat persistente específica do site.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="8dcfc-128">A configuração da política de site substitui a política global, mas somente para o site específico coberto pela política de site.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="8dcfc-129">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8dcfc-130">No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8dcfc-131">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="8dcfc-132">Clique em **Novo** e, em seguida, clique em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="8dcfc-133">Em **Selecionar um Site**, clique no site ao qual a política deverá ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="8dcfc-134">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="8dcfc-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="8dcfc-135">Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="8dcfc-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="8dcfc-136">Em **Descrição**, forneça detalhes sobre a política de site (por exemplo, política de sala de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="8dcfc-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="8dcfc-137">Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="8dcfc-138">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="8dcfc-139">Para criar uma política de usuário para chat persistente</span><span class="sxs-lookup"><span data-stu-id="8dcfc-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="8dcfc-140">No painel de controle do Skype for Business Server, você define as políticas de usuário que podem ser atribuídas aos usuários nos **usuários**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="8dcfc-141">A política de usuário substitui as políticas globais e de site, mas apenas para os usuários específicos aos quais ela é atribuída.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="8dcfc-142">Em uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8dcfc-143">No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8dcfc-144">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="8dcfc-145">Clique em **Novo** e em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="8dcfc-146">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="8dcfc-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="8dcfc-147">Em **Nome**, especifique um nome para a nova política de usuário.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="8dcfc-148">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de chat persistente para um usuário específico).</span><span class="sxs-lookup"><span data-stu-id="8dcfc-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="8dcfc-149">Para controlar o chat persistente para todos os usuários que não são controlados especificamente por meio de uma política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="8dcfc-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="8dcfc-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="8dcfc-151">Para aplicar uma política de usuário de chat persistente a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="8dcfc-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="8dcfc-152">Se um usuário tiver sido habilitado para o Skype for Business Server, você poderá aplicar políticas adequadas a usuários específicos para habilitá-las ou desabilitá-las para um servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="8dcfc-153">Use o procedimento deste tópico para aplicar uma política de usuário de chat persistente criada anteriormente a uma ou mais contas de usuário ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="8dcfc-154">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="8dcfc-155">No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="8dcfc-156">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="8dcfc-157">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="8dcfc-158">Em **Editar usuário do Lync Server** na **política de chat persistente**, selecione a política de usuário de chat persistente que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8dcfc-159">As \*\* \<configurações\> automáticas\*\* aplicam a política em vigor padrão.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="8dcfc-160">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="8dcfc-161">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="8dcfc-161">Click **Commit**.</span></span>
    

