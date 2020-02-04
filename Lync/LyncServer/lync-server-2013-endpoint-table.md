---
title: 'Lync Server 2013: Tabela Endpoint'
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
ms.openlocfilehash: 11da225da1a8120f5de7ac21b3beb318326601f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="f502c-102">Tabela Endpoint no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f502c-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f502c-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f502c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f502c-104">A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram em sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f502c-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f502c-105">Cada registro na tabela representa um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f502c-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f502c-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f502c-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f502c-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f502c-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f502c-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f502c-111">int</span><span class="sxs-lookup"><span data-stu-id="f502c-111">int</span></span></p></td>
<td><p><span data-ttu-id="f502c-112">Primária</span><span class="sxs-lookup"><span data-stu-id="f502c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f502c-113">Número exclusivo que identifica esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f502c-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f502c-114"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="f502c-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f502c-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f502c-116">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="f502c-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="f502c-117">Nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f502c-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f502c-118"><strong>Sistema operacional</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="f502c-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f502c-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f502c-120">Sistema operacional (SO) da empresa.</span><span class="sxs-lookup"><span data-stu-id="f502c-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f502c-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="f502c-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="f502c-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f502c-123">Nome da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f502c-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f502c-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="f502c-125">smallint</span><span class="sxs-lookup"><span data-stu-id="f502c-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f502c-126">Número de núcleos da CPU da empresa.</span><span class="sxs-lookup"><span data-stu-id="f502c-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f502c-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="f502c-128">int</span><span class="sxs-lookup"><span data-stu-id="f502c-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f502c-129">Velocidade do processador da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f502c-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f502c-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f502c-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f502c-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="f502c-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f502c-132">Sinalizador de bit que indica se o sistema está em execução em um ambiente virtualizado:</span><span class="sxs-lookup"><span data-stu-id="f502c-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="f502c-133">0x0000 – nenhum</span><span class="sxs-lookup"><span data-stu-id="f502c-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="f502c-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="f502c-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="f502c-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="f502c-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="f502c-136">0x0004 – Virtual PC</span><span class="sxs-lookup"><span data-stu-id="f502c-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="f502c-137">0x0008 – computador Xen</span><span class="sxs-lookup"><span data-stu-id="f502c-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

