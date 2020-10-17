---
title: 'Lync Server 2013: modo de exibição VoIPDetails'
description: 'Lync Server 2013: modo de exibição VoIPDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566197"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="e4dd1-103">Exibição VoIPDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4dd1-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4dd1-104">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e4dd1-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e4dd1-105">O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="e4dd1-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4dd1-107">O modo de exibição VoIPDetails contém todas as colunas no <A href="lync-server-2013-sessiondetails-view.md">modo de exibição SessionDetails no Lync Server 2013</A> , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4dd1-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="e4dd1-108">Column</span></span></th>
<th><span data-ttu-id="e4dd1-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e4dd1-109">Data Type</span></span></th>
<th><span data-ttu-id="e4dd1-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e4dd1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4dd1-111"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-113">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4dd1-114"><strong>Por telefone</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-116">URI do telefone do usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4dd1-117"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-119">URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4dd1-120"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-122">Tipo da URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="e4dd1-123">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4dd1-124"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-126">Locatário do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4dd1-127"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-129">URI do telefone do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4dd1-130"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-132">Servidor de Mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4dd1-133"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-135">Servidor de Mediação usado pelo usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4dd1-136"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-138">Gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4dd1-139"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="e4dd1-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e4dd1-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e4dd1-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e4dd1-141">Gateway usado pelo usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="e4dd1-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

