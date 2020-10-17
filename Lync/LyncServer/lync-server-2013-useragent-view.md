---
title: 'Lync Server 2013: exibição do UserAgent'
description: 'Lync Server 2013: exibição UserAgent.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9fc5ef2ec01b50f3714dca3690d0844286baaef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558857"
---
# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="82948-103">Exibição UserAgent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82948-103">UserAgent view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82948-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="82948-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="82948-105">A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="82948-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="82948-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82948-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82948-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="82948-107">Column</span></span></th>
<th><span data-ttu-id="82948-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="82948-108">Data Type</span></span></th>
<th><span data-ttu-id="82948-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="82948-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82948-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="82948-110">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="82948-111">int</span><span class="sxs-lookup"><span data-stu-id="82948-111">int</span></span></p></td>
<td><p><span data-ttu-id="82948-112">Número exclusivo que identifica esse agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="82948-112">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82948-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="82948-113">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="82948-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82948-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82948-115">Cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="82948-115">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82948-116">Uatype do</span><span class="sxs-lookup"><span data-stu-id="82948-116">UAType</span></span></p></td>
<td><p><span data-ttu-id="82948-117">smallint</span><span class="sxs-lookup"><span data-stu-id="82948-117">smallint</span></span></p></td>
<td><p><span data-ttu-id="82948-118">Tipo de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="82948-118">Type of user agent.</span></span> <span data-ttu-id="82948-119">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="82948-119">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82948-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="82948-120">UACategory</span></span></p></td>
<td><p><span data-ttu-id="82948-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="82948-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="82948-p103">Categoria que o agente do usuário pertence. Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence à UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="82948-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

