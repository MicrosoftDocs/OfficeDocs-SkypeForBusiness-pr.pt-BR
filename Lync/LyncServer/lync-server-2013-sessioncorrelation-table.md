---
title: 'Lync Server 2013: tabela SessionCorrelation'
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
ms.openlocfilehash: 4be49e052dc7ffd431e980d1a3f969bfffdfce8c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510098"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="0d9d0-102">Tabela SessionCorrelation no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d9d0-102">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d9d0-103">_**Última modificação do tópico:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0d9d0-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0d9d0-104">A tabela SessionCorrelation é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="0d9d0-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="0d9d0-105">Cada registro representa um CorrelationId que é usado para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="0d9d0-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d9d0-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="0d9d0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0d9d0-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="0d9d0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0d9d0-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="0d9d0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0d9d0-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="0d9d0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d9d0-110"><strong>Soma de verificação</strong></span><span class="sxs-lookup"><span data-stu-id="0d9d0-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="0d9d0-111">int</span><span class="sxs-lookup"><span data-stu-id="0d9d0-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d9d0-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="0d9d0-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="0d9d0-113">int</span><span class="sxs-lookup"><span data-stu-id="0d9d0-113">int</span></span></p></td>
<td><p><span data-ttu-id="0d9d0-114">Primário</span><span class="sxs-lookup"><span data-stu-id="0d9d0-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d9d0-115">Número exclusivo que identifica este servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="0d9d0-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d9d0-116"><strong>CorrelationID</strong></span><span class="sxs-lookup"><span data-stu-id="0d9d0-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="0d9d0-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0d9d0-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="0d9d0-118">Diferente</span><span class="sxs-lookup"><span data-stu-id="0d9d0-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="0d9d0-119">As sessões correlacionadas terão a mesma ID de correlação.</span><span class="sxs-lookup"><span data-stu-id="0d9d0-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d9d0-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="0d9d0-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="0d9d0-121">datetime</span><span class="sxs-lookup"><span data-stu-id="0d9d0-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d9d0-122">Apenas para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0d9d0-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

