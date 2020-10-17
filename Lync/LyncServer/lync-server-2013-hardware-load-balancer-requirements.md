---
title: Requisitos do balanceador de carga de hardware do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c4aac657dd1e472068474a3a70d17f1a2a38c63
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530868"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="83b31-102">Requisitos do balanceador de carga de hardware para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83b31-102">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83b31-103">_**Última modificação do tópico:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="83b31-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="83b31-104">A topologia de borda consolidada em escala do Lync Server 2013 é otimizada para o balanceamento de carga de DNS para novas implantações que se federam principalmente com outras organizações usando o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83b31-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="83b31-105">Se a alta disponibilidade for necessária para qualquer um dos cenários a seguir, um balanceador de carga de hardware deverá ser usado nos pools do Servidor de Borda para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83b31-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="83b31-106">Federação com organizações que usam o Office Communications Server 2007 R2 ou o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="83b31-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="83b31-107">UM do Exchange para usuários remotos usando o UM do Exchange antes do Exchange 2010 com SP1</span><span class="sxs-lookup"><span data-stu-id="83b31-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="83b31-108">Conectividade para usuários públicos de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="83b31-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83b31-p102">O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces.</span><span class="sxs-lookup"><span data-stu-id="83b31-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="83b31-p103">Se estiver usando um balanceador de carga de hardware, o balanceador de carga implantado para conexões com a rede interna deverá ser configurado para balancear apenas cargas do tráfego de servidores que executam o serviço de Borda de Acesso e o serviço de Borda A/V. Ele não poderá balancear a carga do tráfego do serviço interno de Borda de Webconferência ou do serviço interno de Proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="83b31-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="83b31-113">O NAT (retorno do servidor direto) não é suportado com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="83b31-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="83b31-114">Para determinar se o seu balanceador de carga de hardware oferece suporte aos recursos necessários exigidos pelo Lync Server 2013, consulte "parceiros do balanceador de carga do Lync Server 2010" em [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="83b31-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="83b31-115">Requisitos do balanceador de carga de hardware para servidores de borda que executam o serviço de Borda A/V</span><span class="sxs-lookup"><span data-stu-id="83b31-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="83b31-116">A seguir estão os requisitos do balanceador de carga de hardware para servidores de borda executando o serviço de borda A/V:</span><span class="sxs-lookup"><span data-stu-id="83b31-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="83b31-p104">Desative o nagling de TCP para as portas interna e externa 443. Nagling é o processo de combinação de diversos pacotes pequenos em um único pacote maior para uma transmissão mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="83b31-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="83b31-119">Desative o nagling de TCP para o intervalo de portas externas 50.000 a 59.999.</span><span class="sxs-lookup"><span data-stu-id="83b31-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="83b31-120">Não use NAT no firewall interno ou externo.</span><span class="sxs-lookup"><span data-stu-id="83b31-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="83b31-121">A interface interna da borda precisa estar em uma rede diferente da interface externa do Servidor de Borda e o roteamento entre elas precisa ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="83b31-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="83b31-122">A interface externa do servidor de borda que executa o serviço de borda A/V deve usar endereços IP roteáveis publicamente e sem NAT ou conversão de porta em qualquer um dos endereços IP externos de borda.</span><span class="sxs-lookup"><span data-stu-id="83b31-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="83b31-123">Requisitos do balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="83b31-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="83b31-124">Os requisitos de afinidade com base em cookies são bastante reduzidos no Lync Server 2013 para serviços Web.</span><span class="sxs-lookup"><span data-stu-id="83b31-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="83b31-125">Se você estiver implantando o Lync Server 2013 e não mantiver servidores front-end do Lync Server 2010 ou pools de front-ends, não precisará de persistência baseada em cookie.</span><span class="sxs-lookup"><span data-stu-id="83b31-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="83b31-126">No entanto, se você mantiver temporariamente ou permanentemente qualquer servidor front-end do Lync Server 2010 ou pools de front-ends, ainda usará a persistência baseada em cookie, pois ela será implantada e configurada para o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="83b31-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83b31-127"><STRONG>Se decidir usar a afinidade baseada em cookie mesmo que sua implantação não exija</STRONG>, isso não causará um impacto negativo.</span><span class="sxs-lookup"><span data-stu-id="83b31-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="83b31-128">Para implantações que **não usarão** afinidade baseada em cookie:</span><span class="sxs-lookup"><span data-stu-id="83b31-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="83b31-p106">No proxy reverso que publica a regra da porta 4443, defina **Encaminhar cabeçalho de host** como Verdadeiro. Isso garantirá que a URL original seja encaminhada.</span><span class="sxs-lookup"><span data-stu-id="83b31-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="83b31-131">Para implantações que **usarão** afinidade baseada em cookie:</span><span class="sxs-lookup"><span data-stu-id="83b31-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="83b31-p107">No proxy reverso que publica a regra da porta 4443, defina **Encaminhar cabeçalho de host** como Verdadeiro. Isso garantirá que a URL original seja encaminhada.</span><span class="sxs-lookup"><span data-stu-id="83b31-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="83b31-134">O cookie do balanceador de carga de hardware NÃO DEVE ser marcado como httpOnly</span><span class="sxs-lookup"><span data-stu-id="83b31-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="83b31-135">O cookie do balanceador de carga de hardware NÃO DEVE conter uma data de vencimento</span><span class="sxs-lookup"><span data-stu-id="83b31-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="83b31-136">O cookie do balanceador de carga de hardware DEVE ser nomeado como **MS-WSMAN** (este é o valor que o serviço Web espera e não pode ser alterado)</span><span class="sxs-lookup"><span data-stu-id="83b31-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="83b31-p108">O cookie do balanceador de carga de hardware DEVE ser definido em todas as respostas HTTP para as quais a solicitação HTTP recebida não contém um cookie, independentemente de uma resposta HTTP anterior na mesma conexão TCP já ter obtido um cookie. Se o balanceador de carga otimiza a inserção de cookie para apenas uma ocorrência por conexão TCP, essa otimização NÃO DEVE ser usada</span><span class="sxs-lookup"><span data-stu-id="83b31-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83b31-139">Configurações típicas do balanceador de carga de hardware usam afinidade de endereço de origem e um tempo de vida de sessão de 20 min. TCP, que é bom para clientes do Lync Server e do Lync 2013 porque o estado da sessão é mantido por meio do uso do cliente e/ou da interação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="83b31-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="83b31-140">Se estiver implantando dispositivos móveis, o balanceador de carga de hardware deverá ser capaz de balancear a carga da solicitação individual em uma sessão TCP (na verdade, você deve poder balancear a carga de uma solicitação individual com base no endereço IP de destino).</span><span class="sxs-lookup"><span data-stu-id="83b31-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="83b31-p109">Os balanceadores de carga de hardware F5 têm um recurso chamado OneConnect que assegura que todas as solicitações de uma conexão TCP tenham a carga balanceada individualmente. Se estiver implantando dispositivos móveis, verifique se o fornecedor do balanceador de carga de hardware tem o mesmo recurso. Os aplicativos móveis mais recentes do Apple iOS exigem a versão 1.2 do protocolo TLS. O F5 oferece configurações específicas para isso.</span><span class="sxs-lookup"><span data-stu-id="83b31-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="83b31-145">Para obter detalhes sobre balanceadores de carga de hardware de terceiros, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="83b31-145">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="83b31-146">A seguir, são apresentados os requisitos do balanceador de carga de hardware para serviços Web do pool de diretores e de front-end:</span><span class="sxs-lookup"><span data-stu-id="83b31-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="83b31-147">Para VIPs de serviços Web internos, defina \_ persistência de endereço de origem (porta interna 80, 443) no balanceador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="83b31-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="83b31-148">Para o Lync Server 2013, \_ a persistência do endereço de origem significa que várias conexões provenientes de um único endereço IP são sempre enviadas a um servidor para manter o estado da sessão.</span><span class="sxs-lookup"><span data-stu-id="83b31-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="83b31-149">Use um tempo de ociosidade de TCP de 1.800 segundos.</span><span class="sxs-lookup"><span data-stu-id="83b31-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="83b31-p111">No firewall entre o proxy reverso e o balanceador de carga de hardware do pool de próximo salto, crie uma regra que permita o tráfego https: na porta 443 do proxy reverso para o balanceador de carga de hardware. O balanceador de carga de hardware deve ser configurado para ouvir as portas 80, 443 e 4443.</span><span class="sxs-lookup"><span data-stu-id="83b31-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="83b31-152">Para ler mais sobre a configuração do balanceador de carga de hardware, revise o <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumo de porta-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="83b31-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="83b31-153">Resumo dos requisitos de afinidade do balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="83b31-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83b31-154">Local do cliente/usuário</span><span class="sxs-lookup"><span data-stu-id="83b31-154">Client/user location</span></span></th>
<th><span data-ttu-id="83b31-155">Requisitos de afinidade de FQDN de serviços Web externos</span><span class="sxs-lookup"><span data-stu-id="83b31-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="83b31-156">Requisitos de afinidade de FQDN de serviços Web internos</span><span class="sxs-lookup"><span data-stu-id="83b31-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83b31-157">Lync Web App (usuários internos e externos)</span><span class="sxs-lookup"><span data-stu-id="83b31-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="83b31-158">Dispositivo móvel (usuários internos e externos)</span><span class="sxs-lookup"><span data-stu-id="83b31-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="83b31-159">Sem afinidade</span><span class="sxs-lookup"><span data-stu-id="83b31-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="83b31-160">Afinidade do endereço de origem</span><span class="sxs-lookup"><span data-stu-id="83b31-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83b31-161">Lync Web App (apenas usuários externos)</span><span class="sxs-lookup"><span data-stu-id="83b31-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="83b31-162">Dispositivo móvel (usuários internos e externos)</span><span class="sxs-lookup"><span data-stu-id="83b31-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="83b31-163">Sem afinidade</span><span class="sxs-lookup"><span data-stu-id="83b31-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="83b31-164">Afinidade do endereço de origem</span><span class="sxs-lookup"><span data-stu-id="83b31-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83b31-165">Lync Web App (apenas usuários internos)</span><span class="sxs-lookup"><span data-stu-id="83b31-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="83b31-166">Dispositivo móvel (não implantado)</span><span class="sxs-lookup"><span data-stu-id="83b31-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="83b31-167">Sem afinidade</span><span class="sxs-lookup"><span data-stu-id="83b31-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="83b31-168">Afinidade do endereço de origem</span><span class="sxs-lookup"><span data-stu-id="83b31-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="83b31-169">Monitoramento de portas dos balanceadores de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="83b31-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="83b31-170">Defina o monitoramento de portas nos balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis devido a uma falha de hardware ou comunicação.</span><span class="sxs-lookup"><span data-stu-id="83b31-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="83b31-171">Por exemplo, se o serviço de servidor front-end (RTCSRV) parar porque o servidor front-end ou o pool de front-ends falha, o monitoramento do HLB também deve parar de receber tráfego nos serviços Web.</span><span class="sxs-lookup"><span data-stu-id="83b31-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="83b31-172">Implante o monitoramento de portas no HLB para monitorar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83b31-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="83b31-173">Pool de usuários do servidor front-end – interface interna do HLB</span><span class="sxs-lookup"><span data-stu-id="83b31-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83b31-174">IP/porta virtual</span><span class="sxs-lookup"><span data-stu-id="83b31-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="83b31-175">Porta do nó</span><span class="sxs-lookup"><span data-stu-id="83b31-175">Node Port</span></span></th>
<th><span data-ttu-id="83b31-176">Máquina/monitor do nó</span><span class="sxs-lookup"><span data-stu-id="83b31-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="83b31-177">Perfil de persistência</span><span class="sxs-lookup"><span data-stu-id="83b31-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="83b31-178">Observações</span><span class="sxs-lookup"><span data-stu-id="83b31-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83b31-179">&lt;&gt;int_mco_443_vs da Web do pool</span><span class="sxs-lookup"><span data-stu-id="83b31-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="83b31-180">443</span><span class="sxs-lookup"><span data-stu-id="83b31-180">443</span></span></p></td>
<td><p><span data-ttu-id="83b31-181">443</span><span class="sxs-lookup"><span data-stu-id="83b31-181">443</span></span></p></td>
<td><p><span data-ttu-id="83b31-182">Front-end</span><span class="sxs-lookup"><span data-stu-id="83b31-182">Front End</span></span></p>
<p><span data-ttu-id="83b31-183">5061</span><span class="sxs-lookup"><span data-stu-id="83b31-183">5061</span></span></p></td>
<td><p><span data-ttu-id="83b31-184">Origem</span><span class="sxs-lookup"><span data-stu-id="83b31-184">Source</span></span></p></td>
<td><p><span data-ttu-id="83b31-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="83b31-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83b31-186">&lt;&gt;int_mco_80_vs da Web do pool</span><span class="sxs-lookup"><span data-stu-id="83b31-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="83b31-187">80</span><span class="sxs-lookup"><span data-stu-id="83b31-187">80</span></span></p></td>
<td><p><span data-ttu-id="83b31-188">80</span><span class="sxs-lookup"><span data-stu-id="83b31-188">80</span></span></p></td>
<td><p><span data-ttu-id="83b31-189">Front-end</span><span class="sxs-lookup"><span data-stu-id="83b31-189">Front End</span></span></p>
<p><span data-ttu-id="83b31-190">5061</span><span class="sxs-lookup"><span data-stu-id="83b31-190">5061</span></span></p></td>
<td><p><span data-ttu-id="83b31-191">Origem</span><span class="sxs-lookup"><span data-stu-id="83b31-191">Source</span></span></p></td>
<td><p><span data-ttu-id="83b31-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="83b31-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="83b31-193">Pool de usuários do servidor front-end – interface externa do HLB</span><span class="sxs-lookup"><span data-stu-id="83b31-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83b31-194">IP/porta virtual</span><span class="sxs-lookup"><span data-stu-id="83b31-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="83b31-195">Porta do nó</span><span class="sxs-lookup"><span data-stu-id="83b31-195">Node Port</span></span></th>
<th><span data-ttu-id="83b31-196">Máquina/monitor do nó</span><span class="sxs-lookup"><span data-stu-id="83b31-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="83b31-197">Perfil de persistência</span><span class="sxs-lookup"><span data-stu-id="83b31-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="83b31-198">Observações</span><span class="sxs-lookup"><span data-stu-id="83b31-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83b31-199">&lt;web_mco_443_vs de pool &gt;</span><span class="sxs-lookup"><span data-stu-id="83b31-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="83b31-200">443</span><span class="sxs-lookup"><span data-stu-id="83b31-200">443</span></span></p></td>
<td><p><span data-ttu-id="83b31-201">4443</span><span class="sxs-lookup"><span data-stu-id="83b31-201">4443</span></span></p></td>
<td><p><span data-ttu-id="83b31-202">Front-end</span><span class="sxs-lookup"><span data-stu-id="83b31-202">Front End</span></span></p>
<p><span data-ttu-id="83b31-203">5061</span><span class="sxs-lookup"><span data-stu-id="83b31-203">5061</span></span></p></td>
<td><p><span data-ttu-id="83b31-204">Nenhum</span><span class="sxs-lookup"><span data-stu-id="83b31-204">None</span></span></p></td>
<td><p><span data-ttu-id="83b31-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="83b31-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83b31-206">&lt;web_mco_80_vs de pool &gt;</span><span class="sxs-lookup"><span data-stu-id="83b31-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="83b31-207">80</span><span class="sxs-lookup"><span data-stu-id="83b31-207">80</span></span></p></td>
<td><p><span data-ttu-id="83b31-208">8080</span><span class="sxs-lookup"><span data-stu-id="83b31-208">8080</span></span></p></td>
<td><p><span data-ttu-id="83b31-209">Front-end</span><span class="sxs-lookup"><span data-stu-id="83b31-209">Front End</span></span></p>
<p><span data-ttu-id="83b31-210">5061</span><span class="sxs-lookup"><span data-stu-id="83b31-210">5061</span></span></p></td>
<td><p><span data-ttu-id="83b31-211">Nenhum</span><span class="sxs-lookup"><span data-stu-id="83b31-211">None</span></span></p></td>
<td><p><span data-ttu-id="83b31-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="83b31-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

