---
title: 'Lync Server 2013: balanceamento de carga de DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="07481-102">Balanceamento de carga de DNS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07481-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07481-103">_**Tópico da última modificação:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="07481-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="07481-104">O Lync Server habilita o balanceamento de carga de DNS, uma solução de software que pode reduzir significativamente a sobrecarga de administração de balanceamento de carga na sua rede.</span><span class="sxs-lookup"><span data-stu-id="07481-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="07481-105">O balanceamento de carga de DNS equilibra o tráfego de rede exclusivo para o Lync Server, como tráfego SIP e tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="07481-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="07481-106">Se você implantar o balanceamento de carga de DNS, a sobrecarga de administração da sua organização para balanceadores de carga de hardware será minimizada.</span><span class="sxs-lookup"><span data-stu-id="07481-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="07481-107">Além disso, a solução de problemas complexa de problemas relacionados à configuração incorreta de balanceadores de carga para tráfego SIP será eliminada.</span><span class="sxs-lookup"><span data-stu-id="07481-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="07481-108">Você também pode evitar conexões do servidor para que você possa colocar servidores offline.</span><span class="sxs-lookup"><span data-stu-id="07481-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="07481-109">O balanceamento de carga de DNS também garante que os problemas de balanceador de carga de hardware não afetem os elementos do tráfego SIP, como roteamento de chamadas básicas.</span><span class="sxs-lookup"><span data-stu-id="07481-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="07481-110">Se você usa o balanceamento de carga de DNS, também é possível comprar saldos de carga de hardware de baixo custo do que se você usava os balanceadores de carga de hardware para todos os tipos de tráfego.</span><span class="sxs-lookup"><span data-stu-id="07481-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="07481-111">Você deve usar balanceadores de carga que passaram no teste de qualificação de interoperabilidade com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="07481-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="07481-112">Para obter detalhes sobre o teste de interoperabilidade do balanceamento de carga, consulte "parceiros do balanceador [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)de carga do Lync Server 2010" em.</span><span class="sxs-lookup"><span data-stu-id="07481-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="07481-113">O balanceamento de carga de DNS tem suporte para pools front-end, pools do servidor de borda, pools de diretor e pools autônomos do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="07481-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="07481-114">Balanceamento de carga de DNS em pools front-end e pools de diretor</span><span class="sxs-lookup"><span data-stu-id="07481-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="07481-115">Você pode usar o balanceamento de carga de DNS para o tráfego SIP em pools de front-end e em pools de diretor.</span><span class="sxs-lookup"><span data-stu-id="07481-115">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools.</span></span> <span data-ttu-id="07481-116">Com o balanceamento de carga de DNS implantado, você ainda precisará usar balanceadores de carga de hardware para esses pools, mas somente para tráfego HTTPS de cliente para servidor.</span><span class="sxs-lookup"><span data-stu-id="07481-116">With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic.</span></span> <span data-ttu-id="07481-117">O balanceador de carga de hardware é usado para tráfego HTTPS de clientes nas portas 443 e 80.</span><span class="sxs-lookup"><span data-stu-id="07481-117">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="07481-118">Embora você ainda precise de balanceadores de carga de hardware para esses pools, a configuração e a Administração serão principalmente para tráfego HTTPS, para o qual os administradores de balanceamento de carga de hardware estão acostumados.</span><span class="sxs-lookup"><span data-stu-id="07481-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="07481-119">Balanceamento de carga de DNS e suporte a clientes e servidores mais antigos</span><span class="sxs-lookup"><span data-stu-id="07481-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="07481-120">O balanceamento de carga de DNS suporta failover automático somente para servidores que executam o Lync Server 2013 ou o Lync Server 2010 e para clientes do Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="07481-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="07481-121">As versões anteriores dos clientes e do Office Communications Server ainda podem se conectar a pools que executam o balanceamento de carga de DNS, mas se não puderem fazer uma conexão com o primeiro servidor ao qual o balanceamento de carga de DNS a referencia, eles não poderão fazer failover para outro servidor no pool .</span><span class="sxs-lookup"><span data-stu-id="07481-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="07481-122">Além disso, se você estiver usando o Exchange UM, deverá usar no mínimo o Exchange 2010 SP1 para obter suporte para o balanceamento de carga de DNS do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="07481-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="07481-123">Se você usar uma versão anterior do Exchange, os usuários não terão recursos de failover para estes cenários do Exchange UM:</span><span class="sxs-lookup"><span data-stu-id="07481-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="07481-124">Reproduzindo a caixa postal do Enterprise Voice em seu telefone</span><span class="sxs-lookup"><span data-stu-id="07481-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="07481-125">Transferindo chamadas de um atendedor automático do Exchange UM</span><span class="sxs-lookup"><span data-stu-id="07481-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="07481-126">Todos os outros cenários do Exchange UM funcionarão corretamente.</span><span class="sxs-lookup"><span data-stu-id="07481-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="07481-127">Implantando o balanceamento de carga de DNS em pools front-end e pools de diretor</span><span class="sxs-lookup"><span data-stu-id="07481-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="07481-128">Implantar o balanceamento de carga de DNS nos pools front-end e nos pools de diretor exige que você execute algumas etapas adicionais com FQDNs e registros DNS.</span><span class="sxs-lookup"><span data-stu-id="07481-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="07481-129">Um pool que usa o balanceamento de carga de DNS deve ter dois FQDNs: o FQDN do pool regular que é usado pelo balanceamento de carga de DNS (como pool01.contoso.com) e é resolvido para o IPs físicos dos servidores no pool e outro FQDN para os serviços Web do pool (como web01.contoso.com), que é resolvido para o endereço IP virtual do pool.</span><span class="sxs-lookup"><span data-stu-id="07481-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="07481-130">Em Construtor de topologia, se você quiser implantar o balanceamento de carga de DNS para um pool, para criar esse FQDN adicional para os serviços Web do pool, você deve selecionar a caixa de seleção **substituir FQDN do pool de serviços Web internos** e digitar o FQDN na página **especificar as URLs de serviços Web para este pool** .</span><span class="sxs-lookup"><span data-stu-id="07481-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="07481-131">Para dar suporte ao FQDN usado pelo balanceamento de carga de DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores do pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="07481-131">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span> <span data-ttu-id="07481-132">Você deve incluir somente os endereços IP dos servidores que estão implantados no momento.</span><span class="sxs-lookup"><span data-stu-id="07481-132">You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="07481-133">Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos.</span><span class="sxs-lookup"><span data-stu-id="07481-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="07481-134">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="07481-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="07481-135">Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="07481-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="07481-136">Se decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="07481-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="07481-137">Balanceamento de carga de DNS nos pools do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="07481-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="07481-138">Você pode implantar o balanceamento de carga de DNS nos pools do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="07481-138">You can deploy DNS load balancing on Edge Server pools.</span></span> <span data-ttu-id="07481-139">Se fizer isso, você deve estar ciente de algumas considerações.</span><span class="sxs-lookup"><span data-stu-id="07481-139">If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="07481-140">Usar o balanceamento de carga de DNS em seus servidores de borda causa uma perda de capacidade de failover nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="07481-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="07481-141">Federação com organizações que estão executando versões do Office Communications Server lançadas antes do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="07481-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="07481-142">Troca de mensagens de chat com usuários de serviços de mensagens instantâneas (IM\!) AOLand Yahoo, além de provedores e servidores baseados no XMPP, como o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="07481-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="07481-143">No momento, o Google Talk é o único parceiro XMPP com suporte.</span><span class="sxs-lookup"><span data-stu-id="07481-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="07481-144">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="07481-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="07481-145">Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="07481-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="07481-146">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="07481-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="07481-147">Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="07481-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="07481-148">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="07481-148">has been announced.</span></span> <span data-ttu-id="07481-149">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="07481-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="07481-150">Esses cenários funcionarão se todos os servidores de borda do pool estiverem em execução, mas se um servidor de borda estiver indisponível, todas as solicitações para esses cenários enviados a ele falharão, em vez de roteamento para outro servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="07481-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="07481-151">Se estiver usando o Exchange UM, você deve usar no mínimo o Exchange 2013 para obter suporte para o balanceamento de carga de DNS do Lync Server no Edge.</span><span class="sxs-lookup"><span data-stu-id="07481-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="07481-152">Se você usar uma versão anterior do Exchange, os usuários remotos não terão recursos de failover para estes cenários do Exchange UM:</span><span class="sxs-lookup"><span data-stu-id="07481-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="07481-153">Reproduzindo a caixa postal do Enterprise Voice em seu telefone</span><span class="sxs-lookup"><span data-stu-id="07481-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="07481-154">Transferindo chamadas de um atendedor automático do Exchange UM</span><span class="sxs-lookup"><span data-stu-id="07481-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="07481-155">Todos os outros cenários do Exchange UM funcionarão corretamente.</span><span class="sxs-lookup"><span data-stu-id="07481-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="07481-156">As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="07481-156">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="07481-157">Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="07481-157">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="07481-158">Implantando o balanceamento de carga de DNS nos pools do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="07481-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="07481-159">Para implantar o balanceamento de carga de DNS na interface externa do pool do servidor de borda, você precisa das seguintes entradas de DNS:</span><span class="sxs-lookup"><span data-stu-id="07481-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="07481-160">Para o serviço de borda de acesso, você precisa de uma entrada para cada servidor do pool.</span><span class="sxs-lookup"><span data-stu-id="07481-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="07481-161">Cada entrada deve resolver o FQDN do serviço de borda de acesso (por exemplo, sip.contoso.com) para o endereço IP do serviço de borda de acesso em um dos servidores de borda do pool.</span><span class="sxs-lookup"><span data-stu-id="07481-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="07481-162">Para o serviço da borda de webconferência, você precisa de uma entrada para cada servidor do pool.</span><span class="sxs-lookup"><span data-stu-id="07481-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="07481-163">Cada entrada deve resolver o FQDN do serviço de borda de Webconferência (por exemplo, webconf.contoso.com) para o endereço IP do serviço Web de Webconferência em um dos servidores de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="07481-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="07481-164">Para o serviço de borda de áudio/vídeo, você precisa de uma entrada para cada servidor do pool.</span><span class="sxs-lookup"><span data-stu-id="07481-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="07481-165">Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo (por exemplo, av.contoso.com) para o endereço IP do serviço de borda A/V em um dos servidores de borda do pool.</span><span class="sxs-lookup"><span data-stu-id="07481-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="07481-166">Para implantar o balanceamento de carga de DNS na interface interna do pool do servidor de borda, você deve adicionar um registro DNS A, que resolve o FQDN interno do pool do servidor de borda para o endereço IP de cada servidor do pool.</span><span class="sxs-lookup"><span data-stu-id="07481-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="07481-167">Usar o balanceamento de carga de DNS nos pools do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="07481-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="07481-168">Você pode usar o balanceamento de carga de DNS em pools de servidores de mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="07481-168">You can use DNS load balancing on stand-alone Mediation Server pools.</span></span> <span data-ttu-id="07481-169">Todo o tráfego SIP e de mídia é balanceado pelo balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="07481-169">All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="07481-170">Para implantar o balanceamento de carga de DNS em um pool do servidor de mediação, você deve provisionar o DNS para resolver o FQDN do pool (por exemplo, mediationpool1.contoso.com) para os endereços IP de todos os servidores do pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="07481-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="07481-171">Bloqueando o tráfego para um servidor com balanceamento de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="07481-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="07481-p117">Se você usar um balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas do endereço IP do Pool FQDN. Você deve remover a entrada DNS do computador.</span><span class="sxs-lookup"><span data-stu-id="07481-p117">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="07481-174">Observe que, para o tráfego de servidor para servidor, o Lync Server 2013 usa o balanceamento de carga compatível com topologia.</span><span class="sxs-lookup"><span data-stu-id="07481-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="07481-175">Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores.</span><span class="sxs-lookup"><span data-stu-id="07481-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="07481-176">Para impedir que um servidor receba tráfego de servidor para servidor, você deve remover o servidor da topologia.</span><span class="sxs-lookup"><span data-stu-id="07481-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

