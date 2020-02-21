---
title: 'Lync Server 2013: criar registros DNS para o serviço de descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 921db63f02be50866e6d26cb33007ac8ddbb32eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="e069c-102">Criar registros DNS para o serviço de descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e069c-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e069c-103">_**Última modificação do tópico:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="e069c-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="e069c-104">Seus usuários móveis do Lync precisarão que você habilite a descoberta automática e uma parte dele envolve a criação de alguns registros de DNS (sistema de nomes de domínio).</span><span class="sxs-lookup"><span data-stu-id="e069c-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="e069c-105">Dependendo das suas necessidades, você precisará do seguinte:</span><span class="sxs-lookup"><span data-stu-id="e069c-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="e069c-106">Um registro DNS interno para dar suporte a usuários móveis que estão se conectando dentro da rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e069c-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="e069c-107">Um registro DNS externo ou público para suportar usuários móveis que estão se conectando a partir da Internet</span><span class="sxs-lookup"><span data-stu-id="e069c-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="e069c-108">Por que ambos?</span><span class="sxs-lookup"><span data-stu-id="e069c-108">Why both?</span></span> <span data-ttu-id="e069c-109">Você precisa criar um registro de DNS interno e um registro de DNS externo para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="e069c-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="e069c-110">Os registros DNS que você cria podem ser registros A (host) ou registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="e069c-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="e069c-111">Para ajudá-lo, vamos examinar como criar esses registros de DNS internos e externos abaixo.</span><span class="sxs-lookup"><span data-stu-id="e069c-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="e069c-112">Se você precisar fazer mais leituras sobre os requisitos de DNS para usuários móveis, confira [os requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="e069c-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="e069c-113">Criando um registro CNAME de DNS interno</span><span class="sxs-lookup"><span data-stu-id="e069c-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="e069c-114">Para criar um registro DNS interno, você precisará fazer logon em um servidor DNS na sua rede com uma conta de domínio que seja membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="e069c-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="e069c-115">Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas Administrativas** e **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e069c-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="e069c-116">Na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para o domínio do Active Directory onde o pool de diretores do Lync Server 2013 e o pool de front-ends estão instalados.</span><span class="sxs-lookup"><span data-stu-id="e069c-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="e069c-117">(por exemplo, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e069c-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="e069c-118">Verifique se existe um registro de host A (AAAA para IPv6) para o pool de diretores de um registro de DNS interno, um registro de host A deve existir para o FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para seu pool de diretores (por exemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e069c-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="e069c-119">Se ele não estiver aqui, talvez você não esteja usando um pool de diretores e você precisará usar o FQDN para seu pool de front-ends ou até mesmo um único FQDN de servidor, se essa for sua configuração.</span><span class="sxs-lookup"><span data-stu-id="e069c-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="e069c-120">Tendo isso em mente, verifique se existe um registro de host A (AAAA para IPv6) para o seu pool de front-ends de um registro de DNS interno, um registro de host A (ou AAAA) deve existir para o FQDN de serviços Web internos do seu pool de front-ends (por exemplo, , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e069c-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="e069c-121">Caso contrário, você precisará anotar o FQDN do servidor front-end ou do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e069c-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="e069c-122">Quando você souber quais registros de host A (ou AAAA) existem, na árvore de console do seu servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e069c-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="e069c-123">Clique com o botão direito no nome do domínio SIP e em **Novo Alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="e069c-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="e069c-124">Em **nome do alias**, digite lyncdiscoverinternal como o nome do host para a URL interna do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e069c-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="e069c-125">Em **nome de domínio totalmente qualificado (FQDN) para o host de destino**, digite ou procure o FQDN dos serviços Web internos para o seu pool de diretores (por exemplo, lyncwebdir01. contoso. local) e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e069c-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="e069c-126">Você deve criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e069c-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="e069c-127">Criando um registro CNAME de DNS externo</span><span class="sxs-lookup"><span data-stu-id="e069c-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="e069c-128">Para criar um registro CNAME de DNS externo, você precisará se conectar ao seu provedor de DNS público e seguir as etapas.</span><span class="sxs-lookup"><span data-stu-id="e069c-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="e069c-129">Não é possível descrever exatamente onde você está no ambiente de seu provedor de DNS, já que pode haver maneiras diferentes de gerenciar seu DNS externo, mas esperamos que essas etapas ajudem.</span><span class="sxs-lookup"><span data-stu-id="e069c-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="e069c-130">Faça logon no provedor de DNS externo com uma conta que possa criar registros DNS nesse ambiente.</span><span class="sxs-lookup"><span data-stu-id="e069c-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="e069c-131">Você já deve ter um domínio SIP criado para esse ambiente.</span><span class="sxs-lookup"><span data-stu-id="e069c-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="e069c-132">Expanda a **zona de pesquisa direta** para este domínio SIP ou selecione-a, dependendo da interface DNS externa que está sendo usada.</span><span class="sxs-lookup"><span data-stu-id="e069c-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="e069c-133">Você já deve ter um registro de host A (AAAA para IPv6) para o seu pool de diretores (como lyncwebexdir01.contoso.com), portanto, confirme se ele está lá.</span><span class="sxs-lookup"><span data-stu-id="e069c-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="e069c-134">Caso contrário, talvez você não esteja usando um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="e069c-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="e069c-135">Se esse for o caso, você precisará usar o FQDN do seu pool de front-ends ou se estiver fazendo isso para um único servidor, para o servidor front-end ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e069c-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="e069c-136">Você também precisará confirmar se um registro de host A (AAAA para IPv6) existe para o nome de domínio totalmente qualificado (FQDN) dos serviços Web externos para seu pool de front-ends (como lyncwebextpool01.contoso.com) ou um FQDN para o FQDN de servidor único, se não houver pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e069c-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="e069c-137">Conforme observado na etapa anterior, você precisará disso, se não tiver um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="e069c-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="e069c-138">Agora, no formato apropriado para seu provedor de DNS externo, escolha a opção para criar um **novo alias (CNAME)** (isso pode ser uma opção de menu ou um link, dependendo do formato do provedor de DNS).</span><span class="sxs-lookup"><span data-stu-id="e069c-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="e069c-139">Deve haver alguma forma de caixa de texto **nome do alias** como com o DNS interno, você deve inserir lyncdiscover como o nome do host para a URL externa do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e069c-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="e069c-140">Também deve haver alguma forma de um **FQDN (nome de domínio totalmente qualificado) para** a caixa de texto host de destino, aqui, onde você inserirá o FQDN de serviços Web externos para o seu pool de diretores (por exemplo, lyncwebexdir01.contoso.com) e clicará em OK ou executará qualquer ação no DNS externo para aceitar a criação dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="e069c-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="e069c-141">Conforme observado na etapa 4, acima, se você não tiver um pool de diretores, será necessário usar o FQDN do pool de front-ends ou o FQDN do servidor único que você configurou, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="e069c-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="e069c-142">Você precisará criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP suportado em seu ambiente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e069c-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="e069c-143">Criando um registro de DNS interno</span><span class="sxs-lookup"><span data-stu-id="e069c-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="e069c-144">Para criar um registro DNS interno, faça logon em um servidor DNS da sua rede com uma conta de domínio que seja membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="e069c-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="e069c-145">Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas Administrativas** e **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e069c-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="e069c-146">Para um registro DNS interno, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio do Active Directory (por exemplo, contoso. local) onde o pool de diretor do Lync Server 2013 e o pool de front-ends estão instalados.</span><span class="sxs-lookup"><span data-stu-id="e069c-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="e069c-147">Verifique se existe um registro de host A (AAAA para IPv6) para o pool de diretores de um registro de DNS interno, um registro de host A deve existir para o FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para seu pool de diretores (por exemplo, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e069c-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="e069c-148">Se ele não estiver aqui, talvez você não esteja usando um pool de diretores e você precisará usar o endereço IP para seu pool de front-ends ou mesmo um endereço IP de servidor único, se essa for sua configuração.</span><span class="sxs-lookup"><span data-stu-id="e069c-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="e069c-149">Tendo isso em mente, verifique se existe um registro de host A (AAAA para IPv6) para o seu pool de front-ends de um registro de DNS interno, um registro de host A (ou AAAA) deve existir para o FQDN de serviços Web internos do seu pool de front-ends (por exemplo, , lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="e069c-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="e069c-150">Caso contrário, você precisará anotar o endereço IP do servidor front-end ou do servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e069c-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="e069c-151">Quando você souber quais registros de host A (ou AAAA) existem, na árvore de console do seu servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e069c-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="e069c-152">Clique com o botão direito no nome do domínio SIP e em **Novo Host (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="e069c-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="e069c-153">Em **nome**, digite lyncdiscoverinternal como o nome do host para a URL interna do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e069c-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="e069c-154">Em **endereço IP**, digite o endereço IP do serviço Web interno do diretor (ou, se você usar um balanceador de carga, digite o IP virtual (VIP) do balanceador de carga do diretor).</span><span class="sxs-lookup"><span data-stu-id="e069c-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="e069c-155">Conforme observado na etapa 4 acima, se você não estiver usando um diretor, talvez seja necessário inserir o endereço IP do servidor front-end ou servidor Standard Edition ou, se você usar um balanceador de carga, digite o VIP do balanceador de carga do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e069c-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="e069c-156">Clique em **Adicionar Host** e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e069c-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="e069c-157">Para criar um registro A ou AAAA adicional, repita as etapas de 8 a 10, lembrando que você precisará criar novos registros de descoberta automática ou AAAA na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e069c-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="e069c-158">Quando terminar de criar os registros A (para IPv6, AAAA), clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e069c-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="e069c-159">Criando um registro de DNS externo</span><span class="sxs-lookup"><span data-stu-id="e069c-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="e069c-160">Para criar um registro de DNS externo, conecte-se ao seu provedor de DNS público e siga nossas etapas.</span><span class="sxs-lookup"><span data-stu-id="e069c-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="e069c-161">Não é possível descrever exatamente onde você está no ambiente de seu provedor de DNS, já que pode haver maneiras diferentes de gerenciar seu DNS externo, mas esperamos que essas etapas ajudem.</span><span class="sxs-lookup"><span data-stu-id="e069c-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="e069c-162">Você precisará estar conectado como uma conta que pode criar registros DNS nesse ambiente.</span><span class="sxs-lookup"><span data-stu-id="e069c-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="e069c-163">Para um registro de DNS externo, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e069c-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="e069c-164">Para um registro de DNS externo, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e069c-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="e069c-165">Você já deve ter um registro de host A (AAAA para IPv6) para o seu pool de diretores (como lyncwebexdir01.contoso.com), portanto, confirme se ele está lá e o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="e069c-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="e069c-166">Caso contrário, talvez você não esteja usando um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="e069c-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="e069c-167">Se esse for o caso, você precisará usar o endereço IP do seu pool de front-ends ou se estiver fazendo isso para um único servidor, para o servidor front-end ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e069c-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="e069c-168">Tenha em mente que seus servidores também podem estar atrás de um balanceador de carga ou usando um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="e069c-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="e069c-169">Anote os endereços IP também para seguir as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="e069c-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="e069c-170">Você também precisará confirmar se um registro de host A (AAAA para IPv6) existe para seu nome de domínio totalmente qualificado (FQDN) dos serviços Web externos para seu pool de front-ends (como lyncwebextpool01.contoso.com) ou um endereço IP para a sua instalação do Lync de servidor único se você Não têm pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e069c-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="e069c-171">Conforme observado na etapa anterior, você precisará disso, se não tiver um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="e069c-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="e069c-172">Agora, no formato apropriado para seu provedor de DNS externo, escolha a opção para criar um **novo host a ou aaaa** (isso pode ser uma opção de menu ou um link, dependendo do formato do provedor de DNS).</span><span class="sxs-lookup"><span data-stu-id="e069c-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="e069c-173">Deve haver um local para inserir um **nome**, digite lyncdiscover como o nome do host para a URL externa do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="e069c-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="e069c-174">Também deve haver uma caixa de texto de **endereço IP** , aqui, onde você inserirá o IP para o seu pool de diretores (por exemplo, lyncwebexdir01.contoso.com) ou, possivelmente, o IP do balanceador de carga do pool (ou um IP de proxy reverso que leva ao mesmo) e clique em OK ou executar qualquer ação no DNS externo para aceitar a criação dessa entrada.</span><span class="sxs-lookup"><span data-stu-id="e069c-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="e069c-175">Conforme observado na etapa 4, acima, se você não tiver um pool de diretores, será necessário usar o endereço IP do pool de front-ends ou o endereço IP do servidor único que você configurou, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="e069c-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="e069c-176">Você precisará criar um novo registro de descoberta automática ou AAAA na zona de pesquisa direta de cada domínio SIP suportado em seu ambiente do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="e069c-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

