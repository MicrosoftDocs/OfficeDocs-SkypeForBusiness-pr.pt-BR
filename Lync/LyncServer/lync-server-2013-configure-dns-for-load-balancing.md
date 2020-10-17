---
title: 'Lync Server 2013: configurar DNS para balanceamento de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 831968516ef155d6ad018f33bfa27226f58292dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537138"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="4e724-102">Configurar DNS para balanceamento de carga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e724-102">Configure DNS for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e724-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4e724-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4e724-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span><span class="sxs-lookup"><span data-stu-id="4e724-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="4e724-105">O balanceamento de carga do DNS (sistema de nomes de domínio) balanceia o tráfego de rede exclusivo do Lync Server 2013, como tráfego SIP e tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="4e724-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="4e724-106">O balanceamento de carga DNS é suportado para pools de Front-Ends, pools de Borda, pools de Diretores e pools de Mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="4e724-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="4e724-107">Um pool configurado para usar o balanceamento de carga DNS deve ter dois nomes de domínio totalmente qualificados (FQDNs) definidos: o FQDN do pool regular que é usado pelo balanceamento de carga DNS (por exemplo, pool1.contoso.com) e que resolve para o IPs físico dos servidores no pool e outro FQDN para os serviços Web do pool (por exemplo, web1.contoso.net), que resolve para o endereço IP virtual do pool.</span><span class="sxs-lookup"><span data-stu-id="4e724-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="4e724-108">Para obter detalhes sobre o balanceamento de carga DNS, consulte [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4e724-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e724-109">O balanceamento de carga de hardware ainda é exigido para tráfego HTTPS de cliente para servidor.</span><span class="sxs-lookup"><span data-stu-id="4e724-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="4e724-110">Antes que possa usar o balanceamento de carga DNS, você deve fazer o seguuinte:</span><span class="sxs-lookup"><span data-stu-id="4e724-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="4e724-111">Substitua o FQDN do pool de serviços Web interno.</span><span class="sxs-lookup"><span data-stu-id="4e724-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4e724-112">Se decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="4e724-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="4e724-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span><span class="sxs-lookup"><span data-stu-id="4e724-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="4e724-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span><span class="sxs-lookup"><span data-stu-id="4e724-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e724-115">Round robin deve ser habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="4e724-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="4e724-116">To override internal Web services FQDN</span><span class="sxs-lookup"><span data-stu-id="4e724-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="4e724-117">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4e724-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="4e724-118">From the console tree, expand the Enterprise Edition Front End pools node.</span><span class="sxs-lookup"><span data-stu-id="4e724-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="4e724-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span><span class="sxs-lookup"><span data-stu-id="4e724-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="4e724-120">Below **Internal web services**, select the **Override FQDN** check box.</span><span class="sxs-lookup"><span data-stu-id="4e724-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="4e724-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span><span class="sxs-lookup"><span data-stu-id="4e724-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="4e724-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e724-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="4e724-123">Na árvore de console, clique em **Lync Server 2013**e, em seguida, no painel **ações** , clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="4e724-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="4e724-124">To create DNS Host (A) Records for all internal pool servers</span><span class="sxs-lookup"><span data-stu-id="4e724-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="4e724-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4e724-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4e724-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span><span class="sxs-lookup"><span data-stu-id="4e724-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="4e724-127">Click **Forward Lookup Zones** to expand it.</span><span class="sxs-lookup"><span data-stu-id="4e724-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="4e724-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="4e724-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="4e724-129">Na caixa **nome** , digite o nome do registro do host (o nome do domínio será anexado automaticamente).</span><span class="sxs-lookup"><span data-stu-id="4e724-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="4e724-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span><span class="sxs-lookup"><span data-stu-id="4e724-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="4e724-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span><span class="sxs-lookup"><span data-stu-id="4e724-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="4e724-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span><span class="sxs-lookup"><span data-stu-id="4e724-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="4e724-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="4e724-133">FQDN</span></span></th>
    <th><span data-ttu-id="4e724-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="4e724-134">Type</span></span></th>
    <th><span data-ttu-id="4e724-135">Dados</span><span class="sxs-lookup"><span data-stu-id="4e724-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4e724-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4e724-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4e724-137">Host (A)</span><span class="sxs-lookup"><span data-stu-id="4e724-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4e724-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="4e724-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4e724-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4e724-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4e724-140">Host (A)</span><span class="sxs-lookup"><span data-stu-id="4e724-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4e724-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="4e724-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="4e724-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4e724-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="4e724-143">Host (A)</span><span class="sxs-lookup"><span data-stu-id="4e724-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="4e724-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="4e724-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="4e724-145">Para obter detalhes sobre como criar registros de host DNS (A), consulte [Configure DNS host Records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="4e724-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="4e724-146">To enable round robin for Windows Server</span><span class="sxs-lookup"><span data-stu-id="4e724-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="4e724-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4e724-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="4e724-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span><span class="sxs-lookup"><span data-stu-id="4e724-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="4e724-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e724-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="4e724-150">![Caixa de diálogo Round Robin DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Caixa de diálogo Round Robin DNS")</span><span class="sxs-lookup"><span data-stu-id="4e724-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e724-151">Este recurso deve ser habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="4e724-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e724-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="4e724-152">See Also</span></span>


[<span data-ttu-id="4e724-153">Balanceamento de carga de DNS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e724-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

