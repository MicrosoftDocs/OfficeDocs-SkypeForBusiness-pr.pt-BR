---
title: 'Lync Server 2013: Resumo de DNS-diretor único'
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
ms.openlocfilehash: 44bcd52c2e7d13ef57e96e4ae5dc8841a58bc3d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="8f61a-102">Resumo de DNS-diretor único no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8f61a-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f61a-103">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="8f61a-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="8f61a-104">A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte ao diretor único.</span><span class="sxs-lookup"><span data-stu-id="8f61a-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="8f61a-105">A função do diretor requer registros DNS similares como o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="8f61a-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="8f61a-106">O número de registros necessários é refletido nos nomes alternativos da entidade necessários no certificado do diretor.</span><span class="sxs-lookup"><span data-stu-id="8f61a-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="8f61a-107">Diferente do servidor front-end, o diretor não hospeda contas de usuário ou hospeda os serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="8f61a-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="8f61a-108">Registros DNS necessários para o diretor</span><span class="sxs-lookup"><span data-stu-id="8f61a-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f61a-109">Local/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8f61a-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8f61a-110">Registro FQDN/DNS</span><span class="sxs-lookup"><span data-stu-id="8f61a-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="8f61a-111">Endereço IP/FQDN</span><span class="sxs-lookup"><span data-stu-id="8f61a-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="8f61a-112">Mapeia para/Comentários</span><span class="sxs-lookup"><span data-stu-id="8f61a-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f61a-113">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="8f61a-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8f61a-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8f61a-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8f61a-115">Be</span><span class="sxs-lookup"><span data-stu-id="8f61a-115">Director</span></span></p></td>
<td><p><span data-ttu-id="8f61a-116">Registro de host do diretor usado para replicação e servidor para servidor</span><span class="sxs-lookup"><span data-stu-id="8f61a-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f61a-117">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="8f61a-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8f61a-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8f61a-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8f61a-119">Be</span><span class="sxs-lookup"><span data-stu-id="8f61a-119">Director</span></span></p></td>
<td><p><span data-ttu-id="8f61a-120">SIP (protocolo de iniciação de sessão de entrada) da interface de borda interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="8f61a-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f61a-121">DNS/A interno</span><span class="sxs-lookup"><span data-stu-id="8f61a-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8f61a-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8f61a-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8f61a-123">Be</span><span class="sxs-lookup"><span data-stu-id="8f61a-123">Director</span></span></p></td>
<td><p><span data-ttu-id="8f61a-124">Serviços Web de discagem publicados do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="8f61a-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f61a-125">DNS/A inverso</span><span class="sxs-lookup"><span data-stu-id="8f61a-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8f61a-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8f61a-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8f61a-127">Be</span><span class="sxs-lookup"><span data-stu-id="8f61a-127">Director</span></span></p></td>
<td><p><span data-ttu-id="8f61a-128">Serviços Web de reunião publicados do proxy reverso</span><span class="sxs-lookup"><span data-stu-id="8f61a-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f61a-129">DNS interno/A</span><span class="sxs-lookup"><span data-stu-id="8f61a-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8f61a-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8f61a-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8f61a-131">Be</span><span class="sxs-lookup"><span data-stu-id="8f61a-131">Director</span></span></p></td>
<td><p><span data-ttu-id="8f61a-132">Publicado e definido pelos serviços Web externos de tíquete da Web de proxy reverso para o diretor</span><span class="sxs-lookup"><span data-stu-id="8f61a-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

