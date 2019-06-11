---
title: 'Lync Server 2013: Resumo de DNS - Cargas de DNS e de HLB balanceadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceccb52a8ef9fae810821ffe6b52b763dd8904c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="177ee-102">Resumo de DNS - Cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="177ee-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="177ee-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="177ee-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="177ee-104">A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor de balanceamento de carga de hardware e carga balanceada do DNS.</span><span class="sxs-lookup"><span data-stu-id="177ee-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="177ee-105">A função do diretor requer registros DNS semelhantes ao servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="177ee-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="177ee-106">O número de registros necessários se reflete nos nomes alternativos da entidade obrigatórios no certificado do diretor.</span><span class="sxs-lookup"><span data-stu-id="177ee-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="177ee-107">Diferente do servidor front-end, o pool de directors não hospeda contas de usuário nem hospeda os serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="177ee-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="177ee-108">Registros DNS necessários para o pool de diretor que usa o balanceamento de carga de DNS e o balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="177ee-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="177ee-109">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="177ee-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="177ee-110">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="177ee-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="177ee-111">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="177ee-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="177ee-112">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="177ee-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="177ee-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="177ee-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="177ee-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="177ee-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="177ee-115">Diretor</span><span class="sxs-lookup"><span data-stu-id="177ee-115">Director</span></span></p></td>
<td><p><span data-ttu-id="177ee-116">Registro de host do diretor usado para replicação e servidor para servidor</span><span class="sxs-lookup"><span data-stu-id="177ee-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177ee-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="177ee-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="177ee-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="177ee-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="177ee-119">Pool de diretores</span><span class="sxs-lookup"><span data-stu-id="177ee-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="177ee-120">Registro de host para o pool de directors de carga balanceada do DNS do servidor para o servidor</span><span class="sxs-lookup"><span data-stu-id="177ee-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177ee-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="177ee-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="177ee-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="177ee-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="177ee-123">Pool de diretores</span><span class="sxs-lookup"><span data-stu-id="177ee-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="177ee-124">Protocolo de iniciação de sessão de entrada (SIP) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="177ee-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177ee-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="177ee-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="177ee-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="177ee-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="177ee-127">VIP de HLB do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="177ee-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="177ee-128">Serviços Web de discagem com carga balanceada do hardware de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="177ee-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="177ee-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="177ee-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="177ee-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="177ee-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="177ee-131">VIP de HLB do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="177ee-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="177ee-132">Publicação de carga de hardware com balanceamento de carga de serviços Web de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="177ee-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="177ee-133">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="177ee-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="177ee-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="177ee-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="177ee-135">VIP de HLB do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="177ee-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="177ee-136">Carga balanceada de carga de hardware publicada e definida pelos serviços Web externos de tíquete de proxy reverso para o pool de diretor</span><span class="sxs-lookup"><span data-stu-id="177ee-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

