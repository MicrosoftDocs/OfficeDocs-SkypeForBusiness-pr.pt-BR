---
title: 'Lync Server 2013: Configurando o DNS para descoberta automática'
description: 'Lync Server 2013: Configurando o DNS para descoberta automática.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98a56cf3aa260bcbec9099e65958a9b17c3eaf26
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548457"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="12369-103">Configurando o DNS para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12369-103">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12369-104">_**Última modificação do tópico:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="12369-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="12369-105">Para dar suporte à descoberta automática para clientes do Lync, você precisa criar os seguintes registros DNS (sistema de nomes de domínio):</span><span class="sxs-lookup"><span data-stu-id="12369-105">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="12369-106">Um registro DNS interno para dar suporte aos clientes do Lync que se conectam de dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="12369-106">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="12369-107">Um registro DNS externo ou público para suportar os clientes do Lync que se conectam a partir da Internet</span><span class="sxs-lookup"><span data-stu-id="12369-107">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="12369-108">Você deve um registro de DNS interno e um externo para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="12369-108">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="12369-109">Os registros DNS podem ser registros A (host) ou registros CNAME, com base na sua capacidade de criar novos certificados com o nome alternativo de entidade (SAN) adicional.</span><span class="sxs-lookup"><span data-stu-id="12369-109">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="12369-110">Se você não conseguir solicitar e implantar um novo certificado externo (público) com o lyncdiscover.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="12369-110">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\></span></span> <span data-ttu-id="12369-111">SAN, use o procedimento para usar a porta 80 HTTP/TCP.</span><span class="sxs-lookup"><span data-stu-id="12369-111">SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="12369-112">Os procedimentos a seguir descrevem como criar registros de DNS internos e externos.</span><span class="sxs-lookup"><span data-stu-id="12369-112">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="12369-113">Para criar registros de DNS CNAME</span><span class="sxs-lookup"><span data-stu-id="12369-113">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="12369-114">Faça o logon em um servidor de DNS conforme segue:</span><span class="sxs-lookup"><span data-stu-id="12369-114">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="12369-115">Para criar um registro de DNS interno, faça o logon em um servidor de DNS em sua rede como membro dos grupos Admins de Domínio ou DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="12369-115">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="12369-116">Para criar um registro de DNS externo, conecte-se ao provedor de DNS público.</span><span class="sxs-lookup"><span data-stu-id="12369-116">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="12369-117">Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas Administrativas** e **DNS**.</span><span class="sxs-lookup"><span data-stu-id="12369-117">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="12369-118">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="12369-118">Do one of the following:</span></span>
    
      - <span data-ttu-id="12369-119">Para um registro de DNS interno, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do Active Directory (por exemplo, contoso.local).</span><span class="sxs-lookup"><span data-stu-id="12369-119">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="12369-120">Esse domínio é o domínio do Active Directory no qual o pool de diretores do Lync Server 2013 &nbsp; e o pool de front-ends estão instalados.</span><span class="sxs-lookup"><span data-stu-id="12369-120">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="12369-121">Para um registro de DNS externo, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12369-121">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="12369-122">Verifique se existe um registro de host A para o pool de diretores da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="12369-122">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="12369-123">Para um registro de DNS interno, um registro de host A deve existir para o FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para seu pool de diretores (por exemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="12369-123">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="12369-124">Para um registro DNS externo, um registro de host A deve existir para o FQDN de serviços Web externos para seu pool de diretor (por exemplo, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12369-124">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="12369-125">Verifique se existe um registro de host A para o seu pool de front-ends da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="12369-125">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="12369-126">Para um registro de DNS interno, um registro de host A deve existir para o FQDN de serviços Web internos para seu pool de front-ends (por exemplo, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="12369-126">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="12369-127">Para um registro DNS externo, um registro de host A deve existir para o FQDN de serviços Web externos para seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12369-127">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="12369-128">Para um registro de DNS interno, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12369-128">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12369-129">Se você estiver criando um registro de DNS externo, <STRONG>Zonas de Pesquisa Direta</STRONG> já está expandido para o domínio SIP da etapa 3.</span><span class="sxs-lookup"><span data-stu-id="12369-129">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="12369-130">Clique com o botão direito no nome do domínio SIP e em **Novo Alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="12369-130">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="12369-131">Em **Nome do alias**, digite uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="12369-131">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="12369-132">Para um registro de DNS interno, digite lyncdiscoverinternal como o nome de host para a URL do Serviço de Descoberta Automática interno.</span><span class="sxs-lookup"><span data-stu-id="12369-132">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="12369-133">Para um registro de DNS externo, digite lyncdiscover como o nome de host para a URL do Serviço de Descoberta Automática externo.</span><span class="sxs-lookup"><span data-stu-id="12369-133">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="12369-134">Em **Nome de domínio totalmente qualificado (FQDN) para o host de destino**, siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="12369-134">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="12369-135">Para um registro de DNS interno, digite ou procure o FQDN de serviços Web internos para o seu pool de diretor (por exemplo, lyncwebdir01. contoso. local) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="12369-135">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="12369-136">Para um registro DNS externo, digite ou procure o FQDN dos serviços Web externos para o seu pool de diretores (por exemplo, lyncwebextdir.contoso.com) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="12369-136">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12369-137">Se você não usar um diretor, use o FQDN de serviços Web internos e externos para o pool de front-ends ou, para um único servidor, o FQDN para o servidor front-end ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12369-137">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="12369-138">Você deve criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12369-138">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="12369-139">Para criar registros de DNS A</span><span class="sxs-lookup"><span data-stu-id="12369-139">To create DNS A records</span></span>

1.  <span data-ttu-id="12369-140">Faça o logon em um servidor de DNS conforme segue:</span><span class="sxs-lookup"><span data-stu-id="12369-140">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="12369-141">Para criar um registro de DNS interno, faça o logon em um servidor de DNS em sua rede como membro dos grupos Admins de Domínio ou DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="12369-141">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="12369-142">Para criar um registro DNS externo, conecte-se ao seu provedor de DNS público ou servidor DNS externo.</span><span class="sxs-lookup"><span data-stu-id="12369-142">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="12369-143">Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas Administrativas** e **DNS**.</span><span class="sxs-lookup"><span data-stu-id="12369-143">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="12369-144">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="12369-144">Do one of the following:</span></span>
    
      - <span data-ttu-id="12369-145">Para um registro de DNS interno, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do Active Directory (por exemplo, contoso.local).</span><span class="sxs-lookup"><span data-stu-id="12369-145">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="12369-146">Esse domínio é o domínio do Active Directory no qual o pool de diretores do Lync Server 2013 &nbsp; e o pool de front-ends estão instalados.</span><span class="sxs-lookup"><span data-stu-id="12369-146">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="12369-147">Para um registro de DNS externo, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12369-147">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="12369-148">Verifique se existe um registro de host A (para IPv6, AAAA) para o pool de diretores da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="12369-148">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="12369-149">Para um registro de DNS interno, um registro de host A (para IPv6, AAAA) deve existir para o FQDN de serviços Web internos do seu pool de diretor (por exemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="12369-149">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="12369-150">Para um registro DNS externo, um registro de host A (para IPv6, AAAA) deve existir para o FQDN de serviços Web externos para o seu pool de diretor (por exemplo, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12369-150">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="12369-151">Verifique se existe um registro de host A (para IPv6, AAAA) para o pool de front-ends da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="12369-151">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="12369-152">Para um registro de DNS interno, um registro de host A (para IPv6, AAAA) deve existir para o FQDN de serviços Web internos para seu pool de front-ends (por exemplo, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="12369-152">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="12369-153">Para um registro DNS externo, um registro de host A (para IPv6, AAAA) deve existir para o FQDN de serviços Web externos para seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12369-153">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="12369-154">Para um registro de DNS interno, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="12369-154">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12369-155">Se você estiver criando um registro de DNS externo, <STRONG>Zonas de Pesquisa Direta</STRONG> já está expandido para o domínio SIP da etapa 3.</span><span class="sxs-lookup"><span data-stu-id="12369-155">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="12369-156">Clique com o botão direito no nome do domínio SIP e em **Novo Host (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="12369-156">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="12369-157">Em **Nome**, digite o nome do host conforme segue:</span><span class="sxs-lookup"><span data-stu-id="12369-157">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="12369-158">Para um registro de DNS interno, digite lyncdiscoverinternal como o nome de host para a URL do Serviço de Descoberta Automática interno.</span><span class="sxs-lookup"><span data-stu-id="12369-158">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="12369-159">Para um registro de DNS externo, digite lyncdiscover como o nome de host para a URL do Serviço de Descoberta Automática externo.</span><span class="sxs-lookup"><span data-stu-id="12369-159">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12369-160">O nome de domínio é suposto a partir da zona em que o registro está definido e, portanto, não precisa ser inserido como parte do registro A.</span><span class="sxs-lookup"><span data-stu-id="12369-160">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="12369-161">Em **Endereço IP**, digite o endereço IP conforme segue:</span><span class="sxs-lookup"><span data-stu-id="12369-161">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="12369-162">Para um registro de DNS interno, digite o endereço IP dos serviços Web internos do diretor (ou, se você usar um balanceador de carga, digite o IP virtual (VIP) do balanceador de carga do diretor).</span><span class="sxs-lookup"><span data-stu-id="12369-162">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="12369-163">Se você não usar um diretor, digite o endereço IP do servidor front-end ou servidor Standard Edition, ou, se você usar um balanceador de carga, digite o VIP do balanceador de carga do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="12369-163">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="12369-164">Para um registro de DNS externo, digite o endereço IP externo ou público do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="12369-164">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="12369-165">Clique em **Adicionar Host** e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="12369-165">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="12369-166">Para criar um registro A adicional, repita as etapas 8 a 10.</span><span class="sxs-lookup"><span data-stu-id="12369-166">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="12369-167">Você deve criar um novo lyncdiscover e lyncdiscoverinternal registros a na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12369-167">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="12369-168">Quando terminar de criar os registros A (para IPv6, AAAA), clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="12369-168">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

