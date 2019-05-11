---
title: Configurar políticas de arquivamento do Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumo: Leia este tópico para saber como configurar políticas de arquivamento iniciais do Skype para usuários corporativos Server.'
ms.openlocfilehash: 83b929a01013fa96dbec9742d36d3cec0387d4ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895907"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="22381-103">Configurar políticas de arquivamento do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="22381-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="22381-104">**Resumo:** Leia este tópico para saber como configurar políticas de arquivamento iniciais do Skype para usuários corporativos Server.</span><span class="sxs-lookup"><span data-stu-id="22381-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="22381-105">Skype para Business Server, você usa políticas para habilitar e desabilitar o arquivamento de comunicações internas e comunicações externas para usuários hospedados no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="22381-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="22381-106">Isso inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22381-106">This includes the following:</span></span>
  
- <span data-ttu-id="22381-107">Uma política global que é criada por padrão, quando você implanta o Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="22381-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="22381-108">Políticas opcionais no nível do local que especificam como o arquivamento é implementado para um local específico</span><span class="sxs-lookup"><span data-stu-id="22381-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="22381-109">Políticas opcionais de nível de usuário que especificam como o arquivamento é implementado para usuários específicos</span><span class="sxs-lookup"><span data-stu-id="22381-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="22381-110">As políticas de arquivamento são configuradas inicialmente ao implantar o arquivamento, mas você pode alterar, adicionar e excluir políticas após a implantação.</span><span class="sxs-lookup"><span data-stu-id="22381-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="22381-111">No painel de controle do servidor de negócios do Skype, você pode usar a página **Política de arquivamento** do grupo de **arquivamento e monitoramento** para gerenciar políticas no nível global, site e níveis de usuário.</span><span class="sxs-lookup"><span data-stu-id="22381-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="22381-112">Para controlar a implementação do arquivamento, você deve especificar opções, como se é necessário arquivar IM ou conferências, o uso do modo crítico e as opções de limpeza.</span><span class="sxs-lookup"><span data-stu-id="22381-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="22381-113">Por padrão, nenhuma opção está habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento de local ou pool.</span><span class="sxs-lookup"><span data-stu-id="22381-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="22381-114">É necessário especificar todas as opções apropriadas antes de habilitar o arquivamento para comunicações internas ou externas.</span><span class="sxs-lookup"><span data-stu-id="22381-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="22381-115">Para obter detalhes, consulte [Configurar opções de arquivamento para Skype para Business Server](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="22381-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="22381-116">Se você habilitar a integração do Microsoft Exchange para sua implantação, o controle de políticas de retenção de In-loco do Exchange se o arquivamento estiver habilitado para os usuários hospedados no Exchange e tem colocado de suas caixas de correio em bloqueio In-loco.</span><span class="sxs-lookup"><span data-stu-id="22381-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="22381-117">Para obter detalhes sobre políticas de arquivamento como funcionam, incluindo a hierarquia de globais, de site e políticas de usuário, consulte [Planejar para arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="22381-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="22381-118">Para obter detalhes sobre como gerenciar políticas após a implantação, consulte [Gerenciar políticas de arquivamento no Skype para Business Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="22381-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="22381-119">Política global</span><span class="sxs-lookup"><span data-stu-id="22381-119">Global policy</span></span>

<span data-ttu-id="22381-120">Quando você implanta seus servidores Front-End, Skype para Business Server cria uma política global para arquivamento.</span><span class="sxs-lookup"><span data-stu-id="22381-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="22381-121">Por padrão, o arquivamento está desabilitado na política global.</span><span class="sxs-lookup"><span data-stu-id="22381-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="22381-122">A política global controla se o arquivamento estiver habilitado para comunicações internas e externas para sua implantação inteira, a menos que você configure políticas de site ou de usuário, que substituem a política global, ou se você usar a integração do Microsoft Exchange para alguns ou todos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="22381-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="22381-123">Se você usar a integração do Microsoft Exchange, a política global não se aplica a todos os usuários hospedados no Exchange e têm as caixas de correio colocadas em retenção In-loco.</span><span class="sxs-lookup"><span data-stu-id="22381-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="22381-124">Configurar a política global para arquivamento para Skype para bancos de dados de arquivamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="22381-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="22381-125">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22381-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22381-126">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="22381-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="22381-127">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="22381-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="22381-128">Na página **Política de Arquivamento**, clique em **Global**, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="22381-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="22381-129">Em **Editar Política de Arquivamento - Global**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22381-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="22381-130">Em **Nome**, se não desejar usar o nome padrão da opção Global, especifique um novo nome para a política global.</span><span class="sxs-lookup"><span data-stu-id="22381-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="22381-131">Em **Descrição**, forneça informações sobre o que é a política (por exemplo, política Global para *divisionName* .</span><span class="sxs-lookup"><span data-stu-id="22381-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="22381-132">Para controlar o arquivamento de comunicações internas para todos os locais e usuários que não estivem sendo controlados especificamente por meio de uma política de local ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="22381-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="22381-133">Para controlar o arquivamento de comunicações externas para todos os locais e usuários que não estivem sendo controlados especificamente por meio de uma política de local ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="22381-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="22381-134">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22381-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="22381-135">Políticas de local</span><span class="sxs-lookup"><span data-stu-id="22381-135">Site policies</span></span>

<span data-ttu-id="22381-136">É possível habilitar ou desabilitar o arquivamento para locais específicos criando uma política de arquivamento para cada um destes locais.</span><span class="sxs-lookup"><span data-stu-id="22381-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="22381-137">Uma política de local substitui a política global, mas as políticas de usuário substituem as políticas de local.</span><span class="sxs-lookup"><span data-stu-id="22381-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="22381-138">Políticas de arquivamento se aplicam somente se você não usar a integração do Microsoft Exchange ou, se você usar a integração do Microsoft Exchange, mas tem colocado de alguns usuários que não são hospedados no Exchange e têm suas caixas de correio em bloqueio In-loco.</span><span class="sxs-lookup"><span data-stu-id="22381-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="22381-139">Para criar uma política de arquivamento para um local</span><span class="sxs-lookup"><span data-stu-id="22381-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="22381-140">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22381-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22381-141">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="22381-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="22381-142">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="22381-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="22381-143">Para obter detalhes sobre políticas de arquivamento como funcionam, incluindo a hierarquia de globais, de site e políticas de usuário, consulte [Planejar para arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="22381-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="22381-144">Clique em **Nova** e em **Política de local**.</span><span class="sxs-lookup"><span data-stu-id="22381-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="22381-145">Em **Selecionar um local**, clique no local ao qual a política deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="22381-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="22381-146">Em **Nova Política de Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22381-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="22381-147">Em **Nome**, especifique um nome para a política do local.</span><span class="sxs-lookup"><span data-stu-id="22381-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="22381-148">Em **Descrição**, forneça as informações sobre a política de local (por exemplo, a política de local para Redmond).</span><span class="sxs-lookup"><span data-stu-id="22381-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="22381-149">Para controlar o arquivamento das comunicações internas do local especificado, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="22381-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="22381-150">Para controlar o arquivamento das comunicações externas do local especificado, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="22381-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="22381-151">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22381-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="22381-152">Políticas de usuário</span><span class="sxs-lookup"><span data-stu-id="22381-152">User policies</span></span>

<span data-ttu-id="22381-153">É possível habilitar ou desabilitar o arquivamento para usuários específicos criando e configurando uma política de arquivamento para usuários e aplicando a política para usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="22381-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="22381-154">As políticas de usuário substituem qualquer política global ou local.</span><span class="sxs-lookup"><span data-stu-id="22381-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="22381-155">Políticas de arquivamento se aplicam somente se você não usar a integração do Microsoft Exchange ou, se você usar a integração do Microsoft Exchange, mas tem colocado de alguns usuários que não são hospedados no Exchange e têm suas caixas de correio em bloqueio In-loco.</span><span class="sxs-lookup"><span data-stu-id="22381-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="22381-156">Configurar uma política de arquivamento para usuários hospedados no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="22381-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="22381-157">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22381-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22381-158">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="22381-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="22381-159">Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="22381-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="22381-160">Clique em **Nova** e em **Política do usuário**.</span><span class="sxs-lookup"><span data-stu-id="22381-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="22381-161">Em **Nova Política de Arquivamento**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22381-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="22381-162">Em **Nome**, especifique o nome da política de usuário.</span><span class="sxs-lookup"><span data-stu-id="22381-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="22381-163">Em **Descrição**, forneça informações sobre a política de usuário (por exemplo, política de usuário do departamento jurídico).</span><span class="sxs-lookup"><span data-stu-id="22381-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="22381-164">Para controlar o arquivamento das comunicações internas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.</span><span class="sxs-lookup"><span data-stu-id="22381-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="22381-165">Para controlar o arquivamento das comunicações externas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.</span><span class="sxs-lookup"><span data-stu-id="22381-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="22381-166">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22381-166">Click **Commit**.</span></span>
    
<span data-ttu-id="22381-167">Uma política de usuário aplica-se somente aos usuários aos quais você a atribui.</span><span class="sxs-lookup"><span data-stu-id="22381-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="22381-168">Aplicar um Skype para Business Server política a um usuário de arquivamento</span><span class="sxs-lookup"><span data-stu-id="22381-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="22381-169">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="22381-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22381-170">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="22381-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="22381-171">Na barra de navegação à esquerda, clique em **Usuários** e procure a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="22381-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="22381-172">Na tabela que lista os resultados da pesquisa, clique em conta de usuário, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="22381-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="22381-173">Em **Editar Skype para usuário Business Server** , em **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="22381-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22381-174">O \*\* \<automática\> \*\* configurações se aplicam as configurações de instalação de servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="22381-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="22381-175">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="22381-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="22381-176">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="22381-176">Click **Commit**.</span></span>
    

