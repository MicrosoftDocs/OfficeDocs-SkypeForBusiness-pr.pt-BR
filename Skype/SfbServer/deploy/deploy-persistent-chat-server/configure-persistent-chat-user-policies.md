---
title: Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumo: Leia este tópico para saber como criar políticas de usuário iniciais para o Servidor de Chat Persistente no Skype for Business Server 2015. As políticas de usuário de Chat Persistente determinam se os usuários têm permissão ou não para acessar salas de chat.'
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802111"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="89086-104">Configurar políticas de usuário de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="89086-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="89086-105">**Resumo:** Leia este tópico para saber como criar políticas de usuário iniciais para o Servidor de Chat Persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="89086-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="89086-106">As políticas de usuário de Chat Persistente determinam se os usuários têm permissão ou não para acessar salas de chat.</span><span class="sxs-lookup"><span data-stu-id="89086-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="89086-107">Você pode gerenciar as políticas de usuário do Servidor de Chat Persistente nos seguintes níveis: global, site ou usuário.</span><span class="sxs-lookup"><span data-stu-id="89086-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="89086-108">Inicialmente, você configura a política global para habilitar as configurações de Chat Persistente para todos os usuários em sua implantação e, em seguida, cria políticas adicionais de usuário e site para controlar se o Chat Persistente está ativado para usuários e sites específicos.</span><span class="sxs-lookup"><span data-stu-id="89086-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="89086-109">Este tópico contém as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="89086-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="89086-110">Configurar a política global</span><span class="sxs-lookup"><span data-stu-id="89086-110">Configure the global policy</span></span>
    
- <span data-ttu-id="89086-111">Criar uma política de site</span><span class="sxs-lookup"><span data-stu-id="89086-111">Create a site policy</span></span>
    
- <span data-ttu-id="89086-112">Criar uma política de usuário</span><span class="sxs-lookup"><span data-stu-id="89086-112">Create a user policy</span></span>
    
- <span data-ttu-id="89086-113">Aplicar uma política a um usuário ou grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="89086-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="89086-114">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="89086-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="89086-115">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="89086-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="89086-116">Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="89086-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="89086-117">Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="89086-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="89086-118">Configurar a política global</span><span class="sxs-lookup"><span data-stu-id="89086-118">Configure the global policy</span></span>

<span data-ttu-id="89086-119">Para configurar a política global:</span><span class="sxs-lookup"><span data-stu-id="89086-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="89086-120">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="89086-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="89086-121">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="89086-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="89086-122">No Painel de Controle do Skype for Business Server, clique em **Chat Persistente** e em Política de **Chat Persistente.**</span><span class="sxs-lookup"><span data-stu-id="89086-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="89086-123">Clique em **Global** na lista de políticas, clique em **Editar** e clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="89086-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="89086-124">Em **Editar Política de Chat Persistente - Global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="89086-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="89086-125">Em **Nome**, especifique um novo nome para a política global, se você não quiser usar o padrão de Global.</span><span class="sxs-lookup"><span data-stu-id="89086-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="89086-126">Em **Descrição,** forneça detalhes sobre a política de usuário (por exemplo, política global  _para centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="89086-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="89086-127">Para controlar o Chat Persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou de usuário, marque ou des marque a caixa de seleção Habilitar **Chat** Persistente.</span><span class="sxs-lookup"><span data-stu-id="89086-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="89086-128">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="89086-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="89086-129">Criar uma política de site</span><span class="sxs-lookup"><span data-stu-id="89086-129">Create a site policy</span></span>

<span data-ttu-id="89086-130">Para cada site implantado, você pode criar uma política de Chat Persistente específica do site.</span><span class="sxs-lookup"><span data-stu-id="89086-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="89086-131">A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política.</span><span class="sxs-lookup"><span data-stu-id="89086-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="89086-132">Para criar uma política de site:</span><span class="sxs-lookup"><span data-stu-id="89086-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="89086-133">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="89086-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="89086-134">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="89086-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="89086-135">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="89086-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="89086-136">Clique em **Novo** e, em seguida, em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="89086-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="89086-137">Em **Selecionar um Site**, clique no site para o qual a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="89086-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="89086-138">Em **Nova Política de Chat Persistente**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="89086-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="89086-139">Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="89086-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="89086-140">Em **Descrição**, forneça detalhes sobre o que é a política de site (por exemplo, política de sala de chat para Redmond).</span><span class="sxs-lookup"><span data-stu-id="89086-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="89086-141">Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="89086-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="89086-142">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="89086-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="89086-143">Criar uma política de usuário</span><span class="sxs-lookup"><span data-stu-id="89086-143">Create a user policy</span></span>

<span data-ttu-id="89086-144">Você pode criar políticas específicas do usuário que substituem a política global e quaisquer políticas de site às quais o usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="89086-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="89086-145">Para criar uma política de usuário:</span><span class="sxs-lookup"><span data-stu-id="89086-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="89086-146">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="89086-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="89086-147">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="89086-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="89086-148">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="89086-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="89086-149">Clique em **Novo** e, em seguida, em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="89086-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="89086-150">Em **Nova Política de Chat Persistente**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="89086-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="89086-151">Em **Nome**, especifique um nome para a nova política de usuário.</span><span class="sxs-lookup"><span data-stu-id="89086-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="89086-152">Em **Descrição,** forneça detalhes sobre a política de usuário (por exemplo, política de Chat Persistente para usuário específico).</span><span class="sxs-lookup"><span data-stu-id="89086-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="89086-153">Para controlar o Chat Persistente para todos os usuários que não são controlados especificamente por meio de uma política de usuário, marque ou des limpe a caixa de seleção **Habilitar Chat** Persistente.</span><span class="sxs-lookup"><span data-stu-id="89086-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="89086-154">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="89086-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="89086-155">Aplicar uma política a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="89086-155">Apply a policy to a user account</span></span>

<span data-ttu-id="89086-156">Depois de criar políticas, você pode aplicá-las a uma conta de usuário da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="89086-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="89086-157">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="89086-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="89086-158">No menu **Iniciar,** selecione o Painel de Controle do Skype for Business Server ou abra uma janela do navegador e insira a URL do Administrador.</span><span class="sxs-lookup"><span data-stu-id="89086-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="89086-159">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="89086-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="89086-160">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="89086-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="89086-161">Em **Editar Usuário do Skype for Business Server em** Política de Chat **Persistente,** selecione a política de usuário de Chat Persistente que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="89086-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89086-162">As **\<Automatic\>** configurações aplicam a política efetiva padrão.</span><span class="sxs-lookup"><span data-stu-id="89086-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="89086-163">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="89086-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="89086-164">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="89086-164">Click **Commit**.</span></span>
    

