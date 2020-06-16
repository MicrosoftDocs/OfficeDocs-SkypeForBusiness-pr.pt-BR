---
title: Configure o tráfego de mídia e rotas de federação
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754957"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="2be0b-102">Configure o tráfego de mídia e rotas de federação</span><span class="sxs-lookup"><span data-stu-id="2be0b-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="2be0b-103">A federação é uma relação de confiança entre dois ou mais domínios SIP que permite que usuários em organizações separadas se comuniquem através dos limites da rede.</span><span class="sxs-lookup"><span data-stu-id="2be0b-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="2be0b-104">Após migrar para o pool piloto do Lync Server 2013, você precisará fazer a transição da rota de Federação de seus servidores de borda do Microsoft Office Communications Server 2007 R2 para a rota de Federação de seus servidores de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2be0b-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="2be0b-105">Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do servidor de borda do Office Communications Server 2007 R2 e do diretor para o servidor de borda do Lync Server 2013, para uma implantação de site único.</span><span class="sxs-lookup"><span data-stu-id="2be0b-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="2be0b-106">Alterar a rota de Federação e a rota de tráfego de mídia exige que você agende o tempo de inatividade de manutenção para os servidores de borda do Lync Server 2013 e do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2be0b-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="2be0b-107">Todo esse processo de transição também significa que o acesso federado não estará disponível durante a interrupção.</span><span class="sxs-lookup"><span data-stu-id="2be0b-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="2be0b-108">Agende o tempo de inatividade para um período no qual você espera o mínimo de atividade de usuário.</span><span class="sxs-lookup"><span data-stu-id="2be0b-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="2be0b-109">Você também deve fornecer notificações suficientes para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="2be0b-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="2be0b-110">Planeje-se adequadamente para essa interrupção e defina as expectativas apropriadas dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="2be0b-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="2be0b-111">Se o servidor de borda do Office Communications Server 2007 R2 herdado estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda A/V, os procedimentos desta seção para fazer a transição da configuração de Federação para um servidor de borda do Lync Server 2013 não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="2be0b-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="2be0b-112">Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, você deverá primeiro migrar todos os usuários do Office Communications Server 2007 R2 para o Lync Server 2013 e, em seguida, encerrar o servidor de borda do Office Communications Server 2007 R2 antes de habilitar a Federação no servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2be0b-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="2be0b-113">Para obter informações detalhadas, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="2be0b-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2be0b-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Mover os usuários restantes para o Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="2be0b-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="2be0b-115">"Remover servidores e funções de servidor" em<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="2be0b-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="2be0b-116">Se sua Federação do XMPP for encaminhada por um servidor de borda do Lync Server 2013, os usuários herdados do Office Communications Server 2007 R2 não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Lync Server 2013, as políticas e certificados do XMPP foram configurados, o parceiro federado do XMPP foi configurado no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be0b-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="2be0b-117">Para publicar, habilitar ou desabilitar com êxito uma topologia ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário membro dos grupos RTCUniversalServerAdmins e Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="2be0b-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="2be0b-118">Também é possível delegar os direitos e permissões apropriados de usuário para adição de funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="2be0b-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="2be0b-119">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2be0b-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="2be0b-120">Para fazer outras alterações na configuração, apenas a associação ao grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="2be0b-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="2be0b-121">Para remover a associação de federação herdada de sites do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be0b-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="2be0b-122">Abra a topologia do pool piloto usando o Construtor de Topologia</span><span class="sxs-lookup"><span data-stu-id="2be0b-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="2be0b-123">No painel esquerdo, navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="2be0b-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="2be0b-124">Clique com o botão direito no site e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="2be0b-125">Selecione **Rota de federação** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="2be0b-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="2be0b-126">Em Atribuição de rota de federação de local, desmarque a caixa de seleção ao lado de **Habilitar federação SIP** para desabilitar a rota de federação pelo **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="2be0b-127">![Caixa de diálogo Editar propriedades, rota de Federação](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Caixa de diálogo Editar propriedades, rota de Federação")</span><span class="sxs-lookup"><span data-stu-id="2be0b-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="2be0b-128">Clique em **OK** para fechar a página Editar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2be0b-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="2be0b-129">A partir do **Construtor de Topologia**, selecione o nó superior **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="2be0b-130">No menu **Ações**, clique em **Publicar topologia** e complete o assistente.</span><span class="sxs-lookup"><span data-stu-id="2be0b-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="2be0b-131">Para configurar o Servidor de Borda herdado como um Servidor de Borda não federado</span><span class="sxs-lookup"><span data-stu-id="2be0b-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="2be0b-132">No **Construtor de Topologia**, no painel **Ações**, clique em **Mesclar topologia do Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="2be0b-133">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="2be0b-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="2be0b-134">Em **Especificar Configuração de Borda**, selecione o **FQDN Interno do Servidor de Borda** configurado atualmente para federação e clique em **Alterar**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="2be0b-135">![Mesclar a topologia do OCS 2007 R2, especificar configuração de borda](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Mesclar a topologia do OCS 2007 R2, especificar configuração de borda")</span><span class="sxs-lookup"><span data-stu-id="2be0b-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="2be0b-136">Clique em **Avançar** e aceite as configurações padrão até chegar à página **Especificar Borda Externa**:</span><span class="sxs-lookup"><span data-stu-id="2be0b-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="2be0b-137">![Página especificar borda externa do construtor de topologia](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Página especificar borda externa do construtor de topologia")</span><span class="sxs-lookup"><span data-stu-id="2be0b-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="2be0b-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span><span class="sxs-lookup"><span data-stu-id="2be0b-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="2be0b-139">This will remove the federation association with the BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="2be0b-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2be0b-140">This step is important.</span><span class="sxs-lookup"><span data-stu-id="2be0b-140">This step is important.</span></span> <span data-ttu-id="2be0b-141">You must clear this option to remove the legacy federation association.</span><span class="sxs-lookup"><span data-stu-id="2be0b-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="2be0b-142">Clique em **Avançar** e aceite as configurações padrão das páginas restantes do assistente.</span><span class="sxs-lookup"><span data-stu-id="2be0b-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="2be0b-143">Em **Resumo**, clique em **Avançar** para começar a mesclar as topologias.</span><span class="sxs-lookup"><span data-stu-id="2be0b-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="2be0b-144">Na coluna **status** , verifique se o valor é **êxito**e clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="2be0b-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="2be0b-145">No menu **Ação**, selecione **Publicar Topologia** e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="2be0b-146">Quando o **Assistente de publicação** é concluído, clique em **Finalizar** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="2be0b-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="2be0b-147">![Construtor de topologias com o site exibido após a mesclagem](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Construtor de topologias com o site exibido após a mesclagem")</span><span class="sxs-lookup"><span data-stu-id="2be0b-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="2be0b-148">Conforme exibido na figura anterior, a  **Federação SIP** localizada na **Atribuição de rota de federação de local** está definida como **Desabilitada**</span><span class="sxs-lookup"><span data-stu-id="2be0b-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="2be0b-149">Para configurar certificados no Servidor de Borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be0b-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="2be0b-150">Exporte o certificado de proxy de acesso externo, com a chave privada, do servidor de borda do Office Communications Server 2007 R2 herdado.</span><span class="sxs-lookup"><span data-stu-id="2be0b-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="2be0b-151">No servidor de borda do Lync Server 2013, importe o certificado externo do proxy de acesso da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="2be0b-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="2be0b-152">Atribua o certificado externo do proxy de acesso à interface externa do Lync Server 2013 do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="2be0b-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="2be0b-153">O certificado de interface interna do servidor de borda do Lync Server 2013 não deve ser alterado.</span><span class="sxs-lookup"><span data-stu-id="2be0b-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="2be0b-154">Para alterar a rota de federação do Office Communications Server 2007 R2 para usar o Servidor de Borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be0b-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="2be0b-155">No servidor do Office Communications Server 2007 R2 Standard Edition ou servidor front-end, abra a ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2be0b-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="2be0b-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span><span class="sxs-lookup"><span data-stu-id="2be0b-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="2be0b-157">Select **Properties**, and then click **Global Properties**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="2be0b-158">Clique na guia **Federação**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="2be0b-159">Marque a caixa de seleção para habilitar a federação e a conectividade de IM pública.</span><span class="sxs-lookup"><span data-stu-id="2be0b-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="2be0b-160">Insira o FQDN do servidor de borda do Lync Server 2013 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="2be0b-161">![Propriedades globais do OCS, guia Federação](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriedades globais do OCS, guia Federação")</span><span class="sxs-lookup"><span data-stu-id="2be0b-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="2be0b-162">Para ativar a federação do Servidor de Borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be0b-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="2be0b-163">No construtor de topologias, no painel esquerdo, navegue até o nó **pools de borda** do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2be0b-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="2be0b-164">Expanda o nó, clique com o botão direito no Servidor de Borda listado e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2be0b-165">A Federação só pode ser habilitada para um único pool de borda.</span><span class="sxs-lookup"><span data-stu-id="2be0b-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="2be0b-166">Se você tiver vários pools de borda, selecione um para usar como o pool de Borda de federação.</span><span class="sxs-lookup"><span data-stu-id="2be0b-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="2be0b-167">Na página **Geral**, marque a caixa de seleção **Habilitar federação para este pool de Borda (Porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="2be0b-168">![Editar propriedades, geral, habilitar Federação de borda](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Editar propriedades, geral, habilitar Federação de borda")</span><span class="sxs-lookup"><span data-stu-id="2be0b-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="2be0b-169">Clique em **OK** para fechar a página Editar Propriedades.</span><span class="sxs-lookup"><span data-stu-id="2be0b-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="2be0b-170">Em seguida, navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="2be0b-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="2be0b-171">Clique com o botão direito do mouse no site e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="2be0b-172">No painel esquerdo, clique em **Rota de federação**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="2be0b-173">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Lync Server 2013 listado.</span><span class="sxs-lookup"><span data-stu-id="2be0b-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="2be0b-174">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="2be0b-175">![Editar propriedades, geral, associar pool de borda](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propriedades, geral, associar pool de borda")</span><span class="sxs-lookup"><span data-stu-id="2be0b-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="2be0b-176">Para implantações entre vários locais, realize este procedimento para cada local.</span><span class="sxs-lookup"><span data-stu-id="2be0b-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="2be0b-177">Para configurar o caminho de mídia de saída do Servidor de Borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be0b-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="2be0b-178">No **Construtor de topologias**, navegue até o pool do Lync Server 2013 abaixo de **servidores front-end Standard Edition** ou **pools de front-ends Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="2be0b-179">Clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="2be0b-180">Na seção **Associações**, marque a caixa de seleção **Associar pool de Borda (para componentes de mídia)**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="2be0b-181">Na caixa suspensa, selecione o servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2be0b-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="2be0b-182">![Caixa de diálogo Editar propriedades, associar pool de borda](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Caixa de diálogo Editar propriedades, associar pool de borda")</span><span class="sxs-lookup"><span data-stu-id="2be0b-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="2be0b-183">Clique em **OK** para fechar a página **Editar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="2be0b-184">Para publicar as alterações de configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="2be0b-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="2be0b-185">A partir do **Construtor de Topologias**, selecione o nó superior **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="2be0b-186">No menu **Ações**, selecione **Publicar Topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="2be0b-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="2be0b-187">Aguarde que a replicação do Active Directory ocorra em todos os pools na implantação.</span><span class="sxs-lookup"><span data-stu-id="2be0b-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2be0b-188">Talvez você veja a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="2be0b-188">You may see the following message:</span></span><BR><span data-ttu-id="2be0b-189"><STRONG>Aviso: a topologia contém mais de um Servidor de Borda Federado. Isso pode ocorrer durante a migração para uma versão superior do produto. Nesse caso, somente um Servidor de Borda seria ativamente usado para federação. Verifique se o registro SRV DNS externo aponta para o Servidor de Borda correto. Se desejar que vários Servidores de Borda de federação permaneçam ativos simultaneamente (isto é, não em um cenário de migração), verifique se todos os parceiros federados estão usando o Office Comunications Server 2007 R2 ou superior e certifique-se de que o registro SRV DNS externo liste todos os Servidores de Borda ativamente para federação.</STRONG></span><span class="sxs-lookup"><span data-stu-id="2be0b-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="2be0b-190">Esse aviso é esperado e pode ser ignorado com segurança.</span><span class="sxs-lookup"><span data-stu-id="2be0b-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="2be0b-191">Para verificar o acesso remoto e de federação para usuários externos</span><span class="sxs-lookup"><span data-stu-id="2be0b-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="2be0b-192">No servidor front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2be0b-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="2be0b-193">Para verificar o status do acesso remoto e de federação, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="2be0b-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="2be0b-194">Para habilitar o acesso remoto e de federação, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="2be0b-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="2be0b-195">Para obter mais informações sobre esses cmdlets, consulte os seguintes tópicos: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) e [set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="2be0b-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="2be0b-196">Aguarde até que a replicação seja concluída antes de colocar os servidores de borda do Lync Server 2013 online e testar a Federação e o acesso externo.</span><span class="sxs-lookup"><span data-stu-id="2be0b-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="2be0b-197">Para configurar o Servidor de Borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be0b-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="2be0b-198">Coloque todos os servidores de borda do Lync Server 2013 online.</span><span class="sxs-lookup"><span data-stu-id="2be0b-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="2be0b-199">Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor de borda do Lync Server 2013, em vez do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="2be0b-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2be0b-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span><span class="sxs-lookup"><span data-stu-id="2be0b-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="2be0b-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span><span class="sxs-lookup"><span data-stu-id="2be0b-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="2be0b-202">Em seguida, pare a **borda de acesso do Lync Server** de cada computador do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="2be0b-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="2be0b-203">Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="2be0b-204">Na lista de serviços, encontre **Borda de Acesso do Office Communications Server**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="2be0b-205">Clique com o botão direito do mouse no nome dos serviços e selecione **Parar** para parar o serviço.</span><span class="sxs-lookup"><span data-stu-id="2be0b-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="2be0b-206">Defina o tipo de inicialização para **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="2be0b-207">Clique em **Ok** para fechar a janela **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2be0b-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="2be0b-208">Para testar a conectividade de usuários externos e o acesso externo</span><span class="sxs-lookup"><span data-stu-id="2be0b-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="2be0b-209">Usuários de pelo menos um domínio federado, um usuário interno no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2be0b-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="2be0b-210">Teste as mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2be0b-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="2be0b-211">Os usuários de cada provedor de serviços públicos de IM que sua organização suporta (e para o qual o provisionamento foi concluído) comunicando-se com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2be0b-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="2be0b-212">Verifique se os usuários anônimos podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="2be0b-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="2be0b-213">Um usuário hospedado no Office Communications Server 2007 R2 usando acesso de usuário remoto (fazendo logon no Office Communications Server 2007 R2 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2be0b-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="2be0b-214">Testar a IM, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2be0b-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="2be0b-215">Um usuário hospedado no Lync Server 2013 usando acesso de usuário remoto (fazendo logon no Lync Server 2013 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2be0b-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="2be0b-216">Testar a IM, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2be0b-216">Test IM, presence, A/V, and desktop sharing.</span></span>

