---
title: 'Lync Server 2013: failover do pool de borda usado para Federação do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4e374337f261c6747bc1b147c9f2e02fa51efe3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="9eb22-102">Failover do pool de borda usado para Federação do Lync Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eb22-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9eb22-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="9eb22-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="9eb22-104">Se o pool de borda no qual a federação do Lync Server está configurada ficar inoperante, você precisará alterar a federação para usar outro Pool de Borda para que ela funcione.</span><span class="sxs-lookup"><span data-stu-id="9eb22-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="9eb22-105">Fazendo failover do pool de borda usado para a federação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9eb22-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="9eb22-p101">Em um servidor front-end, abra o Construtor de Topologias. Expanda **Pools de borda** e clique com o botão direito do mouse no servidor de borda ou pool de servidores de borda atualmente configurado para federação. Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9eb22-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="9eb22-p102">Em **Editar Propriedades** em **Geral**, desmarque **Habilitar federação para este pool de Borda (porta 5061)**. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9eb22-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="9eb22-p103">Expanda **Pools de borda** e clique com o botão direito do mouse no servidor de borda ou pool de servidores de borda que agora deseja usar para federação. Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="9eb22-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="9eb22-p104">Em **Editar Propriedades** em **Geral**, marque **Habilitar federação para este pool de Borda (porta 5061)**. Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9eb22-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="9eb22-p105">Clique em **Ação**, selecione **Topologia**, **Publicar**. Quando solicitado em **Publicar a topologia**, clique em **Avançar**. Quando Publicar é finalizado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="9eb22-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="9eb22-p106">No servidor de Borda, abra o assistente de Implantação do Lync Server. Clique em **Instalar ou atualizar o sistema do Lync Server**, clique em **Instalar ou remover componentes do Lync Server**. Clique em **Executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="9eb22-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="9eb22-p107">Em Instalar componentes do Lync Server, clique em **Avançar**. A tela de resumo mostrará ações conforme são executadas. Quando a implantação estiver concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis. Clique em **Concluir** para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="9eb22-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="9eb22-125">Se o site que contém o pool de borda com falha contiver servidores front-end que ainda estão em execução, você precisará atualizar o Serviço de Webconferência e o Serviço de Conferência A/V nesses pools de frond-ends para usar um pool de borda em um site remoto que ainda esteja ativo.</span><span class="sxs-lookup"><span data-stu-id="9eb22-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="9eb22-126">Para obter mais informações, consulte [alterar o pool de borda associado a um pool de front-ends no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="9eb22-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9eb22-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="9eb22-127">See Also</span></span>


[<span data-ttu-id="9eb22-128">Failover do pool de borda usado para Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eb22-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="9eb22-129">Failback do pool de borda usado para Federação do Lync Server ou Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eb22-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="9eb22-130">Recuperação de desastre do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9eb22-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

