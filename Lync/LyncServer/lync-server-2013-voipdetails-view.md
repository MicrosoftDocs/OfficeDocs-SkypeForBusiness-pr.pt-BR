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
ms.openlocfilehash: 4222ad7251c17501b1d9edec8cbdd8bafc015773
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="2de4a-102">Exibição VoIPDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2de4a-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2de4a-103">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="2de4a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="2de4a-104">O modo de exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde no mínimo um usuário é um usuário VoIP.</span><span class="sxs-lookup"><span data-stu-id="2de4a-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="2de4a-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2de4a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2de4a-106">O modo de exibição VoIPDetails contém todas as colunas no <A href="lync-server-2013-sessiondetails-view.md">modo de exibição SessionDetails no Lync Server 2013</A> , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="2de4a-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2de4a-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="2de4a-107">Column</span></span></th>
<th><span data-ttu-id="2de4a-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2de4a-108">Data Type</span></span></th>
<th><span data-ttu-id="2de4a-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2de4a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2de4a-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2de4a-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-112">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de4a-113"><strong>Por telefone</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2de4a-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-115">URI do telefone do usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2de4a-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2de4a-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-118">URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de4a-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2de4a-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-121">Tipo da URI do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="2de4a-122">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2de4a-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2de4a-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2de4a-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-125">Locatário do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de4a-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2de4a-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-128">URI do telefone do usuário que desconectou da sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2de4a-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2de4a-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-131">Servidor de Mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de4a-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2de4a-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-134">Servidor de Mediação usado pelo usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2de4a-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2de4a-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-137">Gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2de4a-138"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="2de4a-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="2de4a-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2de4a-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2de4a-140">Gateway usado pelo usuário que entrou na sessão.</span><span class="sxs-lookup"><span data-stu-id="2de4a-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

