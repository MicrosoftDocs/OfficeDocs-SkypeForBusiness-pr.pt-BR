---
title: 'Lync Server 2013: tabela TraceRoute'
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
ms.openlocfilehash: 691b7576d59511428400d14a3ff21109525dc5a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="6be96-102">Tabela TraceRoute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6be96-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6be96-103">_**Tópico da última modificação:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="6be96-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="6be96-104">A tabela TraceRoute contém informações de roteamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="6be96-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="6be96-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6be96-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6be96-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6be96-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6be96-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6be96-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6be96-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6be96-111">datetime</span><span class="sxs-lookup"><span data-stu-id="6be96-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6be96-112">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6be96-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6be96-113">Data e hora em que a chamada começou.</span><span class="sxs-lookup"><span data-stu-id="6be96-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6be96-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6be96-115">int</span><span class="sxs-lookup"><span data-stu-id="6be96-115">int</span></span></p></td>
<td><p><span data-ttu-id="6be96-116">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6be96-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6be96-117">Identificador exclusivo usado para distinguir entre várias chamadas que podem ter começado na mesma data e ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="6be96-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6be96-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="6be96-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="6be96-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6be96-120">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6be96-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6be96-121">Representa o tipo de linha de vídeo usado na chamada.</span><span class="sxs-lookup"><span data-stu-id="6be96-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="6be96-122">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="6be96-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6be96-123">0 – áudio</span><span class="sxs-lookup"><span data-stu-id="6be96-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="6be96-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="6be96-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="6be96-125">2 – vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="6be96-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="6be96-126">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="6be96-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6be96-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="6be96-128">bit</span><span class="sxs-lookup"><span data-stu-id="6be96-128">bit</span></span></p></td>
<td><p><span data-ttu-id="6be96-129">Primária</span><span class="sxs-lookup"><span data-stu-id="6be96-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="6be96-130">Ponto de extremidade que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="6be96-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6be96-131"><strong>Hop</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="6be96-132">int</span><span class="sxs-lookup"><span data-stu-id="6be96-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6be96-133">Salto de rede/</span><span class="sxs-lookup"><span data-stu-id="6be96-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6be96-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="6be96-135">int</span><span class="sxs-lookup"><span data-stu-id="6be96-135">int</span></span></p></td>
<td><p><span data-ttu-id="6be96-136">Exterior</span><span class="sxs-lookup"><span data-stu-id="6be96-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6be96-137">Identificador exclusivo do endereço IP.</span><span class="sxs-lookup"><span data-stu-id="6be96-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="6be96-138">As informações de endereço IP são armazenadas na <a href="lync-server-2013-ipaddress-table.md">tabela IPAddress no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6be96-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6be96-139"><strong>RESPOSTA</strong></span><span class="sxs-lookup"><span data-stu-id="6be96-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="6be96-140">int</span><span class="sxs-lookup"><span data-stu-id="6be96-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6be96-141">Tempo de resposta.</span><span class="sxs-lookup"><span data-stu-id="6be96-141">Roundtrip time.</span></span> <span data-ttu-id="6be96-142">O tempo de resposta mede a quantidade de tempo que leva para um pacote de voz alcançar seu destino e enviar notificações de volta para que ele seja recebido.</span><span class="sxs-lookup"><span data-stu-id="6be96-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

