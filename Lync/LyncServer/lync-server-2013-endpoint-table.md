---
title: 'Lync Server 2013: tabela de pontos de extremidade'
description: 'Lync Server 2013: tabela de pontos de extremidade.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575617"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="c6611-103">Tabela de pontos de extremidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6611-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6611-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c6611-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c6611-105">A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6611-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c6611-106">Cada registro da tabela representa um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c6611-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6611-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c6611-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c6611-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c6611-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6611-111"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c6611-112">int</span><span class="sxs-lookup"><span data-stu-id="c6611-112">int</span></span></p></td>
<td><p><span data-ttu-id="c6611-113">Primário</span><span class="sxs-lookup"><span data-stu-id="c6611-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c6611-114">Número exclusivo que identifica esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c6611-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6611-115"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="c6611-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c6611-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c6611-117">Diferente</span><span class="sxs-lookup"><span data-stu-id="c6611-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="c6611-118">Nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c6611-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6611-119"><strong>Opera</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="c6611-120">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="c6611-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c6611-121">Sistema operacional (OS) do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c6611-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6611-122"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="c6611-123">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="c6611-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6611-124">Nome da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c6611-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6611-125"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="c6611-126">smallint</span><span class="sxs-lookup"><span data-stu-id="c6611-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6611-127">Número de núcleos da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c6611-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6611-128"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="c6611-129">int</span><span class="sxs-lookup"><span data-stu-id="c6611-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6611-130">Velocidade do processador da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c6611-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6611-131"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c6611-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6611-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="c6611-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6611-133">Sinalizador de bit que indica se o sistema está em execução em um ambiente virtualizado:</span><span class="sxs-lookup"><span data-stu-id="c6611-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6611-134">0x0000 – nenhum</span><span class="sxs-lookup"><span data-stu-id="c6611-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="c6611-135">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="c6611-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="c6611-136">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="c6611-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="c6611-137">0x0004 – Virtual PC</span><span class="sxs-lookup"><span data-stu-id="c6611-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="c6611-138">0x0008 – PC Xen</span><span class="sxs-lookup"><span data-stu-id="c6611-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

