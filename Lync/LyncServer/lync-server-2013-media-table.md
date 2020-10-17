---
title: 'Lync Server 2013: tabela de mídia'
description: 'Lync Server 2013: tabela de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e30d1f91c59b8e3aa7915fc0d513618d0f709f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558027"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="c7c59-103">Tabela de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7c59-103">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7c59-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c7c59-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c7c59-p101">Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela se mais de um tipo de mídia for usado.</span><span class="sxs-lookup"><span data-stu-id="c7c59-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7c59-p102">A tabela de Mídia não deve ser usada para calcular a duração da mídia de uma sessão. Esta tabela contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é realizada pela solicitação INVITE e StartTime indica a hora que INVITE foi enviado. O horário do convite não necessariamente significa a hora inicial da mídia, porque a mídia começa apenas após o participante aceitar a sessão. O EndTime geralmente significa a hora final desta sessão.</span><span class="sxs-lookup"><span data-stu-id="c7c59-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7c59-111">Coluna</span><span class="sxs-lookup"><span data-stu-id="c7c59-111">Column</span></span></th>
<th><span data-ttu-id="c7c59-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c7c59-112">Data Type</span></span></th>
<th><span data-ttu-id="c7c59-113">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="c7c59-113">Key/Index</span></span></th>
<th><span data-ttu-id="c7c59-114">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c7c59-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7c59-115"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="c7c59-115"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7c59-116">datetime</span><span class="sxs-lookup"><span data-stu-id="c7c59-116">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7c59-117">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="c7c59-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7c59-118">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="c7c59-118">Time of session request.</span></span> <span data-ttu-id="c7c59-119">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="c7c59-119">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c7c59-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c7c59-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7c59-121"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c7c59-121"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c7c59-122">int</span><span class="sxs-lookup"><span data-stu-id="c7c59-122">int</span></span></p></td>
<td><p><span data-ttu-id="c7c59-123">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="c7c59-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7c59-124">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="c7c59-124">ID number to identify the session.</span></span> <span data-ttu-id="c7c59-125">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="c7c59-125">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c7c59-126">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c7c59-126">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7c59-127"><strong>Mediaid</strong></span><span class="sxs-lookup"><span data-stu-id="c7c59-127"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="c7c59-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="c7c59-128">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c7c59-129">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c7c59-129">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c7c59-130">Número exclusivo identificando este tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="c7c59-130">Unique number identifying this media type.</span></span> <span data-ttu-id="c7c59-131">Consulte a <a href="lync-server-2013-medialist-table.md">tabela medialist no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c7c59-131">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7c59-132"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="c7c59-132"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7c59-133">datetime</span><span class="sxs-lookup"><span data-stu-id="c7c59-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="c7c59-134">Primário</span><span class="sxs-lookup"><span data-stu-id="c7c59-134">Primary</span></span></p></td>
<td><p><span data-ttu-id="c7c59-p106">Este é o horário em que a solicitação de mídia foi enviada, não o horário de início de mídia real. O <strong>StartTime</strong> inclui a hora de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="c7c59-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7c59-137"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c7c59-137"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c7c59-138">datetime</span><span class="sxs-lookup"><span data-stu-id="c7c59-138">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c7c59-139">Este é o horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="c7c59-139">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

