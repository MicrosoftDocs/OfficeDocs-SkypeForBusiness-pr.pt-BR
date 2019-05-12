---
title: Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumo: Leia este tópico para saber como criar políticas de usuário inicial para o servidor de Chat persistente no Skype para Business Server 2015. As diretivas de usuário de Chat persistentes determinam se ou não os usuários poderão acesso a salas de bate-papo.'
ms.openlocfilehash: 84bc1236bf8fd08063f55c9a0c3b0d63ff4eb280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894504"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="a6ef7-104">Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a6ef7-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a6ef7-105">**Resumo:** Leia este tópico para saber como criar políticas de usuário inicial para o servidor de Chat persistente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="a6ef7-106">As diretivas de usuário de Chat persistentes determinam se ou não os usuários poderão acesso a salas de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="a6ef7-107">Você pode gerenciar políticas de usuário do servidor de Chat persistente nos seguintes níveis: global, site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="a6ef7-108">Inicialmente, você configura a política global para habilitar configurações de Chat Persistente para todos os usuários na sua implantação, e então cria políticas adicionais de site e usuário para controlar se o Chat Persistente está ativado para sites e usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="a6ef7-109">Este tópico inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="a6ef7-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="a6ef7-110">Configurar a política global</span><span class="sxs-lookup"><span data-stu-id="a6ef7-110">Configure the global policy</span></span>
    
- <span data-ttu-id="a6ef7-111">Criar uma política de site</span><span class="sxs-lookup"><span data-stu-id="a6ef7-111">Create a site policy</span></span>
    
- <span data-ttu-id="a6ef7-112">Criar uma política de usuário</span><span class="sxs-lookup"><span data-stu-id="a6ef7-112">Create a user policy</span></span>
    
- <span data-ttu-id="a6ef7-113">Aplicar uma política a um usuário ou grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="a6ef7-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="a6ef7-114">Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a6ef7-115">A mesma funcionalidade está disponível em equipes.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="a6ef7-116">Para obter mais informações, consulte [jornada do Skype para negócios às equipes da Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="a6ef7-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="a6ef7-117">Se você precisar utilizar o chat persistente, suas opções são para migrar tanto os usuários que requerem essa funcionalidade para equipes ou para continuar usando o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="a6ef7-118">Configurar a política global</span><span class="sxs-lookup"><span data-stu-id="a6ef7-118">Configure the global policy</span></span>

<span data-ttu-id="a6ef7-119">Para configurar a política global:</span><span class="sxs-lookup"><span data-stu-id="a6ef7-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="a6ef7-120">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a6ef7-121">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a6ef7-122">No painel de controle do servidor de negócios do Skype, clique em **Chat persistente**e clique em **Política de Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a6ef7-123">Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a6ef7-124">Em **Editar Política de Chat Persistent - Global**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="a6ef7-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="a6ef7-125">Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="a6ef7-126">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política Global para _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="a6ef7-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="a6ef7-127">Para controlar o Chat persistente para todos os sites e usuários não especificamente controlados através de uma política de site ou usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="a6ef7-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="a6ef7-128">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="a6ef7-129">Criar uma política de site</span><span class="sxs-lookup"><span data-stu-id="a6ef7-129">Create a site policy</span></span>

<span data-ttu-id="a6ef7-130">Para cada site implantado, é possível criar uma política de Chat Persistente específica do site.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="a6ef7-131">A configuração no site substitui a política global, mas somente para o site específico coberto pela política de site.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="a6ef7-132">Para criar uma política de site:</span><span class="sxs-lookup"><span data-stu-id="a6ef7-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="a6ef7-133">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a6ef7-134">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a6ef7-135">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a6ef7-136">Clique em **Novo** e, em seguida, clique em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="a6ef7-137">Em **Selecionar um Site**, clique no site ao qual a política deverá ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="a6ef7-138">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="a6ef7-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="a6ef7-139">Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="a6ef7-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="a6ef7-140">Em **Descrição**, forneça detalhes sobre a política de site (por exemplo, política de sala de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="a6ef7-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="a6ef7-141">Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="a6ef7-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="a6ef7-143">Criar uma política de usuário</span><span class="sxs-lookup"><span data-stu-id="a6ef7-143">Create a user policy</span></span>

<span data-ttu-id="a6ef7-144">Você pode criar políticas específicas de usuário que substituem a política global e quaisquer políticas de site ao qual o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="a6ef7-145">Para criar uma política de usuário:</span><span class="sxs-lookup"><span data-stu-id="a6ef7-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="a6ef7-146">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a6ef7-147">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a6ef7-148">Na barra de navegação esquerda, clique em **Chat Persistente** e, em seguida, clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="a6ef7-149">Clique em **Novo** e em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="a6ef7-150">Em **Nova Política de Chat Persistente**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="a6ef7-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="a6ef7-151">Em **Nome**, especifique um nome para a nova política de usuário.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="a6ef7-152">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de Chat persistente para usuário específico).</span><span class="sxs-lookup"><span data-stu-id="a6ef7-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="a6ef7-153">Para controlar o Chat persistente para todos os usuários que não são especificamente controlados através de uma política de usuário, marque ou desmarque a caixa de seleção **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="a6ef7-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="a6ef7-154">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="a6ef7-155">Aplicar uma política a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="a6ef7-155">Apply a policy to a user account</span></span>

<span data-ttu-id="a6ef7-156">Após criar as políticas, você pode aplicá-las a uma conta de usuário da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a6ef7-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="a6ef7-157">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a6ef7-158">No menu **Iniciar** , selecione o Skype para painel de controle do Business Server ou abrir uma janela de navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a6ef7-159">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="a6ef7-160">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a6ef7-161">Em **Editar Skype para usuário de servidor de negócios** em **política de Chat persistente**, selecione a política de usuário de Chat persistente que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6ef7-162">O \*\* \<automática\> \*\* configurações se aplicam a diretiva padrão de efetiva.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="a6ef7-163">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="a6ef7-164">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a6ef7-164">Click **Commit**.</span></span>
    

