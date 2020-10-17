---
title: 'Lync Server 2013: tabela VideoClientEvent'
description: 'Lync Server 2013: tabela VideoClientEvent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae73ac2548e838241febe60a2d31f80983b01de5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568487"
---
# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="78483-103">Tabela VideoClientEvent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78483-103">VideoClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78483-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="78483-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="78483-105">Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada de vídeo.</span><span class="sxs-lookup"><span data-stu-id="78483-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="78483-106">Normalmente, uma chamada tem dois registros, um para o chamador e um para o receptor.</span><span class="sxs-lookup"><span data-stu-id="78483-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78483-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="78483-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="78483-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="78483-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="78483-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="78483-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="78483-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="78483-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78483-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="78483-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="78483-112">datetime</span><span class="sxs-lookup"><span data-stu-id="78483-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="78483-113">Primário</span><span class="sxs-lookup"><span data-stu-id="78483-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="78483-114">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="78483-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78483-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="78483-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="78483-116">int</span><span class="sxs-lookup"><span data-stu-id="78483-116">int</span></span></p></td>
<td><p><span data-ttu-id="78483-117">Primário</span><span class="sxs-lookup"><span data-stu-id="78483-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="78483-118">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="78483-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78483-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="78483-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="78483-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="78483-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="78483-121">Primário</span><span class="sxs-lookup"><span data-stu-id="78483-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="78483-122">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="78483-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78483-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="78483-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="78483-124">bits</span><span class="sxs-lookup"><span data-stu-id="78483-124">bit</span></span></p></td>
<td><p><span data-ttu-id="78483-125">Primário</span><span class="sxs-lookup"><span data-stu-id="78483-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="78483-126">0: dados do receptor</span><span class="sxs-lookup"><span data-stu-id="78483-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="78483-127">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="78483-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78483-128"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="78483-128"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="78483-129">Porcentagem da sessão que o evento LowBandwidth foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="78483-129">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="78483-130">A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</span><span class="sxs-lookup"><span data-stu-id="78483-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78483-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="78483-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="78483-132">Porcentagem da sessão que o evento ReceiveSendQuality foi acionado para o estado "Bad".</span><span class="sxs-lookup"><span data-stu-id="78483-132">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="78483-133">A qualidade da rede em termos de tremulação ou perda de pacote é grave e afeta a qualidade do áudio que está sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="78483-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

