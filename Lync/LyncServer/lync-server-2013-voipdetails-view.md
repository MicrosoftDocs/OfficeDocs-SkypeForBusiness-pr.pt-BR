---
title: 'Lync Server 2013: modo de exibição VoIPDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="5bff1-102">Exibição VoIPDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bff1-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bff1-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="5bff1-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="5bff1-104">A exibição VoIPDetails armazena informações sobre sessões ponto a ponto, onde pelo menos um usuário é um usuário de VoIP.</span><span class="sxs-lookup"><span data-stu-id="5bff1-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="5bff1-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5bff1-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5bff1-106">A exibição VoIPDetails contém todas as colunas na <A href="lync-server-2013-sessiondetails-view.md">exibição SessionDetails do Lync Server 2013</A> , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="5bff1-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bff1-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="5bff1-107">Column</span></span></th>
<th><span data-ttu-id="5bff1-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="5bff1-108">Data Type</span></span></th>
<th><span data-ttu-id="5bff1-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5bff1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bff1-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5bff1-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-112">URI do telefone do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bff1-113"><strong>Por telefone</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5bff1-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-115">URI do telefone do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bff1-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5bff1-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-118">URL do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bff1-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5bff1-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-121">Tipo de URI do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="5bff1-122">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5bff1-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bff1-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5bff1-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-125">Locatário do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bff1-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5bff1-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-128">URI do telefone do usuário que desconectou a sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bff1-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5bff1-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-131">Servidor de mediação usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bff1-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5bff1-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-134">Servidor de mediação usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bff1-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5bff1-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-137">O gateway usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bff1-138"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="5bff1-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="5bff1-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5bff1-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5bff1-140">O gateway usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="5bff1-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

