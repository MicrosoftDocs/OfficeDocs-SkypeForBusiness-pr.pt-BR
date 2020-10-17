---
title: 'Lync Server 2013: tabela ConferenceUris'
description: 'Lync Server 2013: tabela ConferenceUris.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566737"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="92fc9-103">Tabela ConferenceUris no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92fc9-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92fc9-104">_**Última modificação do tópico:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="92fc9-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="92fc9-p101">A tabela ConferenceUris é uma tabela de suporte que armazena uma lista de diversos URIs de conferência que participaram de sessões de conferência gravadas no banco de dados. Cada registro da tabela representa um pool.</span><span class="sxs-lookup"><span data-stu-id="92fc9-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92fc9-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="92fc9-107">Column</span></span></th>
<th><span data-ttu-id="92fc9-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="92fc9-108">Data Type</span></span></th>
<th><span data-ttu-id="92fc9-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="92fc9-109">Key/Index</span></span></th>
<th><span data-ttu-id="92fc9-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="92fc9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92fc9-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="92fc9-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="92fc9-112">datetime</span><span class="sxs-lookup"><span data-stu-id="92fc9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="92fc9-113">Primário</span><span class="sxs-lookup"><span data-stu-id="92fc9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="92fc9-114">Carimbo de hora, Interno usado.</span><span class="sxs-lookup"><span data-stu-id="92fc9-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92fc9-115"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="92fc9-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="92fc9-116">int</span><span class="sxs-lookup"><span data-stu-id="92fc9-116">int</span></span></p></td>
<td><p><span data-ttu-id="92fc9-117">Primário</span><span class="sxs-lookup"><span data-stu-id="92fc9-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="92fc9-118">Número exclusivo que identifica o URI desta conferência.</span><span class="sxs-lookup"><span data-stu-id="92fc9-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92fc9-119"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="92fc9-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="92fc9-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="92fc9-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92fc9-121">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="92fc9-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92fc9-122"><strong>Soma de verificação</strong></span><span class="sxs-lookup"><span data-stu-id="92fc9-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="92fc9-123">int</span><span class="sxs-lookup"><span data-stu-id="92fc9-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92fc9-p102">Soma de verificação do ConferenceUri. Usado para aumentar a velocidade de pesquisas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="92fc9-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92fc9-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="92fc9-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="92fc9-127">int</span><span class="sxs-lookup"><span data-stu-id="92fc9-127">int</span></span></p></td>
<td><p><span data-ttu-id="92fc9-128">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="92fc9-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="92fc9-129">Tipo de URI, por exemplo, conf:chat para conferência IM ou conf:audio-video para conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="92fc9-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="92fc9-130">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes na tabela do Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="92fc9-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

