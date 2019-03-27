---
title: Configurar rotas de federação e tráfego de mídia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários em organizações separadas se comuniquem pelos limites da rede. Após migrar para o seu pool piloto, você precisa fazer a transição da rota de Federação dos seus servidores de borda de versões anteriores para a rota de federação de sua Skype para servidores de borda de 2019 Business Server.
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880225"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="86182-104">Configurar rotas de federação e tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="86182-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="86182-105">A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários em organizações separadas se comuniquem pelos limites da rede.</span><span class="sxs-lookup"><span data-stu-id="86182-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="86182-106">Após migrar para o seu pool piloto, você precisa fazer a transição da rota de Federação da versão anterior servidores de borda para a rota de federação de sua Skype para servidores de borda de 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="86182-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="86182-107">Use os procedimentos a seguir para fazer a transição da rota de Federação e a rota do tráfego de mídia do servidor de borda e diretor de sua versão anterior para sua Skype para o servidor de borda do Business Server 2019, para uma implantação local único.</span><span class="sxs-lookup"><span data-stu-id="86182-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86182-108">Alterando a rota de Federação e a rota do tráfego de mídia requer que você agendar o tempo de inatividade de manutenção para o Skype para Business Server 2019 e servidores de borda de versão anterior.</span><span class="sxs-lookup"><span data-stu-id="86182-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="86182-109">Esse processo de transição inteira também significa que acesso federado estará indisponível durante a interrupção.</span><span class="sxs-lookup"><span data-stu-id="86182-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="86182-110">Você deve agendar o tempo de inatividade por um período quando você espera que a atividade mínima do usuário.</span><span class="sxs-lookup"><span data-stu-id="86182-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="86182-111">Você também deve fornecer notificação suficiente para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="86182-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="86182-112">Planeje apropriadamente para este interrupção e o conjunto apropriado expectativas dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="86182-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="86182-113">Se o seu servidor de borda herdado está configurado para usar o mesmo FQDN para o serviço de borda de acesso, serviço de borda de webconferência e A / não há suporte para o serviço de borda de V, os procedimentos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="86182-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="86182-114">Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, primeiro você precisa migrar todos os seus usuários e encerre as servidor de borda de versões anteriores antes de habilitar a federação no Skype para servidor de borda de 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="86182-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="86182-115">Se sua federação XMPP é encaminhada por um Skype para o servidor de borda de 2019 Business Server, os usuários da versão anterior não será capazes de se comunicar com um parceiro federado XMPP até que todos os usuários foram movidos para Skype para Business Server 2019, políticas XMPP e certificados tiverem sido configurados, parceiro federado XMPP tiver sido configurado no Skype para Business Server 2019 e, por fim, as entradas DNS foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="86182-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="86182-116">Para remover a associação de Federação herdada do Skype para sites corporativos Server 2019</span><span class="sxs-lookup"><span data-stu-id="86182-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="86182-117">No Skype para o servidor de negócios 2019 Front-End Server, abra a topologia existente no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="86182-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="86182-118">No painel esquerdo, navegue até o nó do site, que está localizado diretamente abaixo **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="86182-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="86182-119">Com o botão direito do site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="86182-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="86182-120">No painel esquerdo, selecione **rota de Federação**.</span><span class="sxs-lookup"><span data-stu-id="86182-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="86182-121">Em **atribuição de rota de Federação do Site**, desmarque a caixa de seleção **Habilitar federação SIP** para desabilitar a rota de Federação através do ambiente herdado.</span><span class="sxs-lookup"><span data-stu-id="86182-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="86182-122">Clique em **Okey** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="86182-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="86182-123">A partir do **Construtor de topologias**, selecione o nó superior **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="86182-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="86182-124">No menu **ação** , clique em **Publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="86182-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="86182-125">Clique em **Avançar** para concluir o processo de publicação e clique em **Concluir** quando o processo de publicação for concluído.</span><span class="sxs-lookup"><span data-stu-id="86182-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="86182-126">Para configurar o servidor de borda herdado como um servidor de borda não federado</span><span class="sxs-lookup"><span data-stu-id="86182-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="86182-127">No painel esquerdo, navegue até o nó install herdado e, em seguida, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="86182-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="86182-128">Com o botão direito no servidor de borda e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="86182-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="86182-129">Selecione **Geral** no painel à esquerda.</span><span class="sxs-lookup"><span data-stu-id="86182-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="86182-130">Desmarque a caixa de seleção **Habilitar federação para este pool de borda (porta 5061)** e selecione **Okey** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="86182-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="86182-131">No menu **ação** , selecione **Publicar topologia**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="86182-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="86182-132">Quando o **Assistente para publicação** for concluído, clique em **Concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="86182-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="86182-133">Verifique se a federação para o servidor de borda herdado está desabilitada no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="86182-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="86182-134">Para configurar certificados no servidor de borda herdado</span><span class="sxs-lookup"><span data-stu-id="86182-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="86182-135">Exporte o certificado externo do Proxy de acesso, com a chave privada, do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="86182-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="86182-136">Sobre o Skype para servidor de borda do Business Server 2019 e importação de certificado externo do Proxy de acesso da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="86182-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="86182-137">Atribua o certificado externo do Proxy de acesso para o Skype para Business Server 2019 a interface externa do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="86182-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="86182-138">O certificado da interface interna do Skype para o servidor de borda de 2019 Business Server deve ser solicitado por uma autoridade de certificação confiável e atribuído.</span><span class="sxs-lookup"><span data-stu-id="86182-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="86182-139">Para alterar a rota de Federação da versão anterior para usar Skype para o servidor de borda do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="86182-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="86182-140">No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype para Business Server 2019** e, depois, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="86182-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="86182-141">Com o botão direito no servidor de borda e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="86182-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="86182-142">Selecione **Geral** no painel à esquerda.</span><span class="sxs-lookup"><span data-stu-id="86182-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="86182-143">Marque a caixa de seleção para **Habilitar a federação para este pool de borda (porta 5061)** e, em seguida, clique em **Okey** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="86182-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="86182-144">No menu **ação** , selecione **Publicar topologia**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="86182-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="86182-145">Quando o **Assistente para publicação** for concluído, clique em **Concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="86182-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="86182-146">Verifique se **federação (porta 5061)** está definido como **Enabled** no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="86182-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="86182-147">Para atualizar o Skype para o próximo salto da federação de servidor de borda do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="86182-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="86182-148">No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype para Business Server 2019** e, depois, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="86182-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="86182-149">Expanda o nó, clique com o botão o servidor de borda listado e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="86182-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="86182-150">Na página **Geral** , em **seleção do próximo salto**, selecione na lista suspensa o Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="86182-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="86182-151">Clique em **Okey** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="86182-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="86182-152">A partir do **Construtor de topologias**, selecione o nó superior **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="86182-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="86182-153">No menu **ação** , clique em **Publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="86182-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="86182-154">Para configurar o Skype para o caminho de mídia de saída do servidor de borda do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="86182-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="86182-155">No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype para Business Server 2019** e, depois, para o pool abaixo de **pools de Front End do Enterprise Edition**ou **Standard Edition servidores Front-End** .</span><span class="sxs-lookup"><span data-stu-id="86182-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="86182-156">Com o botão direito do pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="86182-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="86182-157">Na seção **associações** , marque a caixa de seleção **associar pool de borda (para componentes de mídia)** .</span><span class="sxs-lookup"><span data-stu-id="86182-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="86182-158">Na caixa de lista suspensa, selecione o Skype para servidor de borda de 2019 Business Server.</span><span class="sxs-lookup"><span data-stu-id="86182-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="86182-159">Clique em **Okey** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="86182-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="86182-160">Para ativar Skype para federação do servidor de borda do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="86182-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="86182-161">No construtor de topologias, no painel esquerdo, navegue até o nó do **Skype para Business Server 2019** e, depois, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="86182-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="86182-162">Expanda o nó, clique com o botão o servidor de borda listado e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="86182-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="86182-163">Federação só pode ser habilitada para um único pool de borda.</span><span class="sxs-lookup"><span data-stu-id="86182-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="86182-164">Se você tiver vários pools de borda, selecione um para usar como o pool de borda federating.</span><span class="sxs-lookup"><span data-stu-id="86182-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="86182-165">Na página **Geral** , verifique se que a caixa de seleção **Habilitar federação para este pool de borda (porta 5061)** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="86182-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="86182-166">Clique em **Okey** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="86182-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="86182-167">Navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="86182-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="86182-168">Com o botão direito do site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="86182-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="86182-169">No painel esquerdo, clique em **rota de Federação**.</span><span class="sxs-lookup"><span data-stu-id="86182-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="86182-170">Em **atribuição de rota de Federação do Site**, selecione **Habilitar federação SIP**e, em seguida, na lista Selecione o Skype para o servidor de borda do Business Server 2019 listados.</span><span class="sxs-lookup"><span data-stu-id="86182-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="86182-171">Clique em **Okey** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="86182-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="86182-172">Para implantações de vários locais, conclua este procedimento em cada site.</span><span class="sxs-lookup"><span data-stu-id="86182-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="86182-173">Para publicar as alterações de configuração do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86182-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="86182-174">A partir do **Construtor de topologias**, selecione o nó superior **Skype para Business Server**.</span><span class="sxs-lookup"><span data-stu-id="86182-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="86182-175">No menu **ação** , selecione **Publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="86182-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="86182-176">Aguarde a replicação do Active Directory ocorra em todos os pools na implantação.</span><span class="sxs-lookup"><span data-stu-id="86182-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86182-177">Você pode ver a seguinte mensagem: **Aviso: A topologia contém mais de um servidor de borda federados. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um servidor de borda seria usado ativamente para federação. Verifique se o registro SRV de DNS aponta para o servidor de borda correto. Se desejar implantar vários federação de servidor de borda a ser ativo simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados são usando Skype para Business Server. Verifique se o registro SRV de DNS lista todos os servidores de borda de Federação habilitada.**</span><span class="sxs-lookup"><span data-stu-id="86182-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="86182-178">Esse aviso é esperado e pode ser ignorado com segurança.</span><span class="sxs-lookup"><span data-stu-id="86182-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="86182-179">Para configurar o Skype para o servidor de borda do Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="86182-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="86182-180">Colocar todas a Skype para os servidores de borda do Business Server 2019 on-line.</span><span class="sxs-lookup"><span data-stu-id="86182-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="86182-181">Atualizar as regras de roteamento do firewall externo ou as configurações de Balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente, a porta 443) e federação (geralmente, a porta 5061) para o Skype para negócios 2019 borda Server, em vez do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="86182-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86182-182">Se você não tiver um balanceador de carga de hardware, você precisará atualizar o registro DNS A para federação resolver para o novo Skype para o servidor de borda de acesso do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="86182-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="86182-183">Para realizar isso com um mínimo de interrupção, reduza o valor TLL para o Skype externo para o FQDN de borda de acesso do Business Server para que ao DNS é atualizado para apontar para o novo Skype para borda de acesso do servidor de negócios, Federação e acesso remoto serão atualizados rapidamente.</span><span class="sxs-lookup"><span data-stu-id="86182-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="86182-184">Pare o **Skype para borda de acesso do servidor de negócios** de cada computador do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="86182-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="86182-185">Em cada computador do servidor de borda herdado, abra o miniaplicativo **Serviços** em **Ferramentas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="86182-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="86182-186">Na lista de serviços, encontre **Skype para borda de acesso do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="86182-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="86182-187">Nome do serviço do mouse em e selecione **Parar** para parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="86182-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="86182-188">Defina o tipo de inicialização para **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="86182-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="86182-189">Clique em **Okey** para fechar a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="86182-189">Click **OK** to close the **Properties** window.</span></span> 
    

