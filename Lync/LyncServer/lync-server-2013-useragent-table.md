---
title: 'Lync Server 2013: Tabela UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09bb2e3a71f81014bcb08952c03b59c93ac6a62f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="682d2-102">Tabela UserAgent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="682d2-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="682d2-103">_**Tópico da última modificação:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="682d2-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="682d2-104">A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="682d2-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="682d2-105">Cada registro na tabela representa um agente do usuário</span><span class="sxs-lookup"><span data-stu-id="682d2-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="682d2-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="682d2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="682d2-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="682d2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="682d2-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="682d2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="682d2-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="682d2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="682d2-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="682d2-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="682d2-111">int</span><span class="sxs-lookup"><span data-stu-id="682d2-111">int</span></span></p></td>
<td><p><span data-ttu-id="682d2-112">Primária</span><span class="sxs-lookup"><span data-stu-id="682d2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="682d2-113">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="682d2-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="682d2-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="682d2-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="682d2-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="682d2-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="682d2-116">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="682d2-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="682d2-117">Cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="682d2-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="682d2-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="682d2-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="682d2-119">smallint</span><span class="sxs-lookup"><span data-stu-id="682d2-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="682d2-120">1 é o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="682d2-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="682d2-121">2 é um servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="682d2-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="682d2-122">4 é o Lync.</span><span class="sxs-lookup"><span data-stu-id="682d2-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="682d2-123">8 é o telefone IP.</span><span class="sxs-lookup"><span data-stu-id="682d2-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="682d2-124">16 é o console do Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="682d2-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="682d2-125">o 32 é uma ferramenta de validação de implantação (DVT).</span><span class="sxs-lookup"><span data-stu-id="682d2-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="682d2-126">o 64 é o Lync em computadores Macintosh.</span><span class="sxs-lookup"><span data-stu-id="682d2-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="682d2-127">o 128 é o Office Communications Server 2007 R2 Attendant.</span><span class="sxs-lookup"><span data-stu-id="682d2-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="682d2-128">o 256 é o serviço de anúncio de conferências.</span><span class="sxs-lookup"><span data-stu-id="682d2-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="682d2-129">o 512 é o atendedor automático da conferência.</span><span class="sxs-lookup"><span data-stu-id="682d2-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="682d2-130">o 1024 é um aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="682d2-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="682d2-131">2048 está fora do controle de voz.</span><span class="sxs-lookup"><span data-stu-id="682d2-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

