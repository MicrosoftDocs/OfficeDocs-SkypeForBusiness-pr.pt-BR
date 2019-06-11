---
title: 'Lync Server 2013: Failover do pool de Borda usado para federação do Servidor Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="c5bb6-102">Failover do pool de Borda usado para federação do Servidor Lync no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5bb6-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5bb6-103">_**Tópico da última modificação:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="c5bb6-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="c5bb6-104">Se o pool de bordas em que você tem a Federação do Lync Server configurada ficar inativo, você deverá alterar a Federação para usar um pool de bordas diferente para o trabalho de Federação.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="c5bb6-105">Falha sobre o pool de bordas usado para a Federação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c5bb6-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="c5bb6-106">Em um servidor front-end, abra o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-106">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="c5bb6-107">Expanda Pools de **bordas**, clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que está atualmente configurado para Federação.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-107">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="c5bb6-108">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-108">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="c5bb6-109">Em **Editar propriedades** em **geral**, desmarque **habilitar Federação para este pool de bordas (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-109">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="c5bb6-110">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-110">Click **OK**.</span></span>

3.  <span data-ttu-id="c5bb6-111">Expanda Pools de **bordas**e clique com o botão direito do mouse no servidor de borda ou no pool do servidor de borda que você agora deseja usar para a Federação.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="c5bb6-112">Selecione **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-112">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="c5bb6-113">Em **Editar propriedades** em **geral**, selecione **habilitar Federação para este pool de bordas (porta 5061)**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-113">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="c5bb6-114">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-114">Click **OK**.</span></span>

5.  <span data-ttu-id="c5bb6-115">Clique em **ação**, selecione **topologia**, selecione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-115">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="c5bb6-116">Quando solicitado em **publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-116">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="c5bb6-117">Quando a publicação estiver concluída, clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-117">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="c5bb6-118">No servidor de borda, abra o assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="c5bb6-119">Clique em **instalar ou atualizar o Lync Server System**e, em seguida, clique em **Configurar ou remover componentes do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-119">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="c5bb6-120">Clique em **executar novamente**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-120">Click **Run Again**.</span></span>

7.  <span data-ttu-id="c5bb6-121">Em configurar componentes do Lync Server, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-121">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="c5bb6-122">A tela Resumo mostrará as ações conforme elas são executadas.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="c5bb6-123">Depois que a implantação for concluída, clique em **Exibir log** para exibir os arquivos de log disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-123">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="c5bb6-124">Clique em **concluir** para concluir a implantação.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-124">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="c5bb6-125">Se o site que contém o pool de bordas com falha contiver servidores front-end que ainda estão em execução, você deve atualizar o serviço de Webconferência e o serviço de conferência A/V nesses pools de front-ends para usar um pool de bordas em um site remoto que ainda esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="c5bb6-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="c5bb6-126">Para obter mais informações, consulte [alterando o pool de bordas associado a um pool de front-end no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="c5bb6-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5bb6-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="c5bb6-127">See Also</span></span>


[<span data-ttu-id="c5bb6-128">Failover do pool de Borda usado para federação de XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5bb6-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="c5bb6-129">Failback do pool de Borda usado para federação do Lync Server ou federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5bb6-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="c5bb6-130">Recuperação de desastres do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5bb6-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

