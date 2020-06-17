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
description: A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede. Após migrar para o pool piloto, você precisará fazer a transição da rota de Federação de seus servidores de borda de versões anteriores para a rota de Federação de seus servidores de borda do Skype for Business Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754031"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="1b473-104">Configure o tráfego de mídia e rotas de federação</span><span class="sxs-lookup"><span data-stu-id="1b473-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="1b473-105">A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede.</span><span class="sxs-lookup"><span data-stu-id="1b473-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="1b473-106">Após migrar para o pool piloto, você precisará fazer a transição da rota de Federação dos servidores de borda da versão anterior para a rota de Federação de seus servidores de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1b473-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="1b473-107">Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do diretor e servidor de borda da versão anterior para o servidor de borda do Skype for Business Server 2019, para uma implantação de site único.</span><span class="sxs-lookup"><span data-stu-id="1b473-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1b473-108">Alterar a rota de Federação e a rota de tráfego de mídia exige que você agende o tempo de inatividade de manutenção para o Skype for Business Server 2019 e para os servidores de borda de versão anterior.</span><span class="sxs-lookup"><span data-stu-id="1b473-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="1b473-109">Todo esse processo de transição também significa que o acesso federado não estará disponível durante a interrupção.</span><span class="sxs-lookup"><span data-stu-id="1b473-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="1b473-110">Agende o tempo de inatividade para um período no qual você espera o mínimo de atividade de usuário.</span><span class="sxs-lookup"><span data-stu-id="1b473-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="1b473-111">Você também deve fornecer notificações suficientes para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="1b473-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="1b473-112">Planeje-se adequadamente para essa interrupção e defina as expectativas apropriadas dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="1b473-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1b473-113">Se o servidor de borda herdado estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda A/V, não haverá suporte para os procedimentos desta seção.</span><span class="sxs-lookup"><span data-stu-id="1b473-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="1b473-114">Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, você deverá primeiro migrar todos os seus usuários e, em seguida, encerrar o servidor de borda de versões anteriores antes de habilitar a Federação no servidor de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1b473-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1b473-115">Se sua Federação do XMPP for encaminhada por um servidor de borda do Skype for Business Server 2019, os usuários da versão anterior não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Skype for Business Server 2019, as políticas e os certificados do XMPP tenham sido configurados, o parceiro federado do XMPP tenha sido configurado no Skype for Business Server 2019 e, por fim, as entradas DNS foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="1b473-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="1b473-116">Para remover a associação de Federação herdada dos sites do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b473-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="1b473-117">No servidor front-end do Skype for Business Server 2019, abra a topologia existente no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="1b473-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="1b473-118">No painel esquerdo, navegue até o nó do site, que está localizado diretamente abaixo **do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1b473-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="1b473-119">Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="1b473-120">No painel esquerdo, selecione **Rota de federação**.</span><span class="sxs-lookup"><span data-stu-id="1b473-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="1b473-121">Em **atribuição de rota de Federação do site**, desmarque a caixa de seleção **habilitar Federação SIP** para desabilitar a rota de Federação pelo ambiente herdado.</span><span class="sxs-lookup"><span data-stu-id="1b473-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="1b473-122">Clique em **OK** para fechar a página Editar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="1b473-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="1b473-123">No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1b473-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="1b473-124">No menu \*\*Ação \*\*, clique em **Publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="1b473-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="1b473-125">Clique em **Avançar** para concluir o processo de publicação e, em seguida, clique em **concluir** quando o processo de publicação for concluído.</span><span class="sxs-lookup"><span data-stu-id="1b473-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="1b473-126">Para configurar o Servidor de Borda herdado como um Servidor de Borda não federado</span><span class="sxs-lookup"><span data-stu-id="1b473-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="1b473-127">No painel esquerdo, navegue até o nó de instalação herdado e, em seguida, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="1b473-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="1b473-128">Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="1b473-129">Selecionar **Geral** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="1b473-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="1b473-130">Desmarque a caixa de seleção **habilitar Federação para este pool de borda (porta 5061)** e selecione **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="1b473-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="1b473-131">No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1b473-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="1b473-132">Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="1b473-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="1b473-133">Verifique se a Federação do servidor de borda herdado está desabilitada no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="1b473-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="1b473-134">Para configurar certificados no servidor de borda herdado</span><span class="sxs-lookup"><span data-stu-id="1b473-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="1b473-135">Exporte o certificado de proxy de acesso externo, com a chave privada, do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="1b473-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="1b473-136">No servidor de borda do Skype for Business Server 2019 e importe o certificado externo do proxy de acesso da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="1b473-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="1b473-137">Atribua o certificado externo do proxy de acesso à interface externa do Skype for Business Server 2019 do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1b473-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="1b473-138">O certificado de interface interna do servidor de borda do Skype for Business Server 2019 deve ser solicitado de uma AC confiável e atribuído.</span><span class="sxs-lookup"><span data-stu-id="1b473-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="1b473-139">Para alterar a rota de Federação da versão anterior para usar o servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b473-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="1b473-140">No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="1b473-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="1b473-141">Clique com o botão direito no servidor de borda, e depois em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="1b473-142">Selecionar **Geral** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="1b473-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="1b473-143">Marque a caixa de seleção **habilitar Federação para este pool de borda (porta 5061)** e clique em **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="1b473-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="1b473-144">No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1b473-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="1b473-145">Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="1b473-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="1b473-146">Verifique se **Federation (porta 5061)** está definido como **habilitado** no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="1b473-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="1b473-147">Para atualizar o próximo salto de Federação do servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b473-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="1b473-148">No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="1b473-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="1b473-149">Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="1b473-150">Na página **geral** , em **seleção do próximo salto**, selecione na lista suspensa o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1b473-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="1b473-151">Clique em **OK** para fechar a página Editar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="1b473-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="1b473-152">No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1b473-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="1b473-153">No menu **Ações**, clique em **Publicar topologia** e complete o assistente.</span><span class="sxs-lookup"><span data-stu-id="1b473-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="1b473-154">Para configurar o caminho de mídia de saída do servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b473-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="1b473-155">No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o pool abaixo de **servidores front-end Standard Edition** ou **pools de front-ends Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="1b473-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="1b473-156">Clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="1b473-157">Na seção **Associações**, marque a caixa de seleção **Associar pool de Borda (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="1b473-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="1b473-158">Na caixa suspensa, selecione o servidor de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1b473-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="1b473-159">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="1b473-160">Para ativar a Federação do servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b473-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="1b473-161">No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="1b473-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="1b473-162">Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1b473-163">A Federação só pode ser habilitada para um único pool de borda.</span><span class="sxs-lookup"><span data-stu-id="1b473-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="1b473-164">Se você tiver vários pools de borda, selecione um para usar como o pool de Borda de federação.</span><span class="sxs-lookup"><span data-stu-id="1b473-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="1b473-165">Na página **geral** , verifique se a caixa de seleção **habilitar Federação para este pool de borda (porta 5061)** está marcada.</span><span class="sxs-lookup"><span data-stu-id="1b473-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="1b473-166">Clique em **OK** para fechar a página Editar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="1b473-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="1b473-167">Navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="1b473-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="1b473-168">Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="1b473-169">No painel esquerdo, clique em **Rota de federação**.</span><span class="sxs-lookup"><span data-stu-id="1b473-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="1b473-170">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Skype for Business Server 2019 listado.</span><span class="sxs-lookup"><span data-stu-id="1b473-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="1b473-171">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="1b473-172">Para implantações de múltiplos sites, complete esse procedimento em cada site.</span><span class="sxs-lookup"><span data-stu-id="1b473-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="1b473-173">Para publicar as alterações de configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="1b473-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="1b473-174">No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1b473-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="1b473-175">No menu **Ações**, selecione **Publicar Topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="1b473-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="1b473-176">Aguarde que a replicação do Active Directory ocorra em todos os pools na implantação.</span><span class="sxs-lookup"><span data-stu-id="1b473-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b473-177">Você pode ver a seguinte mensagem: **AVISO: a topologia contém mais de um servidor de borda federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, somente um servidor de borda seria usado ativamente para Federação. Verifique se o registro SRV de DNS externo aponta para o servidor de borda correto. Se você deseja implantar vários servidores de borda de Federação para que fiquem ativos simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Skype for Business Server. Verifique se o registro SRV DNS externo lista todos os servidores de borda habilitados para Federação.**</span><span class="sxs-lookup"><span data-stu-id="1b473-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="1b473-178">Esse aviso é esperado e pode ser ignorado com segurança.</span><span class="sxs-lookup"><span data-stu-id="1b473-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="1b473-179">Para configurar o servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b473-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="1b473-180">Traga todos os servidores de borda do Skype for Business Server 2019 online.</span><span class="sxs-lookup"><span data-stu-id="1b473-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="1b473-181">Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor de borda do Skype for Business Server 2019, em vez do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="1b473-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1b473-182">Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro a de DNS para que a Federação seja resolvida para o novo servidor de borda de acesso do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1b473-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="1b473-183">Para fazer isso com o mínimo de interrupção, reduza o valor de TLL para o FQDN externo de borda de acesso do Skype for Business Server, para que, quando o DNS for atualizado para apontar para a nova borda de acesso do Skype for Business Server, a Federação e o acesso remoto sejam atualizados rapidamente.</span><span class="sxs-lookup"><span data-stu-id="1b473-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="1b473-184">Interrompa a **borda de acesso do Skype for Business Server** de cada computador do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1b473-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="1b473-185">Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="1b473-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="1b473-186">Na lista serviços, encontre **borda de acesso do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1b473-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="1b473-187">Clique com o botão direito do mouse no nome dos serviços e selecione **Parar** para parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="1b473-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="1b473-188">Defina o tipo de inicialização para **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="1b473-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="1b473-189">Clique em **OK** para fechar a janela **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1b473-189">Click **OK** to close the **Properties** window.</span></span> 
    

