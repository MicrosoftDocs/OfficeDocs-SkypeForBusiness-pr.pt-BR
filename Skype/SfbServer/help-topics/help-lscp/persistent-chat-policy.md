---
title: Política de Chat Persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Você pode usar a página Política de Chat Persistente do grupo de Chat Persistente para gerenciar políticas em um nível global, de pool, de site ou de usuário, incluindo a configuração da política global padrão e a criação de uma ou mais políticas adicionais de usuário e site para sua implantação. Se o Servidor de Chat Persistente estiver habilitado para um usuário por política, o ambiente do Servidor de Chat Persistente aparecerá em seu cliente.
ms.openlocfilehash: e7148530f571a46937ee8d8a3bf44315ac692eb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819291"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="57133-104">Política de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="57133-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="57133-105">Você pode usar a página Política de **Chat** Persistente do grupo de **Chat** Persistente para gerenciar políticas em um nível global, de pool, de site ou de usuário, incluindo a configuração da política global padrão e a criação de uma ou mais políticas adicionais de usuário e site para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="57133-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="57133-106">Se o Servidor de Chat Persistente estiver habilitado para um usuário por política, o ambiente do Servidor de Chat Persistente aparecerá em seu cliente.</span><span class="sxs-lookup"><span data-stu-id="57133-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="57133-107">A política global é criada automaticamente quando você implanta o Servidor de Chat Persistente e pode ser configurada, mas não excluída.</span><span class="sxs-lookup"><span data-stu-id="57133-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="57133-108">Como a política global se aplica a todos os usuários, ela não precisa ser definida por usuário.</span><span class="sxs-lookup"><span data-stu-id="57133-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="57133-109">Você pode criar e configurar várias políticas de site e de usuário que, juntamente com a política global, habilitam usuários para o Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="57133-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="57133-110">As políticas de Servidor de Chat Persistente de pool e site substituem a política global do Servidor de Chat Persistente, mas somente para usuários desse site.</span><span class="sxs-lookup"><span data-stu-id="57133-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="57133-111">As políticas de usuário substituem as políticas global, de pool e de site para os usuários aos quais a política de usuário é atribuída.</span><span class="sxs-lookup"><span data-stu-id="57133-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57133-112">Para configurar e usar o Servidor de Chat Persistente, primeiro você deve usar o Construtor de Topologias para adicionar suporte ao Servidor de Chat Persistente à topologia e publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="57133-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="57133-113">Para obter detalhes, [consulte Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="57133-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="57133-114">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="57133-114">Tasks that you can perform</span></span>

<span data-ttu-id="57133-115">É possível executar as seguintes tarefas na página Política de **Chat Persistente:** habilitar política de Servidor de Chat Persistente; gerenciar a política do Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="57133-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="57133-116">Para configurar a Política Global para Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="57133-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="57133-117">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="57133-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57133-118">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="57133-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="57133-119">No Painel de Controle do Skype for Business Server, clique em **Chat Persistente** e em Política de **Chat Persistente.**</span><span class="sxs-lookup"><span data-stu-id="57133-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="57133-120">Clique em **Global** na lista de políticas, clique em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="57133-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="57133-121">Em **Editar Política de Chat Persistente - Global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="57133-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="57133-122">Em **Nome**, especifique um novo nome para a política global, se você não quiser usar o padrão de Global.</span><span class="sxs-lookup"><span data-stu-id="57133-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="57133-123">Em **Descrição,** forneça detalhes sobre a política de usuário (por exemplo, política global  _para centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="57133-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="57133-124">Para controlar o Chat Persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou de usuário, marque ou des marque a caixa de seleção Habilitar **Chat** Persistente.</span><span class="sxs-lookup"><span data-stu-id="57133-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="57133-125">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="57133-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="57133-126">Para criar uma política de Chat Persistente para um site</span><span class="sxs-lookup"><span data-stu-id="57133-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="57133-127">Para cada site implantado, você pode criar uma política de Chat Persistente específica do site.</span><span class="sxs-lookup"><span data-stu-id="57133-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="57133-128">A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política.</span><span class="sxs-lookup"><span data-stu-id="57133-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="57133-129">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="57133-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57133-130">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="57133-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="57133-131">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="57133-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="57133-132">Clique em **Novo** e, em seguida, em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="57133-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="57133-133">Em **Selecionar um Site**, clique no site para o qual a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="57133-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="57133-134">Em **Nova Política de Chat Persistente**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="57133-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="57133-135">Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="57133-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="57133-136">Em **Descrição**, forneça detalhes sobre o que é a política de site (por exemplo, política de sala de chat para Redmond).</span><span class="sxs-lookup"><span data-stu-id="57133-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="57133-137">Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="57133-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="57133-138">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="57133-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="57133-139">Para criar uma política de usuário para Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="57133-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="57133-140">No Painel de Controle do Skype for Business Server, defina as políticas de usuário que podem ser atribuídas aos usuários em **Usuários.**</span><span class="sxs-lookup"><span data-stu-id="57133-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="57133-141">A política de usuário substitui a política global e as políticas de site, mas somente para os usuários específicos atribuídos à política de usuário.</span><span class="sxs-lookup"><span data-stu-id="57133-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="57133-142">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="57133-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57133-143">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="57133-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="57133-144">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="57133-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="57133-145">Clique em **Novo** e, em seguida, em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="57133-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="57133-146">Em **Nova Política de Chat Persistente**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="57133-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="57133-147">Em **Nome**, especifique um nome para a nova política de usuário.</span><span class="sxs-lookup"><span data-stu-id="57133-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="57133-148">Em **Descrição,** forneça detalhes sobre a política de usuário (por exemplo, política de Chat Persistente para usuário específico).</span><span class="sxs-lookup"><span data-stu-id="57133-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="57133-149">Para controlar o Chat Persistente para todos os usuários que não são controlados especificamente por meio de uma política de usuário, marque ou des limpe a caixa de seleção **Habilitar Chat** Persistente.</span><span class="sxs-lookup"><span data-stu-id="57133-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="57133-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="57133-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="57133-151">Para aplicar uma política de usuário de Chat Persistente a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="57133-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="57133-152">Se um usuário tiver sido habilitado para o Skype for Business Server, você poderá aplicar políticas apropriadas a usuários específicos para habilita-los ou desabilitá-los para o Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="57133-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="57133-153">Use o procedimento neste tópico para aplicar uma política de usuário de Chat Persistente criada anteriormente a uma ou mais contas de usuário ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="57133-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="57133-154">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="57133-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57133-155">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="57133-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="57133-156">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="57133-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="57133-157">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="57133-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="57133-158">Em **Editar Usuário do Lync Server em** Política de Chat **Persistente,** selecione a política de usuário de Chat Persistente que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="57133-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57133-159">As **\<Automatic\>** configurações aplicam a política efetiva padrão.</span><span class="sxs-lookup"><span data-stu-id="57133-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="57133-160">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="57133-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="57133-161">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="57133-161">Click **Commit**.</span></span>
    

