---
title: 'Lync Server 2013: requisitos de DNS para entrada automática do cliente'
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
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="674ff-102">Requisitos de DNS para entrada automática do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="674ff-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="674ff-103">_**Tópico da última modificação:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="674ff-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="674ff-104">Esta seção explica os registros de sistema de nome de domínio (DNS) necessários para a entrada automática do cliente.</span><span class="sxs-lookup"><span data-stu-id="674ff-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="674ff-105">Ao implantar seus servidores Standard Edition ou pools front-end, você pode configurar seus clientes para usar a descoberta automática para entrar no servidor padrão da edição ou no pool de front-end apropriado.</span><span class="sxs-lookup"><span data-stu-id="674ff-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="674ff-106">Se você planeja exigir que seus clientes se conectem manualmente ao Lync Server 2013, poderá ignorar este tópico.</span><span class="sxs-lookup"><span data-stu-id="674ff-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="674ff-107">Para dar suporte à entrada automática do cliente, você deve:</span><span class="sxs-lookup"><span data-stu-id="674ff-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="674ff-108">Designe um único servidor ou pool para distribuir e autenticar solicitações de entrada do cliente.</span><span class="sxs-lookup"><span data-stu-id="674ff-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="674ff-109">Pode ser um servidor ou pool existente em sua organização que hospeda usuários ou você pode designar um servidor ou pool dedicado para essa finalidade que não hospede usuários.</span><span class="sxs-lookup"><span data-stu-id="674ff-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="674ff-110">Para alta disponibilidade, recomendamos que você designe um pool de front-ends para essa função.</span><span class="sxs-lookup"><span data-stu-id="674ff-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="674ff-111">Crie um registro SRV DNS interno para dar suporte à entrada automática do cliente para este servidor ou pool.</span><span class="sxs-lookup"><span data-stu-id="674ff-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="674ff-112">Nos seguintes requisitos de registro, o domínio SIP refere-se à porção host dos URIs SIP atribuídos aos usuários.</span><span class="sxs-lookup"><span data-stu-id="674ff-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="674ff-113">Por exemplo, se URIs SIP forem do formato \* @contoso. com, contoso.com será o domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="674ff-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="674ff-114">O domínio SIP muitas vezes é diferente do domínio interno do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="674ff-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="674ff-115">Uma organização também pode dar suporte a vários domínios SIP.</span><span class="sxs-lookup"><span data-stu-id="674ff-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="674ff-116">Para habilitar a configuração automática para seus clientes, você deve criar um registro SRV DNS interno que mapeie um dos seguintes registros para o nome de domínio totalmente qualificado (FQDN) do pool de front-ends ou do servidor Standard Edition que distribui solicitações de entrada do Lync clientes</span><span class="sxs-lookup"><span data-stu-id="674ff-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="674ff-117">\_sipinternaltls. \_TCP. \<domínio\> – para conexões de TLS internas</span><span class="sxs-lookup"><span data-stu-id="674ff-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="674ff-118">Você só precisa criar um único registro SRV para o pool de front-end ou o servidor Standard Edition, ou isso distribuirá solicitações de entrada.</span><span class="sxs-lookup"><span data-stu-id="674ff-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="674ff-119">A tabela a seguir mostra alguns exemplos de registros necessários para a contoso da empresa fictícia, que oferece suporte a domínios SIP do contoso.com e do retail.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="674ff-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="674ff-120">Exemplo de registros DNS necessários para a entrada automática do cliente com vários domínios SIP</span><span class="sxs-lookup"><span data-stu-id="674ff-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="674ff-121">FQDN do pool de front-end usado para distribuir solicitações de entrada</span><span class="sxs-lookup"><span data-stu-id="674ff-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="674ff-122">Domínio SIP</span><span class="sxs-lookup"><span data-stu-id="674ff-122">SIP domain</span></span></th>
<th><span data-ttu-id="674ff-123">Registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="674ff-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="674ff-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="674ff-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="674ff-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="674ff-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="674ff-126">Um registro SRV para o domínio _sipinternaltls. _tcp. contoso. com na porta 5061 que mapeia para pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="674ff-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="674ff-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="674ff-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="674ff-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="674ff-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="674ff-129">Um registro SRV para o domínio _sipinternaltls. _tcp. Retail. contoso. com na porta 5061 que mapeia para pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="674ff-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="674ff-130">Por padrão, as consultas de registros DNS aderem à correspondência de nome de domínio estrito entre o domínio no nome de usuário e o registro SRV.</span><span class="sxs-lookup"><span data-stu-id="674ff-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="674ff-131">Se você preferir que as consultas DNS do cliente usem a correspondência de sufixo em vez disso, você pode configurar a política de grupo DisableStrictDNSNaming.</span><span class="sxs-lookup"><span data-stu-id="674ff-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="674ff-132">Para obter detalhes, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">planejando para clientes e dispositivos no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="674ff-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="674ff-133">Exemplo dos certificados e dos registros DNS necessários para a entrada automática do cliente</span><span class="sxs-lookup"><span data-stu-id="674ff-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="674ff-134">Este exemplo usa os mesmos nomes de exemplo na tabela anterior.</span><span class="sxs-lookup"><span data-stu-id="674ff-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="674ff-135">A organização Contoso suporta os domínios SIP do contoso.com e do retail.contoso.com, e todos os seus usuários têm um URI SIP em um dos seguintes formatos:</span><span class="sxs-lookup"><span data-stu-id="674ff-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="674ff-136">\<usuário\>@retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="674ff-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="674ff-137">\<usuário\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="674ff-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

