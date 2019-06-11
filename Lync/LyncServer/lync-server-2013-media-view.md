---
title: 'Lync Server 2013: modo de exibição de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="bb2f8-102">Modo de exibição de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb2f8-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb2f8-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="bb2f8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="bb2f8-104">O modo de exibição mídia armazena informações sobre um tipo de mídia usado em uma sessão ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="bb2f8-105">Uma sessão seria representada por vários registros na tabela, se mais de um tipo de mídia for usado.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="bb2f8-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bb2f8-107">O modo de exibição de mídia não deve ser usado para calcular a duração da mídia de uma sessão.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="bb2f8-108">Este modo de exibição contém os detalhes de sinalização da troca de mídia em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="bb2f8-109">A troca de mídia é feita pela solicitação de convite e StartTime indica a hora em que o convite foi enviado. O tempo de convite não significa necessariamente a hora de início da mídia porque a mídia só inicia após a aceitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="bb2f8-110">O modo de exibição de mídia contém todas as colunas na [exibição SessionDetails no Lync Server 2013](lync-server-2013-sessiondetails-view.md) , além das listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb2f8-111">Coluna</span><span class="sxs-lookup"><span data-stu-id="bb2f8-111">Column</span></span></th>
<th><span data-ttu-id="bb2f8-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="bb2f8-112">Data Type</span></span></th>
<th><span data-ttu-id="bb2f8-113">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bb2f8-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb2f8-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="bb2f8-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="bb2f8-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bb2f8-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bb2f8-116">Tipo de mídia.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-116">Media type.</span></span> <span data-ttu-id="bb2f8-117">Consulte a <a href="lync-server-2013-medialist-table.md">tabela medialist no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb2f8-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb2f8-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb2f8-119">datetime</span><span class="sxs-lookup"><span data-stu-id="bb2f8-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb2f8-120">Tempo em que uma solicitação de mídia foi enviada.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb2f8-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="bb2f8-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bb2f8-122">datetime</span><span class="sxs-lookup"><span data-stu-id="bb2f8-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="bb2f8-123">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="bb2f8-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

