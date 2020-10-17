---
title: Failback do pool de borda usado para Federação do Lync Server ou Federação XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2fc24adb8808eae3d3152b74e29426b2facecfb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530988"
---
# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="e3bed-102">Failback do pool de borda usado para Federação do Lync Server ou Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3bed-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3bed-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e3bed-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e3bed-104">Após um pool de Borda em falha usado para hospedar a federação entre o retorno online, use este procedimento para realizar um fail back da rota de federação do Lync Server e/ou a rota de federação XMPP para usar novamente este pool de Borda restaurado.</span><span class="sxs-lookup"><span data-stu-id="e3bed-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="e3bed-105">Failing Back da federação para um pool de borda restaurado</span><span class="sxs-lookup"><span data-stu-id="e3bed-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="e3bed-106">No pool de Borda disponível novamente, inicie os Serviços de Borda.</span><span class="sxs-lookup"><span data-stu-id="e3bed-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="e3bed-107">Se você deseja realizar o fail back da rota de federação do Lync Server para usar o Servidor de Borda restaurado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e3bed-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="e3bed-p101">No servidor de front-end, abra o Construtor de Topologia. Expanda **Pools de borda**, clique com o botão direito no servidor de Borda ou pool do servidor de Borda atualmente configurado para Federação. Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e3bed-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="e3bed-p102">Em **Editar propriedades**, em **Geral**, desmarque **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3bed-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="e3bed-p103">Expanda **Pools de borda**, clique com o botão direito no servidor de Borda original ou pool de servidor de Borda que você deseja usar novamente para Federação. Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e3bed-p103">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="e3bed-p104">Em **Editar propriedades**, em **Geral**, selecione **Habilitar federação para este pool de Borda (Porta 5061)**. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3bed-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="e3bed-p105">Clique em **Ação**, selecione **Topologia**, **Publicar**. Quando solicitado em **Publicar a topologia**, clique em **Avançar**. Quando Publicar é finalizado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="e3bed-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="e3bed-p106">No servidor de Borda, abra o assistente de Implantação do Lync Server. Clique em **Instalar ou atualizar o sistema do Lync Server**, clique em **Instalar ou remover componentes do Lync Server**. Clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="e3bed-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="e3bed-p107">Em Instalar componentes do Lync Server, clique em **Avançar**. A tela de resumo mostrará ações conforme são executadas. Quando a implantação estiver concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis. Clique em **Concluir** para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="e3bed-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="e3bed-127">Se você deseja realizar o fail back da rota de federação XMPP para usar o Servidor de Borda restaurado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e3bed-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="e3bed-128">Execute o seguinte cmdlet para reapontar a rota de federação XMPP para o pool de Borda que irá hospedar agora a federação XMPP (neste exemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="e3bed-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="e3bed-129">Neste exemplo, Site1 é o local contendo o pool de Borda que irá agora hospedar a rota de federação XMPP e EdgeServer1.contoso.com é o FQDN de um Servidor de Borda no pool.</span><span class="sxs-lookup"><span data-stu-id="e3bed-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="e3bed-p108">Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolve o pool de Borda que hospedará a federação XMPP, você deve adicioná-lo, conforme no exemplo a seguir. Este registro SRV deve ter um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="e3bed-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="e3bed-132">No servidor DNS externo, altere o registro DNS A para federação XMPP apontar para o EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e3bed-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="e3bed-133">Verifique se o pool de Borda irá agora hospedar federação XMPP com porta 5269 aberta externamente.</span><span class="sxs-lookup"><span data-stu-id="e3bed-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="e3bed-134">Se os pools de front-end permanecem executando no site contendo o pool de Borda que falhou e foi restaurado, você deve atualizar o Serviço de Conferência da Web e o Serviço de Conferência A/V nestes pools de front-end para usar novamente os pools de Borda em seu site local.</span><span class="sxs-lookup"><span data-stu-id="e3bed-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="e3bed-135">Para obter mais informações, consulte [alterar o pool de borda associado a um pool de front-ends no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="e3bed-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="e3bed-136">Se o pool de front-end no mesmo site possui um pool de Borda em falha que também falhou, é possível agora usar Invoke–CsPoolFailback para fazer o fail back do pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="e3bed-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e3bed-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="e3bed-137">See Also</span></span>


[<span data-ttu-id="e3bed-138">Failover do pool de borda usado para Federação do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3bed-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="e3bed-139">Failover do pool de borda usado para Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3bed-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="e3bed-140">Recuperação de desastre do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3bed-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

