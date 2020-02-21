---
title: 'Lync Server 2013: modo de exibição VoIPDetails'
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
ms.openlocfilehash: 7911a203a46d9bfa5698d01dc43c27c5f789c89a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="b9ee6-102">Exibição VoIPDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9ee6-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9ee6-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b9ee6-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b9ee6-104">O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="b9ee6-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9ee6-106">O modo de exibição VoIPDetails contém todas as colunas no <A href="lync-server-2013-sessiondetails-view.md">modo de exibição SessionDetails no Lync Server 2013</A> , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9ee6-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="b9ee6-107">Column</span></span></th>
<th><span data-ttu-id="b9ee6-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b9ee6-108">Data Type</span></span></th>
<th><span data-ttu-id="b9ee6-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b9ee6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9ee6-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-112">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee6-113"><strong>Por telefone</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-115">URI do telefone do usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee6-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-118">URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee6-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-121">Tipo da URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="b9ee6-122">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee6-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-125">Locatário do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee6-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-128">URI do telefone do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee6-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-131">Servidor de Mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee6-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-134">Servidor de Mediação usado pelo usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ee6-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-137">Gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ee6-138"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="b9ee6-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ee6-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9ee6-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9ee6-140">Gateway usado pelo usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="b9ee6-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

