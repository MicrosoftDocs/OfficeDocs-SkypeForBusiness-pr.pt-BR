---
title: 'Lync Server 2013: Tabela VideoClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79b428a639cee6fb0df04cc969b529c5bbbfb2c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="f7e4b-102">Tabela VideoClientEvent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7e4b-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7e4b-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f7e4b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f7e4b-104">Cada registro contém um evento de cliente para um ponto de extremidade em uma chamada com vídeo.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="f7e4b-105">Geralmente, uma chamada tem dois registros, um para o chamador e outro para o receptor.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7e4b-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f7e4b-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f7e4b-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f7e4b-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7e4b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f7e4b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f7e4b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f7e4b-112">Primária</span><span class="sxs-lookup"><span data-stu-id="f7e4b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f7e4b-113">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7e4b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f7e4b-115">int</span><span class="sxs-lookup"><span data-stu-id="f7e4b-115">int</span></span></p></td>
<td><p><span data-ttu-id="f7e4b-116">Primária</span><span class="sxs-lookup"><span data-stu-id="f7e4b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f7e4b-117">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7e4b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f7e4b-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f7e4b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f7e4b-120">Primária</span><span class="sxs-lookup"><span data-stu-id="f7e4b-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f7e4b-121">Referenciado da <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7e4b-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="f7e4b-123">bit</span><span class="sxs-lookup"><span data-stu-id="f7e4b-123">bit</span></span></p></td>
<td><p><span data-ttu-id="f7e4b-124">Primária</span><span class="sxs-lookup"><span data-stu-id="f7e4b-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f7e4b-125">0: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="f7e4b-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="f7e4b-126">1: dados do chamador</span><span class="sxs-lookup"><span data-stu-id="f7e4b-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7e4b-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f7e4b-128">Porcentagem da sessão o evento LowBandwidth foi disparado para o estado ' ruim '.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="f7e4b-129">A largura de banda disponível é insuficiente para uma experiência de voz aceitável.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7e4b-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f7e4b-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f7e4b-131">Porcentagem da sessão o evento ReceiveSendQuality foi disparado para o estado ' ruim '.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="f7e4b-132">A qualidade da rede em termos de tremulação ou perda de pacote é severa e afeta a qualidade do áudio sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="f7e4b-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

