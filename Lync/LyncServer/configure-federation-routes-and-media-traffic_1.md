---
title: Configurar rotas de federação e tráfego de mídia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4542ae02cc72dfbac05dfa982e2fbda7f2924919
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836784"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="09ffa-102">Configurar rotas de federação e tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="09ffa-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="09ffa-103">A Federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários de organizações separadas se comuniquem entre os limites da rede.</span><span class="sxs-lookup"><span data-stu-id="09ffa-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="09ffa-104">Depois de migrar para o pool piloto do Lync Server 2013, você precisará fazer a transição da rota de Federação de seus servidores do Microsoft Office Communications Server 2007 R2 Edge para a rota de Federação do seu Lync Server 2013 Servers Edge.</span><span class="sxs-lookup"><span data-stu-id="09ffa-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="09ffa-105">Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do servidor de borda do Office Communications Server 2007 R2 e do diretor para o servidor do Lync Server 2013 para uma implantação de um único site.</span><span class="sxs-lookup"><span data-stu-id="09ffa-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="09ffa-106">Alterar a rota de Federação e a rota de tráfego de mídia requer que você agende o tempo de inatividade de manutenção dos servidores do Lync Server 2013 e do Office Communications Server 2007 R2 Edge.</span><span class="sxs-lookup"><span data-stu-id="09ffa-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="09ffa-107">Esse processo de transição inteiro também significa que o acesso federado estará indisponível para a duração da interrupção.</span><span class="sxs-lookup"><span data-stu-id="09ffa-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="09ffa-108">Você deve programar o tempo de inatividade para um horário em que espera a atividade do usuário mínima.</span><span class="sxs-lookup"><span data-stu-id="09ffa-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="09ffa-109">Você também deve fornecer uma notificação suficiente para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="09ffa-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="09ffa-110">Planeje-se adequadamente para esta interrupção e defina as expectativas adequadas dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="09ffa-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="09ffa-111">Se seu servidor herdado do Office Communications Server 2007 R2 estiver configurado para usar o mesmo FQDN para o serviço de borda de acesso, o serviço de borda de Webconferência e o serviço de borda a/V, os procedimentos desta seção serão usados para fazer a transição da configuração de Federação para um Lync Server Não há suporte para o servidor de borda do 2013.</span><span class="sxs-lookup"><span data-stu-id="09ffa-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="09ffa-112">Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, primeiro você deve migrar todos os seus usuários do Office Communications Server 2007 R2 para o Lync Server 2013 e, em seguida, encerrar o servidor do Office Communications Server 2007 R2 Edge Server antes de habilitar a Federação em o servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09ffa-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="09ffa-113">Para detalhes, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="09ffa-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="09ffa-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Mover usuários restantes para Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="09ffa-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="09ffa-115">"Remover servidores e funções de servidor" em<A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="09ffa-115">"Remove Servers and Server Roles" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268790">http://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="09ffa-116">Se a sua Federação do XMPP for roteada por meio de um servidor de borda do Lync Server 2013, os usuários herdados do Office Communications Server 2007 R2 não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para as políticas do Lync Server 2013, XMPP e os certificados foram configurados, o parceiro federado do XMPP foi configurado no Lync Server 2013 e, por último, as entradas DNS foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="09ffa-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="09ffa-117">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio.</span><span class="sxs-lookup"><span data-stu-id="09ffa-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="09ffa-118">Também é possível delegar os direitos de usuário e permissões adequados para adicionar funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="09ffa-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="09ffa-119">Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="09ffa-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="09ffa-120">Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="09ffa-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="09ffa-121">Para remover a associação de Federação herdada dos sites do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ffa-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="09ffa-122">Abra a topologia do pool piloto usando o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="09ffa-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="09ffa-123">No painel esquerdo, navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="09ffa-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="09ffa-124">Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="09ffa-125">Selecione **roteiro de Federação** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="09ffa-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="09ffa-126">Em atribuição de rota de Federação do site, desmarque a caixa de seleção ao lado de **habilitar Federação SIP** para desabilitar a rota de Federação por meio do **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="09ffa-127">![Caixa de diálogo Editar propriedades, roteiro de Federação] (images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Caixa de diálogo Editar propriedades, roteiro de Federação")</span><span class="sxs-lookup"><span data-stu-id="09ffa-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="09ffa-128">Clique em **OK** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="09ffa-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="09ffa-129">No **Construtor**de topologias, selecione o nó superior do **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="09ffa-130">No menu **ação** , clique em **publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="09ffa-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="09ffa-131">Para configurar o servidor de borda herdado como um servidor de borda não federativo</span><span class="sxs-lookup"><span data-stu-id="09ffa-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="09ffa-132">No **Construtor de topologia**, no menu **ação** , clique em **mesclar topologia do Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="09ffa-133">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="09ffa-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="09ffa-134">Na **configuração especificar borda**, selecione o **FQDN interno do servidor de borda** que está configurado atualmente para Federação e clique em **alterar**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="09ffa-135">![Mescle a topologia do OCS 2007 R2, especifique a configuração de borda] (images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Mescle a topologia do OCS 2007 R2, especifique a configuração de borda")</span><span class="sxs-lookup"><span data-stu-id="09ffa-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="09ffa-136">Clique em **Avançar** e aceite as configurações padrão até chegar à página **especificar borda externa** :</span><span class="sxs-lookup"><span data-stu-id="09ffa-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="09ffa-137">![Construtor de topologias especificar página de borda externa] (images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Construtor de topologias especificar página de borda externa")</span><span class="sxs-lookup"><span data-stu-id="09ffa-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="09ffa-138">Em **especificar borda externa**, desmarque a caixa de seleção **este pool de bordas é usado para a Federação e conectividade de im pública** .</span><span class="sxs-lookup"><span data-stu-id="09ffa-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="09ffa-139">Isso irá remover a associação de Federação com o BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="09ffa-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="09ffa-140">Esta etapa é importante.</span><span class="sxs-lookup"><span data-stu-id="09ffa-140">This step is important.</span></span> <span data-ttu-id="09ffa-141">Você deve desmarcar essa opção para remover a associação de Federação herdada.</span><span class="sxs-lookup"><span data-stu-id="09ffa-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="09ffa-142">Clique em **Avançar** e aceite as configurações padrão das páginas restantes do assistente.</span><span class="sxs-lookup"><span data-stu-id="09ffa-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="09ffa-143">Em **Resumo**, clique em **Avançar** para começar a mesclar as topologias.</span><span class="sxs-lookup"><span data-stu-id="09ffa-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="09ffa-144">Na coluna **status** , verifique se o valor é **êxito**e clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="09ffa-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="09ffa-145">No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="09ffa-146">Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="09ffa-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="09ffa-147">![Construtor de topologias com o site exibido após] a mesclagem (images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Construtor de topologias com o site exibido após") a mesclagem</span><span class="sxs-lookup"><span data-stu-id="09ffa-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="09ffa-148">Como mostrado na figura anterior, a **Federação SIP** localizada em **atribuição de rota de Federação do site** está definida como **desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="09ffa-149">Para configurar certificados no servidor de borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ffa-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="09ffa-150">Exportar o certificado de proxy de acesso externo, com a chave privada, do servidor de borda do Office Communications Server 2007 R2 herdado.</span><span class="sxs-lookup"><span data-stu-id="09ffa-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="09ffa-151">No servidor de borda do Lync Server 2013, importe o certificado de proxy externo do Access da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="09ffa-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="09ffa-152">Atribua o certificado de proxy externo do Access à interface externa do Lync Server 2013 do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="09ffa-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="09ffa-153">O certificado de interface interna do servidor de borda do Lync Server 2013 não deve ser alterado.</span><span class="sxs-lookup"><span data-stu-id="09ffa-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="09ffa-154">Para alterar a rota de Federação do Office Communications Server 2007 R2 para usar o servidor de borda 2013 do Lync Server</span><span class="sxs-lookup"><span data-stu-id="09ffa-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="09ffa-155">No servidor do Office Communications Server 2007 R2 Standard Edition ou no servidor front-end, abra a ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="09ffa-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="09ffa-156">No painel esquerdo, expanda o nó superior e clique com o botão direito do mouse no nó da **floresta** .</span><span class="sxs-lookup"><span data-stu-id="09ffa-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="09ffa-157">Selecione **Propriedades**e, em seguida, clique em **propriedades globais**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="09ffa-158">Clique na guia **Federação** .</span><span class="sxs-lookup"><span data-stu-id="09ffa-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="09ffa-159">Marque a caixa de seleção para habilitar a conectividade de mensagens de chat pública e de Federação.</span><span class="sxs-lookup"><span data-stu-id="09ffa-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="09ffa-160">Digite o FQDN do servidor de borda do Lync Server 2013 e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="09ffa-161">![Propriedades globais do OCS, guia Federação] (images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Propriedades globais do OCS, guia Federação")</span><span class="sxs-lookup"><span data-stu-id="09ffa-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="09ffa-162">Para ativar a Federação do servidor de borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ffa-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="09ffa-163">No construtor de topologias, no painel esquerdo, navegue até o nó de **pools de borda** do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09ffa-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="09ffa-164">Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="09ffa-165">A Federação só pode ser habilitada para um único pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="09ffa-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="09ffa-166">Se você tiver vários pools de bordas, selecione um para usá-lo como o pool de bordas de Federação.</span><span class="sxs-lookup"><span data-stu-id="09ffa-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="09ffa-167">Na página **geral** , marque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** .</span><span class="sxs-lookup"><span data-stu-id="09ffa-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="09ffa-168">![Editar propriedades, geral, habilitar Federação de borda] (images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Editar propriedades, geral, habilitar Federação de borda")</span><span class="sxs-lookup"><span data-stu-id="09ffa-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="09ffa-169">Clique em **OK** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="09ffa-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="09ffa-170">Em seguida, navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="09ffa-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="09ffa-171">Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="09ffa-172">No painel esquerdo, clique em **rota de Federação**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="09ffa-173">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Lync Server 2013 listado.</span><span class="sxs-lookup"><span data-stu-id="09ffa-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="09ffa-174">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="09ffa-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="09ffa-175">![Editar propriedades, geral, associar pool de bordas] (images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Editar propriedades, geral, associar pool de bordas")</span><span class="sxs-lookup"><span data-stu-id="09ffa-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="09ffa-176">Para implantações em vários locais, conclua este procedimento em cada site.</span><span class="sxs-lookup"><span data-stu-id="09ffa-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="09ffa-177">Para configurar o caminho da mídia de saída do servidor de borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ffa-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="09ffa-178">No **Construtor**de topologias, navegue até o pool do Lync Server 2013 abaixo de **servidores front-end da edição padrão** ou **pools front-ends do Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="09ffa-179">Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="09ffa-180">Na seção **associações** , marque a caixa de seleção **associar o pool de bordas (para componentes de mídia)** .</span><span class="sxs-lookup"><span data-stu-id="09ffa-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="09ffa-181">Na caixa suspensa, selecione o servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09ffa-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="09ffa-182">![Caixa de diálogo Editar propriedades, associar pool de bordas] (images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Caixa de diálogo Editar propriedades, associar pool de bordas")</span><span class="sxs-lookup"><span data-stu-id="09ffa-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="09ffa-183">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="09ffa-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="09ffa-184">Para publicar as alterações de configuração do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="09ffa-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="09ffa-185">No **Construtor**de topologias, selecione o nó superior do **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="09ffa-186">No menu **ação** , selecione **publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="09ffa-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="09ffa-187">Aguarde até que a replicação do Active Directory ocorra em todos os pools da implantação.</span><span class="sxs-lookup"><span data-stu-id="09ffa-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="09ffa-188">Você pode ver a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="09ffa-188">You may see the following message:</span></span><BR><span data-ttu-id="09ffa-189"><STRONG>Aviso: a topologia contém mais de um servidor de borda federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um servidor de borda seria usado ativamente para Federação. Verifique se o registro SRV DNS externo aponta para o servidor de borda correto. Se você quiser implantar várias bordas de servidor de borda para ativar simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Office Communications Server 2007 R2 ou o Lync Server. Verifique se o registro SRV DNS externo lista todos os servidores de borda habilitados para Federação.</STRONG></span><span class="sxs-lookup"><span data-stu-id="09ffa-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="09ffa-190">Este aviso é esperado e pode ser ignorado com segurança.</span><span class="sxs-lookup"><span data-stu-id="09ffa-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="09ffa-191">Para verificar a Federação e o acesso remoto para usuários externos</span><span class="sxs-lookup"><span data-stu-id="09ffa-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="09ffa-192">No servidor de front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09ffa-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="09ffa-193">Para verificar o status da Federação e do acesso remoto, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="09ffa-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="09ffa-194">Para habilitar a Federação e o acesso remoto, na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="09ffa-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="09ffa-195">Para obter mais informações sobre esses cmdlets, consulte os tópicos a seguir: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) e [set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="09ffa-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="09ffa-196">Aguarde até que a replicação seja concluída antes de colocar os servidores de borda do Lync Server 2013 online e testar a Federação e o acesso externo.</span><span class="sxs-lookup"><span data-stu-id="09ffa-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="09ffa-197">Para configurar o servidor de borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09ffa-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="09ffa-198">Reúna todos os servidores do Lync Server 2013 Edge online.</span><span class="sxs-lookup"><span data-stu-id="09ffa-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="09ffa-199">Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor do Lync 2013, em vez do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="09ffa-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="09ffa-200">Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS A para Federação para resolver o novo servidor de borda de acesso do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09ffa-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="09ffa-201">Para fazer isso com interrupção mínima, reduza o valor TTL do FQDN do servidor de borda de acesso externo do Lync Server, para que, quando o DNS for atualizado para apontar para o novo servidor de borda de acesso do Lync Server, a Federação e o acesso remoto sejam atualizados rapidamente.</span><span class="sxs-lookup"><span data-stu-id="09ffa-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="09ffa-202">Em seguida, interrompa a **borda de acesso do Lync Server** de cada computador do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="09ffa-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="09ffa-203">Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="09ffa-204">Na lista serviços, localize a **borda de acesso do Office Communications Server**.</span><span class="sxs-lookup"><span data-stu-id="09ffa-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="09ffa-205">Clique com o botão direito do mouse no nome dos serviços e, em seguida, selecione **parar** para interromper o serviço.</span><span class="sxs-lookup"><span data-stu-id="09ffa-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="09ffa-206">Defina o tipo de inicialização \*\*\*\* como desabilitado.</span><span class="sxs-lookup"><span data-stu-id="09ffa-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="09ffa-207">Clique em **OK** para fechar a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="09ffa-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="09ffa-208">Para testar a conectividade de usuários externos e acesso externo</span><span class="sxs-lookup"><span data-stu-id="09ffa-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="09ffa-209">Usuários de pelo menos um domínio federado, um usuário interno no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="09ffa-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="09ffa-210">Testar mensagens instantâneas (IM), presença, áudio/vídeo (A/V) e compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="09ffa-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="09ffa-211">Os usuários de cada provedor de serviço de mensagens de chat público compatível com a sua organização (e para a qual o provisionamento foi concluído) se comunicam com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="09ffa-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="09ffa-212">Verifique se usuários anônimos podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="09ffa-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="09ffa-213">Um usuário hospedado no Office Communications Server 2007 R2 usando acesso de usuário remoto (conectando-se ao Office Communications Server 2007 R2 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="09ffa-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="09ffa-214">Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="09ffa-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="09ffa-215">Um usuário hospedado no Lync Server 2013 usando acesso de usuário remoto (fazendo logon no Lync Server 2013 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="09ffa-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="09ffa-216">Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="09ffa-216">Test IM, presence, A/V, and desktop sharing.</span></span>

