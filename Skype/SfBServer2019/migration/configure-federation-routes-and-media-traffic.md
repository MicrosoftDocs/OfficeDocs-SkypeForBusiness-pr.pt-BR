---
title: Configurar rotas de federação e tráfego de mídia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: A Federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários de organizações separadas se comuniquem entre os limites da rede. Depois de migrar para o pool piloto, você precisa fazer a transição da rota de Federação de seus servidores de borda de versões anteriores para a rota de Federação dos seus servidores de borda do Skype for Business Server 2019.
ms.openlocfilehash: 71417307fd46c2c29535cea3a52f0286ad6dc951
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813809"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="8bae7-104">Configurar rotas de federação e tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="8bae7-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="8bae7-105">A Federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários de organizações separadas se comuniquem entre os limites da rede.</span><span class="sxs-lookup"><span data-stu-id="8bae7-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="8bae7-106">Depois de migrar para o pool piloto, você precisará fazer a transição da rota de Federação dos servidores de borda da versão anterior para a rota de Federação dos seus servidores de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8bae7-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="8bae7-107">Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do servidor de borda e do diretor da sua versão anterior para o seu servidor de borda do Skype for Business Server 2019 para uma implantação de um único site.</span><span class="sxs-lookup"><span data-stu-id="8bae7-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8bae7-108">Alterar a rota de Federação e a rota de tráfego de mídia requer que você agende o tempo de inatividade de manutenção para os servidores do Skype for Business Server 2019 e do Edge versão anterior.</span><span class="sxs-lookup"><span data-stu-id="8bae7-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="8bae7-109">Esse processo de transição inteiro também significa que o acesso federado estará indisponível para a duração da interrupção.</span><span class="sxs-lookup"><span data-stu-id="8bae7-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="8bae7-110">Você deve programar o tempo de inatividade para um horário em que espera a atividade do usuário mínima.</span><span class="sxs-lookup"><span data-stu-id="8bae7-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="8bae7-111">Você também deve fornecer uma notificação suficiente para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="8bae7-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="8bae7-112">Planeje-se adequadamente para esta interrupção e defina as expectativas adequadas dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8bae7-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8bae7-113">Se o servidor de borda herdado estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda a/V, os procedimentos desta seção não serão suportados.</span><span class="sxs-lookup"><span data-stu-id="8bae7-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="8bae7-114">Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, primeiro você deve migrar todos os seus usuários e, em seguida, encerrar o servidor de borda de versões anteriores antes de habilitar a Federação no servidor de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8bae7-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8bae7-115">Se a sua Federação do XMPP for roteada por meio de um servidor de borda do Skype for Business Server 2019, os usuários na versão anterior não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Skype for Business Server 2019, políticas do XMPP e os certificados foram configurados, o parceiro federado do XMPP foi configurado no Skype for Business Server 2019 e, finalmente, as entradas DNS foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="8bae7-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="8bae7-116">Para remover a associação de Federação herdada dos sites do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8bae7-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="8bae7-117">No servidor front-end do Skype for Business Server 2019, abra a topologia existente no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8bae7-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="8bae7-118">No painel esquerdo, navegue até o nó do site, localizado diretamente abaixo **do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="8bae7-119">Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="8bae7-120">No painel esquerdo, selecione **roteiro de Federação**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="8bae7-121">Em **atribuição de rota de Federação do site**, desmarque a caixa de seleção **habilitar Federação SIP** para desabilitar a rota de Federação por meio do ambiente herdado.</span><span class="sxs-lookup"><span data-stu-id="8bae7-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="8bae7-122">Clique em **OK** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="8bae7-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="8bae7-123">No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="8bae7-124">No menu **ação** , clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="8bae7-125">Clique em **Avançar** para concluir o processo de publicação e, em seguida, clique em **concluir** quando o processo de publicação estiver concluído.</span><span class="sxs-lookup"><span data-stu-id="8bae7-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="8bae7-126">Para configurar o servidor de borda herdado como um servidor de borda não federativo</span><span class="sxs-lookup"><span data-stu-id="8bae7-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="8bae7-127">No painel esquerdo, navegue até o nó instalação herdada e, em seguida, para o nó **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="8bae7-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="8bae7-128">Clique com o botão direito do mouse no servidor de borda e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="8bae7-129">Selecione **geral** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="8bae7-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="8bae7-130">Desmarque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** e selecione **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="8bae7-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="8bae7-131">No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="8bae7-132">Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="8bae7-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="8bae7-133">Verifique se a Federação do servidor de borda herdada está desabilitada no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8bae7-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="8bae7-134">Para configurar certificados no servidor de borda herdado</span><span class="sxs-lookup"><span data-stu-id="8bae7-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="8bae7-135">Exportar o certificado de proxy de acesso externo, com a chave privada, do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="8bae7-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="8bae7-136">No servidor de borda do Skype for Business Server 2019 e importar o certificado externo de proxy do Access da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="8bae7-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="8bae7-137">Atribua o certificado de proxy externo do Access à interface externa do Skype for Business Server 2019 do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8bae7-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="8bae7-138">O certificado de interface interna do servidor de borda do Skype for Business Server 2019 deve ser solicitado de uma autoridade de certificação confiável e atribuído.</span><span class="sxs-lookup"><span data-stu-id="8bae7-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="8bae7-139">Para alterar a rota de Federação da versão anterior para usar o servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8bae7-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="8bae7-140">No construtor de topologia, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó de **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="8bae7-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="8bae7-141">Clique com o botão direito do mouse no servidor de borda e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="8bae7-142">Selecione **geral** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="8bae7-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="8bae7-143">Marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** e, em seguida, clique em **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="8bae7-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="8bae7-144">No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="8bae7-145">Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="8bae7-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="8bae7-146">Verifique se a **Federação (porta 5061)** está definida como **Enabled** no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="8bae7-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="8bae7-147">Para atualizar o Skype for Business Server 2019 o próximo nó de Federação do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="8bae7-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="8bae7-148">No construtor de topologia, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó de **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="8bae7-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="8bae7-149">Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="8bae7-150">Na página **geral** , em **seleção do próximo salto**, selecione na lista suspensa o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8bae7-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="8bae7-151">Clique em **OK** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="8bae7-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="8bae7-152">No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="8bae7-153">No menu **ação** , clique em **publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="8bae7-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="8bae7-154">Para configurar o caminho da mídia de saída do servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8bae7-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="8bae7-155">No construtor de topologia, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o pool abaixo de **servidores front-end da edição padrão** ou **pools front-ends do Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="8bae7-156">Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="8bae7-157">Na seção **associações** , marque a caixa de seleção **associar o pool de bordas (para componentes de mídia)** .</span><span class="sxs-lookup"><span data-stu-id="8bae7-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="8bae7-158">Na caixa suspensa, selecione o servidor de borda do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8bae7-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="8bae7-159">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="8bae7-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="8bae7-160">Para ativar a Federação do servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8bae7-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="8bae7-161">No construtor de topologia, no painel esquerdo, navegue até o nó do **Skype for Business Server 2019** e, em seguida, para o nó de **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="8bae7-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="8bae7-162">Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8bae7-163">A Federação só pode ser habilitada para um único pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="8bae7-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="8bae7-164">Se você tiver vários pools de bordas, selecione um para usá-lo como o pool de bordas de Federação.</span><span class="sxs-lookup"><span data-stu-id="8bae7-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="8bae7-165">Na página **geral** , verifique se a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** está marcada.</span><span class="sxs-lookup"><span data-stu-id="8bae7-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="8bae7-166">Clique em **OK** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="8bae7-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="8bae7-167">Navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="8bae7-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="8bae7-168">Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="8bae7-169">No painel esquerdo, clique em **rota de Federação**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="8bae7-170">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Skype for Business Server 2019 listado.</span><span class="sxs-lookup"><span data-stu-id="8bae7-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="8bae7-171">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="8bae7-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="8bae7-172">Para implantações em vários locais, conclua este procedimento em cada site.</span><span class="sxs-lookup"><span data-stu-id="8bae7-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="8bae7-173">Para publicar as alterações de configuração do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="8bae7-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="8bae7-174">No **Construtor de topologias**, selecione o nó superior **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="8bae7-175">No menu **ação** , selecione **publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="8bae7-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="8bae7-176">Aguarde até que a replicação do Active Directory ocorra em todos os pools da implantação.</span><span class="sxs-lookup"><span data-stu-id="8bae7-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8bae7-177">Você pode ver a seguinte mensagem: **AVISO: a topologia contém mais de um servidor de borda federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um servidor de borda seria usado ativamente para Federação. Verifique se o registro SRV DNS externo aponta para o servidor de borda correto. Se você quiser implantar várias bordas de servidor de borda para ativar simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Skype for Business Server. Verifique se o registro SRV DNS externo lista todos os servidores de borda habilitados para Federação.**</span><span class="sxs-lookup"><span data-stu-id="8bae7-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="8bae7-178">Este aviso é esperado e pode ser ignorado com segurança.</span><span class="sxs-lookup"><span data-stu-id="8bae7-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="8bae7-179">Para configurar o servidor de borda do Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8bae7-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="8bae7-180">Reúna todos os servidores de borda do Skype for Business Server 2019 online.</span><span class="sxs-lookup"><span data-stu-id="8bae7-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="8bae7-181">Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) ao Skype for Business Server 2019 Edge Server, em vez do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="8bae7-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8bae7-182">Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS a para que a Federação seja resolvida para o novo servidor de borda de acesso do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8bae7-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="8bae7-183">Para fazer isso com o mínimo de interrupções, reduza o valor de TLL para o FQDN externo de borda de acesso do Skype for Business Server, de forma que, quando o DNS for atualizado para apontar para a nova borda de acesso do Skype for Business Server, a Federação e o acesso remoto serão atualizados rapidamente.</span><span class="sxs-lookup"><span data-stu-id="8bae7-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="8bae7-184">Pare a **borda de acesso do Skype for Business Server** de cada computador do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8bae7-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="8bae7-185">Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="8bae7-186">Na lista serviços, localize **borda de acesso do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="8bae7-187">Clique com o botão direito do mouse no nome dos serviços e, em seguida, selecione **parar** para interromper o serviço.</span><span class="sxs-lookup"><span data-stu-id="8bae7-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="8bae7-188">Defina o tipo de inicialização como **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="8bae7-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="8bae7-189">Clique em **OK** para fechar a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="8bae7-189">Click **OK** to close the **Properties** window.</span></span> 
    

