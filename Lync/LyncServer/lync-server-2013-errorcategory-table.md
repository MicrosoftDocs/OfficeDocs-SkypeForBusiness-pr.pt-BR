---
title: 'Lync Server 2013: tabela ErrorCategory'
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
ms.openlocfilehash: 7a80ab2b570a067a1157e999d056c47d514ec4ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="c752b-102">Tabela ErrorCategory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c752b-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c752b-103">_**Última modificação do tópico:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="c752b-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="c752b-104">A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c752b-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="c752b-105">Por padrão, o Lync Server 2013 usa as seguintes classificações:</span><span class="sxs-lookup"><span data-stu-id="c752b-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="c752b-106">0 -- Sucesso</span><span class="sxs-lookup"><span data-stu-id="c752b-106">0 -- Success</span></span>

  - <span data-ttu-id="c752b-107">1--falha esperada</span><span class="sxs-lookup"><span data-stu-id="c752b-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="c752b-108">2 – Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="c752b-108">2 – Unexpected failure</span></span>

<span data-ttu-id="c752b-109">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c752b-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c752b-110">Coluna</span><span class="sxs-lookup"><span data-stu-id="c752b-110">Column</span></span></th>
<th><span data-ttu-id="c752b-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c752b-111">Data Type</span></span></th>
<th><span data-ttu-id="c752b-112">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="c752b-112">Key/Index</span></span></th>
<th><span data-ttu-id="c752b-113">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c752b-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c752b-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="c752b-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="c752b-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="c752b-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c752b-116">Primário</span><span class="sxs-lookup"><span data-stu-id="c752b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="c752b-117">Identificador único para a classificação.</span><span class="sxs-lookup"><span data-stu-id="c752b-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c752b-118"><strong>Nome</strong></span><span class="sxs-lookup"><span data-stu-id="c752b-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="c752b-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c752b-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c752b-p102">Valor e nome amigável atribuídos à classificação. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="c752b-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c752b-122">0 -- Sucesso</span><span class="sxs-lookup"><span data-stu-id="c752b-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="c752b-123">1--falha esperada</span><span class="sxs-lookup"><span data-stu-id="c752b-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="c752b-124">2 – Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="c752b-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

