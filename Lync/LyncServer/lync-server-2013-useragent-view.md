---
title: 'Lync Server 2013: modo de exibição do UserAgent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="068e7-102">Modo de exibição do UserAgent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="068e7-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="068e7-103">_**Tópico da última modificação:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="068e7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="068e7-104">A exibição do UserAgent armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="068e7-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="068e7-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="068e7-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="068e7-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="068e7-106">Column</span></span></th>
<th><span data-ttu-id="068e7-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="068e7-107">Data Type</span></span></th>
<th><span data-ttu-id="068e7-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="068e7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="068e7-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="068e7-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="068e7-110">int</span><span class="sxs-lookup"><span data-stu-id="068e7-110">int</span></span></p></td>
<td><p><span data-ttu-id="068e7-111">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="068e7-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="068e7-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="068e7-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="068e7-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="068e7-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="068e7-114">Cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="068e7-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="068e7-115">UAType</span><span class="sxs-lookup"><span data-stu-id="068e7-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="068e7-116">smallint</span><span class="sxs-lookup"><span data-stu-id="068e7-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="068e7-117">Tipo de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="068e7-117">Type of user agent.</span></span> <span data-ttu-id="068e7-118">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="068e7-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="068e7-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="068e7-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="068e7-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="068e7-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="068e7-121">Categoria à qual o agente do usuário pertence.</span><span class="sxs-lookup"><span data-stu-id="068e7-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="068e7-122">Por exemplo, o agente de usuário Conferencing_Attendant_ 1.0 pertence ao UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="068e7-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

