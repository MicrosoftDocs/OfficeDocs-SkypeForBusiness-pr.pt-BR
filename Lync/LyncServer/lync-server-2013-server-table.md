---
title: 'Lync Server 2013: Tabela Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363c07a6ab3be8f5acdf0286a4223f96a8bd3700
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="e38d8-102">Tabela Server no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e38d8-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e38d8-103">_**Tópico da última modificação:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e38d8-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e38d8-104">A tabela do servidor é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e38d8-104">The Server table is a supporting table.</span></span> <span data-ttu-id="e38d8-105">Cada registro representa um servidor.</span><span class="sxs-lookup"><span data-stu-id="e38d8-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e38d8-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e38d8-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e38d8-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e38d8-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e38d8-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e38d8-111">int</span><span class="sxs-lookup"><span data-stu-id="e38d8-111">int</span></span></p></td>
<td><p><span data-ttu-id="e38d8-112">Primária</span><span class="sxs-lookup"><span data-stu-id="e38d8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e38d8-113">Número exclusivo que identifica o servidor.</span><span class="sxs-lookup"><span data-stu-id="e38d8-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e38d8-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="e38d8-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e38d8-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e38d8-116">dedo</span><span class="sxs-lookup"><span data-stu-id="e38d8-116">index</span></span></p></td>
<td><p><span data-ttu-id="e38d8-117">Cadeia de caracteres de endereço MAC.</span><span class="sxs-lookup"><span data-stu-id="e38d8-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e38d8-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="e38d8-119">int</span><span class="sxs-lookup"><span data-stu-id="e38d8-119">int</span></span></p></td>
<td><p><span data-ttu-id="e38d8-120">Exterior</span><span class="sxs-lookup"><span data-stu-id="e38d8-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e38d8-121">1: servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="e38d8-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="e38d8-122">2: a/V Conferência Server16394: A/V Edge service32769: gateway</span><span class="sxs-lookup"><span data-stu-id="e38d8-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e38d8-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="e38d8-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="e38d8-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e38d8-125">Pool ao qual o servidor pertence.</span><span class="sxs-lookup"><span data-stu-id="e38d8-125">Pool the server belongs to.</span></span> <span data-ttu-id="e38d8-126">Aplicável somente para o servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="e38d8-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e38d8-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="e38d8-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="e38d8-128">datetime</span><span class="sxs-lookup"><span data-stu-id="e38d8-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e38d8-129">Somente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e38d8-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

