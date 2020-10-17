---
title: 'Lync Server 2013: tabela ErrorCategory'
description: 'Lync Server 2013: tabela ErrorCategory.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8154c73f33b5dad62a338335a960553cfc06ec13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546427"
---
# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="87bc8-103">Tabela ErrorCategory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87bc8-103">ErrorCategory table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87bc8-104">_**Última modificação do tópico:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="87bc8-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="87bc8-105">A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87bc8-105">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="87bc8-106">Por padrão, o Lync Server 2013 usa as seguintes classificações:</span><span class="sxs-lookup"><span data-stu-id="87bc8-106">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="87bc8-107">0 -- Sucesso</span><span class="sxs-lookup"><span data-stu-id="87bc8-107">0 -- Success</span></span>

  - <span data-ttu-id="87bc8-108">1--falha esperada</span><span class="sxs-lookup"><span data-stu-id="87bc8-108">1 -- Expected failure</span></span>

  - <span data-ttu-id="87bc8-109">2 – Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="87bc8-109">2 – Unexpected failure</span></span>

<span data-ttu-id="87bc8-110">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="87bc8-110">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87bc8-111">Coluna</span><span class="sxs-lookup"><span data-stu-id="87bc8-111">Column</span></span></th>
<th><span data-ttu-id="87bc8-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="87bc8-112">Data Type</span></span></th>
<th><span data-ttu-id="87bc8-113">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="87bc8-113">Key/Index</span></span></th>
<th><span data-ttu-id="87bc8-114">Detalhes</span><span class="sxs-lookup"><span data-stu-id="87bc8-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87bc8-115"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="87bc8-115"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="87bc8-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="87bc8-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="87bc8-117">Primário</span><span class="sxs-lookup"><span data-stu-id="87bc8-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="87bc8-118">Identificador único para a classificação.</span><span class="sxs-lookup"><span data-stu-id="87bc8-118">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87bc8-119"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="87bc8-119"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="87bc8-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="87bc8-120">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="87bc8-p102">Valor e nome amigável atribuídos à classificação. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="87bc8-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="87bc8-123">0 -- Sucesso</span><span class="sxs-lookup"><span data-stu-id="87bc8-123">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="87bc8-124">1--falha esperada</span><span class="sxs-lookup"><span data-stu-id="87bc8-124">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="87bc8-125">2 – Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="87bc8-125">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

