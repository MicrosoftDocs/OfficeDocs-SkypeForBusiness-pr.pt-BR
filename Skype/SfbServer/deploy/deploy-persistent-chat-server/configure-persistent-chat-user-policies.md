---
title: Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumo: Leia este tópico para saber como criar políticas de usuário inicial para o servidor de Chat persistente no Skype para Business Server 2015. As diretivas de usuário de Chat persistentes determinam se ou não os usuários poderão acesso a salas de bate-papo.'
ms.openlocfilehash: 01ed6eb048f1949c93260c554eb58d0c76c5259f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="f8d82-104">Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f8d82-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f8d82-105">**Resumo:** Leia este tópico para saber como criar políticas de usuário inicial para o servidor de Chat persistente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f8d82-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="f8d82-106">As diretivas de usuário de Chat persistentes determinam se ou não os usuários poderão acesso a salas de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="f8d82-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="f8d82-107">Você pode gerenciar políticas de usuário do servidor de Chat persistente nos seguintes níveis: global, site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="f8d82-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="f8d82-108">Inicialmente, você configura a política global para habilitar configurações de Chat Persistente para todos os usuários na sua implantação, e então cria políticas adicionais de site e usuário para controlar se o Chat Persistente está ativado para sites e usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="f8d82-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="f8d82-109">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="f8d82-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="f8d82-110">Configurar a política global</span><span class="sxs-lookup"><span data-stu-id="f8d82-110">Configure the global policy</span></span>
    
- <span data-ttu-id="f8d82-111">Criar uma política de site</span><span class="sxs-lookup"><span data-stu-id="f8d82-111">Create a site policy</span></span>
    
- <span data-ttu-id="f8d82-112">Criar uma política de usuário</span><span class="sxs-lookup"><span data-stu-id="f8d82-112">Create a user policy</span></span>
    
- <span data-ttu-id="f8d82-113">Aplicar uma política a um usuário ou grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="f8d82-113">Apply a policy to a user or user group</span></span>
    
## <a name="configure-the-global-policy"></a><span data-ttu-id="f8d82-114">Configurar a política global</span><span class="sxs-lookup"><span data-stu-id="f8d82-114">Configure the global policy</span></span>

<span data-ttu-id="f8d82-115">Para configurar a política global:</span><span class="sxs-lookup"><span data-stu-id="f8d82-115">To configure the global policy:</span></span>
  
1. <span data-ttu-id="f8d82-116">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f8d82-116">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f8d82-117">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="f8d82-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="f8d82-118">No painel de controle do servidor de negócios do Skype, clique em **Chat persistente**e clique em **Política de Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-118">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="f8d82-119">Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f8d82-120">Em **Editar Política de Chat Persistent - Global**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="f8d82-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="f8d82-121">Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.</span><span class="sxs-lookup"><span data-stu-id="f8d82-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="f8d82-122">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política Global para _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="f8d82-122">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="f8d82-123">Para controlar o Chat persistente para todos os sites e usuários não especificamente controlados através de uma política de site ou usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="f8d82-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="f8d82-124">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-124">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="f8d82-125">Criar uma política de site</span><span class="sxs-lookup"><span data-stu-id="f8d82-125">Create a site policy</span></span>

<span data-ttu-id="f8d82-126">Para cada site implantado, é possível criar uma política de Chat Persistente específica do site.</span><span class="sxs-lookup"><span data-stu-id="f8d82-126">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="f8d82-127">A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site.</span><span class="sxs-lookup"><span data-stu-id="f8d82-127">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="f8d82-128">Para criar uma política de site:</span><span class="sxs-lookup"><span data-stu-id="f8d82-128">To create a site policy:</span></span>
  
1. <span data-ttu-id="f8d82-129">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f8d82-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f8d82-130">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="f8d82-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="f8d82-131">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="f8d82-132">Clique em **Novo** e, em seguida, clique em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="f8d82-133">Em **Selecionar um Site**, clique no site ao qual a política deverá ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="f8d82-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="f8d82-134">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="f8d82-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="f8d82-135">Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="f8d82-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="f8d82-136">Em **Descrição**, forneça detalhes sobre a política de site (por exemplo, política de sala de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="f8d82-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="f8d82-137">Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="f8d82-138">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-138">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="f8d82-139">Criar uma política de usuário</span><span class="sxs-lookup"><span data-stu-id="f8d82-139">Create a user policy</span></span>

<span data-ttu-id="f8d82-140">Você pode criar políticas específicas de usuário que substituem a política global e quaisquer políticas de site ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="f8d82-140">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="f8d82-141">Para criar uma política de usuário:</span><span class="sxs-lookup"><span data-stu-id="f8d82-141">To create a user policy:</span></span>
  
1. <span data-ttu-id="f8d82-142">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f8d82-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f8d82-143">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="f8d82-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="f8d82-144">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="f8d82-145">Clique em **Novo** e em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="f8d82-146">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="f8d82-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="f8d82-147">Em **Nome**, especifique um nome para a nova política de usuário.</span><span class="sxs-lookup"><span data-stu-id="f8d82-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="f8d82-148">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de Chat persistente para usuário específico).</span><span class="sxs-lookup"><span data-stu-id="f8d82-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="f8d82-149">Para controlar o Chat persistente para todos os usuários que não são especificamente controlados através de uma política de usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="f8d82-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="f8d82-150">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-150">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="f8d82-151">Aplicar uma política a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="f8d82-151">Apply a policy to a user account</span></span>

<span data-ttu-id="f8d82-152">Após criar as políticas, você pode aplicá-las a uma conta de usuário da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f8d82-152">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="f8d82-153">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="f8d82-153">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f8d82-154">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="f8d82-154">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="f8d82-155">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="f8d82-155">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="f8d82-156">Na tabela que lista os resultados da pesquisa, clique na conta de usuário, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-156">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f8d82-157">Em **Editar Skype para usuário de servidor de negócios** em **política de Chat persistente**, selecione a política de usuário de Chat persistente que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="f8d82-157">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8d82-158">O ** \<automática\> ** configurações se aplicam a diretiva padrão de efetiva.</span><span class="sxs-lookup"><span data-stu-id="f8d82-158">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="f8d82-159">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="f8d82-159">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="f8d82-160">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f8d82-160">Click **Commit**.</span></span>
    

