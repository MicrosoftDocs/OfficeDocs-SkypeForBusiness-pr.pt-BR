---
title: 'Lync Server 2013: Criando registros de DNS para o Serviço de Autodiscover'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5307251e9c3dea202b08b48bf45e109ef19449ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="3cc38-102">Criando registros de DNS para o Serviço de Autodiscover no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3cc38-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cc38-103">_**Tópico da última modificação:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="3cc38-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="3cc38-104">Os usuários do Lync Mobile precisarão que você habilite a descoberta automática, e uma parte dela envolve a criação de alguns registros DNS (sistema de nomes de domínio).</span><span class="sxs-lookup"><span data-stu-id="3cc38-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="3cc38-105">Dependendo das suas necessidades, você precisará do seguinte:</span><span class="sxs-lookup"><span data-stu-id="3cc38-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="3cc38-106">Um registro DNS interno para dar suporte a usuários móveis que estão se conectando dentro da rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3cc38-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="3cc38-107">Um registro DNS externo ou público para dar suporte a usuários móveis que estão se conectando pela Internet</span><span class="sxs-lookup"><span data-stu-id="3cc38-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="3cc38-108">Por que ambos?</span><span class="sxs-lookup"><span data-stu-id="3cc38-108">Why both?</span></span> <span data-ttu-id="3cc38-109">Você precisa criar um registro DNS interno e um registro DNS externo para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="3cc38-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="3cc38-110">Os registros DNS que você cria podem ser registros (host) ou registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="3cc38-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="3cc38-111">Para ajudá-lo, vamos examinar como criar esses registros DNS internos e externos abaixo.</span><span class="sxs-lookup"><span data-stu-id="3cc38-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="3cc38-112">Se você precisar fazer mais informações sobre os requisitos de DNS para usuários móveis, confira [os requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="3cc38-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="3cc38-113">Criando um registro CNAME DNS interno</span><span class="sxs-lookup"><span data-stu-id="3cc38-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="3cc38-114">Para criar um registro DNS interno, você precisará fazer logon em um servidor DNS na sua rede com uma conta de domínio que seja membro do grupo Domain admins ou um membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="3cc38-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="3cc38-115">Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas administrativas**e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="3cc38-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="3cc38-116">Na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para o domínio do Active Directory onde o pool de directors do Lync Server 2013 e o pool de front-end estão instalados.</span><span class="sxs-lookup"><span data-stu-id="3cc38-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="3cc38-117">(por exemplo, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3cc38-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="3cc38-118">Verifique se há um registro de host A (AAAA para IPv6) para o seu pool de directors para um registro DNS interno, deve haver um registro de host a para o nome de domínio totalmente qualificado dos serviços Web internos (FQDN) do seu pool de diretor (por exemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3cc38-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="3cc38-119">Se não estiver aqui, você pode não estar usando um pool de directors, e você precisará usar o FQDN para o seu pool Front-end ou mesmo para um único FQDN do servidor, se for a sua configuração.</span><span class="sxs-lookup"><span data-stu-id="3cc38-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="3cc38-120">Lembre-se disso, verifique e veja se existe um registro do host A (AAAA para IPv6) para o seu pool de front-end para um registro DNS interno, um registro de host A (ou AAAA) deve existir para o FQDN de serviços Web internos do seu pool de front-ends (por exemplo, , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3cc38-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="3cc38-121">Se não tiver, você precisará anotar o FQDN do servidor front-end ou do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3cc38-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="3cc38-122">Quando souber o que os registros do host A (ou AAAA) existem, na árvore de console do seu servidor DNS, expanda as **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3cc38-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="3cc38-123">Clique com o botão direito do mouse no nome do domínio SIP e, em seguida, clique em **novo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="3cc38-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="3cc38-124">Em **nome do alias**, digite lyncdiscoverinternal como o nome do host para a URL do serviço de descoberta automática interna.</span><span class="sxs-lookup"><span data-stu-id="3cc38-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="3cc38-125">Em **nome de domínio totalmente qualificado (FQDN) para o host de destino**, digite ou navegue até o FQDN de serviços Web internos para o seu pool de diretor (por exemplo, lyncwebdir01. contoso. local) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cc38-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="3cc38-126">Você deve criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP ao qual você dá suporte no ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc38-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="3cc38-127">Criando um registro CNAME DNS externo</span><span class="sxs-lookup"><span data-stu-id="3cc38-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="3cc38-128">Para criar um registro CNAME DNS externo, você precisará se conectar ao seu provedor de DNS público e seguir nossas etapas.</span><span class="sxs-lookup"><span data-stu-id="3cc38-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="3cc38-129">Não podemos descrever exatamente onde você está no ambiente do seu provedor DNS, pois pode haver diferentes maneiras de gerenciar seu DNS externo, mas esperamos que estas etapas ajudem.</span><span class="sxs-lookup"><span data-stu-id="3cc38-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="3cc38-130">Conecte-se ao seu provedor de DNS externo com uma conta que possa criar registros de DNS nesse ambiente.</span><span class="sxs-lookup"><span data-stu-id="3cc38-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="3cc38-131">Você já deve ter um domínio SIP criado para esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="3cc38-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="3cc38-132">Expanda a **zona de pesquisa direta** para este domínio SIP ou selecione-o, dependendo da interface DNS externa sendo usada.</span><span class="sxs-lookup"><span data-stu-id="3cc38-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="3cc38-133">Você já deve ver um registro do host A (AAAA para IPv6) para o seu pool de diretor (como lyncwebexdir01.contoso.com), portanto, confirme se ele está lá.</span><span class="sxs-lookup"><span data-stu-id="3cc38-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="3cc38-134">Se não for, você pode não estar usando um pool de directors.</span><span class="sxs-lookup"><span data-stu-id="3cc38-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="3cc38-135">Se for esse o caso, você precisará usar o FQDN do seu pool Front-end, ou se estiver fazendo isso para um único servidor, para o servidor front-end ou o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3cc38-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="3cc38-136">Você também precisará confirmar que um registro do host A (AAAA para IPv6) existe para o seu nome de domínio totalmente qualificado dos serviços Web (FQDN) do seu pool Front-end (como lyncwebextpool01.contoso.com) ou um FQDN para o FQDN do servidor único, se você não tiver um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="3cc38-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="3cc38-137">Conforme observado na etapa anterior, você precisará disso abaixo se não tiver um pool de directors.</span><span class="sxs-lookup"><span data-stu-id="3cc38-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="3cc38-138">Agora, no formato apropriado para seu provedor de DNS externo, escolha a opção para criar um **novo alias (CNAME)** (isso pode ser uma opção de menu ou um link, dependendo do formato do provedor de DNS).</span><span class="sxs-lookup"><span data-stu-id="3cc38-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="3cc38-139">Deve haver alguma forma de caixa de texto **nome do alias** , como com o DNS interno, você deve digitar lyncdiscover como o nome do host para a URL do serviço de descoberta automática externa.</span><span class="sxs-lookup"><span data-stu-id="3cc38-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="3cc38-140">Também deve haver uma forma de um **FQDN (nome de domínio totalmente qualificado) para a caixa de texto de host de destino** , aqui você irá inserir o FQDN de serviços Web externos para o seu pool de diretor (por exemplo, lyncwebexdir01.contoso.com) e clicar em OK ou levar o que for ação no DNS externo para aceitar a criação dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="3cc38-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="3cc38-141">Conforme observado na etapa 4, acima, se você não tiver um pool de directors, será necessário usar o FQDN do pool de front-end ou o FQDN do servidor único que você configurou, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="3cc38-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="3cc38-142">Você precisará criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc38-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="3cc38-143">Criando um registro DNS interno A</span><span class="sxs-lookup"><span data-stu-id="3cc38-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="3cc38-144">Para criar um registro DNS interno, faça logon em um servidor DNS na sua rede com uma conta de domínio que seja membro do grupo Domain admins ou um membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="3cc38-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="3cc38-145">Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas administrativas**e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="3cc38-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="3cc38-146">Para um registro DNS interno, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para o seu domínio do Active Directory (por exemplo, contoso. local) onde o pool de directors do Lync Server 2013 e o pool de front-ends estão instalados.</span><span class="sxs-lookup"><span data-stu-id="3cc38-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="3cc38-147">Verifique se há um registro de host A (AAAA para IPv6) para o seu pool de directors para um registro DNS interno, deve haver um registro de host a para o nome de domínio totalmente qualificado dos serviços Web internos (FQDN) do seu pool de diretor (por exemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3cc38-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="3cc38-148">Se não estiver aqui, você pode não estar usando um pool de directors, e você precisará usar o endereço IP do seu pool Front-end ou até mesmo um único endereço IP de servidor, se for a sua configuração.</span><span class="sxs-lookup"><span data-stu-id="3cc38-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="3cc38-149">Lembre-se disso, verifique e veja se existe um registro do host A (AAAA para IPv6) para o seu pool de front-end para um registro DNS interno, um registro de host A (ou AAAA) deve existir para o FQDN de serviços Web internos do seu pool de front-ends (por exemplo, , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3cc38-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="3cc38-150">Se não tiver, você precisará anotar o endereço IP do servidor front-end ou do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3cc38-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="3cc38-151">Quando souber o que os registros do host A (ou AAAA) existem, na árvore de console do seu servidor DNS, expanda as **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3cc38-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="3cc38-152">Clique com o botão direito do mouse no nome do domínio SIP e clique em **novo host (A ou aaaa)**.</span><span class="sxs-lookup"><span data-stu-id="3cc38-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="3cc38-153">Em **nome**, digite lyncdiscoverinternal como o nome do host para a URL do serviço de descoberta automática interna.</span><span class="sxs-lookup"><span data-stu-id="3cc38-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="3cc38-154">Em **endereço IP**, digite o endereço IP dos serviços Web internos do diretor (ou, se você usar um balanceador de carga, digite o IP virtual (VIP) do balanceador de carga do diretor).</span><span class="sxs-lookup"><span data-stu-id="3cc38-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="3cc38-155">Conforme observado na etapa 4 acima, se você não estiver usando um director, talvez seja necessário inserir o endereço IP do servidor front-end ou o servidor Standard Edition ou, se você usar um balanceador de carga, digite o VIP do balanceador de carga do pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="3cc38-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="3cc38-156">Clique em **Adicionar host**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cc38-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="3cc38-157">Para criar um registro adicional ou AAAA, repita as etapas de 8 a 10, lembrando-se de que você precisará criar novos registros de descoberta automática ou AAAA na zona de pesquisa direta de cada domínio SIP com suporte no ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc38-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="3cc38-158">Quando terminar de criar os registros (para IPv6, AAAA), clique em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="3cc38-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="3cc38-159">Criando um registro DNS externo</span><span class="sxs-lookup"><span data-stu-id="3cc38-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="3cc38-160">Para criar um registro DNS externo, conecte-se ao seu provedor de DNS público e siga nossas etapas.</span><span class="sxs-lookup"><span data-stu-id="3cc38-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="3cc38-161">Não podemos descrever exatamente onde você está no ambiente do seu provedor DNS, pois pode haver diferentes maneiras de gerenciar seu DNS externo, mas esperamos que estas etapas ajudem.</span><span class="sxs-lookup"><span data-stu-id="3cc38-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="3cc38-162">Você precisará estar conectado como uma conta que pode criar registros DNS nesse ambiente.</span><span class="sxs-lookup"><span data-stu-id="3cc38-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="3cc38-163">Para um registro DNS externo, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3cc38-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="3cc38-164">Para um registro DNS externo, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3cc38-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="3cc38-165">Você já deve ver um registro do host A (AAAA para IPv6) para o seu pool de diretor (como lyncwebexdir01.contoso.com), portanto, confirme se ele está lá e o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="3cc38-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="3cc38-166">Se não for, você pode não estar usando um pool de directors.</span><span class="sxs-lookup"><span data-stu-id="3cc38-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="3cc38-167">Se for esse o caso, você precisará usar o endereço IP do seu pool de front-end ou, se estiver fazendo isso para um único servidor, para o servidor front-end ou o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3cc38-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="3cc38-168">Lembre-se de que seus servidores também podem estar atrás de um balanceador de carga ou usando um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="3cc38-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="3cc38-169">Anote os endereços IP também para seguir as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="3cc38-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="3cc38-170">Você também precisará confirmar que um registro do host A (AAAA para IPv6) existe para o nome de domínio totalmente qualificado de seus serviços Web (FQDN) para seu pool de front-end (como lyncwebextpool01.contoso.com) ou um endereço IP para a instalação do Lync de servidor único se você Não tem um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="3cc38-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="3cc38-171">Conforme observado na etapa anterior, você precisará disso abaixo se não tiver um pool de directors.</span><span class="sxs-lookup"><span data-stu-id="3cc38-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="3cc38-172">Agora, no formato apropriado para seu provedor de DNS externo, escolha a opção para criar um **novo host a ou aaaa** (isso pode ser uma opção de menu ou um link, dependendo do formato do provedor de DNS).</span><span class="sxs-lookup"><span data-stu-id="3cc38-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="3cc38-173">Deve haver um local para inserir um **nome**, digite lyncdiscover como o nome do host para a URL do serviço de descoberta automática externa.</span><span class="sxs-lookup"><span data-stu-id="3cc38-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="3cc38-174">Também deve haver uma caixa de texto de **endereço IP** , aqui está onde você digitará o IP para o seu pool de diretor (por exemplo, lyncwebexdir01.contoso.com) ou o IP do balanceador de carga do pool (ou um IP de proxy reverso que leva ao mesmo) e, em seguida, clique em OK ou execute qualquer ação no DNS externo para aceitar a criação dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="3cc38-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="3cc38-175">Conforme observado na etapa 4, acima, se você não tiver um pool de directors, será necessário usar o endereço IP do pool de front-end ou o endereço IP do servidor único que você configurou, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="3cc38-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="3cc38-176">Você precisará criar um novo registro de descoberta automática A ou AAAA na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3cc38-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

