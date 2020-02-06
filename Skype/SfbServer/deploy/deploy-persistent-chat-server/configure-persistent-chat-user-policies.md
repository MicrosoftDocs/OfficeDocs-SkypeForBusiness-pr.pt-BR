---
title: Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumo: Leia este tópico para saber como criar políticas iniciais de usuário para o servidor de chat persistente no Skype for Business Server 2015. Políticas de usuário de chat persistente determinam se os usuários podem ou não acesso a salas de chat.'
ms.openlocfilehash: a51304c9e85951e9858d56c511aa8c7519babe51
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795692"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="22eea-104">Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="22eea-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="22eea-105">**Resumo:** Leia este tópico para saber como criar políticas iniciais de usuário para o servidor de chat persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="22eea-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="22eea-106">Políticas de usuário de chat persistente determinam se os usuários podem ou não acesso a salas de chat.</span><span class="sxs-lookup"><span data-stu-id="22eea-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="22eea-107">Você pode gerenciar políticas de usuário do servidor de chat persistente nos seguintes níveis: global, site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="22eea-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="22eea-108">Inicialmente, você configura a política global para habilitar configurações de Chat Persistente para todos os usuários na sua implantação, e então cria políticas adicionais de site e usuário para controlar se o Chat Persistente está ativado para sites e usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="22eea-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="22eea-109">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="22eea-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="22eea-110">Configurar a política global</span><span class="sxs-lookup"><span data-stu-id="22eea-110">Configure the global policy</span></span>
    
- <span data-ttu-id="22eea-111">Criar uma política de site</span><span class="sxs-lookup"><span data-stu-id="22eea-111">Create a site policy</span></span>
    
- <span data-ttu-id="22eea-112">Criar uma política de usuário</span><span class="sxs-lookup"><span data-stu-id="22eea-112">Create a user policy</span></span>
    
- <span data-ttu-id="22eea-113">Aplicar uma política a um usuário ou grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="22eea-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="22eea-114">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="22eea-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="22eea-115">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22eea-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="22eea-116">Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="22eea-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="22eea-117">Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="22eea-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="22eea-118">Configurar a política global</span><span class="sxs-lookup"><span data-stu-id="22eea-118">Configure the global policy</span></span>

<span data-ttu-id="22eea-119">Para configurar a política global:</span><span class="sxs-lookup"><span data-stu-id="22eea-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="22eea-120">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22eea-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22eea-121">No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="22eea-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="22eea-122">No painel de controle do Skype for Business Server, clique em **chat persistente**e, em seguida, clique em **política de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="22eea-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="22eea-123">Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="22eea-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="22eea-124">Em **Editar Política de Chat Persistent - Global**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="22eea-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="22eea-125">Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.</span><span class="sxs-lookup"><span data-stu-id="22eea-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="22eea-126">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política global para _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="22eea-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="22eea-127">Para controlar o chat persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="22eea-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="22eea-128">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22eea-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="22eea-129">Criar uma política de site</span><span class="sxs-lookup"><span data-stu-id="22eea-129">Create a site policy</span></span>

<span data-ttu-id="22eea-130">Para cada site implantado, é possível criar uma política de Chat Persistente específica do site.</span><span class="sxs-lookup"><span data-stu-id="22eea-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="22eea-131">A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site.</span><span class="sxs-lookup"><span data-stu-id="22eea-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="22eea-132">Para criar uma política de site:</span><span class="sxs-lookup"><span data-stu-id="22eea-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="22eea-133">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22eea-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22eea-134">No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="22eea-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="22eea-135">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="22eea-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="22eea-136">Clique em **Novo** e, em seguida, clique em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="22eea-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="22eea-137">Em **Selecionar um Site**, clique no site ao qual a política deverá ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="22eea-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="22eea-138">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="22eea-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="22eea-139">Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="22eea-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="22eea-140">Em **Descrição**, forneça detalhes sobre a política de site (por exemplo, política de sala de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="22eea-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="22eea-141">Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="22eea-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="22eea-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22eea-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="22eea-143">Criar uma política de usuário</span><span class="sxs-lookup"><span data-stu-id="22eea-143">Create a user policy</span></span>

<span data-ttu-id="22eea-144">Você pode criar políticas específicas de usuário que substituem a política global e quaisquer políticas de site ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="22eea-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="22eea-145">Para criar uma política de usuário:</span><span class="sxs-lookup"><span data-stu-id="22eea-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="22eea-146">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22eea-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22eea-147">No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="22eea-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="22eea-148">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="22eea-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="22eea-149">Clique em **Novo** e em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="22eea-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="22eea-150">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="22eea-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="22eea-151">Em **Nome**, especifique um nome para a nova política de usuário.</span><span class="sxs-lookup"><span data-stu-id="22eea-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="22eea-152">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de chat persistente para um usuário específico).</span><span class="sxs-lookup"><span data-stu-id="22eea-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="22eea-153">Para controlar o chat persistente para todos os usuários que não são controlados especificamente por meio de uma política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="22eea-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="22eea-154">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22eea-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="22eea-155">Aplicar uma política a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="22eea-155">Apply a policy to a user account</span></span>

<span data-ttu-id="22eea-156">Após criar as políticas, você pode aplicá-las a uma conta de usuário da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="22eea-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="22eea-157">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22eea-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22eea-158">No menu **Iniciar** , selecione o painel de controle do Skype for Business Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="22eea-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="22eea-159">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="22eea-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="22eea-160">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="22eea-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="22eea-161">Em **Editar o usuário do Skype for Business Server** na **política de chat persistente**, selecione a política de usuário de chat persistente que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="22eea-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22eea-162">As \*\* \<configurações\> automáticas\*\* aplicam a política em vigor padrão.</span><span class="sxs-lookup"><span data-stu-id="22eea-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="22eea-163">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="22eea-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="22eea-164">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22eea-164">Click **Commit**.</span></span>
    

