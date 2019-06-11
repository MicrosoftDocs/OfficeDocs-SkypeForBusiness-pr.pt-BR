---
title: 'Lync Server 2013: Recuperação de desastres do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="77427-102">Recuperação de desastres do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77427-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77427-103">_**Tópico da última modificação:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="77427-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="77427-104">Assim como em outras funções de servidor, a melhor maneira de fornecer alta disponibilidade para seus servidores de borda é implantar vários servidores de borda em pools em cada site.</span><span class="sxs-lookup"><span data-stu-id="77427-104">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site.</span></span> <span data-ttu-id="77427-105">Se um servidor de borda ficar inoperante, os outros servidores do pool continuarão a fornecer serviços de borda.</span><span class="sxs-lookup"><span data-stu-id="77427-105">If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="77427-106">Para habilitar os procedimentos de recuperação de desastre, você deve ter pools de servidores de borda separados implantados em sites separados.</span><span class="sxs-lookup"><span data-stu-id="77427-106">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites.</span></span> <span data-ttu-id="77427-107">Você não precisa emparelhar explicitamente pools de bordas juntos como faz com pools de front-end, mas ter vários pools de bordas ainda oferece a disponibilidade para executar se um pool de borda inteiro ficar inativo.</span><span class="sxs-lookup"><span data-stu-id="77427-107">You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down.</span></span> <span data-ttu-id="77427-108">As seções a seguir fornecem detalhes sobre a recuperação de desastres para as várias funções dos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="77427-108">The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="77427-109">Acesso remoto</span><span class="sxs-lookup"><span data-stu-id="77427-109">Remote Access</span></span>

<span data-ttu-id="77427-110">Se você tiver vários sites, cada um com um pool de servidores de borda e um pool de bordas inteira falhar, os serviços de acesso remoto continuarão a funcionar sem a necessidade de ação do administrador.</span><span class="sxs-lookup"><span data-stu-id="77427-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="77427-111">Ao criar pools de borda em sites diferentes, você não pode usar o mesmo FQDN.</span><span class="sxs-lookup"><span data-stu-id="77427-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="77427-112">Cada pool de bordas deve ter FQDNs exclusivos (internos e externos).</span><span class="sxs-lookup"><span data-stu-id="77427-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="77427-113">Os pools de bordas não usam regras de publicação de proxy reverso para conversar com os servidores de front-end.</span><span class="sxs-lookup"><span data-stu-id="77427-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="77427-114">O failover automático ocorre quando o cliente consulta novamente os registros do serviço DNS de acesso remoto e os usuários remotos são roteados para os servidores de borda em outro site.</span><span class="sxs-lookup"><span data-stu-id="77427-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="77427-115">O cliente tenta cada FQDN de borda externa de acordo com a prioridade dos registros SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="77427-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77427-116">Para que o failover funcione tranqüilamente, certifique-se de que o firewall permita que os servidores de front-end de cada pool se comuniquem com todos os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="77427-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="77427-117">Federação</span><span class="sxs-lookup"><span data-stu-id="77427-117">Federation</span></span>

<span data-ttu-id="77427-118">Para relações de Federação com outras organizações que executam o Lync Server, as solicitações de Federação de entrada continuarão funcionando desde que você tenha soluções como GTM de DNS geográficos.</span><span class="sxs-lookup"><span data-stu-id="77427-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="77427-119">É importante entender que o failover de Federação não fornece failover com prioridade em Registros SRV.</span><span class="sxs-lookup"><span data-stu-id="77427-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="77427-120">Uma solução fornecida anteriormente pode ajudá-lo a fornecer recursos de recuperação de desastres para a Federação de entrada.</span><span class="sxs-lookup"><span data-stu-id="77427-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="77427-121">A Federação de saída sempre é configurada por meio de um pool de bordas publicado ou um servidor de borda na organização.</span><span class="sxs-lookup"><span data-stu-id="77427-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="77427-122">Se esse pool de bordas estiver desativado, você deve usar o construtor de topologias para alterar a rota de Federação de saída para usar um pool de bordas que ainda está em execução.</span><span class="sxs-lookup"><span data-stu-id="77427-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="77427-123">Para obter detalhes, consulte [falha sobre o pool de borda usado para Federação do Lync Server no Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="77427-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="77427-124">Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="77427-124">XMPP Federation</span></span>

<span data-ttu-id="77427-125">Para a Federação do XMPP, o tráfego de entrada e saída falhará se o pool de bordas que está designado como o gateway de Federação do XMPP ficar inativo.</span><span class="sxs-lookup"><span data-stu-id="77427-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="77427-126">Para fazer com que a Federação do XMPP funcione novamente, você deve alterar a Federação do XMPP para usar um pool de bordas diferente.</span><span class="sxs-lookup"><span data-stu-id="77427-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="77427-127">Para obter detalhes, consulte [falha sobre o pool de borda usado para a Federação do XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="77427-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="77427-128">O pool de bordas falha, mas o pool de front-end ainda está em execução</span><span class="sxs-lookup"><span data-stu-id="77427-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="77427-129">Se um pool de bordas falhar em um site, mas o pool de front-end nesse site ainda estiver em execução, será necessário alterar o pool de front-ends para usar um pool de bordas diferente em um site diferente enquanto esse primeiro pool de bordas estiver inoperante.</span><span class="sxs-lookup"><span data-stu-id="77427-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="77427-130">Para obter mais informações, consulte [alterando o pool de bordas associado a um pool de front-end no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="77427-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

