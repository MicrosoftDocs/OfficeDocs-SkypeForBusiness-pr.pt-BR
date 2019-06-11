---
title: 'Lync Server 2013: Configurar DNS para balanceamento de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="f75f3-102">Configurar DNS para balanceamento de carga no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f75f3-102">Configure DNS for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f75f3-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f75f3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f75f3-104">Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou domínio minimamente como membro do grupo Domain admins ou um membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="f75f3-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="f75f3-105">O balanceamento de carga de DNS (sistema de nomes de domínio) equilibra o tráfego de rede exclusivo para o Lync Server 2013, como tráfego SIP e tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="f75f3-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="f75f3-106">O balanceamento de carga de DNS tem suporte para pools de front-end, pools de borda, pools de diretor e pools de mediação autônomos.</span><span class="sxs-lookup"><span data-stu-id="f75f3-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="f75f3-107">Um pool configurado para usar o balanceamento de carga de DNS deve ter dois nomes de domínio totalmente qualificados (FQDNs) definidos: o FQDN do pool regular que é usado pelo balanceamento de carga de DNS (por exemplo, pool1.contoso.com) e que é resolvido para o IPs físicos dos servidores no pool e outro FQDN para os serviços Web do pool (por exemplo, web1.contoso.net), que é resolvido para o endereço IP virtual do pool.</span><span class="sxs-lookup"><span data-stu-id="f75f3-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="f75f3-108">Para obter detalhes sobre o balanceamento de carga de DNS, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="f75f3-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f75f3-109">O balanceamento de carga de hardware ainda é necessário para o cliente para o tráfego HTTPS do cliente.</span><span class="sxs-lookup"><span data-stu-id="f75f3-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="f75f3-110">Antes de poder usar o balanceamento de carga de DNS, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f75f3-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="f75f3-111">Substituir o FQDN do pool de serviços Web internos.</span><span class="sxs-lookup"><span data-stu-id="f75f3-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f75f3-112">Se decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="f75f3-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="f75f3-113">Crie registros de host DNS a para resolver o FQDN do pool para os endereços IP de todos os servidores do pool.</span><span class="sxs-lookup"><span data-stu-id="f75f3-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="f75f3-114">Habilite a randomização de endereços IP ou, para o DNS do Windows Server, ative o rodízio.</span><span class="sxs-lookup"><span data-stu-id="f75f3-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f75f3-115">O Round Robin deve ser habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f75f3-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="f75f3-116">Para substituir FQDN de serviços Web internos</span><span class="sxs-lookup"><span data-stu-id="f75f3-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="f75f3-117">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="f75f3-118">Na árvore de console, expanda o nó do pool de front-end do Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="f75f3-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="f75f3-119">Clique com o botão direito do mouse no pool, clique em **Editar propriedades**e, em seguida, clique em **Serviços Web**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="f75f3-120">Abaixo de **Serviços Web internos**, marque a caixa de seleção **substituir FQDN** .</span><span class="sxs-lookup"><span data-stu-id="f75f3-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="f75f3-121">Digite o FQDN do pool que é resolvido para os endereços IP físicos dos servidores do pool.</span><span class="sxs-lookup"><span data-stu-id="f75f3-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="f75f3-122">Abaixo de **Serviços Web externos**, digite o FQDN do pool externo que é resolvido para os endereços IP virtuais do pool e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="f75f3-123">Na árvore de console, clique em **Lync Server 2013**e, em seguida, no painel **ações** , clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="f75f3-124">Para criar registros de host DNS (A) para todos os servidores de pool interno</span><span class="sxs-lookup"><span data-stu-id="f75f3-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="f75f3-125">Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f75f3-126">No **Gerenciador DNS**, clique no servidor DNS que gerencia seus registros para expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="f75f3-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="f75f3-127">Clique em **zonas de pesquisa direta** para expandi-la.</span><span class="sxs-lookup"><span data-stu-id="f75f3-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="f75f3-128">Clique com o botão direito do mouse no domínio DNS ao qual você precisa adicionar registros e, em seguida, clique em **novo host (A ou aaaa)**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="f75f3-129">Na caixa **Nome**, digite o nome do registro host (o nome do domínio será automaticamente acrescentado).</span><span class="sxs-lookup"><span data-stu-id="f75f3-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="f75f3-130">Na caixa endereço IP, digite o endereço IP do servidor front-end individual e, em seguida, selecione **criar registro de ponteiro associado (PTR)** ou **permitir que qualquer usuário autenticado atualize registros de DNS com o mesmo nome de proprietário**, se aplicável.</span><span class="sxs-lookup"><span data-stu-id="f75f3-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="f75f3-131">Continuar criando registros para todos os servidores de front-end do membro que participarão do balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="f75f3-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="f75f3-132">Por exemplo, se você tivesse um pool chamado pool1.contoso.com e três servidores front-end, você criaria as seguintes entradas DNS:</span><span class="sxs-lookup"><span data-stu-id="f75f3-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="f75f3-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="f75f3-133">FQDN</span></span></th>
    <th><span data-ttu-id="f75f3-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="f75f3-134">Type</span></span></th>
    <th><span data-ttu-id="f75f3-135">Dados</span><span class="sxs-lookup"><span data-stu-id="f75f3-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="f75f3-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f75f3-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="f75f3-137">Host (A)</span><span class="sxs-lookup"><span data-stu-id="f75f3-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="f75f3-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="f75f3-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="f75f3-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f75f3-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="f75f3-140">Host (A)</span><span class="sxs-lookup"><span data-stu-id="f75f3-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="f75f3-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="f75f3-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="f75f3-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f75f3-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="f75f3-143">Host (A)</span><span class="sxs-lookup"><span data-stu-id="f75f3-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="f75f3-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="f75f3-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="f75f3-145">Para obter detalhes sobre a criação de registros de host DNS (A), consulte [Configurar registros de host DNS para o Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="f75f3-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="f75f3-146">Para habilitar o rodízio para Windows Server</span><span class="sxs-lookup"><span data-stu-id="f75f3-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="f75f3-147">Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f75f3-148">Expanda **DNS**, clique com o botão direito do mouse no servidor DNS que você deseja configurar e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="f75f3-149">Clique na guia **avançado** , selecione **habilitar rodízio** e **Habilitar classificação de máscara de rede**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f75f3-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="f75f3-150">![Caixa de diálogo rodízio de DNS] (images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Caixa de diálogo rodízio de DNS")</span><span class="sxs-lookup"><span data-stu-id="f75f3-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f75f3-151">Esse recurso deve ser habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f75f3-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f75f3-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="f75f3-152">See Also</span></span>


[<span data-ttu-id="f75f3-153">Balanceamento de carga de DNS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f75f3-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

