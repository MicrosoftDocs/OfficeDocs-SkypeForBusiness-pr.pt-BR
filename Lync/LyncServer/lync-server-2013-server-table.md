---
title: 'Lync Server 2013: tabela de servidor'
description: 'Lync Server 2013: tabela de servidor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00990a91aec64063480d96a16380171990913ad4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576517"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="39b91-103">Tabela de servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39b91-103">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b91-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="39b91-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="39b91-105">A tabela do servidor é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="39b91-105">The Server table is a supporting table.</span></span> <span data-ttu-id="39b91-106">Cada registro representa um servidor.</span><span class="sxs-lookup"><span data-stu-id="39b91-106">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="39b91-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="39b91-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="39b91-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="39b91-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39b91-111"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-111"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="39b91-112">int</span><span class="sxs-lookup"><span data-stu-id="39b91-112">int</span></span></p></td>
<td><p><span data-ttu-id="39b91-113">Primário</span><span class="sxs-lookup"><span data-stu-id="39b91-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="39b91-114">Número exclusivo que identifica o servidor.</span><span class="sxs-lookup"><span data-stu-id="39b91-114">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b91-115"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-115"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="39b91-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="39b91-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="39b91-117">index</span><span class="sxs-lookup"><span data-stu-id="39b91-117">index</span></span></p></td>
<td><p><span data-ttu-id="39b91-118">Cadeia de caracteres de endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="39b91-118">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b91-119"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-119"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="39b91-120">int</span><span class="sxs-lookup"><span data-stu-id="39b91-120">int</span></span></p></td>
<td><p><span data-ttu-id="39b91-121">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="39b91-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="39b91-122">1: servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="39b91-122">1: Mediation Server</span></span></p>
<p><span data-ttu-id="39b91-123">2: Server16394 de conferência a/V: service32769 de borda A/V: gateway</span><span class="sxs-lookup"><span data-stu-id="39b91-123">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39b91-124"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-124"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="39b91-125">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="39b91-125">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b91-126">Pool ao qual o servidor pertence.</span><span class="sxs-lookup"><span data-stu-id="39b91-126">Pool the server belongs to.</span></span> <span data-ttu-id="39b91-127">Aplicável somente para o servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="39b91-127">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="39b91-128"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="39b91-128"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="39b91-129">datetime</span><span class="sxs-lookup"><span data-stu-id="39b91-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="39b91-130">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="39b91-130">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

