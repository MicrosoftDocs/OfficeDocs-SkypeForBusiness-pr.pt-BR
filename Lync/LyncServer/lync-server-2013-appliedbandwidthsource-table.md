---
title: 'Lync Server 2013: tabela AppliedBandwidthSource'
description: 'Lync Server 2013: tabela AppliedBandwidthSource.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc22d3a978a99cb13317e2a32fdb65382ce106c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573497"
---
# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="e6369-103">Tabela AppliedBandwidthSource no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6369-103">AppliedBandwidthSource table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6369-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e6369-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e6369-p101">A tabela AppliedBandwidthSource é uma tabela de suporte. Cada registro representa uma origem.</span><span class="sxs-lookup"><span data-stu-id="e6369-p101">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6369-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="e6369-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e6369-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="e6369-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e6369-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="e6369-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e6369-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="e6369-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6369-111"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="e6369-111"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e6369-112">int</span><span class="sxs-lookup"><span data-stu-id="e6369-112">int</span></span></p></td>
<td><p><span data-ttu-id="e6369-113">Primário</span><span class="sxs-lookup"><span data-stu-id="e6369-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e6369-114">Número exclusivo que identifica a origem.</span><span class="sxs-lookup"><span data-stu-id="e6369-114">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6369-115"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="e6369-115"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="e6369-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e6369-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6369-117">Diferente</span><span class="sxs-lookup"><span data-stu-id="e6369-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="e6369-p102">Essa é a origem do cap de largura de banda que está sendo imposto. Descreve de onde o limite de largura de banda está vindo (por exemplo, "Política de servidor", "Servidor TURN" ou "Modalidade").</span><span class="sxs-lookup"><span data-stu-id="e6369-p102">This is the source of the bandwidth cap being imposed. It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

