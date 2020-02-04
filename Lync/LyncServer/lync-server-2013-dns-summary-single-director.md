---
title: 'Lync Server 2013: Resumo de DNS - Diretor Único'
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
ms.openlocfilehash: 71fb3052de36a92afb4ed9076820f7fcb2b54997
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="f0538-102">Resumo de DNS - Diretor Único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0538-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0538-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="f0538-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f0538-104">A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor único.</span><span class="sxs-lookup"><span data-stu-id="f0538-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="f0538-105">A função do diretor requer registros DNS semelhantes ao servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="f0538-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="f0538-106">O número de registros necessários se reflete nos nomes alternativos da entidade obrigatórios no certificado do diretor.</span><span class="sxs-lookup"><span data-stu-id="f0538-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="f0538-107">Diferente do servidor front-end, o diretor não hospeda contas de usuário nem hospeda os serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="f0538-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="f0538-108">Registros DNS necessários para o diretor</span><span class="sxs-lookup"><span data-stu-id="f0538-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0538-109">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="f0538-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="f0538-110">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="f0538-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="f0538-111">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="f0538-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="f0538-112">Mapas para/comentários</span><span class="sxs-lookup"><span data-stu-id="f0538-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0538-113">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f0538-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f0538-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f0538-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f0538-115">Diretor</span><span class="sxs-lookup"><span data-stu-id="f0538-115">Director</span></span></p></td>
<td><p><span data-ttu-id="f0538-116">Registro de host do diretor usado para replicação e servidor para servidor</span><span class="sxs-lookup"><span data-stu-id="f0538-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0538-117">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f0538-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f0538-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0538-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f0538-119">Diretor</span><span class="sxs-lookup"><span data-stu-id="f0538-119">Director</span></span></p></td>
<td><p><span data-ttu-id="f0538-120">Protocolo de iniciação de sessão de entrada (SIP) da interface de borda interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="f0538-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0538-121">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f0538-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f0538-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0538-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f0538-123">Diretor</span><span class="sxs-lookup"><span data-stu-id="f0538-123">Director</span></span></p></td>
<td><p><span data-ttu-id="f0538-124">Serviços da discagem publicados do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="f0538-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0538-125">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f0538-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f0538-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0538-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f0538-127">Diretor</span><span class="sxs-lookup"><span data-stu-id="f0538-127">Director</span></span></p></td>
<td><p><span data-ttu-id="f0538-128">Serviços Web de reunião publicados do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="f0538-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0538-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="f0538-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="f0538-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0538-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f0538-131">Diretor</span><span class="sxs-lookup"><span data-stu-id="f0538-131">Director</span></span></p></td>
<td><p><span data-ttu-id="f0538-132">Publicado e definido pelos serviços Web externos de tíquete de proxy reverso para o diretor</span><span class="sxs-lookup"><span data-stu-id="f0538-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

