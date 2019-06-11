---
title: 'Lync Server 2013: tabela ErrorCategory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9bd9cebf26a147b00873c17372eca77f0a11f2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="505bd-102">Tabela ErrorCategory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="505bd-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="505bd-103">_**Tópico da última modificação:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="505bd-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="505bd-104">A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="505bd-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="505bd-105">Por padrão, o Lync Server 2013 usa as seguintes classificações:</span><span class="sxs-lookup"><span data-stu-id="505bd-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="505bd-106">0--sucesso</span><span class="sxs-lookup"><span data-stu-id="505bd-106">0 -- Success</span></span>

  - <span data-ttu-id="505bd-107">1--falha prevista</span><span class="sxs-lookup"><span data-stu-id="505bd-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="505bd-108">2 – falha inesperada</span><span class="sxs-lookup"><span data-stu-id="505bd-108">2 – Unexpected failure</span></span>

<span data-ttu-id="505bd-109">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="505bd-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="505bd-110">Coluna</span><span class="sxs-lookup"><span data-stu-id="505bd-110">Column</span></span></th>
<th><span data-ttu-id="505bd-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="505bd-111">Data Type</span></span></th>
<th><span data-ttu-id="505bd-112">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="505bd-112">Key/Index</span></span></th>
<th><span data-ttu-id="505bd-113">Detalhes</span><span class="sxs-lookup"><span data-stu-id="505bd-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="505bd-114"><strong>CódigoDaCategoria</strong></span><span class="sxs-lookup"><span data-stu-id="505bd-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="505bd-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="505bd-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="505bd-116">Primária</span><span class="sxs-lookup"><span data-stu-id="505bd-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="505bd-117">Identificador exclusivo da classificação.</span><span class="sxs-lookup"><span data-stu-id="505bd-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="505bd-118"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="505bd-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="505bd-119">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="505bd-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="505bd-120">Valor e nome amigável atribuídos à classificação.</span><span class="sxs-lookup"><span data-stu-id="505bd-120">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="505bd-121">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="505bd-121">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="505bd-122">0--sucesso</span><span class="sxs-lookup"><span data-stu-id="505bd-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="505bd-123">1--falha prevista</span><span class="sxs-lookup"><span data-stu-id="505bd-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="505bd-124">2 – falha inesperada</span><span class="sxs-lookup"><span data-stu-id="505bd-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

