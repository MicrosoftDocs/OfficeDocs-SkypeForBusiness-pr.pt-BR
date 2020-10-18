---
title: 'Lync Server 2013: tabela SessionCorrelation'
description: 'Lync Server 2013: tabela SessionCorrelation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814b7e8539d89f87e7df60ceb03e70800553fb55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579657"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="c4807-103">Tabela SessionCorrelation no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4807-103">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4807-104">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c4807-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c4807-105">A tabela SessionCorrelation é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="c4807-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="c4807-106">Cada registro representa um CorrelationId que é usado para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="c4807-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4807-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="c4807-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c4807-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="c4807-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c4807-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="c4807-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c4807-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="c4807-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4807-111"><strong>Soma de verificação</strong></span><span class="sxs-lookup"><span data-stu-id="c4807-111"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="c4807-112">int</span><span class="sxs-lookup"><span data-stu-id="c4807-112">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4807-113"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="c4807-113"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c4807-114">int</span><span class="sxs-lookup"><span data-stu-id="c4807-114">int</span></span></p></td>
<td><p><span data-ttu-id="c4807-115">Primário</span><span class="sxs-lookup"><span data-stu-id="c4807-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="c4807-116">Número exclusivo que identifica este servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="c4807-116">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4807-117"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="c4807-117"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="c4807-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4807-118">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4807-119">Diferente</span><span class="sxs-lookup"><span data-stu-id="c4807-119">Unique</span></span></p></td>
<td><p><span data-ttu-id="c4807-120">As sessões correlacionadas terão a mesma ID de correlação.</span><span class="sxs-lookup"><span data-stu-id="c4807-120">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4807-121"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="c4807-121"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="c4807-122">datetime</span><span class="sxs-lookup"><span data-stu-id="c4807-122">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c4807-123">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="c4807-123">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

