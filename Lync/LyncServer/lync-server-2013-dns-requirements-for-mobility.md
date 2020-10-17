---
title: 'Lync Server 2013: requisitos de DNS para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 508e9c8e030de7aeb496a1285ff7b965e43c2a6b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501428"
---
# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="5d43d-102">Requisitos de DNS para mobilidade com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d43d-102">DNS requirements for mobility with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d43d-103">_**Última modificação do tópico:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="5d43d-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="5d43d-104">Ao implantar o recurso de mobilidade do Lync Server 2013, você pode usar as novas URLs que estão disponíveis com o serviço de descoberta automática do Microsoft Lync Server 2013 ou você pode usar suas URLs de serviços da Web existentes.</span><span class="sxs-lookup"><span data-stu-id="5d43d-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="5d43d-105">Se você usar suas URLs existentes, os usuários precisarão inserir manualmente as URLs em suas configurações de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="5d43d-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="5d43d-106">Essa opção normalmente é usada para a solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="5d43d-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="5d43d-107">Quando você usa as novas URLs, os clientes móveis podem descobrir automaticamente os recursos do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d43d-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="5d43d-108">Quando você dá suporte à descoberta automática, precisa adicionar novos registros de DNS (sistema de nomes de domínio).</span><span class="sxs-lookup"><span data-stu-id="5d43d-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="5d43d-109">Esta seção descreve os registros DNS necessários para a descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="5d43d-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="5d43d-110">Para oferecer suporte à descoberta automática, você precisa criar os seguintes registros DNS para cada domínio SIP:</span><span class="sxs-lookup"><span data-stu-id="5d43d-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="5d43d-111">Um registro DNS interno para suportar usuários móveis que se conectam de dentro da rede da organização</span><span class="sxs-lookup"><span data-stu-id="5d43d-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="5d43d-112">Um registro DNS externo ou público para suportar usuários móveis que se conectam pela Internet</span><span class="sxs-lookup"><span data-stu-id="5d43d-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="5d43d-113">A URL de descoberta automática interna não deve ser endereçável de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="5d43d-113">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="5d43d-114">A URL de descoberta automática externa não deve ser endereçável de dentro da rede.</span><span class="sxs-lookup"><span data-stu-id="5d43d-114">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="5d43d-115">No entanto, se você não puder atender a esse requisito para a URL externa, o cliente móvel não deve ser afetado.</span><span class="sxs-lookup"><span data-stu-id="5d43d-115">However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="5d43d-116">Os registros DNS podem ser registros CNAME ou registros A (host).</span><span class="sxs-lookup"><span data-stu-id="5d43d-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="5d43d-117">**Registros DNS internos**</span><span class="sxs-lookup"><span data-stu-id="5d43d-117">**Internal DNS records**</span></span>

<span data-ttu-id="5d43d-118">Você precisa criar um dos seguintes registros DNS internos:</span><span class="sxs-lookup"><span data-stu-id="5d43d-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d43d-119">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="5d43d-119">Record type</span></span></th>
<th><span data-ttu-id="5d43d-120">Nome do host ou definição SRV</span><span class="sxs-lookup"><span data-stu-id="5d43d-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="5d43d-121">Resolve para</span><span class="sxs-lookup"><span data-stu-id="5d43d-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d43d-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d43d-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="5d43d-123">lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5d43d-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="5d43d-124">FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para o seu pool de diretores, se você tiver um, ou para seu pool de front-ends, se não tiver um diretor</span><span class="sxs-lookup"><span data-stu-id="5d43d-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d43d-125">A (host)</span><span class="sxs-lookup"><span data-stu-id="5d43d-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="5d43d-126">lyncdiscoverinternal. &lt; sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5d43d-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="5d43d-127">Endereço IP de serviços Web interno (endereço IP virtual (VIP) se você usar um balanceador de carga) do seu pool de diretores, se você tiver um, ou do seu pool de front-ends, se não tiver um diretor</span><span class="sxs-lookup"><span data-stu-id="5d43d-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5d43d-128">**Registros DNS externos**</span><span class="sxs-lookup"><span data-stu-id="5d43d-128">**External DNS records**</span></span>

<span data-ttu-id="5d43d-129">É necessário criar um dos seguintes registros DNS externos:</span><span class="sxs-lookup"><span data-stu-id="5d43d-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d43d-130">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="5d43d-130">Record type</span></span></th>
<th><span data-ttu-id="5d43d-131">Nome do Host</span><span class="sxs-lookup"><span data-stu-id="5d43d-131">Host name</span></span></th>
<th><span data-ttu-id="5d43d-132">Resolve para</span><span class="sxs-lookup"><span data-stu-id="5d43d-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d43d-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d43d-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="5d43d-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="5d43d-134">lyncdiscover.</span></span> <span data-ttu-id="5d43d-135">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5d43d-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="5d43d-136">FQDN de serviços Web externos para seu pool de diretor, se você tiver um, ou para seu pool de front-ends se não tiver um diretor</span><span class="sxs-lookup"><span data-stu-id="5d43d-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d43d-137">A (host)</span><span class="sxs-lookup"><span data-stu-id="5d43d-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="5d43d-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="5d43d-138">lyncdiscover.</span></span> <span data-ttu-id="5d43d-139">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5d43d-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="5d43d-140">Endereço IP externo ou público (endereço VIP se você usar um balanceador de carga) do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="5d43d-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d43d-141">SRV</span><span class="sxs-lookup"><span data-stu-id="5d43d-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="5d43d-142">_sipfederationtls _sipfederationtls._tcp.</span><span class="sxs-lookup"><span data-stu-id="5d43d-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="5d43d-143">&lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="5d43d-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="5d43d-144">Resolve para registro de host (A ou AAAA) do serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="5d43d-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5d43d-145">Para dar suporte ao serviço de notificação por push e ao Apple Push Notification Service, você cria um registro SRV para cada domínio SIP que tenha clientes móveis do Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="5d43d-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="5d43d-146">Esse requisito aplica-se somente aos clientes móveis do Microsoft Lync em dispositivos móveis baseados em Apple ou Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d43d-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="5d43d-147">Os dispositivos Andriod e Nokia Symbian não usam a notificação por push.</span><span class="sxs-lookup"><span data-stu-id="5d43d-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5d43d-148">Lyncdiscover, também conhecido como descoberta automática, o tráfego passa pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="5d43d-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="5d43d-149">O registro SRV aponta para um registro que resolve através do serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="5d43d-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

