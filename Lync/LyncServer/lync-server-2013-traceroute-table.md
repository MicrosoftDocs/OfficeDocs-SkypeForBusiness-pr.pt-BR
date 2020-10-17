---
title: 'Lync Server 2013: tabela de TraceRoute'
description: 'Lync Server 2013: tabela TraceRoute.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af33e572065fbab1eaaaef684997e7f95edaed9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549057"
---
# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="5ef7c-103">Tabela de TraceRoute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ef7c-103">TraceRoute table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ef7c-104">_**Última modificação do tópico:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="5ef7c-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="5ef7c-105">A tabela TraceRoute contém informações de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="5ef7c-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="5ef7c-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ef7c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ef7c-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5ef7c-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5ef7c-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5ef7c-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ef7c-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5ef7c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5ef7c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="5ef7c-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-114">Data e hora de início da chamada.</span><span class="sxs-lookup"><span data-stu-id="5ef7c-114">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ef7c-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5ef7c-116">int</span><span class="sxs-lookup"><span data-stu-id="5ef7c-116">int</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="5ef7c-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-118">Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e hora.</span><span class="sxs-lookup"><span data-stu-id="5ef7c-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ef7c-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5ef7c-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="5ef7c-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-121">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="5ef7c-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-p102">Representa o tipo de linha de vídeo usada na chamada. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="5ef7c-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="5ef7c-124">0 – áudio</span><span class="sxs-lookup"><span data-stu-id="5ef7c-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="5ef7c-125">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="5ef7c-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="5ef7c-126">2 – Vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="5ef7c-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="5ef7c-127">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="5ef7c-127">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ef7c-128"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-128"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="5ef7c-129">bits</span><span class="sxs-lookup"><span data-stu-id="5ef7c-129">bit</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-130">Primário</span><span class="sxs-lookup"><span data-stu-id="5ef7c-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-131">Ponto de extremidade que executou a chamada.</span><span class="sxs-lookup"><span data-stu-id="5ef7c-131">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ef7c-132"><strong>Saltos</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-132"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="5ef7c-133">int</span><span class="sxs-lookup"><span data-stu-id="5ef7c-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ef7c-134">Salto de rede/</span><span class="sxs-lookup"><span data-stu-id="5ef7c-134">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ef7c-135"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-135"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="5ef7c-136">int</span><span class="sxs-lookup"><span data-stu-id="5ef7c-136">int</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-137">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="5ef7c-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5ef7c-138">Identificador exclusivo do endereço IP.</span><span class="sxs-lookup"><span data-stu-id="5ef7c-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="5ef7c-139">As informações de endereço IP são armazenadas na <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="5ef7c-139">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ef7c-140"><strong>RESPOSTA</strong></span><span class="sxs-lookup"><span data-stu-id="5ef7c-140"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="5ef7c-141">int</span><span class="sxs-lookup"><span data-stu-id="5ef7c-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5ef7c-p104">Tempo de viagem de ida e volta. O tempo de viagem de ida e volta mede quanto tempo leva para que um pacote de voz chegue ao seu destino e retorne uma notificação de recebimento.</span><span class="sxs-lookup"><span data-stu-id="5ef7c-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

