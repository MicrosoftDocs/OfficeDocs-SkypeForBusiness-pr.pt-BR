---
title: 'Lync Server 2013: Resumo de DNS-diretor único'
description: 'Lync Server 2013: Resumo de DNS-diretor único.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78ef19383df45644ad951ca5da69ef893b231980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553227"
---
# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="ba494-103">Resumo de DNS-diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba494-103">DNS summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba494-104">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ba494-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ba494-105">A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor único.</span><span class="sxs-lookup"><span data-stu-id="ba494-105">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="ba494-106">A função do diretor requer registros DNS similares como o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ba494-106">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="ba494-107">O número de registros necessários é refletido nos nomes alternativos da entidade necessários no certificado do diretor.</span><span class="sxs-lookup"><span data-stu-id="ba494-107">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="ba494-108">Diferente do servidor front-end, o diretor não hospeda contas de usuário ou hospeda os serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="ba494-108">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="ba494-109">Registros DNS necessários para o diretor</span><span class="sxs-lookup"><span data-stu-id="ba494-109">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba494-110">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="ba494-110">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="ba494-111">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="ba494-111">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="ba494-112">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="ba494-112">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="ba494-113">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="ba494-113">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba494-114">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="ba494-114">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ba494-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ba494-115">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ba494-116">Diretor</span><span class="sxs-lookup"><span data-stu-id="ba494-116">Director</span></span></p></td>
<td><p><span data-ttu-id="ba494-117">Registro de host do diretor usado para replicação e servidor para servidor</span><span class="sxs-lookup"><span data-stu-id="ba494-117">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba494-118">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="ba494-118">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ba494-119">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba494-119">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ba494-120">Diretor</span><span class="sxs-lookup"><span data-stu-id="ba494-120">Director</span></span></p></td>
<td><p><span data-ttu-id="ba494-121">SIP (protocolo de iniciação de sessão de entrada) da interface de borda interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba494-121">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba494-122">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="ba494-122">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ba494-123">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba494-123">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ba494-124">Diretor</span><span class="sxs-lookup"><span data-stu-id="ba494-124">Director</span></span></p></td>
<td><p><span data-ttu-id="ba494-125">Serviços Web de discagem publicados do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="ba494-125">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba494-126">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="ba494-126">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ba494-127">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba494-127">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ba494-128">Diretor</span><span class="sxs-lookup"><span data-stu-id="ba494-128">Director</span></span></p></td>
<td><p><span data-ttu-id="ba494-129">Serviços Web de reunião publicados do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="ba494-129">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba494-130">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="ba494-130">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ba494-131">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ba494-131">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ba494-132">Diretor</span><span class="sxs-lookup"><span data-stu-id="ba494-132">Director</span></span></p></td>
<td><p><span data-ttu-id="ba494-133">Publicado e definido pelos serviços Web externos de tíquete da Web de proxy reverso para o diretor</span><span class="sxs-lookup"><span data-stu-id="ba494-133">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

