---
title: 'Lync Server 2013: recuperação de desastre do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cd85a769d021aae6873a50a719a6043ef72f770
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="8e0da-102">Recuperação de desastre do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e0da-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e0da-103">_**Última modificação do tópico:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="8e0da-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="8e0da-p101">Assim como ocorre com outras funções de servidor, a melhor maneira de fornecer alta disponibilidade para seus Servidores de Borda é implantar múltiplos Servidores de borda em pools em cada site. Se um Servidor de Borda ficar inativo, os outros servidores no pool continuarão a fornecer serviços de Borda.</span><span class="sxs-lookup"><span data-stu-id="8e0da-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="8e0da-p102">Para habilitar procedimentos de recuperação de desastre, é necessário ter pools de Servidor de Borda separados implantados em sites separados. Não é necessário parear explicitamente os pools de Borda da mesma forma que você faz com os pools Front-End, mas ter vários pools de Borda ainda fornece a disponibilidade para continuar caso um pool de Borda inteiro fique inativo. As seções a seguir fornecem detalhes sobre recuperação de desastre para as diversas funções dos Servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="8e0da-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="8e0da-109">Acesso remoto</span><span class="sxs-lookup"><span data-stu-id="8e0da-109">Remote Access</span></span>

<span data-ttu-id="8e0da-110">Se você tiver vários sites, cada um com um pool de servidores de borda e um pool de borda inteiro falhar, os serviços de acesso remoto continuarão a funcionar sem a necessidade de ação do administrador.</span><span class="sxs-lookup"><span data-stu-id="8e0da-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="8e0da-111">Ao criar pools de borda em sites diferentes, você não pode usar o mesmo FQDN.</span><span class="sxs-lookup"><span data-stu-id="8e0da-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="8e0da-112">Cada pool de borda deve ter FQDNs exclusivos (internos e externos).</span><span class="sxs-lookup"><span data-stu-id="8e0da-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="8e0da-113">Os pools de borda não usam regras de publicação de proxy reverso para falar com os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8e0da-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="8e0da-114">O failover automático ocorre quando o cliente consulta novamente os registros de serviço DNS de acesso remoto e os usuários remotos são roteados para os servidores de borda em outro site.</span><span class="sxs-lookup"><span data-stu-id="8e0da-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="8e0da-115">O cliente tenta cada FQDN de borda externa de acordo com a prioridade dos registros SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="8e0da-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e0da-116">Para que o failover funcione suavemente, verifique se o firewall permite que os servidores front-end de cada pool se comuniquem com todos os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="8e0da-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="8e0da-117">Federação</span><span class="sxs-lookup"><span data-stu-id="8e0da-117">Federation</span></span>

<span data-ttu-id="8e0da-118">Para relações de Federação com outras organizações que executam o Lync Server, as solicitações de Federação de entrada continuarão funcionando desde que você tenha soluções como GTM de DNS geográficos.</span><span class="sxs-lookup"><span data-stu-id="8e0da-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="8e0da-119">É importante entender que o failover de Federação não fornece failover com prioridade em Registros SRV.</span><span class="sxs-lookup"><span data-stu-id="8e0da-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="8e0da-120">Uma solução fornecida anteriormente pode ajudá-lo a fornecer recursos de recuperação de desastre para a Federação de entrada.</span><span class="sxs-lookup"><span data-stu-id="8e0da-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="8e0da-121">A federação de saída sempre é configurada por meio de um pool de Borda ou Servidor de Borda publicado na organização.</span><span class="sxs-lookup"><span data-stu-id="8e0da-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="8e0da-122">Se esse pool de Borda estiver inativo, será necessário usar o Construtor de Topologia para alterar a rota de federação de saída a fim de usar um pool de Borda que ainda está em execução.</span><span class="sxs-lookup"><span data-stu-id="8e0da-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="8e0da-123">Para obter detalhes, consulte [failover do pool de borda usado para Federação do Lync Server no Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="8e0da-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="8e0da-124">Federação XMPP</span><span class="sxs-lookup"><span data-stu-id="8e0da-124">XMPP Federation</span></span>

<span data-ttu-id="8e0da-125">Para federação XMPP, o tráfego de saída e de entrada falhará se o pool de Borda designado como o gateway de federação XMPP ficar inativo.</span><span class="sxs-lookup"><span data-stu-id="8e0da-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="8e0da-126">Para fazer a federação XMPP funcionar novamente, é necessário alterar a federação XMPP a fim de usar um pool de Borda diferente.</span><span class="sxs-lookup"><span data-stu-id="8e0da-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="8e0da-127">Para obter detalhes, consulte [failover do pool de borda usado para Federação XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="8e0da-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="8e0da-128">Pool de Borda falha, mas o pool Front-End ainda está em execução</span><span class="sxs-lookup"><span data-stu-id="8e0da-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="8e0da-129">Se um pool de Borda falhar em um site, mas o pool Front-End nesse site ainda estiver em execução, será necessário alterar o pool Front-End a fim de usar um pool de Borda diferente em um site diferente, enquanto o primeiro pool de Borda está inativo.</span><span class="sxs-lookup"><span data-stu-id="8e0da-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="8e0da-130">Para obter mais informações, consulte [alterar o pool de borda associado a um pool de front-ends no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="8e0da-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

