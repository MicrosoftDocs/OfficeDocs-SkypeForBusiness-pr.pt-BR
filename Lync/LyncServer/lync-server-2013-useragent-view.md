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
ms.openlocfilehash: 7b82d8a03f159aa1c99d53dd06a0811847f77b12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="55313-102">Exibição UserAgent no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55313-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55313-103">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="55313-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="55313-104">A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55313-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="55313-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55313-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55313-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="55313-106">Column</span></span></th>
<th><span data-ttu-id="55313-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="55313-107">Data Type</span></span></th>
<th><span data-ttu-id="55313-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="55313-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55313-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="55313-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="55313-110">int</span><span class="sxs-lookup"><span data-stu-id="55313-110">int</span></span></p></td>
<td><p><span data-ttu-id="55313-111">Número exclusivo que identifica esse agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="55313-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55313-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="55313-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="55313-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55313-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55313-114">Cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="55313-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55313-115">Uatype do</span><span class="sxs-lookup"><span data-stu-id="55313-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="55313-116">smallint</span><span class="sxs-lookup"><span data-stu-id="55313-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="55313-117">Tipo de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="55313-117">Type of user agent.</span></span> <span data-ttu-id="55313-118">Consulte a <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="55313-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55313-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="55313-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="55313-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="55313-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="55313-p103">Categoria que o agente do usuário pertence. Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence à UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="55313-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

