---
title: 'Lync Server 2013: tabela de TraceRoute'
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
ms.openlocfilehash: 1bc4a6d990c91f87022b041d9478b6dde5a71bb5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="69bf9-102">Tabela de TraceRoute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69bf9-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69bf9-103">_**Última modificação do tópico:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="69bf9-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="69bf9-104">A tabela TraceRoute contém informações de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="69bf9-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="69bf9-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69bf9-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69bf9-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="69bf9-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="69bf9-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="69bf9-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69bf9-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69bf9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="69bf9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="69bf9-112">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="69bf9-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bf9-113">Data e hora de início da chamada.</span><span class="sxs-lookup"><span data-stu-id="69bf9-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bf9-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="69bf9-115">int</span><span class="sxs-lookup"><span data-stu-id="69bf9-115">int</span></span></p></td>
<td><p><span data-ttu-id="69bf9-116">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="69bf9-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bf9-117">Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e hora.</span><span class="sxs-lookup"><span data-stu-id="69bf9-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bf9-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="69bf9-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="69bf9-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="69bf9-120">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="69bf9-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bf9-p102">Representa o tipo de linha de vídeo usada na chamada. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="69bf9-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="69bf9-123">0 – áudio</span><span class="sxs-lookup"><span data-stu-id="69bf9-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="69bf9-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="69bf9-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="69bf9-125">2 – Vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="69bf9-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="69bf9-126">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="69bf9-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bf9-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="69bf9-128">bits</span><span class="sxs-lookup"><span data-stu-id="69bf9-128">bit</span></span></p></td>
<td><p><span data-ttu-id="69bf9-129">Primário</span><span class="sxs-lookup"><span data-stu-id="69bf9-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="69bf9-130">Ponto de extremidade que executou a chamada.</span><span class="sxs-lookup"><span data-stu-id="69bf9-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bf9-131"><strong>Saltos</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="69bf9-132">int</span><span class="sxs-lookup"><span data-stu-id="69bf9-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bf9-133">Salto de rede/</span><span class="sxs-lookup"><span data-stu-id="69bf9-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69bf9-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="69bf9-135">int</span><span class="sxs-lookup"><span data-stu-id="69bf9-135">int</span></span></p></td>
<td><p><span data-ttu-id="69bf9-136">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="69bf9-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69bf9-137">Identificador exclusivo do endereço IP.</span><span class="sxs-lookup"><span data-stu-id="69bf9-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="69bf9-138">As informações de endereço IP são armazenadas na <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="69bf9-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69bf9-139"><strong>RESPOSTA</strong></span><span class="sxs-lookup"><span data-stu-id="69bf9-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="69bf9-140">int</span><span class="sxs-lookup"><span data-stu-id="69bf9-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69bf9-p104">Tempo de viagem de ida e volta. O tempo de viagem de ida e volta mede quanto tempo leva para que um pacote de voz chegue ao seu destino e retorne uma notificação de recebimento.</span><span class="sxs-lookup"><span data-stu-id="69bf9-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

