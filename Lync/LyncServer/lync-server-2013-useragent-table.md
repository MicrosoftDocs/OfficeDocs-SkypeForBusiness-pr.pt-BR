---
title: 'Lync Server 2013: tabela UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 041db946d80226f626b7248f604f1b3fa00a7ffc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="4f806-102">Tabela UserAgent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f806-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f806-103">_**Última modificação do tópico:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="4f806-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="4f806-104">A tabela UserAgent é uma tabela de suporte que armazena uma lista dos vários agentes de usuário que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="4f806-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4f806-105">Cada registro da tabela representa um agente do usuário</span><span class="sxs-lookup"><span data-stu-id="4f806-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f806-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="4f806-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4f806-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="4f806-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4f806-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="4f806-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4f806-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="4f806-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f806-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="4f806-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4f806-111">int</span><span class="sxs-lookup"><span data-stu-id="4f806-111">int</span></span></p></td>
<td><p><span data-ttu-id="4f806-112">Primário</span><span class="sxs-lookup"><span data-stu-id="4f806-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4f806-113">Número exclusivo que identifica esse agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="4f806-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f806-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="4f806-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="4f806-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4f806-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4f806-116">Diferente</span><span class="sxs-lookup"><span data-stu-id="4f806-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="4f806-117">Cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="4f806-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f806-118"><strong>Uatype do</strong></span><span class="sxs-lookup"><span data-stu-id="4f806-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="4f806-119">smallint</span><span class="sxs-lookup"><span data-stu-id="4f806-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4f806-120">1 é o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="4f806-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="4f806-121">2 é o servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="4f806-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="4f806-122">4 é o Lync.</span><span class="sxs-lookup"><span data-stu-id="4f806-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="4f806-123">8 é o telefone IP.</span><span class="sxs-lookup"><span data-stu-id="4f806-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="4f806-124">16 é o console do Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="4f806-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="4f806-125">32 é a ferramenta de validação de implantação (DVT).</span><span class="sxs-lookup"><span data-stu-id="4f806-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="4f806-126">64 é Lync em computadores Macintosh.</span><span class="sxs-lookup"><span data-stu-id="4f806-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="4f806-127">128 é o Office Communications Server 2007 R2 Attendant.</span><span class="sxs-lookup"><span data-stu-id="4f806-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="4f806-128">256 é serviço de anúncio de conferência.</span><span class="sxs-lookup"><span data-stu-id="4f806-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="4f806-129">512 é o atendedor automático de conferência.</span><span class="sxs-lookup"><span data-stu-id="4f806-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="4f806-130">1024 é o aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="4f806-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="4f806-131">2048 está fora do controle de voz.</span><span class="sxs-lookup"><span data-stu-id="4f806-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

