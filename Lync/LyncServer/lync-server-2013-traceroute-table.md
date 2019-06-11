---
title: 'Lync Server 2013: tabela TraceRoute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="a516b-102">Tabela TraceRoute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a516b-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a516b-103">_**Tópico da última modificação:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="a516b-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="a516b-104">A tabela TraceRoute contém informações de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="a516b-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="a516b-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a516b-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a516b-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a516b-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a516b-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a516b-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a516b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a516b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a516b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a516b-112">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="a516b-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a516b-113">Data e hora em que a chamada começou.</span><span class="sxs-lookup"><span data-stu-id="a516b-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a516b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a516b-115">int</span><span class="sxs-lookup"><span data-stu-id="a516b-115">int</span></span></p></td>
<td><p><span data-ttu-id="a516b-116">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="a516b-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a516b-117">Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="a516b-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a516b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a516b-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="a516b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a516b-120">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="a516b-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="a516b-121">Representa o tipo de linha de vídeo usado na chamada.</span><span class="sxs-lookup"><span data-stu-id="a516b-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="a516b-122">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="a516b-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="a516b-123">0 – áudio</span><span class="sxs-lookup"><span data-stu-id="a516b-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="a516b-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="a516b-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="a516b-125">2 – vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="a516b-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="a516b-126">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="a516b-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a516b-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="a516b-128">bit</span><span class="sxs-lookup"><span data-stu-id="a516b-128">bit</span></span></p></td>
<td><p><span data-ttu-id="a516b-129">Primária</span><span class="sxs-lookup"><span data-stu-id="a516b-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="a516b-130">Ponto de extremidade que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="a516b-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a516b-131"><strong>Hop</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="a516b-132">int</span><span class="sxs-lookup"><span data-stu-id="a516b-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a516b-133">Salto de rede/</span><span class="sxs-lookup"><span data-stu-id="a516b-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a516b-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a516b-135">int</span><span class="sxs-lookup"><span data-stu-id="a516b-135">int</span></span></p></td>
<td><p><span data-ttu-id="a516b-136">Exterior</span><span class="sxs-lookup"><span data-stu-id="a516b-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a516b-137">Identificador exclusivo do endereço IP.</span><span class="sxs-lookup"><span data-stu-id="a516b-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="a516b-138">As informações de endereço IP são armazenadas na <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="a516b-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a516b-139"><strong>RESPOSTA</strong></span><span class="sxs-lookup"><span data-stu-id="a516b-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="a516b-140">int</span><span class="sxs-lookup"><span data-stu-id="a516b-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a516b-141">Tempo de resposta.</span><span class="sxs-lookup"><span data-stu-id="a516b-141">Roundtrip time.</span></span> <span data-ttu-id="a516b-142">O tempo de resposta mede a quantidade de tempo que leva para um pacote de voz alcançar seu destino e enviar notificações de volta para que ele seja recebido.</span><span class="sxs-lookup"><span data-stu-id="a516b-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

