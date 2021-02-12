---
title: Configure o tráfego de mídia e rotas de federação
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Depois de migrar para o pool piloto, você precisará fazer a transição da rota de federação dos Servidores de Borda de versões anteriores para a rota de federação dos Servidores de Borda do Skype for Business Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754031"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="4ea74-104">Configure o tráfego de mídia e rotas de federação</span><span class="sxs-lookup"><span data-stu-id="4ea74-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="4ea74-105">A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede.</span><span class="sxs-lookup"><span data-stu-id="4ea74-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="4ea74-106">Depois de migrar para o pool piloto, você precisará fazer a transição da rota de federação dos Servidores de Borda da versão anterior para a rota de federação dos Servidores de Borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4ea74-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="4ea74-107">Use os procedimentos a seguir para fazer a transição da rota de federação e da rota de tráfego de mídia do Servidor de Borda e diretor da versão anterior para o Servidor de Borda do Skype for Business Server 2019, para uma implantação de site único.</span><span class="sxs-lookup"><span data-stu-id="4ea74-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4ea74-108">Alterar a rota de federação e a rota de tráfego de mídia exige que você agende o tempo de inatividade de manutenção para o Skype for Business Server 2019 e os Servidores de Borda da versão anterior.</span><span class="sxs-lookup"><span data-stu-id="4ea74-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="4ea74-109">Todo esse processo de transição também significa que o acesso federado não estará disponível durante a interrupção.</span><span class="sxs-lookup"><span data-stu-id="4ea74-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="4ea74-110">Agende o tempo de inatividade para um período no qual você espera o mínimo de atividade de usuário.</span><span class="sxs-lookup"><span data-stu-id="4ea74-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="4ea74-111">Você também deve fornecer notificações suficientes para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="4ea74-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="4ea74-112">Planeje-se adequadamente para essa interrupção e defina as expectativas apropriadas dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="4ea74-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4ea74-113">Se seu Servidor de Borda herdado estiver configurado para usar o mesmo FQDN para o serviço de Borda de Acesso, o serviço de Borda de Webconferência e o serviço de Borda A/V, os procedimentos nesta seção não serão suportados.</span><span class="sxs-lookup"><span data-stu-id="4ea74-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="4ea74-114">Se os serviços de Borda herdados estão configurados para usar o mesmo FQDN, primeiro você deve migrar todos os usuários e, em seguida, descomissionar o Servidor de Borda de versões anteriores antes de habilitar a federação no Servidor de Borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4ea74-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4ea74-115">Se sua federação XMPP for roteada através de um Servidor de Borda do Skype for Business Server 2019, os usuários na versão anterior não poderão se comunicar com o parceiro federado XMPP até que todos os usuários tenham sido movidos para o Skype for Business Server 2019, as políticas E certificados XMPP tenham sido configurados, o parceiro federado XMPP foi configurado no Skype for Business Server 2019 e, por fim, as entradas DNS foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="4ea74-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="4ea74-116">Para remover a associação de federação herdada dos sites do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4ea74-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="4ea74-117">No servidor front-end do Skype for Business Server 2019, abra a topologia existente no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="4ea74-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="4ea74-118">No painel esquerdo, navegue até o nó do site, que está localizado diretamente **abaixo do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="4ea74-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="4ea74-119">Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="4ea74-120">No painel esquerdo, selecione **Rota de federação**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="4ea74-121">Em **Atribuição da rota de federação do site,** **des** clear the Enable SIP federation check box to disable the federation route through the legacy environment.</span><span class="sxs-lookup"><span data-stu-id="4ea74-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="4ea74-122">Clique em **OK** para fechar a página Editar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="4ea74-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="4ea74-123">No **Construtor de Topologias,** selecione o nó **superior do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="4ea74-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="4ea74-124">No menu **Ação**, clique em **Publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="4ea74-125">Clique **em Próximo** para concluir o processo de publicação e clique em **Concluir** quando o processo de publicação for concluído.</span><span class="sxs-lookup"><span data-stu-id="4ea74-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="4ea74-126">Para configurar o Servidor de Borda herdado como um Servidor de Borda não federado</span><span class="sxs-lookup"><span data-stu-id="4ea74-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="4ea74-127">No painel esquerdo, navegue até o nó de instalação herddo e, em seguida, para o **nó pools de** Borda.</span><span class="sxs-lookup"><span data-stu-id="4ea74-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="4ea74-128">Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="4ea74-129">Selecionar **Geral** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="4ea74-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="4ea74-130">Des limpe a caixa de seleção Habilitar federação para este pool de Borda **(porta 5061)** e selecione **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="4ea74-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="4ea74-131">No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="4ea74-132">Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="4ea74-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="4ea74-133">Verifique se a federação para o servidor de Borda herdado está desabilitada no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="4ea74-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="4ea74-134">Para configurar certificados no Servidor de Borda herddo</span><span class="sxs-lookup"><span data-stu-id="4ea74-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="4ea74-135">Exporte o certificado de Proxy de Acesso externo, com a chave privada, do Servidor de Borda herdado.</span><span class="sxs-lookup"><span data-stu-id="4ea74-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="4ea74-136">No Servidor de Borda do Skype for Business Server 2019 e importe o certificado externo do Proxy de Acesso da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="4ea74-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="4ea74-137">Atribua o certificado externo do Proxy de Acesso à interface externa do Skype for Business Server 2019 do Servidor de Borda.</span><span class="sxs-lookup"><span data-stu-id="4ea74-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="4ea74-138">O certificado de interface interna do Servidor de Borda do Skype for Business Server 2019 deve ser solicitado a uma CA confiável e atribuído.</span><span class="sxs-lookup"><span data-stu-id="4ea74-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="4ea74-139">Para alterar a rota de federação da versão anterior para usar o Servidor de Borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4ea74-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="4ea74-140">No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, para o nó **pools de** Borda.</span><span class="sxs-lookup"><span data-stu-id="4ea74-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="4ea74-141">Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="4ea74-142">Selecionar **Geral** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="4ea74-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="4ea74-143">Marque a caixa de seleção Habilitar federação para este pool de Borda **(porta 5061)** e clique em **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="4ea74-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="4ea74-144">No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="4ea74-145">Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="4ea74-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="4ea74-146">Verifique se **a Federação (porta 5061)** está definida **como Habilitada** no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="4ea74-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="4ea74-147">Para atualizar o próximo salto da federação do Servidor de Borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4ea74-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="4ea74-148">No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, para o nó **pools de** Borda.</span><span class="sxs-lookup"><span data-stu-id="4ea74-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="4ea74-149">Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="4ea74-150">Na página **Geral,** em **Seleção** de Próximo salto, selecione na lista drop-down o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4ea74-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="4ea74-151">Clique em **OK** para fechar a página Editar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="4ea74-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="4ea74-152">No **Construtor de Topologias,** selecione o nó **superior do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="4ea74-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="4ea74-153">No menu **Ações**, clique em **Publicar topologia** e complete o assistente.</span><span class="sxs-lookup"><span data-stu-id="4ea74-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="4ea74-154">Para configurar o caminho de mídia de saída do Servidor de Borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4ea74-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="4ea74-155">No Construtor de Topologias, no painel esquerdo, navegue até o nó **skype for Business Server 2019** e, em seguida, para o pool abaixo servidores de **front-end Standard Edition** ou pools de **front-end Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="4ea74-156">Clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="4ea74-157">Na seção **Associações**, marque a caixa de seleção **Associar pool de Borda (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="4ea74-158">Na caixa de lista, selecione o Servidor de Borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4ea74-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="4ea74-159">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="4ea74-160">Para ativar a federação do Servidor de Borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4ea74-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="4ea74-161">No Construtor de Topologias, no painel esquerdo, navegue até o nó **Skype for Business Server 2019** e, em seguida, para o nó **pools de** Borda.</span><span class="sxs-lookup"><span data-stu-id="4ea74-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="4ea74-162">Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4ea74-163">A federação só pode ser habilitada para um único pool de Borda.</span><span class="sxs-lookup"><span data-stu-id="4ea74-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="4ea74-164">Se você tiver vários pools de borda, selecione um para usar como o pool de Borda de federação.</span><span class="sxs-lookup"><span data-stu-id="4ea74-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="4ea74-165">Na página **Geral,** verifique se a caixa de seleção Habilitar federação para este pool de Borda **(Porta 5061)** está marcada.</span><span class="sxs-lookup"><span data-stu-id="4ea74-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="4ea74-166">Clique em **OK** para fechar a página Editar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="4ea74-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="4ea74-167">Navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="4ea74-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="4ea74-168">Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="4ea74-169">No painel esquerdo, clique em **Rota de federação**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="4ea74-170">Em **Atribuição da** rota de federação do site, selecione Habilitar federação **SIP** e, na lista, selecione o Servidor de Borda do Skype for Business Server 2019 listado.</span><span class="sxs-lookup"><span data-stu-id="4ea74-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="4ea74-171">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="4ea74-172">Para implantações de múltiplos sites, complete esse procedimento em cada site.</span><span class="sxs-lookup"><span data-stu-id="4ea74-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="4ea74-173">Para publicar as alterações de configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="4ea74-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="4ea74-174">No **Construtor de Topologias,** selecione o nó **superior do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="4ea74-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="4ea74-175">No menu **Ações**, selecione **Publicar Topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="4ea74-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="4ea74-176">Aguarde que a replicação do Active Directory ocorra em todos os pools na implantação.</span><span class="sxs-lookup"><span data-stu-id="4ea74-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ea74-177">Você pode ver a seguinte mensagem: **Aviso: A topologia contém mais de um Servidor de Borda Federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um Servidor de Borda seria usado ativamente para federação. Verifique se o registro SRV de DNS externo aponta para o Servidor de Borda correto. Se você quiser implantar vários Servidores de Borda de federação para estar ativo simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Skype for Business Server. Verifique se o registro SRV de DNS externo lista todos os Servidores de Borda habilitados para federação.**</span><span class="sxs-lookup"><span data-stu-id="4ea74-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="4ea74-178">Esse aviso é esperado e pode ser ignorado com segurança.</span><span class="sxs-lookup"><span data-stu-id="4ea74-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="4ea74-179">Para configurar o Servidor de Borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="4ea74-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="4ea74-180">Colocar todos os Servidores de Borda do Skype for Business Server 2019 online.</span><span class="sxs-lookup"><span data-stu-id="4ea74-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="4ea74-181">Atualize as regras de roteamento de firewall externo ou as configurações do balanceador de carga de hardware para enviar tráfego SIP para acesso externo (normalmente porta 443) e federação (normalmente a porta 5061) para o Servidor de Borda do Skype for Business Server 2019, em vez do Servidor de Borda herdado.</span><span class="sxs-lookup"><span data-stu-id="4ea74-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ea74-182">Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS A para que a federação seja resolvida para o novo servidor de Borda de Acesso do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4ea74-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="4ea74-183">Para fazer isso com o mínimo de interrupção, reduza o valor de TLL para o FQDN externo da Borda de Acesso do Skype for Business Server para que, quando o DNS for atualizado para apontar para a nova Borda de Acesso do Skype for Business Server, a federação e o acesso remoto sejam atualizados rapidamente.</span><span class="sxs-lookup"><span data-stu-id="4ea74-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="4ea74-184">Pare a **Borda de Acesso do Skype for Business Server** de cada computador servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4ea74-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="4ea74-185">Em cada computador servidor de borda herddo, abra **o** applet serviços das **Ferramentas Administrativas**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="4ea74-186">Na lista de serviços, encontre a **Borda de Acesso do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="4ea74-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="4ea74-187">Clique com o botão direito do mouse no nome dos serviços e selecione **Parar** para parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="4ea74-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="4ea74-188">Defina o tipo de inicialização para **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="4ea74-189">Clique em **OK** para fechar a janela **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4ea74-189">Click **OK** to close the **Properties** window.</span></span> 
    

