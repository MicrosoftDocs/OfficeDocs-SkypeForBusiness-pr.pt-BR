---
title: 'Lync Server 2013: requisitos de DNS para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb933e20b8da627ad48a30802ff86c7ed95faff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="5857e-102">Requisitos de DNS para mobilidade com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5857e-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5857e-103">_**Tópico da última modificação:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="5857e-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="5857e-104">Ao implantar o recurso de mobilidade do Lync Server 2013, você pode usar as novas URLs disponíveis com o serviço de descoberta automática do Microsoft Lync Server 2013 ou pode usar suas URLs de serviços Web existentes.</span><span class="sxs-lookup"><span data-stu-id="5857e-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="5857e-105">Se você usar suas URLs existentes, os usuários precisarão inserir manualmente as URLs nas configurações do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="5857e-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="5857e-106">Essa opção geralmente é usada para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="5857e-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="5857e-107">Quando você usa as novas URLs, os clientes móveis podem descobrir automaticamente os recursos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5857e-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="5857e-108">Ao oferecer suporte à descoberta automática, você precisa adicionar novos registros de sistema de nome de domínio (DNS).</span><span class="sxs-lookup"><span data-stu-id="5857e-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="5857e-109">Esta seção descreve os registros DNS necessários para a descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="5857e-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="5857e-110">Para dar suporte à descoberta automática, você precisa criar os seguintes registros DNS para cada domínio SIP:</span><span class="sxs-lookup"><span data-stu-id="5857e-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="5857e-111">Um registro DNS interno para dar suporte a usuários móveis que se conectam dentro da rede da sua organização</span><span class="sxs-lookup"><span data-stu-id="5857e-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="5857e-112">Um registro DNS externo ou público para dar suporte a usuários móveis que se conectam à Internet</span><span class="sxs-lookup"><span data-stu-id="5857e-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="5857e-113">A URL de descoberta automática interna não deve ser endereçável de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="5857e-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="5857e-114">A URL de descoberta automática externa não deve ser endereçada dentro da sua rede.</span><span class="sxs-lookup"><span data-stu-id="5857e-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="5857e-115">No entanto, se você não puder atender a esse requisito para a URL externa, a funcionalidade do cliente móvel não deve ser afetada.</span><span class="sxs-lookup"><span data-stu-id="5857e-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="5857e-116">Os registros DNS podem ser registros CNAME ou registros (host).</span><span class="sxs-lookup"><span data-stu-id="5857e-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="5857e-117">**Registros DNS internos**</span><span class="sxs-lookup"><span data-stu-id="5857e-117">**Internal DNS records**</span></span>

<span data-ttu-id="5857e-118">Você precisa criar um dos seguintes registros de DNS interno:</span><span class="sxs-lookup"><span data-stu-id="5857e-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5857e-119">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="5857e-119">Record type</span></span></th>
<th><span data-ttu-id="5857e-120">Nome do host ou definição de SRV</span><span class="sxs-lookup"><span data-stu-id="5857e-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="5857e-121">Resolve para</span><span class="sxs-lookup"><span data-stu-id="5857e-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5857e-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="5857e-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="5857e-123">lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5857e-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="5857e-124">FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para o seu pool de directors, se você tiver um ou para o seu pool de front-end se não tiver um director</span><span class="sxs-lookup"><span data-stu-id="5857e-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5857e-125">A (host)</span><span class="sxs-lookup"><span data-stu-id="5857e-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="5857e-126">lyncdiscoverinternal. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5857e-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="5857e-127">Endereço IP interno dos serviços Web (VIP) se você usar um balanceador de carga) do seu pool de director, se você tiver um ou do seu pool Front-End se não tiver um director</span><span class="sxs-lookup"><span data-stu-id="5857e-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5857e-128">**Registros DNS externos**</span><span class="sxs-lookup"><span data-stu-id="5857e-128">**External DNS records**</span></span>

<span data-ttu-id="5857e-129">Você precisa criar um dos seguintes registros de DNS externo:</span><span class="sxs-lookup"><span data-stu-id="5857e-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5857e-130">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="5857e-130">Record type</span></span></th>
<th><span data-ttu-id="5857e-131">Nome do host</span><span class="sxs-lookup"><span data-stu-id="5857e-131">Host name</span></span></th>
<th><span data-ttu-id="5857e-132">Resolve para</span><span class="sxs-lookup"><span data-stu-id="5857e-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5857e-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="5857e-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="5857e-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="5857e-134">lyncdiscover.</span></span> <span data-ttu-id="5857e-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5857e-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="5857e-136">FQDN de serviços Web externos para o seu pool de directors, se você tiver um ou para o seu pool de front-end se não tiver um director</span><span class="sxs-lookup"><span data-stu-id="5857e-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5857e-137">A (host)</span><span class="sxs-lookup"><span data-stu-id="5857e-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="5857e-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="5857e-138">lyncdiscover.</span></span> <span data-ttu-id="5857e-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5857e-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="5857e-140">Endereço IP externo ou público (endereço VIP se você usar um balanceador de carga) do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="5857e-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5857e-141">SRV</span><span class="sxs-lookup"><span data-stu-id="5857e-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="5857e-142">_sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="5857e-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="5857e-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5857e-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="5857e-144">Resolve para registro de host (A ou AAAA) do serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="5857e-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5857e-145">Para dar suporte ao serviço de notificação por push e ao Apple Push Notification Service, crie um registro SRV para cada domínio SIP que tenha clientes móveis do Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="5857e-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="5857e-146">Este requisito aplica-se somente aos clientes móveis do Microsoft Lync em dispositivos móveis baseados em Apple ou Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5857e-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="5857e-147">Os dispositivos Android e Nokia Symbian não usam notificações por push.</span><span class="sxs-lookup"><span data-stu-id="5857e-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5857e-148">Lyncdiscover, também conhecido como descoberta automática, o tráfego passa pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="5857e-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="5857e-149">O registro SRV aponta para um registro que é resolvido por meio do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="5857e-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

