---
title: 'Lync Server 2013: Resumo de DNS - Pool de diretores em escala, balanceadores de carga do hardware'
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
ms.openlocfilehash: 891b69339416c81d81e72e43edf5f09bbf9da3e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="f78df-102">Resumo de DNS - Pool de diretores em escala, balanceadores de carga do hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f78df-102">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f78df-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f78df-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f78df-104">A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor de carga balanceada do hardware.</span><span class="sxs-lookup"><span data-stu-id="f78df-104">The following table contains a summary of the DNS records that are required to support the hardware load balanced Director.</span></span> <span data-ttu-id="f78df-105">A função do diretor requer registros DNS semelhantes ao servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f78df-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="f78df-106">O número de registros necessários se reflete nos nomes alternativos da entidade obrigatórios no certificado do diretor.</span><span class="sxs-lookup"><span data-stu-id="f78df-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="f78df-107">Diferente do servidor front-end, o pool de directors não hospeda contas de usuário nem hospeda os serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="f78df-107">Different from the Front End Server, the Director pool does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director-pool-using-a-hardware-load-balancer-and-dns-load-balancing"></a><span data-ttu-id="f78df-108">Registros DNS necessários para o pool diretor que usa um balanceador de carga de hardware e equilíbrio de carga de DNS</span><span class="sxs-lookup"><span data-stu-id="f78df-108">DNS Records Required for the Director pool using a Hardware Load Balancer and DNS Load Balancing</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f78df-109">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="f78df-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f78df-110">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="f78df-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f78df-111">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="f78df-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f78df-112">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="f78df-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f78df-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f78df-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f78df-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f78df-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f78df-115">Diretor</span><span class="sxs-lookup"><span data-stu-id="f78df-115">Director</span></span></p></td>
<td><p><span data-ttu-id="f78df-116">Registro de host do diretor usado para a comunicação de servidor para replicação e servidor</span><span class="sxs-lookup"><span data-stu-id="f78df-116">Director host record used for replication and server to server communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f78df-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f78df-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f78df-118">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f78df-118">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f78df-119">VIP de HLB do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="f78df-119">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f78df-120">Registro de host para o pool de directors de carga balanceada do DNS</span><span class="sxs-lookup"><span data-stu-id="f78df-120">Host record for the DNS load balanced Director pool</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f78df-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f78df-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f78df-122">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f78df-122">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f78df-123">VIP de HLB do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="f78df-123">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f78df-124">Protocolo de iniciação de sessão de entrada (SIP) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="f78df-124">Inbound session initiation protocol (SIP) from the internal interface of the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f78df-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f78df-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f78df-126">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f78df-126">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f78df-127">VIP de HLB do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="f78df-127">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f78df-128">Serviços Web de discagem com carga balanceada do hardware de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="f78df-128">Hardware load balanced published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f78df-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f78df-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f78df-130">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f78df-130">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f78df-131">VIP de HLB do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="f78df-131">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f78df-132">Publicação de carga de hardware com balanceamento de carga de serviços Web de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="f78df-132">Hardware load balanced published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f78df-133">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f78df-133">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f78df-134">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f78df-134">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f78df-135">VIP de HLB do pool do diretor</span><span class="sxs-lookup"><span data-stu-id="f78df-135">Director pool HLB VIP</span></span></p></td>
<td><p><span data-ttu-id="f78df-136">Carga balanceada de carga de hardware publicada e definida pelos serviços Web externos de tíquete de proxy reverso para o pool de diretor</span><span class="sxs-lookup"><span data-stu-id="f78df-136">Hardware load balanced published and defined by the reverse proxy Web Ticket external web services for the Director pool</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

