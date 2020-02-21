---
title: 'Lync Server 2013: requisitos de DNS para pools de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae56cdf07ae76ca0499050574793421864de818
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="b21c1-102">Requisitos de DNS para pools de front-ends no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b21c1-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b21c1-103">_**Última modificação do tópico:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="b21c1-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="b21c1-104">Esta seção descreve os registros de DNS (Sistema de Nomes de Domínio) necessários para a implantação dos pools de Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="b21c1-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="b21c1-105">Registros DNS para pools Front-End</span><span class="sxs-lookup"><span data-stu-id="b21c1-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="b21c1-106">A tabela a seguir especifica os requisitos de DNS para uma implantação de pool de front-ends do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b21c1-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="b21c1-107">Requisitos DNS para um pool Front-End</span><span class="sxs-lookup"><span data-stu-id="b21c1-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b21c1-108">Cenário da implantação</span><span class="sxs-lookup"><span data-stu-id="b21c1-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="b21c1-109">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="b21c1-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b21c1-110">Pool Front-End com múltiplos servidores Front-End e um balanceador de carga de hardware (mesmo que o balanceamento de carga DNS também esteja implantado nesse pool)</span><span class="sxs-lookup"><span data-stu-id="b21c1-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="b21c1-111">Ao usar um balanceador de carga DNS e um balanceador de carga de hardware, é necessário Hospedar (A) registros.</span><span class="sxs-lookup"><span data-stu-id="b21c1-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="b21c1-112">Criar um registro A interno que resolve o FQDN (nome de domínio totalmente qualificado) do pool de Front-ends para o balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="b21c1-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="b21c1-113">Criar um registro de host interno (A) para os serviços da Web interno para o endereço de IP virtual (VIP) do balanceador de carga.</span><span class="sxs-lookup"><span data-stu-id="b21c1-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="b21c1-114">Você deve usar o nome de serviços Web internos, conforme definido no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b21c1-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="b21c1-115">Por exemplo, se você usar o balanceamento de carga DNS e o balanceamento de carga de hardware, você terá um registro A para cada servidor de front-end em um pool para balanceamento de carga DNS e um registro A para os serviços Web internos apontando para o IP virtual do balanceador de carga de hardware :</span><span class="sxs-lookup"><span data-stu-id="b21c1-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="b21c1-116">Balanceamento de carga DNS:   Pool01.contoso.net   Endereço IP do pool   10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="b21c1-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="b21c1-117">Cada servidor de front-end também terá um registro A distinto:</span><span class="sxs-lookup"><span data-stu-id="b21c1-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="b21c1-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="b21c1-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="b21c1-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="b21c1-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="b21c1-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="b21c1-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="b21c1-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="b21c1-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="b21c1-122">Balanceamento de carga de hardware:   WebInternal.contoso.net   Endereço IP de HLB VIP   192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="b21c1-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="b21c1-p102">Todo o tráfego, exceto o tráfego HTTP/HTTPS, usará o registro Pool01.contoso.net. O tráfego HTTP/HTTPS usará o endereço de serviço da Web interno definido de 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="b21c1-p102">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record. HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b21c1-125">Pool Front-End com balanceamento de carga DNS implantado</span><span class="sxs-lookup"><span data-stu-id="b21c1-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="b21c1-p103">Um conjunto de registros A internos que resolvem o FQDN do pool para o endereço IP de cada servidor no pool. É preciso ter um registro A para cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="b21c1-p103">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool. There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b21c1-128">Pool Front-End com balanceamento de carga DNS implantando</span><span class="sxs-lookup"><span data-stu-id="b21c1-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="b21c1-129">Um conjunto de registros A internos que resolvem o FQDN de cada servidor no pool para o endereço IP desse servidor.</span><span class="sxs-lookup"><span data-stu-id="b21c1-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="b21c1-130">Para obter detalhes, consulte <a href="lync-server-2013-dns-load-balancing.md">DNS Load Balancing in Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="b21c1-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b21c1-131">Pool Front-End com um único Servidor Front-End e um banco de dados back-end dedicado, mas sem balanceador de carga</span><span class="sxs-lookup"><span data-stu-id="b21c1-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="b21c1-132">Um registro A interno que resolve o FQDN do pool Front-End para o endereço IP do Servidor Front-End Enterprise Edition único.</span><span class="sxs-lookup"><span data-stu-id="b21c1-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b21c1-133">Entrada automática do cliente</span><span class="sxs-lookup"><span data-stu-id="b21c1-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="b21c1-134">Para cada domínio SIP com suporte, um registro SRV para _sipinternaltls. _tcp. &lt;domínio&gt; sobre a porta 5061 que mapeia para o FQDN do pool de front-ends que autentica e redireciona as solicitações do cliente para entrada.</span><span class="sxs-lookup"><span data-stu-id="b21c1-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="b21c1-135">Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS Requirements for Automatic Client Sign-in in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b21c1-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b21c1-136">Descoberta do serviço Web de Atualização de Dispositivo por dispositivos de UC (comunicações unificadas)</span><span class="sxs-lookup"><span data-stu-id="b21c1-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="b21c1-137">Um registro A interno com o nome ucupdates-r2. &lt;Domínio&gt; SIP que resolve para o endereço IP do pool de front-ends que hospeda o serviço Web de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b21c1-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="b21c1-138">Na situação na qual um dispositivo UC é ativado, mas um usuário nunca entrou no dispositivo, o registro A permite que o dispositivo descubra o pool Front-End que hospeda o Serviço Web de Atualização de Dispositivo e obtenha atualizações.</span><span class="sxs-lookup"><span data-stu-id="b21c1-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="b21c1-139">Caso contrário, os dispositivos obtêm essas informações por meio do fornecimento em banda na primeira vez que um usuário faz login.</span><span class="sxs-lookup"><span data-stu-id="b21c1-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="b21c1-140">Se você tiver uma implantação existente do serviço Web de atualização de dispositivo no Lync Server 2010, você já criou um registro A interno com o nome ucupdates. &lt;Domínio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="b21c1-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="b21c1-141">Para o Microsoft Office Communications Server 2007 R2, você deve criar um registro DNS A adicional com o nome ucupdates-r2. &lt;Domínio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="b21c1-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b21c1-142">Um proxy reverso para dar suporte ao tráfego HTTP</span><span class="sxs-lookup"><span data-stu-id="b21c1-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="b21c1-143">Um registro A externo que resolva o FQDN da Web farm externa como o endereço IP externo do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="b21c1-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="b21c1-144">Os clientes e os dispositivos de UC usam esse registro para se conectar ao proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="b21c1-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="b21c1-145">Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="b21c1-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b21c1-146">A tabela a seguir mostra um exemplo dos registros DNS exigidos para o FQDN da web farm interna.</span><span class="sxs-lookup"><span data-stu-id="b21c1-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="b21c1-147">Exemplos de registros DNS para FQDN da web farm interna</span><span class="sxs-lookup"><span data-stu-id="b21c1-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b21c1-148">FQDN da web farm interna</span><span class="sxs-lookup"><span data-stu-id="b21c1-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="b21c1-149">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="b21c1-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="b21c1-150">Registro(s) A de DNS</span><span class="sxs-lookup"><span data-stu-id="b21c1-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b21c1-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21c1-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b21c1-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21c1-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b21c1-153">Registro A de DNS do ee-pool.contoso.com que se resolva como o endereço VIP do balanceador de carga usado pelos Servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="b21c1-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="b21c1-154">Registro A de DNS do webcon.contoso.com que se resolva como o endereço VIP do balanceador de carga usado pelos Servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="b21c1-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b21c1-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21c1-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b21c1-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b21c1-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b21c1-157">Registro A de DNS do ee-pool.contoso.com que se resolva como o endereço VIP (IP virtual) do balanceador de carga usado pelos servidores Enterprise Edition no pool Front-End.</span><span class="sxs-lookup"><span data-stu-id="b21c1-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="b21c1-158">Observe que se você estiver usando o balanceamento de carga DNS nesse pool, seu pool Front-End e web farm interna não poderão ter o mesmo FQDN.</span><span class="sxs-lookup"><span data-stu-id="b21c1-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

