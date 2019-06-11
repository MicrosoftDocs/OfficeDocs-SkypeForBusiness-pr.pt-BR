---
title: 'Lync Server 2013: requisitos de DNS para pools front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a><span data-ttu-id="506a1-102">Requisitos de DNS para pools front-end no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="506a1-102">DNS requirements for Front End pools in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="506a1-103">_**Tópico da última modificação:** 2012-11-07_</span><span class="sxs-lookup"><span data-stu-id="506a1-103">_**Topic Last Modified:** 2012-11-07_</span></span>

<span data-ttu-id="506a1-104">Esta seção descreve os registros DNS (sistema de nomes de domínio) necessários para a implantação de pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="506a1-104">This section describes the Domain Name System (DNS) records that are required for deployment of Front End pools.</span></span>

<div>

## <a name="dns-records-for-front-end-pools"></a><span data-ttu-id="506a1-105">Registros de DNS para pools front-end</span><span class="sxs-lookup"><span data-stu-id="506a1-105">DNS Records for Front End Pools</span></span>

<span data-ttu-id="506a1-106">A tabela a seguir especifica requisitos de DNS para a implantação de pool de front-end do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="506a1-106">The following table specifies DNS requirements for a Lync Server 2013 Front End pool deployment.</span></span>

### <a name="dns-requirements-for-a-front-end-pool"></a><span data-ttu-id="506a1-107">Requisitos de DNS para um pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="506a1-107">DNS Requirements for a Front End Pool</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="506a1-108">Cenário da implantação</span><span class="sxs-lookup"><span data-stu-id="506a1-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="506a1-109">Requisitos de DNS</span><span class="sxs-lookup"><span data-stu-id="506a1-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="506a1-110">Pool de front-end com vários servidores front-end e balanceador de carga de hardware (se o balanceamento de carga de DNS também é implantado nesse pool)</span><span class="sxs-lookup"><span data-stu-id="506a1-110">Front End pool with multiple Front End Servers and a hardware load balancer (whether or not DNS load balancing is also deployed on that pool)</span></span></p></td>
<td><p><span data-ttu-id="506a1-111">Ao usar o balanceamento de carga de DNS e um balanceador de carga de hardware, você precisa hospedar (A) registros.</span><span class="sxs-lookup"><span data-stu-id="506a1-111">When using both DNS load balancing and a hardware load balancer, you need to Host (A) records.</span></span> <span data-ttu-id="506a1-112">Crie um registro interno que resolva o FQDN (nome de domínio totalmente qualificado) do pool de front-ends para o balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="506a1-112">Create an internal A record that resolves the fully qualified domain name (FQDN) of the Front End pool for DNS load balancing.</span></span> <span data-ttu-id="506a1-113">Crie um registro de host interno (A) para os serviços internos da Web para o endereço VIP (IP virtual) do balanceador de carga.</span><span class="sxs-lookup"><span data-stu-id="506a1-113">Create an internal host (A) record for the internal Web services to the virtual IP (VIP) address of the load balancer.</span></span> <span data-ttu-id="506a1-114">Você deve usar o nome interno dos serviços Web conforme definido no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="506a1-114">You must use the internal Web services name as defined in Topology Builder.</span></span></p>
<p><span data-ttu-id="506a1-115">Por exemplo, se você usar o balanceamento de carga de DNS e o balanceamento de carga de hardware, você teria um registro A para cada servidor front-end em um pool para balanceamento de carga de DNS e um registro A para os serviços Web internos apontando para o IP virtual do balanceador de carga de hardware :</span><span class="sxs-lookup"><span data-stu-id="506a1-115">For example, if you use both DNS load balancing and hardware load balancing, you would have an A record for each Front End Server in a pool for DNS load balancing, and an A record for the internal Web services pointing to the virtual IP of the hardware load balancer:</span></span></p>
<ul>
<li><p><span data-ttu-id="506a1-116">Balanceamento de carga de DNS: Pool01.contoso.net Endereço IP do pool 10.10.10.5</span><span class="sxs-lookup"><span data-stu-id="506a1-116">DNS load balancing:   Pool01.contoso.net   IP Address of pool   10.10.10.5</span></span></p>
<div>

> [!WARNING]  
> <span data-ttu-id="506a1-117">Cada servidor front-end também terá um registro distinto:</span><span class="sxs-lookup"><span data-stu-id="506a1-117">Each Front End Server will also have a distinct A record:</span></span>


