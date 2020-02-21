---
title: 'Lync Server 2013: requisitos de DNS para entrada automática de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e49d50173439e36bd5bb7f35f668837fe04b46b7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="ce3a0-102">Requisitos de DNS para entrada de cliente automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce3a0-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce3a0-103">_**Última modificação do tópico:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ce3a0-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ce3a0-104">Esta seção explica os registros do DNS (Sistema de Nomes de Domínio) que são necessários para entrada automática de clientes.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="ce3a0-105">Quando você implanta servidores Standard Edition ou pools de Front-Ends, é possível configurar os clientes para que eles usem a descoberta automática para entrar no servidor Standard Edition ou no pool Front-End.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="ce3a0-106">Se você planeja exigir que seus clientes se conectem manualmente ao Lync Server 2013, você pode ignorar este tópico.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="ce3a0-107">Para dar suporte à entrada automática de clientes, você deve:</span><span class="sxs-lookup"><span data-stu-id="ce3a0-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="ce3a0-p102">Designar um único servidor ou pool para distribuir e autenticar as solicitações de entrada dos clientes. Ele pode ser um servidor ou pool existente em sua organização que hospede usuários, ou você pode designar para essa finalidade um servidor ou pool dedicado que não hospede usuários. Para que haja alta disponibilidade, recomendamos que você designe um pool Front-End para essa função.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="ce3a0-111">Criar um registro SRV de DNS interno para dar suporte à entrada automática de clientes nesse servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ce3a0-p103">Nos requisitos de registro a seguir, o domínio SIP se refere à parte de host dos URIs do SIP atribuídos aos usuários. Por exemplo, se os URIs do SIP estiverem no formato \*@contoso.com, contoso.com será o domínio SIP. O domínio SIP é geralmente diferente do domínio interno do Active Directory. Uma organização também poderá oferecer suporte a vários domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="ce3a0-116">Para habilitar a configuração automática para seus clientes, você deve criar um registro SRV de DNS interno que mapeia um dos seguintes registros para o nome de domínio totalmente qualificado (FQDN) do pool de front-ends ou servidor Standard Edition que distribui solicitações de entrada do Lync nos</span><span class="sxs-lookup"><span data-stu-id="ce3a0-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="ce3a0-117">\_sipinternaltls. \_TCP. \<domínio\> -para conexões TLS internas</span><span class="sxs-lookup"><span data-stu-id="ce3a0-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="ce3a0-118">Você só precisa criar um único registro SRV para o pool Front-End ou servidor Standard Edition que distribuirá as solicitações de entrada.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="ce3a0-119">A tabela a seguir mostra alguns exemplos de registros necessários para a empresa fictícia Contoso, que oferece suporte aos domínios SIP contoso.com e retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="ce3a0-120">Exemplo de registros DNS necessários para entrada automática de clientes com vários domínios SIP</span><span class="sxs-lookup"><span data-stu-id="ce3a0-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce3a0-121">FQDN do pool Front-End usado para distribuir solicitações de entrada</span><span class="sxs-lookup"><span data-stu-id="ce3a0-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="ce3a0-122">Domínio SIP</span><span class="sxs-lookup"><span data-stu-id="ce3a0-122">SIP domain</span></span></th>
<th><span data-ttu-id="ce3a0-123">Registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="ce3a0-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce3a0-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce3a0-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ce3a0-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce3a0-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ce3a0-126">Um registro SRV para o domínio _sipinternaltls._tcp.contoso.com através da porta 5061 que mapeie para pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce3a0-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce3a0-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce3a0-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ce3a0-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce3a0-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ce3a0-129">Um registro SRV para o domínio _sipinternaltls._tcp.retail.contoso.com através da porta 5061 que mapeie para pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce3a0-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="ce3a0-130">Por padrão, as consultas de registros DNS seguem uma correspondência estrita de nomes de domínio entre o domínio no nome do usuário e o registro SRV.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="ce3a0-131">Se, em vez disso, você preferir que as consultas de DNS dos clientes usem a correspondência de sufixo, poderá configurar a política de grupo DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="ce3a0-132">Para obter detalhes, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ce3a0-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="ce3a0-133">Exemplo dos certificados e dos registros DNS necessários para a entrada automática de clientes</span><span class="sxs-lookup"><span data-stu-id="ce3a0-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="ce3a0-p105">Esse exemplo usa os mesmos nomes de exemplo da tabela anterior. A organização Contoso oferece suporte aos domínios SIP contoso.com e retail.contoso.com, e todos os seus usuários têm um URI do SIP em um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="ce3a0-p105">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="ce3a0-136">\<@retail\>de usuário. contoso.com</span><span class="sxs-lookup"><span data-stu-id="ce3a0-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="ce3a0-137">\<usuário\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="ce3a0-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

