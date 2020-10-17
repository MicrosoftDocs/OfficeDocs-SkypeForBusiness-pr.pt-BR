---
title: 'Lync Server 2013: modo de exibição de mídia'
description: 'Lync Server 2013: modo de exibição de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558007"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="8d8d3-103">Exibição de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d8d3-103">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d8d3-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8d8d3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8d8d3-105">A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-105">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="8d8d3-106">Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="8d8d3-107">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d8d3-p102">A exibição de mídia não deve ser usada para calcular a duração de mídia para uma sessão. Essa exibição contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação INVITE, e o StartTime indica o horário em que o INVITE foi enviado. O horário de convite não significa, necessariamente, o horário de início da mídia, pois a mídia só começa depois que a sessão tenha sido aceita.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="8d8d3-111">O modo de exibição de mídia contém todas as colunas no [modo de exibição SessionDetails no Lync Server 2013](lync-server-2013-sessiondetails-view.md) , além das listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-111">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d8d3-112">Coluna</span><span class="sxs-lookup"><span data-stu-id="8d8d3-112">Column</span></span></th>
<th><span data-ttu-id="8d8d3-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8d8d3-113">Data Type</span></span></th>
<th><span data-ttu-id="8d8d3-114">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8d8d3-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d8d3-115"><strong>Mídia</strong></span><span class="sxs-lookup"><span data-stu-id="8d8d3-115"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="8d8d3-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8d8d3-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d8d3-117">Tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-117">Media type.</span></span> <span data-ttu-id="8d8d3-118">Consulte a <a href="lync-server-2013-medialist-table.md">tabela medialist no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-118">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d8d3-119"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="8d8d3-119"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8d8d3-120">datetime</span><span class="sxs-lookup"><span data-stu-id="8d8d3-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d8d3-121">Horário em que a solicitação de mídia foi enviada.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-121">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d8d3-122"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="8d8d3-122"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8d8d3-123">datetime</span><span class="sxs-lookup"><span data-stu-id="8d8d3-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d8d3-124">Horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="8d8d3-124">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

