---
title: 'Lync Server 2013: Tabela Media'
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
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="905f1-102">Tabela Media no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="905f1-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="905f1-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="905f1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="905f1-104">Cada registro representa um tipo de mídia usado em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="905f1-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="905f1-105">Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado.</span><span class="sxs-lookup"><span data-stu-id="905f1-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="905f1-106">A tabela de mídia não deve ser usada para calcular a duração da mídia de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="905f1-107">Esta tabela contém os detalhes de sinalização da troca de mídia em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="905f1-108">A troca de mídia é feita pela solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convite não necessariamente significa a hora de início da mídia porque a mídia só inicia depois que a sessão aceita a sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="905f1-109">A EndTime geralmente significa a hora de término desta sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="905f1-110">Coluna</span><span class="sxs-lookup"><span data-stu-id="905f1-110">Column</span></span></th>
<th><span data-ttu-id="905f1-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="905f1-111">Data Type</span></span></th>
<th><span data-ttu-id="905f1-112">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="905f1-112">Key/Index</span></span></th>
<th><span data-ttu-id="905f1-113">Detalhes</span><span class="sxs-lookup"><span data-stu-id="905f1-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="905f1-114"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="905f1-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="905f1-115">datetime</span><span class="sxs-lookup"><span data-stu-id="905f1-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="905f1-116">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="905f1-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="905f1-117">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-117">Time of session request.</span></span> <span data-ttu-id="905f1-118">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="905f1-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="905f1-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="905f1-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="905f1-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="905f1-121">int</span><span class="sxs-lookup"><span data-stu-id="905f1-121">int</span></span></p></td>
<td><p><span data-ttu-id="905f1-122">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="905f1-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="905f1-123">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-123">ID number to identify the session.</span></span> <span data-ttu-id="905f1-124">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="905f1-125">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="905f1-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="905f1-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="905f1-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="905f1-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="905f1-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="905f1-128">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="905f1-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="905f1-129">Número exclusivo que identifica esse tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="905f1-129">Unique number identifying this media type.</span></span> <span data-ttu-id="905f1-130">Consulte a <a href="lync-server-2013-medialist-table.md">tabela medialist no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="905f1-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="905f1-131"><strong>StartTime </strong></span><span class="sxs-lookup"><span data-stu-id="905f1-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="905f1-132">datetime</span><span class="sxs-lookup"><span data-stu-id="905f1-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="905f1-133">Primária</span><span class="sxs-lookup"><span data-stu-id="905f1-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="905f1-134">Esta é a hora em que uma solicitação de mídia foi enviada, e não a hora de início da mídia real.</span><span class="sxs-lookup"><span data-stu-id="905f1-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="905f1-135"><strong>StartTime</strong> inclui o tempo de configuração da sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="905f1-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="905f1-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="905f1-137">datetime</span><span class="sxs-lookup"><span data-stu-id="905f1-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="905f1-138">Esta é a hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="905f1-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

