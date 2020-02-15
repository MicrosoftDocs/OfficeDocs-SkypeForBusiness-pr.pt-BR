---
title: 'Lync Server 2013: Resumo de DNS-pool de diretores em escala, balanceador de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled Director pool, hardware load balancer
ms:assetid: 08ba48e6-bfa1-4ab0-bc89-d58ddb9c20af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204655(v=OCS.15)
ms:contentKeyID: 48183340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ed4a3a810e4f1aa2fc5228e61cd68af163c91f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="59dc0-102">Resumo de DNS-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59dc0-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59dc0-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="59dc0-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="59dc0-104">A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor de carga balanceada do hardware.</span><span class="sxs-lookup"><span data-stu-id="59dc0-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="59dc0-105">A função do diretor requer registros DNS similares como o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="59dc0-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="59dc0-106">O número de registros necessários é refletido nos nomes alternativos da entidade necessários no certificado do diretor.</span><span class="sxs-lookup"><span data-stu-id="59dc0-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="59dc0-107">Diferente do servidor front-end, o pool de diretores não hospeda contas de usuário ou hospeda os serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="59dc0-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="59dc0-108">Registros DNS necessários para o pool de diretores usando um balanceador de carga de hardware e balanceamento de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="59dc0-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59dc0-109">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="59dc0-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="59dc0-110">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="59dc0-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="59dc0-111">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="59dc0-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="59dc0-112">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="59dc0-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59dc0-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="59dc0-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="59dc0-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="59dc0-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="59dc0-115">Be</span><span class="sxs-lookup"><span data-stu-id="59dc0-115">Director</span></span></p></td>
<td><p><span data-ttu-id="59dc0-116">Registro de host do diretor usado para a comunicação de replicação e servidor</span><span class="sxs-lookup"><span data-stu-id="59dc0-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59dc0-117">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="59dc0-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="59dc0-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="59dc0-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="59dc0-119">VIP HLB do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="59dc0-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="59dc0-120">Registro de host para o pool de diretor balanceado de carga DNS</span><span class="sxs-lookup"><span data-stu-id="59dc0-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59dc0-121">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="59dc0-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="59dc0-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="59dc0-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="59dc0-123">VIP HLB do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="59dc0-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="59dc0-124">SIP (protocolo de iniciação de sessão de entrada) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="59dc0-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59dc0-125">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="59dc0-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="59dc0-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="59dc0-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="59dc0-127">VIP HLB do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="59dc0-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="59dc0-128">Carga de hardware balanceada publicada nos serviços da Web de discagem do proxy inverso</span><span class="sxs-lookup"><span data-stu-id="59dc0-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59dc0-129">DNS/A inverso</span><span class="sxs-lookup"><span data-stu-id="59dc0-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="59dc0-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="59dc0-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="59dc0-131">VIP HLB do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="59dc0-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="59dc0-132">Carga de hardware balanceada publicada pelos serviços da Web de reunião do proxy inverso</span><span class="sxs-lookup"><span data-stu-id="59dc0-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59dc0-133">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="59dc0-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="59dc0-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="59dc0-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="59dc0-135">VIP HLB do pool de diretor</span><span class="sxs-lookup"><span data-stu-id="59dc0-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="59dc0-136">Carga de hardware balanceada publicada e definida pelos Serviços da Web externos de Ticket da Web do proxy inverso do pool de Diretores</span><span class="sxs-lookup"><span data-stu-id="59dc0-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

