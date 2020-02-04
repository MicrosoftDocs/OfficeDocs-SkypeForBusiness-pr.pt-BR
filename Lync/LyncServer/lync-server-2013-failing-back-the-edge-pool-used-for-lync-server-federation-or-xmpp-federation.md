---
title: Failback do pool de Borda usado para federação do Lync Server ou federação XMPP
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
ms.openlocfilehash: 98fec3082c172cc9e31d931d1c64ef3eaeccd04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="c160e-102">Failback do pool de Borda usado para federação do Lync Server ou federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c160e-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c160e-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c160e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c160e-104">Depois que um pool de borda com falha que foi usado para hospedar a Federação foi colocado online novamente, use este procedimento para fazer failback do roteiro de Federação do Lync Server e/ou da rota de Federação do XMPP novamente para usar este pool de bordas restaurado.</span><span class="sxs-lookup"><span data-stu-id="c160e-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="c160e-105">Falha ao fazer a Federação para um pool de bordas restaurado</span><span class="sxs-lookup"><span data-stu-id="c160e-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="c160e-106">No pool de bordas que agora está disponível novamente, inicie os serviços de borda.</span><span class="sxs-lookup"><span data-stu-id="c160e-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="c160e-107">Se você quiser fazer failback da rota de Federação do Lync Server para usar o servidor de borda restaurado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c160e-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="c160e-108">Em um servidor front-end, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="c160e-108">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="c160e-109">Expanda **pools de bordas**, clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que está atualmente configurado para Federação.</span><span class="sxs-lookup"><span data-stu-id="c160e-109">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="c160e-110">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c160e-110">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="c160e-111">Em **Editar propriedades** em **geral**, desmarque **habilitar Federação para este pool de bordas (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="c160e-111">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="c160e-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c160e-112">Click **OK**.</span></span>
    
      - <span data-ttu-id="c160e-113">Expanda **pools de bordas**e clique com o botão direito do mouse no servidor de borda original ou no pool do servidor de borda que você deseja usar novamente para a Federação.</span><span class="sxs-lookup"><span data-stu-id="c160e-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="c160e-114">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c160e-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="c160e-115">Em **Editar propriedades** em **geral**, selecione **habilitar Federação para este pool de bordas (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="c160e-115">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="c160e-116">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c160e-116">Click **OK**.</span></span>
    
      - <span data-ttu-id="c160e-117">Clique em **ação**, selecione **topologia**, selecione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="c160e-117">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="c160e-118">Quando solicitado em **publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c160e-118">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="c160e-119">Quando a publicação estiver concluída, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="c160e-119">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="c160e-120">No servidor de borda, abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c160e-120">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="c160e-121">Clique em **instalar ou atualizar o Lync Server System**e, em seguida, clique em **Configurar ou remover componentes do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c160e-121">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="c160e-122">Clique em **executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="c160e-122">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="c160e-123">Em configurar componentes do Lync Server, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c160e-123">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="c160e-124">A tela Resumo mostrará as ações conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="c160e-124">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="c160e-125">Depois que a implantação for concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c160e-125">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="c160e-126">Clique em **concluir** para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="c160e-126">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="c160e-127">Se você quiser fazer failback na rota de Federação do XMPP para usar o servidor de borda restaurado, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c160e-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="c160e-128">Execute o cmdlet a seguir para redirecionar a rota de Federação do XMPP para o pool de borda que agora hospeda a Federação XMPP (neste exemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="c160e-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="c160e-129">Neste exemplo, site1 é o site que contém o pool de borda que agora hospeda a rota de Federação do XMPP, e EdgeServer1.contoso.com é o FQDN de um servidor de borda nesse pool.</span><span class="sxs-lookup"><span data-stu-id="c160e-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="c160e-130">Se você ainda não tiver um registro SRV DNS para a Federação do XMPP, que é resolvido para o pool de borda que agora hospedará a Federação do XMPP, você deve adicioná-lo, como no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="c160e-130">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="c160e-131">Esse registro SRV deve ter um valor de porta 5269.</span><span class="sxs-lookup"><span data-stu-id="c160e-131">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="c160e-132">No servidor DNS externo, altere o registro DNS a para a Federação XMPP para apontar para EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c160e-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="c160e-133">Verifique se o pool de bordas que agora hospeda a Federação do XMPP tem a porta 5269 aberta externamente.</span><span class="sxs-lookup"><span data-stu-id="c160e-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="c160e-134">Se os pools de front-end permanecerem sendo executados no site que contém o pool de borda que falhou e foi restaurado, você deverá atualizar o serviço de Webconferência e o serviço de conferência A/V nesses pools de front-ends para usar novamente os pools de borda em seu site local.</span><span class="sxs-lookup"><span data-stu-id="c160e-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="c160e-135">Para obter mais informações, consulte [alterando o pool de bordas associado a um pool de front-end no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="c160e-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="c160e-136">Se o pool de front-ends no mesmo site do pool de borda com falha também falhar, agora você pode usar Invoke – CsPoolFailback para fazer failback do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c160e-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c160e-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="c160e-137">See Also</span></span>


[<span data-ttu-id="c160e-138">Failover do pool de Borda usado para federação do Servidor Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c160e-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="c160e-139">Failover do pool de Borda usado para federação de XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c160e-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="c160e-140">Recuperação de desastres do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c160e-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

