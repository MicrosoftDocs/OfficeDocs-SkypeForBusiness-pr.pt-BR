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
ms.openlocfilehash: 0d08c56e8b88f13a965f7ab24c8f497e01f10400
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="338ee-102">Balanceamento de carga de DNS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="338ee-102">DNS load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="338ee-103">_**Última modificação do tópico:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="338ee-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="338ee-104">O Lync Server habilita o balanceamento de carga de DNS, uma solução de software que pode reduzir significativamente a sobrecarga de administração para balanceamento de carga na sua rede.</span><span class="sxs-lookup"><span data-stu-id="338ee-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="338ee-105">O balanceamento de carga DNS balanceia o tráfego de rede que é exclusivo do Lync Server, como tráfego SIP e tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="338ee-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="338ee-106">Se você implantar o balanceamento de carga DNS, a sobrecarga de administração da sua organização para balanceadores de carga de hardware será minimizada.</span><span class="sxs-lookup"><span data-stu-id="338ee-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="338ee-107">Além disso, a solução complexa de problemas relacionados à configuração incorreta de balanceadores de carga de tráfego SIP será eliminada.</span><span class="sxs-lookup"><span data-stu-id="338ee-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="338ee-108">Você também pode impedir as conexões de servidor para que seja possível assumir servidores offline.</span><span class="sxs-lookup"><span data-stu-id="338ee-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="338ee-109">O balanceamento de carga DNS também garante que os problemas de balanceador de carga de hardware não afetem elementos do tráfego SIP, como o roteamento básico de chamada.</span><span class="sxs-lookup"><span data-stu-id="338ee-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="338ee-110">Se você usar o balanceamento de carga DNS, também poderá adquirir os balanceadores de carga de hardware de custo mais baixo do que se usasse os balanceadores de carga de hardware para todos os tipos de tráfego.</span><span class="sxs-lookup"><span data-stu-id="338ee-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="338ee-111">Você deve usar balanceadores de carga que passaram no teste de qualificação de interoperabilidade com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="338ee-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="338ee-112">Para obter detalhes sobre o teste de interoperabilidade do balanceador de carga, consulte "parceiros do balanceador de carga do Lync Server 2010" em [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span><span class="sxs-lookup"><span data-stu-id="338ee-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="338ee-113">O balanceamento de carga DNS é suportado para pools de Front-Ends,  pools de Servidor de Borda, pools do Diretor e pools autônomos do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="338ee-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="338ee-114">Balanceamento de carga DNS em  pools do Diretor e  pools de Front-End</span><span class="sxs-lookup"><span data-stu-id="338ee-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="338ee-p104">Você pode usar o  balanceamento de carga DNS para o tráfego SIP em pools de Front-End e  pools do Diretor. Com o balanceamento de carga DNS implantado, você precisará usar também os balanceadores de carga de hardware para esses pools, mas somente para tráfego HTTPS de cliente-servidor. O balanceador de carga de hardware é usado para tráfego HTTPS de clientes nas portas 443 e 80.</span><span class="sxs-lookup"><span data-stu-id="338ee-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="338ee-118">Embora você ainda precisará de balanceadores de carga de hardware para estes pools, sua configuração e administração será principalmente para o tráfego HTTPS, aos quais os administradores dos balanceadores de carga de hardware estão acostumados.</span><span class="sxs-lookup"><span data-stu-id="338ee-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="338ee-119">Balanceamento de carga DNS e suporte aos clientes e servidores mais antigos</span><span class="sxs-lookup"><span data-stu-id="338ee-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="338ee-120">O balanceamento de carga DNS oferece suporte a failover automático somente para servidores que executam o Lync Server 2013 ou o Lync Server 2010 e para clientes do Lync 2013 e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="338ee-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="338ee-121">As versões anteriores de clientes e o Office Communications Server ainda podem se conectar a pools que executam o balanceamento de carga DNS, mas se não puderem estabelecer uma conexão com o primeiro servidor ao qual o balanceamento de carga DNS as referencia, eles não poderão fazer failover para outro servidor no pool .</span><span class="sxs-lookup"><span data-stu-id="338ee-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="338ee-122">Além disso, se você estiver usando o UM do Exchange, deverá usar um mínimo de Exchange 2010 SP1 para obter suporte para o balanceamento de carga DNS do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="338ee-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="338ee-123">Se você usar uma versão anterior do Exchange, seus usuários não terão recursos de failover para esses cenários de UM do Exchange:</span><span class="sxs-lookup"><span data-stu-id="338ee-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="338ee-124">Reproduzindo a caixa postal do Enterprise no telefone</span><span class="sxs-lookup"><span data-stu-id="338ee-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="338ee-125">Transferindo chamadas de um Atendedor Automático UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="338ee-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="338ee-126">Todos os outros cenários UM do Exchange funcionarão corretamente.</span><span class="sxs-lookup"><span data-stu-id="338ee-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="338ee-127">A implantação do balanceamento de carga DNS em  pools do Diretor e  pools de Front-End</span><span class="sxs-lookup"><span data-stu-id="338ee-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="338ee-128">A  implantação do balanceamento DNS de carga nos pools de Front-Ends e  pools do Diretor requer a execução de algumas etapas extras com os registros DNS e FQDNs.</span><span class="sxs-lookup"><span data-stu-id="338ee-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="338ee-129">Um pool que usa o balanceamento de carga DNS deve ter dois FQDNs: o pool FQDN normal usado pelo balanceamento de carga DNS (como pool01.contoso.com) e resolve para os IPs físicos dos servidores no pool e outro FQDN para os serviços Web do pool (como web01.contoso.com), que resolve para o endereço IP virtual do pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="338ee-130">No construtor de topologia, se você deseja implantar o balanceamento de carga DNS para um pool, para criar esse FQDN extra para os serviços Web do pool, você deve marcar a caixa de seleção **substituir FQDN do pool de serviços Web internos** e digitar o FQDN, na página **especificar as URLs de serviços Web para este pool** .</span><span class="sxs-lookup"><span data-stu-id="338ee-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="338ee-p107">Para suportar o FQDN usado pelo balanceamento de carga DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão atualmente implantados.</span><span class="sxs-lookup"><span data-stu-id="338ee-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="338ee-133">Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="338ee-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="338ee-134">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="338ee-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="338ee-135">Se você também estiver implantando diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deverá ser exclusivo de qualquer outro diretor ou pool de diretores, bem como de qualquer pool de front-ends ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="338ee-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="338ee-136">Se decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="338ee-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="338ee-137">Balanceamento de carga DNS em pools de servidor de borda</span><span class="sxs-lookup"><span data-stu-id="338ee-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="338ee-p109">Você pode implantar o balanceamento de carga DNS em pools de servidor de borda. Se você fizer isso, deve estar ciente de algumas considerações.</span><span class="sxs-lookup"><span data-stu-id="338ee-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="338ee-140">Usar o balanceamento de carga DNS nos servidores de borda provoca uma perda da capacidade de failover nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="338ee-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="338ee-141">Federação com organizações que estão executando versões do Office Communications Server lançadas antes do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="338ee-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="338ee-142">Troca de mensagens instantâneas com usuários de serviços de mensagens instantâneas (IM\!) AOLand Yahoo, além de provedores e servidores baseados em XMPP, como o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="338ee-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="338ee-143">O Google Talk atualmente é o único parceiro do XMPP com suporte.</span><span class="sxs-lookup"><span data-stu-id="338ee-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="338ee-144">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="338ee-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="338ee-145">Os clientes com licenças ativas poderão continuar a se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="338ee-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="338ee-146">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="338ee-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="338ee-147">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="338ee-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="338ee-148">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="338ee-148">has been announced.</span></span> <span data-ttu-id="338ee-149">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="338ee-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="338ee-150">Esses cenários funcionarão desde que todos os servidores de borda no pool estejam funcionando. Se um servidor de borda estiver disponível, as solicitações enviadas para esses cenários falharão, em vez de rotear para outro servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="338ee-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="338ee-151">Se estiver usando um do Exchange, você deve usar um mínimo de Exchange 2013 para obter suporte para o balanceamento de carga DNS do Lync Server no Edge.</span><span class="sxs-lookup"><span data-stu-id="338ee-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="338ee-152">Se você usar uma versão anterior do Exchange, seus usuários remotos não terão recursos de failover para esses cenários de UM do Exchange:</span><span class="sxs-lookup"><span data-stu-id="338ee-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="338ee-153">Reproduzindo a caixa postal do Enterprise no telefone</span><span class="sxs-lookup"><span data-stu-id="338ee-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="338ee-154">Transferindo chamadas de um Atendedor Automático UM do Exchange</span><span class="sxs-lookup"><span data-stu-id="338ee-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="338ee-155">Todos os outros cenários UM do Exchange funcionarão corretamente.</span><span class="sxs-lookup"><span data-stu-id="338ee-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="338ee-p112">A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda.</span><span class="sxs-lookup"><span data-stu-id="338ee-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="338ee-158">Implantando o Balanceamento de Carga DNS em Pools de Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="338ee-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="338ee-159">Para implantar o balanceamento de carga DNS na interface externa do seu pool de Servidor de Borda, são necessárias as seguintes entradas DNS:</span><span class="sxs-lookup"><span data-stu-id="338ee-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="338ee-160">Para o serviço de borda de acesso, você precisa de uma entrada para cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="338ee-161">Cada entrada deve resolver o FQDN do serviço de borda de acesso (por exemplo, sip.contoso.com) para o endereço IP do serviço de borda de acesso em um dos servidores de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="338ee-162">Para o serviço de borda de webconferência, você precisa de uma entrada para cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="338ee-163">Cada entrada deve resolver o FQDN do serviço de borda de Webconferência (por exemplo, webconf.contoso.com) para o endereço IP do serviço de borda de Webconferência em um dos servidores de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="338ee-164">Para o serviço de borda de áudio/vídeo, você precisa de uma entrada para cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="338ee-165">Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo (por exemplo, av.contoso.com) para o endereço IP do serviço de borda A/V em um dos servidores de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="338ee-166">Para implantar o balanceamento de carga DNS na interface interna do pool de Servidor de Borda, você deve adicionar um registro DNS A, que resolve o FQDN interno do pool do Servidor de Borda para o endereço IP de cada servidor do pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="338ee-167">Usando o balanceamento de carga DNS em pools do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="338ee-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="338ee-p116">Você pode usar um  balanceamento de carga DNS em pools do Servidor de Mediação autônomos. Todo o tráfego SIP e de mídia é balanceado pelo balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="338ee-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="338ee-170">Para implantar o balanceamento de carga DNS em um pool do Servidor de Mediação, vcê deve provisionar o DNS para resolver o FQDN do pool (por exemplo, mediationpool1.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).</span><span class="sxs-lookup"><span data-stu-id="338ee-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="338ee-171">Bloqueando o tráfego para um servidor com balanceamento de carga DNS</span><span class="sxs-lookup"><span data-stu-id="338ee-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="338ee-172">Se você usar o balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas de endereço IP do FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="338ee-172">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="338ee-173">Você também deve remover a entrada DNS do computador.</span><span class="sxs-lookup"><span data-stu-id="338ee-173">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="338ee-174">Observe que, para o tráfego de servidor para servidor, o Lync Server 2013 usa o balanceamento de carga com reconhecimento de topologia.</span><span class="sxs-lookup"><span data-stu-id="338ee-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="338ee-175">Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores.</span><span class="sxs-lookup"><span data-stu-id="338ee-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="338ee-176">Para impedir que um servidor receba tráfego de servidor para servidor, você deve remover o servidor da topologia.</span><span class="sxs-lookup"><span data-stu-id="338ee-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

