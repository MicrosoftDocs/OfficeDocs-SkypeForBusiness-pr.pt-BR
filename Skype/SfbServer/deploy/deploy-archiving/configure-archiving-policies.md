---
title: Configurar políticas de arquivamento para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumo: Leia este tópico para saber como configurar as políticas iniciais de arquivamento para usuários do Skype for Business Server.'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820851"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="59d43-103">Configurar políticas de arquivamento para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="59d43-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="59d43-104">**Resumo:** Leia este tópico para saber como configurar as políticas iniciais de arquivamento para usuários do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59d43-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="59d43-105">No Skype for Business Server, você usa políticas para habilitar e desabilitar o arquivamento de comunicações internas e externas para usuários que estão no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59d43-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="59d43-106">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="59d43-106">This includes the following:</span></span>
  
- <span data-ttu-id="59d43-107">Uma política global que é criada por padrão quando você implanta o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="59d43-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="59d43-108">Políticas opcionais no nível do site que especificam como o arquivamento é implementado para um site específico</span><span class="sxs-lookup"><span data-stu-id="59d43-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="59d43-109">Políticas opcionais no nível do usuário que especificam como o arquivamento é implementado para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="59d43-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="59d43-110">Inicialmente, você configura políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir políticas após a implantação.</span><span class="sxs-lookup"><span data-stu-id="59d43-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="59d43-111">No Painel de Controle do Skype  for Business Server,  você pode usar a página Política de Arquivamento do grupo Arquivamento e Monitoramento para gerenciar políticas nos níveis global, de site e de usuário.</span><span class="sxs-lookup"><span data-stu-id="59d43-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="59d43-112">Para controlar a implementação do arquivamento, você deve especificar opções, como arquivar IM ou conferências, o uso de modo crítico e opções de purgação.</span><span class="sxs-lookup"><span data-stu-id="59d43-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="59d43-113">Por padrão, nenhuma opção está habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento de site ou pool.</span><span class="sxs-lookup"><span data-stu-id="59d43-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="59d43-114">Você deve especificar todas as opções apropriadas antes de ativar o arquivamento para comunicações internas ou externas.</span><span class="sxs-lookup"><span data-stu-id="59d43-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="59d43-115">Para obter detalhes, [consulte Configurar opções de arquivamento para o Skype for Business Server.](configure-archiving-options.md)</span><span class="sxs-lookup"><span data-stu-id="59d43-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="59d43-116">Se você habilitar a integração com o Microsoft Exchange para sua implantação, as políticas de In-Place de Espera do Exchange controlarão se o arquivamento está habilitado para os usuários que estão no Exchange e têm suas caixas de correio colocadas em In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="59d43-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="59d43-117">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte Plano para arquivamento no [Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="59d43-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="59d43-118">Para obter detalhes sobre como gerenciar políticas após a implantação, consulte Gerenciar políticas de arquivamento [no Skype for Business Server.](../../manage/archiving/policies.md)</span><span class="sxs-lookup"><span data-stu-id="59d43-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="59d43-119">Política global</span><span class="sxs-lookup"><span data-stu-id="59d43-119">Global policy</span></span>

<span data-ttu-id="59d43-120">Quando você implanta seus Servidores Front-End, o Skype for Business Server cria uma política global para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="59d43-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="59d43-121">Por padrão, o arquivamento está desabilitado na política global.</span><span class="sxs-lookup"><span data-stu-id="59d43-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="59d43-122">A política global controla se o arquivamento está habilitado para comunicações internas e externas para toda a sua implantação, a menos que você tenha definido políticas de site ou de usuário, o que substitui a política global ou se você usa a integração com o Microsoft Exchange para alguns ou todos os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="59d43-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="59d43-123">Se você usar a integração com o Microsoft Exchange, a política global não se aplicará a todos os usuários que estão no Exchange e que tenham as caixas de correio colocadas em In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="59d43-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="59d43-124">Configurar a política global para arquivamento de bancos de dados de arquivamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="59d43-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="59d43-125">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59d43-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="59d43-126">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59d43-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="59d43-127">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="59d43-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="59d43-128">Na página **Política de Arquivamento**, clique em **Global**, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="59d43-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="59d43-129">Em **Editar Política de Arquivamento - Global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="59d43-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="59d43-130">Em **Nome**, se não desejar usar o nome padrão de global, especifique um novo nome para a política global.</span><span class="sxs-lookup"><span data-stu-id="59d43-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="59d43-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span><span class="sxs-lookup"><span data-stu-id="59d43-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="59d43-132">Para controlar o arquivamento de comunicações internas para todos os sites e usuários que não estivem sendo controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="59d43-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="59d43-133">Para controlar o arquivamento de comunicações externas para todos os sites e usuários que não estivem sendo controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="59d43-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="59d43-134">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="59d43-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="59d43-135">Políticas de site</span><span class="sxs-lookup"><span data-stu-id="59d43-135">Site policies</span></span>

<span data-ttu-id="59d43-136">Você pode habilitar ou desabilitar o arquivamento para sites específicos criando uma política de arquivamento para cada um desses sites.</span><span class="sxs-lookup"><span data-stu-id="59d43-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="59d43-137">Uma política de site substitui a política global, mas as políticas de usuário substituem as políticas de site.</span><span class="sxs-lookup"><span data-stu-id="59d43-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="59d43-138">As políticas de arquivamento só se aplicarão se você não usar a integração do Microsoft Exchange ou se você usar a integração com o Microsoft Exchange, mas tiver alguns usuários que não estão no Exchange e têm suas caixas de correio colocadas em In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="59d43-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="59d43-139">Criar uma política de arquivamento para um site</span><span class="sxs-lookup"><span data-stu-id="59d43-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="59d43-140">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59d43-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="59d43-141">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59d43-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="59d43-142">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="59d43-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="59d43-143">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte Plano para arquivamento no [Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="59d43-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="59d43-144">Clique em **Novo** e, em seguida, em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="59d43-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="59d43-145">Em **Selecionar um site,** clique no site ao qual a política deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="59d43-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="59d43-146">Em **Nova Política de Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="59d43-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="59d43-147">Em **Nome,** especifique o nome da política de site.</span><span class="sxs-lookup"><span data-stu-id="59d43-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="59d43-148">Em **Descrição,** forneça informações sobre a política de site (por exemplo, política de site para Redmond).</span><span class="sxs-lookup"><span data-stu-id="59d43-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="59d43-149">Para controlar o arquivamento de comunicações internas para o site especificado, marque ou des marque a caixa de seleção **Arquivar comunicações** internas.</span><span class="sxs-lookup"><span data-stu-id="59d43-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="59d43-150">Para controlar o arquivamento de comunicações externas para o site especificado, marque ou des des limpe a caixa de seleção **Arquivar comunicações externas.**</span><span class="sxs-lookup"><span data-stu-id="59d43-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="59d43-151">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="59d43-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="59d43-152">Políticas de usuário</span><span class="sxs-lookup"><span data-stu-id="59d43-152">User policies</span></span>

<span data-ttu-id="59d43-153">Você pode habilitar ou desabilitar o arquivamento para usuários específicos criando e configurando uma política de arquivamento para usuários e aplicando a política a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="59d43-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="59d43-154">As políticas de usuário substituem qualquer política global ou locais.</span><span class="sxs-lookup"><span data-stu-id="59d43-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="59d43-155">As políticas de arquivamento só se aplicarão se você não usar a integração do Microsoft Exchange ou se você usar a integração com o Microsoft Exchange, mas tiver alguns usuários que não estão no Exchange e têm suas caixas de correio colocadas em In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="59d43-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="59d43-156">Configurar uma política de arquivamento para usuários que estão no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="59d43-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="59d43-157">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59d43-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="59d43-158">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59d43-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="59d43-159">Na barra de navegação esquerda, clique em **Monitoração e Arquivamento** e em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="59d43-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="59d43-160">Clique em **Novo** e em **Política do usuário**.</span><span class="sxs-lookup"><span data-stu-id="59d43-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="59d43-161">Em **Nova Política de Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="59d43-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="59d43-162">Em **Nome**, especifique o nome da política de usuário.</span><span class="sxs-lookup"><span data-stu-id="59d43-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="59d43-163">Em **Descrição**, forneça informações sobre a política de usuário (por exemplo, política de usuário do departamento jurídico).</span><span class="sxs-lookup"><span data-stu-id="59d43-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="59d43-164">Para controlar o arquivamento das comunicações internas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="59d43-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="59d43-165">Para controlar o arquivamento das comunicações externas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="59d43-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="59d43-166">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="59d43-166">Click **Commit**.</span></span>
    
<span data-ttu-id="59d43-167">Uma política de usuário aplica-se somente aos usuários aos quais você a atribui.</span><span class="sxs-lookup"><span data-stu-id="59d43-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="59d43-168">Aplicar uma política de arquivamento do Skype for Business Server a um usuário</span><span class="sxs-lookup"><span data-stu-id="59d43-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="59d43-169">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="59d43-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="59d43-170">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="59d43-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="59d43-171">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="59d43-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="59d43-172">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="59d43-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="59d43-173">Em **Editar usuário do Skype for Business Server** em **Política** de Arquivamento, selecione a política de usuário de arquivamento que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="59d43-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="59d43-174">As **\<Automatic\>** configurações aplicam as configurações de instalação do servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="59d43-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="59d43-175">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="59d43-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="59d43-176">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="59d43-176">Click **Commit**.</span></span>
    

