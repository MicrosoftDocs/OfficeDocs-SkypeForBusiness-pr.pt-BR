---
title: 'Lync Server 2013: tabela de mídia'
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
ms.openlocfilehash: 92bd1abb28b74fe7f2c46ad89d713a9b6244f4c3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="46c6c-102">Tabela de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46c6c-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46c6c-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="46c6c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="46c6c-p101">Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto. Uma sessão será representada por vários registros na tabela se mais de um tipo de mídia for usado.</span><span class="sxs-lookup"><span data-stu-id="46c6c-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46c6c-p102">A tabela de Mídia não deve ser usada para calcular a duração da mídia de uma sessão. Esta tabela contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é realizada pela solicitação INVITE e StartTime indica a hora que INVITE foi enviado. O horário do convite não necessariamente significa a hora inicial da mídia, porque a mídia começa apenas após o participante aceitar a sessão. O EndTime geralmente significa a hora final desta sessão.</span><span class="sxs-lookup"><span data-stu-id="46c6c-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="46c6c-110">Coluna</span><span class="sxs-lookup"><span data-stu-id="46c6c-110">Column</span></span></th>
<th><span data-ttu-id="46c6c-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="46c6c-111">Data Type</span></span></th>
<th><span data-ttu-id="46c6c-112">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="46c6c-112">Key/Index</span></span></th>
<th><span data-ttu-id="46c6c-113">Detalhes</span><span class="sxs-lookup"><span data-stu-id="46c6c-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46c6c-114"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="46c6c-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="46c6c-115">datetime</span><span class="sxs-lookup"><span data-stu-id="46c6c-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="46c6c-116">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="46c6c-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="46c6c-117">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="46c6c-117">Time of session request.</span></span> <span data-ttu-id="46c6c-118">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="46c6c-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="46c6c-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="46c6c-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46c6c-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="46c6c-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="46c6c-121">int</span><span class="sxs-lookup"><span data-stu-id="46c6c-121">int</span></span></p></td>
<td><p><span data-ttu-id="46c6c-122">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="46c6c-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="46c6c-123">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="46c6c-123">ID number to identify the session.</span></span> <span data-ttu-id="46c6c-124">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="46c6c-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="46c6c-125">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="46c6c-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46c6c-126"><strong>Mediaid</strong></span><span class="sxs-lookup"><span data-stu-id="46c6c-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="46c6c-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="46c6c-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="46c6c-128">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="46c6c-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="46c6c-129">Número exclusivo identificando este tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="46c6c-129">Unique number identifying this media type.</span></span> <span data-ttu-id="46c6c-130">Consulte a <a href="lync-server-2013-medialist-table.md">tabela medialist no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="46c6c-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46c6c-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="46c6c-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="46c6c-132">datetime</span><span class="sxs-lookup"><span data-stu-id="46c6c-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="46c6c-133">Primário</span><span class="sxs-lookup"><span data-stu-id="46c6c-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="46c6c-p106">Este é o horário em que a solicitação de mídia foi enviada, não o horário de início de mídia real. O <strong>StartTime</strong> inclui a hora de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="46c6c-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46c6c-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="46c6c-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="46c6c-137">datetime</span><span class="sxs-lookup"><span data-stu-id="46c6c-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="46c6c-138">Este é o horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="46c6c-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

