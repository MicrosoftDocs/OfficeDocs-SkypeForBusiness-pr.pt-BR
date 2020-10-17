---
title: 'Lync Server 2013: modo de exibição de mídia'
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
ms.openlocfilehash: d0e6cd8658278a8d7798153698355f5a73f2952b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516148"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="7a707-102">Exibição de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a707-102">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a707-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7a707-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7a707-104">A exibição de mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="7a707-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="7a707-105">Uma sessão será representada por vários registros na tabela caso mais de um tipo de mídia seja usado.</span><span class="sxs-lookup"><span data-stu-id="7a707-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="7a707-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a707-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a707-p102">A exibição de mídia não deve ser usada para calcular a duração de mídia para uma sessão. Essa exibição contém os detalhes de sinalização da troca de mídia em uma sessão. A troca de mídia é feita pela solicitação INVITE, e o StartTime indica o horário em que o INVITE foi enviado. O horário de convite não significa, necessariamente, o horário de início da mídia, pois a mídia só começa depois que a sessão tenha sido aceita.</span><span class="sxs-lookup"><span data-stu-id="7a707-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="7a707-110">O modo de exibição de mídia contém todas as colunas no [modo de exibição SessionDetails no Lync Server 2013](lync-server-2013-sessiondetails-view.md) , além das listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="7a707-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a707-111">Coluna</span><span class="sxs-lookup"><span data-stu-id="7a707-111">Column</span></span></th>
<th><span data-ttu-id="7a707-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="7a707-112">Data Type</span></span></th>
<th><span data-ttu-id="7a707-113">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7a707-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a707-114"><strong>Mídia</strong></span><span class="sxs-lookup"><span data-stu-id="7a707-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="7a707-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7a707-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7a707-116">Tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="7a707-116">Media type.</span></span> <span data-ttu-id="7a707-117">Consulte a <a href="lync-server-2013-medialist-table.md">tabela medialist no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7a707-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a707-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="7a707-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7a707-119">datetime</span><span class="sxs-lookup"><span data-stu-id="7a707-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="7a707-120">Horário em que a solicitação de mídia foi enviada.</span><span class="sxs-lookup"><span data-stu-id="7a707-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a707-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="7a707-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7a707-122">datetime</span><span class="sxs-lookup"><span data-stu-id="7a707-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="7a707-123">Horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="7a707-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

