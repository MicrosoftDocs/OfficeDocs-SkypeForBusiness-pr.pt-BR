---
title: Política de Chat Persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Você pode usar a página Política de Chat Persistente do grupo Chat Persistente para gerenciar políticas no nível global, de pool, de site ou de usuário, inclusive para configurar a política global padrão e criar uma ou mais políticas de usuário e de site para sua implantação. Se o servidor de Chat persistente estiver habilitado para um usuário por diretiva, o ambiente de servidor de Chat persistente aparece em seu cliente.
ms.openlocfilehash: fc994f74acc0abf8d4d615d3d85ea3662c367904
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894926"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="36bdf-104">Política de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="36bdf-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="36bdf-105">Você pode usar a página **Política de Chat Persistente** do grupo **Chat Persistente** para gerenciar políticas no nível global, de pool, de site ou de usuário, inclusive para configurar a política global padrão e criar uma ou mais políticas de usuário e de site para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="36bdf-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="36bdf-106">Se o servidor de Chat persistente estiver habilitado para um usuário por diretiva, o ambiente de servidor de Chat persistente aparece em seu cliente.</span><span class="sxs-lookup"><span data-stu-id="36bdf-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="36bdf-107">A política global é criada automaticamente quando você implantar o servidor de Chat persistente, e ele pode ser configurado, mas não excluído.</span><span class="sxs-lookup"><span data-stu-id="36bdf-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="36bdf-108">Porque a política global se aplica a todos os usuários, ele não tem que ser definida por usuário.</span><span class="sxs-lookup"><span data-stu-id="36bdf-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="36bdf-109">Você pode criar e configurar várias políticas de site e de usuário que, juntamente com a política global, habilitar usuários para o servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="36bdf-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="36bdf-110">Políticas de Persistent Chat Server pool e site substituem a política de servidor de Chat persistente global, mas somente para usuários do site.</span><span class="sxs-lookup"><span data-stu-id="36bdf-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="36bdf-111">As políticas de usuário substituem as políticas globais, de pool e de site para os usuários aos quais são atribuídas.</span><span class="sxs-lookup"><span data-stu-id="36bdf-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36bdf-112">Para configurar e usar o servidor de Chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte ao servidor de Chat persistente à topologia e, em seguida, publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="36bdf-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="36bdf-113">Para obter detalhes, consulte [Adicionar servidor de Chat persistente para seu Skype para a topologia de negócios Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="36bdf-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="36bdf-114">Tarefas que você pode executar</span><span class="sxs-lookup"><span data-stu-id="36bdf-114">Tasks that you can perform</span></span>

<span data-ttu-id="36bdf-115">Você pode executar as seguintes tarefas na página **Política de Chat Persistente**: habilitar e gerenciar a política de Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="36bdf-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="36bdf-116">Para configurar a política Global para o Chat persistente</span><span class="sxs-lookup"><span data-stu-id="36bdf-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="36bdf-117">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="36bdf-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="36bdf-118">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="36bdf-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="36bdf-119">No painel de controle do servidor de negócios do Skype, clique em **Chat persistente**e clique em **Política de Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="36bdf-120">Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="36bdf-121">Em **Editar Política de Chat Persistent - Global**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="36bdf-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="36bdf-122">Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.</span><span class="sxs-lookup"><span data-stu-id="36bdf-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="36bdf-123">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política Global para _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="36bdf-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="36bdf-124">Para controlar o Chat persistente para todos os sites e usuários não especificamente controlados através de uma política de site ou usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="36bdf-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="36bdf-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="36bdf-126">Para criar uma política de Chat persistente para um site</span><span class="sxs-lookup"><span data-stu-id="36bdf-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="36bdf-127">Para cada site implantado, você pode criar uma política de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="36bdf-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="36bdf-128">A configuração da política de site substitui a política global, mas somente para o site específico coberto pela política de site.</span><span class="sxs-lookup"><span data-stu-id="36bdf-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="36bdf-129">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="36bdf-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="36bdf-130">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="36bdf-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="36bdf-131">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="36bdf-132">Clique em **Novo** e, em seguida, clique em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="36bdf-133">Em **Selecionar um Site**, clique no site ao qual a política deverá ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="36bdf-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="36bdf-134">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="36bdf-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="36bdf-135">Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="36bdf-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="36bdf-136">Em **Descrição**, forneça detalhes sobre a política de site (por exemplo, política de sala de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="36bdf-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="36bdf-137">Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="36bdf-138">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="36bdf-139">Para criar uma política de usuário para o Chat persistente</span><span class="sxs-lookup"><span data-stu-id="36bdf-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="36bdf-140">No Skype para painel de controle do Business Server, você define as políticas de usuário que podem ser atribuídas aos usuários em **usuários**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="36bdf-141">A política de usuário substitui as políticas globais e de site, mas apenas para os usuários específicos aos quais ela é atribuída.</span><span class="sxs-lookup"><span data-stu-id="36bdf-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="36bdf-142">Em uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="36bdf-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="36bdf-143">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="36bdf-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="36bdf-144">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="36bdf-145">Clique em **Novo** e em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="36bdf-146">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="36bdf-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="36bdf-147">Em **Nome**, especifique um nome para a nova política de usuário.</span><span class="sxs-lookup"><span data-stu-id="36bdf-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="36bdf-148">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de Chat persistente para usuário específico).</span><span class="sxs-lookup"><span data-stu-id="36bdf-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="36bdf-149">Para controlar o Chat persistente para todos os usuários que não são especificamente controlados através de uma política de usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="36bdf-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="36bdf-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="36bdf-151">Para aplicar uma política de usuário de Chat persistente para uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="36bdf-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="36bdf-152">Se um usuário tiver sido habilitado para Skype para Business Server, você pode aplicar as políticas adequadas a usuários específicos para habilitar ou desabilitá-las para o servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="36bdf-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="36bdf-153">Use o procedimento neste tópico para aplicar uma política de usuário de Chat persistente criada anteriormente para uma ou mais contas de usuário ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="36bdf-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="36bdf-154">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="36bdf-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="36bdf-155">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="36bdf-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="36bdf-156">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="36bdf-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="36bdf-157">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="36bdf-158">Em **Editar usuário do Lync Server** , em **política de Chat persistente**, selecione a política de usuário de Chat persistente que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="36bdf-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="36bdf-159">O \*\* \<automática\> \*\* configurações se aplicam a diretiva padrão de efetiva.</span><span class="sxs-lookup"><span data-stu-id="36bdf-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="36bdf-160">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="36bdf-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="36bdf-161">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="36bdf-161">Click **Commit**.</span></span>
    

