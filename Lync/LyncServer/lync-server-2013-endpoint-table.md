---
title: 'Lync Server 2013: tabela de pontos de extremidade'
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
ms.openlocfilehash: 201e2ae3b44f59f0edb128f58af6c18e18e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="a775e-102">Tabela de pontos de extremidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a775e-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a775e-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a775e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a775e-104">A tabela de pontos de extremidade é uma tabela de suporte que armazena informações sobre os pontos de extremidade que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a775e-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="a775e-105">Cada registro da tabela representa um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a775e-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a775e-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a775e-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a775e-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a775e-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a775e-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="a775e-111">int</span><span class="sxs-lookup"><span data-stu-id="a775e-111">int</span></span></p></td>
<td><p><span data-ttu-id="a775e-112">Primário</span><span class="sxs-lookup"><span data-stu-id="a775e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a775e-113">Número exclusivo que identifica esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a775e-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a775e-114"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="a775e-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a775e-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a775e-116">Diferente</span><span class="sxs-lookup"><span data-stu-id="a775e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="a775e-117">Nome do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a775e-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a775e-118"><strong>Opera</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="a775e-119">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a775e-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a775e-120">Sistema operacional (OS) do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a775e-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a775e-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="a775e-122">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="a775e-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a775e-123">Nome da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a775e-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a775e-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="a775e-125">smallint</span><span class="sxs-lookup"><span data-stu-id="a775e-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a775e-126">Número de núcleos da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a775e-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a775e-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="a775e-128">int</span><span class="sxs-lookup"><span data-stu-id="a775e-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a775e-129">Velocidade do processador da CPU do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="a775e-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a775e-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a775e-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a775e-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="a775e-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a775e-132">Sinalizador de bit que indica se o sistema está em execução em um ambiente virtualizado:</span><span class="sxs-lookup"><span data-stu-id="a775e-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="a775e-133">0x0000 – nenhum</span><span class="sxs-lookup"><span data-stu-id="a775e-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="a775e-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="a775e-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="a775e-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="a775e-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="a775e-136">0x0004 – Virtual PC</span><span class="sxs-lookup"><span data-stu-id="a775e-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="a775e-137">0x0008 – PC Xen</span><span class="sxs-lookup"><span data-stu-id="a775e-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

