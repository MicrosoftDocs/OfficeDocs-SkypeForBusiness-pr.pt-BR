---
title: 'Lync Server 2013: exibição do UserAgent'
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
ms.openlocfilehash: cb9e70635fc4c54448f6fe3f549d3d6853612070
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530118"
---
# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="2bfa5-102">Exibição UserAgent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bfa5-102">UserAgent view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bfa5-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2bfa5-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2bfa5-104">A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2bfa5-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="2bfa5-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2bfa5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2bfa5-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="2bfa5-106">Column</span></span></th>
<th><span data-ttu-id="2bfa5-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2bfa5-107">Data Type</span></span></th>
<th><span data-ttu-id="2bfa5-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="2bfa5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bfa5-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="2bfa5-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="2bfa5-110">int</span><span class="sxs-lookup"><span data-stu-id="2bfa5-110">int</span></span></p></td>
<td><p><span data-ttu-id="2bfa5-111">Número exclusivo que identifica esse agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="2bfa5-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bfa5-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="2bfa5-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="2bfa5-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2bfa5-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2bfa5-114">Cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="2bfa5-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bfa5-115">Uatype do</span><span class="sxs-lookup"><span data-stu-id="2bfa5-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="2bfa5-116">smallint</span><span class="sxs-lookup"><span data-stu-id="2bfa5-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="2bfa5-117">Tipo de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="2bfa5-117">Type of user agent.</span></span> <span data-ttu-id="2bfa5-118">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="2bfa5-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bfa5-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="2bfa5-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="2bfa5-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2bfa5-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2bfa5-p103">Categoria que o agente do usuário pertence. Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence à UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="2bfa5-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