</div>
<ol>
<li><p><span data-ttu-id="506a1-118">FE01.contoso.net 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="506a1-118">FE01.contoso.net    10.10.10.1</span></span></p></li>
<li><p><span data-ttu-id="506a1-119">FE02.contoso.net 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="506a1-119">FE02.contoso.net    10.10.10.2</span></span></p></li>
<li><p><span data-ttu-id="506a1-120">FE03.contoso.net 10.10.10.3</span><span class="sxs-lookup"><span data-stu-id="506a1-120">FE03.contoso.net    10.10.10.3</span></span></p></li>
<li><p><span data-ttu-id="506a1-121">FE04.contoso.net 10.10.10.4</span><span class="sxs-lookup"><span data-stu-id="506a1-121">FE04.contoso.net    10.10.10.4</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="506a1-122">Balanceamento de carga de hardware: WebInternal.contoso.net Endereço IP de HLB VIP 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="506a1-122">Hardware load balancing:   WebInternal.contoso.net   IP Address of HLB VIP   192.168.10.5</span></span></p></li>
</ul>
<p><span data-ttu-id="506a1-123">Todo o tráfego, exceto o tráfego HTTP/HTTPS, usará o registro Pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="506a1-123">All traffic except for HTTP/HTTPS traffic will use the Pool01.contoso.net record.</span></span> <span data-ttu-id="506a1-124">O tráfego HTTP/HTTPS usará o endereço de serviços Web interno definido do 192.168.10.5</span><span class="sxs-lookup"><span data-stu-id="506a1-124">HTTP/HTTPS traffic will use the defined internal Web services address of 192.168.10.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="506a1-125">Pool de front-ends com balanceamento de carga de DNS implantado</span><span class="sxs-lookup"><span data-stu-id="506a1-125">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="506a1-126">Um conjunto de registros internos que resolvem o FQDN do pool para o endereço IP de cada servidor no pool.</span><span class="sxs-lookup"><span data-stu-id="506a1-126">A set of internal A records that resolve the FQDN of the pool to the IP address of each server in the pool.</span></span> <span data-ttu-id="506a1-127">Deve haver um registro para cada servidor do pool.</span><span class="sxs-lookup"><span data-stu-id="506a1-127">There must one A record for each server in the pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="506a1-128">Pool de front-ends com balanceamento de carga de DNS implantado</span><span class="sxs-lookup"><span data-stu-id="506a1-128">Front End pool with DNS load balancing deployed</span></span></p></td>
<td><p><span data-ttu-id="506a1-129">Um conjunto de registros internos que resolvem o FQDN de cada servidor no pool para o endereço IP desse servidor.</span><span class="sxs-lookup"><span data-stu-id="506a1-129">A set of internal A records that resolve the FQDN of each server in the pool to the IP address of that server.</span></span> <span data-ttu-id="506a1-130">Para obter detalhes, consulte <a href="lync-server-2013-dns-load-balancing.md">balanceamento de carga de DNS no Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="506a1-130">For details, see <a href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="506a1-131">Pool de front-end com um único servidor front-end e um banco de dados back-end dedicado, mas sem balanceador de carga</span><span class="sxs-lookup"><span data-stu-id="506a1-131">Front End pool with a single Front End Server and a dedicated back-end database but no load balancer</span></span></p></td>
<td><p><span data-ttu-id="506a1-132">Um registro interno que resolve o FQDN do pool de front-end para o endereço IP do servidor front-end do single Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="506a1-132">An internal A record that resolves the FQDN of the Front End pool to the IP address of the single Enterprise Edition Front End Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="506a1-133">Entrada automática do cliente</span><span class="sxs-lookup"><span data-stu-id="506a1-133">Automatic client sign-in</span></span></p></td>
<td><p><span data-ttu-id="506a1-134">Para cada domínio SIP compatível, um registro SRV para _sipinternaltls. _ TCP. &lt;domínio&gt; na porta 5061 que mapeia para o FQDN do pool de front-end que autentica e redireciona solicitações do cliente para entrada.</span><span class="sxs-lookup"><span data-stu-id="506a1-134">For each supported SIP domain, an SRV record for _sipinternaltls._tcp.&lt;domain&gt; over port 5061 that maps to the FQDN of the Front End pool that authenticates and redirects client requests for sign-in.</span></span> <span data-ttu-id="506a1-135">Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para entrada automática do cliente no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="506a1-135">For details, see <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS requirements for automatic client sign-in in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="506a1-136">Descoberta de serviços Web de atualização de dispositivo por dispositivos de comunicação unificada (UC)</span><span class="sxs-lookup"><span data-stu-id="506a1-136">Device Update Web service discovery by unified communications (UC) devices</span></span></p></td>
<td><p><span data-ttu-id="506a1-137">Um registro interno de um com o nome ucupdates-r2. &lt;Domínio&gt; SIP que é resolvido para o endereço IP do pool de front-end que hospeda o serviço Web de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="506a1-137">An internal A record with the name ucupdates-r2.&lt;SIP domain&gt; that resolves to the IP address of the Front End pool that hosts the Device Update Web service.</span></span> <span data-ttu-id="506a1-138">Na situação em que um dispositivo UC está ativado, mas um usuário nunca se conectou ao dispositivo, o registro a permite que o dispositivo descubra o pool de front-end que hospeda o serviço Web de atualização de dispositivo e obtenha atualizações.</span><span class="sxs-lookup"><span data-stu-id="506a1-138">In the situation where a UC device is turned on, but a user has never logged into the device, the A record allows the device to discover the Front End pool hosting Device Update Web service and obtain updates.</span></span> <span data-ttu-id="506a1-139">Caso contrário, os dispositivos obtêm essas informações no modo de provisionamento em banda na primeira vez que um usuário faz logon.</span><span class="sxs-lookup"><span data-stu-id="506a1-139">Otherwise, devices obtain this information though in-band provisioning the first time a user logs in.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="506a1-140">Se você tiver uma implantação existente do serviço Web de atualização de dispositivo no Lync Server 2010, você já criou um registro interno de um com o nome ucupdates. &lt;Domínio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="506a1-140">If you have an existing deployment of Device Update Web service in Lync Server 2010, you have already created an internal A record with the name ucupdates.&lt;SIP domain&gt;.</span></span> <span data-ttu-id="506a1-141">Para o Microsoft Office Communications Server 2007 R2, você deve criar um registro DNS adicional com o nome ucupdates-r2. &lt;Domínio&gt;SIP.</span><span class="sxs-lookup"><span data-stu-id="506a1-141">For Microsoft Office Communications Server 2007 R2, you must create an additional DNS A record with the name ucupdates-r2.&lt;SIP domain&gt;.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="506a1-142">Um proxy reverso para dar suporte ao tráfego HTTP</span><span class="sxs-lookup"><span data-stu-id="506a1-142">A reverse proxy to support HTTP traffic</span></span></p></td>
<td><p><span data-ttu-id="506a1-143">Um registro externo que resolve o FQDN do Web farm externo para o endereço IP externo do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="506a1-143">An external A record that resolves the external web farm FQDN to the external IP address of the reverse proxy.</span></span> <span data-ttu-id="506a1-144">Clientes e dispositivos UC usam esse registro para se conectar ao proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="506a1-144">Clients and UC devices use this record to connect to the reverse proxy.</span></span> <span data-ttu-id="506a1-145">Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar requisitos de DNS para o Lync Server 2013</a> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="506a1-145">For details, see <a href="lync-server-2013-determine-dns-requirements.md">Determine DNS requirements for Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="506a1-146">A tabela a seguir mostra um exemplo dos registros DNS necessários para o FQDN do Web farm interno.</span><span class="sxs-lookup"><span data-stu-id="506a1-146">The following table shows an example of the DNS records required for the internal web farm FQDN.</span></span>

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a><span data-ttu-id="506a1-147">Exemplo de registros DNS para FQDN do Web farm interno</span><span class="sxs-lookup"><span data-stu-id="506a1-147">Example DNS Records for Internal Web Farm FQDN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="506a1-148">FQDN da Web farm interna</span><span class="sxs-lookup"><span data-stu-id="506a1-148">Internal web farm FQDN</span></span></th>
<th><span data-ttu-id="506a1-149">FQDN do pool</span><span class="sxs-lookup"><span data-stu-id="506a1-149">Pool FQDN</span></span></th>
<th><span data-ttu-id="506a1-150">DNS A (s) registro (s)</span><span class="sxs-lookup"><span data-stu-id="506a1-150">DNS A record(s)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="506a1-151">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="506a1-151">webcon.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="506a1-152">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="506a1-152">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="506a1-153">DNS um registro para o ee-pool.contoso.com que é resolvido para o endereço VIP do balanceador de carga usado pelos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="506a1-153">DNS A record for the ee-pool.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p>
<p><span data-ttu-id="506a1-154">DNS um registro para webcon.contoso.com que é resolvido para o endereço VIP do balanceador de carga usado pelos servidores front end.</span><span class="sxs-lookup"><span data-stu-id="506a1-154">DNS A record for webcon.contoso.com that resolves to the VIP address of the load balancer used by the Front End Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="506a1-155">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="506a1-155">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="506a1-156">ee-pool.contoso.com</span><span class="sxs-lookup"><span data-stu-id="506a1-156">ee-pool.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="506a1-157">DNS um registro para ee-pool.contoso.com que é resolvido para o endereço VIP (IP virtual) do balanceador de carga usado pelos servidores front-end do Enterprise Edition no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="506a1-157">DNS A record for ee-pool.contoso.com that resolves to the virtual IP (VIP) address of the load balancer used by the Enterprise Edition Front End Servers in the Front End pool.</span></span></p>
<p><span data-ttu-id="506a1-158">Observe que, se você estiver usando o balanceamento de carga de DNS nesse pool, o pool de front-end e o Web farm interno não poderão ter o mesmo FQDN.</span><span class="sxs-lookup"><span data-stu-id="506a1-158">Note that if you are using DNS load balancing on this pool, your Front End pool and internal web farm cannot have the same FQDN.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

