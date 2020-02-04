---
title: Configurar rotas de federação e tráfego de mídia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="38d03-102">Configurar rotas de federação e tráfego de mídia</span><span class="sxs-lookup"><span data-stu-id="38d03-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38d03-103">_**Tópico da última modificação:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="38d03-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="38d03-104">A Federação é uma relação de confiança entre dois ou mais domínios SIP que permite que os usuários de organizações separadas se comuniquem entre os limites da rede.</span><span class="sxs-lookup"><span data-stu-id="38d03-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="38d03-105">Depois de migrar para o pool piloto do Lync Server 2013, você precisará fazer a transição da rota de Federação dos seus servidores do Lync Server 2010 Edge para a rota de Federação do servidor do Lync Server 2013 para servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="38d03-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="38d03-106">Use os procedimentos a seguir para fazer a transição da rota de Federação e da rota de tráfego de mídia do servidor de borda e do diretor do Lync Server 2010 para o servidor do Lync Server 2013 Edge para uma implantação de um único site.</span><span class="sxs-lookup"><span data-stu-id="38d03-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="38d03-107">Alterar a rota de Federação e a rota de tráfego de mídia requer que você agende o tempo de inatividade de manutenção para os servidores Lync Server 2013 e Lync Server 2010 Edge.</span><span class="sxs-lookup"><span data-stu-id="38d03-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="38d03-108">Esse processo de transição inteiro também significa que o acesso federado estará indisponível para a duração da interrupção.</span><span class="sxs-lookup"><span data-stu-id="38d03-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="38d03-109">Você deve programar o tempo de inatividade para um horário em que espera a atividade do usuário mínima.</span><span class="sxs-lookup"><span data-stu-id="38d03-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="38d03-110">Você também deve fornecer uma notificação suficiente para seus usuários finais.</span><span class="sxs-lookup"><span data-stu-id="38d03-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="38d03-111">Planeje-se adequadamente para esta interrupção e defina as expectativas adequadas dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="38d03-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="38d03-112">Se seu servidor de borda herdado do Lync Server 2010 está configurado para usar o mesmo FQDN para o serviço de borda de acesso, serviço de borda de Webconferência e o serviço de borda A/V, os procedimentos desta seção não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="38d03-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="38d03-113">Se os serviços de borda herdados estiverem configurados para usar o mesmo FQDN, você deve primeiro migrar todos os usuários do Lync Server 2010 para o Lync Server 2013 e, em seguida, encerrar o servidor de borda do Lync Server 2010 antes de habilitar a Federação no servidor do Lync Server 2013 Edge.</span><span class="sxs-lookup"><span data-stu-id="38d03-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="38d03-114">Se a sua Federação do XMPP for roteada por meio de um servidor de borda do Lync Server 2013, os usuários herdados do Lync Server 2010 não poderão se comunicar com o parceiro federado do XMPP até que todos os usuários tenham sido movidos para o Lync Server 2013, as políticas e os certificados do XMPP foram configurada, o parceiro federado do XMPP foi configurado no Lync Server 2013 e, por último, as entradas DNS foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="38d03-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="38d03-115">Para remover a associação de Federação herdada dos sites do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d03-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="38d03-116">No servidor de front-end do Lync Server 2013, abra a topologia existente no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="38d03-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="38d03-117">No painel esquerdo, navegue até o nó do site, localizado diretamente abaixo do **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38d03-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="38d03-118">Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38d03-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="38d03-119">No painel esquerdo, selecione **roteiro de Federação**.</span><span class="sxs-lookup"><span data-stu-id="38d03-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="38d03-120">Em **atribuição de rota de Federação do site**, desmarque a caixa de seleção **habilitar Federação SIP** para desabilitar a rota de Federação por meio do ambiente herdado do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="38d03-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="38d03-121">![Caixa de diálogo Editar propriedades, página rota de Federação](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Caixa de diálogo Editar propriedades, página rota de Federação")</span><span class="sxs-lookup"><span data-stu-id="38d03-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="38d03-122">Clique em **OK** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="38d03-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="38d03-123">No **Construtor de topologias**, selecione o nó superior do **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38d03-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="38d03-124">No menu **ação** , clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="38d03-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="38d03-125">Clique em **Avançar** para concluir o processo de publicação e, em seguida, clique em **concluir** quando o processo de publicação estiver concluído.</span><span class="sxs-lookup"><span data-stu-id="38d03-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="38d03-126">Para configurar o servidor de borda herdado como um servidor de borda não federativo</span><span class="sxs-lookup"><span data-stu-id="38d03-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="38d03-127">No painel esquerdo, navegue até o nó do **Lync Server 2010** e, em seguida, para o nó de **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="38d03-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="38d03-128">Clique com o botão direito do mouse no servidor de borda e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38d03-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="38d03-129">Selecione **geral** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="38d03-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="38d03-130">Desmarque a caixa de seleção **habilitar Federação para este pool de bordas (porta 5061)** e selecione **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="38d03-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="38d03-131">![Editar propriedades, geral, limpar habilitar Federação](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Editar propriedades, geral, limpar habilitar Federação")</span><span class="sxs-lookup"><span data-stu-id="38d03-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="38d03-132">No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="38d03-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="38d03-133">Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="38d03-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="38d03-134">Verifique se a Federação para o servidor de borda herdada está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="38d03-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="38d03-135">![Construtor de topologia, pool de bordas, agrupamento desabilitado](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Construtor de topologia, pool de bordas, agrupamento desabilitado")</span><span class="sxs-lookup"><span data-stu-id="38d03-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="38d03-136">Para configurar certificados no servidor de borda do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="38d03-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="38d03-137">Exportar o certificado de proxy de acesso externo, com a chave privada, do servidor de borda do Lync Server 2010 herdado.</span><span class="sxs-lookup"><span data-stu-id="38d03-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="38d03-138">No servidor de borda do Lync Server 2013, importe o certificado de proxy externo do Access da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="38d03-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="38d03-139">Atribua o certificado de proxy externo do Access à interface externa do Lync Server 2013 do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="38d03-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="38d03-140">O certificado de interface interna do servidor de borda do Lync Server 2013 deve ser solicitado de uma autoridade de certificação confiável e atribuído.</span><span class="sxs-lookup"><span data-stu-id="38d03-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="38d03-141">Para alterar a rota de Federação do Lync Server 2010 para usar o Lync Server 2013 Edge Server</span><span class="sxs-lookup"><span data-stu-id="38d03-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="38d03-142">No construtor de topologia, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o nó de **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="38d03-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="38d03-143">Clique com o botão direito do mouse no servidor de borda e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38d03-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="38d03-144">Selecione **geral** no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="38d03-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="38d03-145">Marque a entrada da caixa de seleção para **habilitar a Federação para este pool de bordas (porta 5061)** e clique em **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="38d03-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="38d03-146">![Caixa de diálogo Editar propriedades, página Geral](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")</span><span class="sxs-lookup"><span data-stu-id="38d03-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="38d03-147">No menu **ação** , selecione **publicar topologia**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="38d03-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="38d03-148">Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="38d03-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="38d03-149">Verifique se a **Federação (porta 5061)** está definida como **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="38d03-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="38d03-150">![Construtor de topologia, pool de bordas, agrupamento habilitado](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Construtor de topologia, pool de bordas, agrupamento habilitado")</span><span class="sxs-lookup"><span data-stu-id="38d03-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="38d03-151">Para atualizar o Lync Server 2013 o próximo nó de Federação do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38d03-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="38d03-152">No construtor de topologia, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o nó de **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="38d03-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="38d03-153">Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38d03-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="38d03-154">Na página **geral** , em **seleção do próximo salto**, selecione na lista suspensa o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38d03-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="38d03-155">![Caixa de diálogo Editar propriedades, página de próximo salto](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Caixa de diálogo Editar propriedades, página de próximo salto")</span><span class="sxs-lookup"><span data-stu-id="38d03-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="38d03-156">Clique em **OK** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="38d03-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="38d03-157">No **Construtor de topologias**, selecione o nó superior do **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="38d03-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="38d03-158">No menu **ação** , clique em **publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="38d03-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="38d03-159">Para configurar o caminho da mídia de saída do servidor de borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d03-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="38d03-160">No construtor de topologia, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o pool abaixo de **servidores front-end da edição padrão** ou **pools front-ends do Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="38d03-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="38d03-161">Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38d03-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="38d03-162">Na seção **associações** , marque a caixa de seleção **associar o pool de bordas (para componentes de mídia)** .</span><span class="sxs-lookup"><span data-stu-id="38d03-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="38d03-163">![Editar propriedades, geral, associar pool de bordas](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Editar propriedades, geral, associar pool de bordas")</span><span class="sxs-lookup"><span data-stu-id="38d03-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="38d03-164">Na caixa suspensa, selecione o servidor de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38d03-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="38d03-165">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="38d03-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="38d03-166">Para ativar a Federação do servidor de borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d03-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="38d03-167">No construtor de topologia, no painel esquerdo, navegue até o nó do **Lync Server 2013** e, em seguida, para o nó de **pools de borda** .</span><span class="sxs-lookup"><span data-stu-id="38d03-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="38d03-168">Expanda o nó, clique com o botão direito do mouse no servidor de borda listado e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38d03-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38d03-169">A Federação só pode ser habilitada para um único pool de bordas.</span><span class="sxs-lookup"><span data-stu-id="38d03-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="38d03-170">Se você tiver vários pools de bordas, selecione um para usá-lo como o pool de bordas de Federação.</span><span class="sxs-lookup"><span data-stu-id="38d03-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="38d03-171">Na página **geral** , verifique se a configuração **habilitar Federação para este pool de bordas (porta 5061)** está marcada.</span><span class="sxs-lookup"><span data-stu-id="38d03-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="38d03-172">![Caixa de diálogo Editar propriedades, página Geral](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Caixa de diálogo Editar propriedades, página Geral")</span><span class="sxs-lookup"><span data-stu-id="38d03-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="38d03-173">Clique em **OK** para fechar a página Editar propriedades.</span><span class="sxs-lookup"><span data-stu-id="38d03-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="38d03-174">Em seguida, navegue até o nó do site.</span><span class="sxs-lookup"><span data-stu-id="38d03-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="38d03-175">Clique com o botão direito do mouse no site e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="38d03-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="38d03-176">No painel esquerdo, clique em **rota de Federação**.</span><span class="sxs-lookup"><span data-stu-id="38d03-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="38d03-177">Em **atribuição de rota de Federação do site**, selecione **habilitar Federação SIP**e, em seguida, na lista Selecione o servidor de borda do Lync Server 2013 listado.</span><span class="sxs-lookup"><span data-stu-id="38d03-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="38d03-178">![Editar propriedades, página de roteiro de Federação](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Editar propriedades, página de roteiro de Federação")</span><span class="sxs-lookup"><span data-stu-id="38d03-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="38d03-179">Clique em **OK** para fechar a página **Editar propriedades** .</span><span class="sxs-lookup"><span data-stu-id="38d03-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="38d03-180">Para implantações em vários locais, conclua este procedimento em cada site.</span><span class="sxs-lookup"><span data-stu-id="38d03-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="38d03-181">Para publicar as alterações de configuração do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="38d03-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="38d03-182">No **Construtor de topologias**, selecione o nó superior do **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="38d03-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="38d03-183">No menu **ação** , selecione **publicar topologia** e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="38d03-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="38d03-184">Aguarde até que a replicação do Active Directory ocorra em todos os pools da implantação.</span><span class="sxs-lookup"><span data-stu-id="38d03-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38d03-185">Você pode ver a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="38d03-185">You may see the following message:</span></span><BR><span data-ttu-id="38d03-186"><STRONG>Aviso: a topologia contém mais de um servidor de borda federado. Isso pode ocorrer durante a migração para uma versão mais recente do produto. Nesse caso, apenas um servidor de borda seria usado ativamente para Federação. Verifique se o registro SRV DNS externo aponta para o servidor de borda correto. Se você quiser implantar várias bordas de servidor de borda para ativar simultaneamente (ou seja, não um cenário de migração), verifique se todos os parceiros federados estão usando o Lync Server. Verifique se o registro SRV DNS externo lista todos os servidores de borda habilitados para Federação.</STRONG></span><span class="sxs-lookup"><span data-stu-id="38d03-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="38d03-187">Este aviso é esperado e pode ser ignorado com segurança.</span><span class="sxs-lookup"><span data-stu-id="38d03-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="38d03-188">Para configurar o servidor de borda do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38d03-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="38d03-189">Reúna todos os servidores do Lync Server 2013 Edge online.</span><span class="sxs-lookup"><span data-stu-id="38d03-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="38d03-190">Atualize as regras de roteamento do firewall externo ou as configurações do balanceador de carga de hardware para enviar o tráfego SIP para acesso externo (geralmente a porta 443) e a Federação (geralmente a porta 5061) para o servidor do Lync 2013, em vez do servidor de borda herdado.</span><span class="sxs-lookup"><span data-stu-id="38d03-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38d03-191">Se você não tiver um balanceador de carga de hardware, será necessário atualizar o registro DNS a para que a Federação seja resolvida para o novo servidor de borda de acesso do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38d03-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="38d03-192">Para fazer isso com o mínimo de interrupção, reduza o valor TLL do FQDN do servidor de borda de acesso externo do Lync Server, para que, quando o DNS for atualizado, aponte para a nova borda de acesso do Lync Server, a Federação e o acesso remoto sejam atualizados rapidamente.</span><span class="sxs-lookup"><span data-stu-id="38d03-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="38d03-193">Em seguida, interrompa a **borda de acesso do Lync Server** de cada computador do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="38d03-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="38d03-194">Em cada computador do servidor de borda herdado, abra o applet de **Serviços** nas **Ferramentas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="38d03-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="38d03-195">Na lista serviços, localize a **borda de acesso do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38d03-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="38d03-196">Clique com o botão direito do mouse no nome dos serviços e, em seguida, selecione **parar** para interromper o serviço.</span><span class="sxs-lookup"><span data-stu-id="38d03-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="38d03-197">Defina o tipo de inicialização como **desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="38d03-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="38d03-198">Clique em **OK** para fechar a janela **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="38d03-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

