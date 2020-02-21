---
title: 'Lync Server 2013: Resumo de DNS-balanceamento de carga DNS e HLB'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - DNS and HLB load balanced
ms:assetid: d2132695-1956-4190-a98e-cd7255cbded6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205273(v=OCS.15)
ms:contentKeyID: 48185447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86a4b90cc78b3fdcb6b5a02332d95468f8246c84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="db67a-102">Resumo de DNS-cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db67a-102">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db67a-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="db67a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="db67a-104">A tabela a seguir contém um resumo dos registros DNS que são necessários para dar suporte ao diretor de carga balanceada e balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="db67a-104">The following table contains a summary of the DNS records that are required to support the DNS load balanced and hardware load balanced Director.</span></span> <span data-ttu-id="db67a-105">A função do diretor requer registros DNS similares como o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="db67a-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="db67a-106">O número de registros necessários é refletido nos nomes alternativos da entidade necessários no certificado do diretor.</span><span class="sxs-lookup"><span data-stu-id="db67a-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="db67a-107">Diferente do servidor front-end, o pool de diretores não hospeda contas de usuário ou hospeda os serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="db67a-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-dns-load-balancing-and-hardware-load-balancer"></a><span data-ttu-id="db67a-108">Registros DNS necessários para o Pool de Diretor usando o balanceamento de carga DNS e o balanceador de carga de hardware</span><span class="sxs-lookup"><span data-stu-id="db67a-108">DNS Records Required for the Director Pool using DNS Load Balancing and Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db67a-109">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="db67a-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="db67a-110">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="db67a-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="db67a-111">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="db67a-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="db67a-112">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="db67a-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db67a-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="db67a-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="db67a-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="db67a-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="db67a-115">Be</span><span class="sxs-lookup"><span data-stu-id="db67a-115">Director</span></span></p></td>
<td><p><span data-ttu-id="db67a-116">Registro de host do diretor usado para replicação e servidor para servidor</span><span class="sxs-lookup"><span data-stu-id="db67a-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db67a-117">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="db67a-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="db67a-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="db67a-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="db67a-119">Director pool</span><span class="sxs-lookup"><span data-stu-id="db67a-119">Director pool</span></span></p></td>
<td><p><span data-ttu-id="db67a-120">Registro de host do pool de diretor balanceado de carga de DNS para servidor para servidor</span><span class="sxs-lookup"><span data-stu-id="db67a-120">Host record for the DNS load balanced Director pool for server to server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db67a-121">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="db67a-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="db67a-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db67a-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="db67a-123">Director pool</span><span class="sxs-lookup"><span data-stu-id="db67a-123">Director pool</span></span></p></td>
<td><p><span data-ttu-id="db67a-124">SIP (protocolo de iniciação de sessão de entrada) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="db67a-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db67a-125">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="db67a-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="db67a-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db67a-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="db67a-127">VIP HLB do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="db67a-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="db67a-128">Carga de hardware balanceada publicada nos serviços da Web de discagem do proxy inverso</span><span class="sxs-lookup"><span data-stu-id="db67a-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db67a-129">DNS/A inverso</span><span class="sxs-lookup"><span data-stu-id="db67a-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="db67a-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db67a-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="db67a-131">VIP HLB do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="db67a-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="db67a-132">Carga de hardware balanceada publicada pelos serviços da Web de reunião do proxy inverso</span><span class="sxs-lookup"><span data-stu-id="db67a-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db67a-133">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="db67a-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="db67a-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db67a-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="db67a-135">VIP HLB do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="db67a-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="db67a-136">Carga de hardware balanceada publicada e definida pelos Serviços da Web externos de Ticket da Web do proxy inverso do pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="db67a-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

