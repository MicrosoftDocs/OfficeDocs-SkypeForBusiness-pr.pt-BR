---
title: 'Lync Server 2013: tabela ErrorDef'
description: 'Lync Server 2013: tabela ErrorDef.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542747"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="c0f9b-103">Tabela ErrorDef no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0f9b-103">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0f9b-104">_**Última modificação do tópico:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="c0f9b-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="c0f9b-105">A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="c0f9b-106">Cada registro é um tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-106">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0f9b-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="c0f9b-107">Column</span></span></th>
<th><span data-ttu-id="c0f9b-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c0f9b-108">Data Type</span></span></th>
<th><span data-ttu-id="c0f9b-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="c0f9b-109">Key/Index</span></span></th>
<th><span data-ttu-id="c0f9b-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c0f9b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0f9b-111"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="c0f9b-111"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="c0f9b-112">int</span><span class="sxs-lookup"><span data-stu-id="c0f9b-112">int</span></span></p></td>
<td><p><span data-ttu-id="c0f9b-113">Primário</span><span class="sxs-lookup"><span data-stu-id="c0f9b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c0f9b-114">Número de identificação exclusivo que identifica esse tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-114">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0f9b-115"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c0f9b-115"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c0f9b-116">int</span><span class="sxs-lookup"><span data-stu-id="c0f9b-116">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0f9b-117">Código de resposta SIP padrão associado a esse erro.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-117">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0f9b-118"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="c0f9b-118"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="c0f9b-119">int</span><span class="sxs-lookup"><span data-stu-id="c0f9b-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0f9b-120">ID de diagnóstico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-120">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0f9b-121"><strong>Callid</strong></span><span class="sxs-lookup"><span data-stu-id="c0f9b-121"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="c0f9b-122">Int</span><span class="sxs-lookup"><span data-stu-id="c0f9b-122">Int</span></span></p></td>
<td><p><span data-ttu-id="c0f9b-123">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="c0f9b-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c0f9b-124">Tipo da chamada.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-124">Type of the call.</span></span> <span data-ttu-id="c0f9b-125">Consulte a <a href="lync-server-2013-calltype-table.md">tabela CallType no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-125">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0f9b-126"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="c0f9b-126"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="c0f9b-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="c0f9b-127">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0f9b-128">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-128">Type of request that failed.</span></span></p>
<p><span data-ttu-id="c0f9b-129">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c0f9b-129">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0f9b-130"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="c0f9b-130"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="c0f9b-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="c0f9b-131">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c0f9b-132">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="c0f9b-132">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="c0f9b-133">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c0f9b-133">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

