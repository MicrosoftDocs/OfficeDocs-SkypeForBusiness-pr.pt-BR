---
title: 'Lync Server 2013: Tabela ErrorDef'
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
ms.openlocfilehash: 55a6ab9a8bf50639267824c8330701ee74cb3f5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="de7b1-102">Tabela ErrorDef no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de7b1-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de7b1-103">_**Tópico da última modificação:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="de7b1-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="de7b1-104">A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="de7b1-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="de7b1-105">Cada registro é um tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="de7b1-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de7b1-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="de7b1-106">Column</span></span></th>
<th><span data-ttu-id="de7b1-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="de7b1-107">Data Type</span></span></th>
<th><span data-ttu-id="de7b1-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="de7b1-108">Key/Index</span></span></th>
<th><span data-ttu-id="de7b1-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="de7b1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de7b1-110"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="de7b1-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="de7b1-111">int</span><span class="sxs-lookup"><span data-stu-id="de7b1-111">int</span></span></p></td>
<td><p><span data-ttu-id="de7b1-112">Primária</span><span class="sxs-lookup"><span data-stu-id="de7b1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="de7b1-113">Número de identificação exclusivo que identifica esse tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="de7b1-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de7b1-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="de7b1-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="de7b1-115">int</span><span class="sxs-lookup"><span data-stu-id="de7b1-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de7b1-116">Código de resposta SIP padrão associado a esse erro.</span><span class="sxs-lookup"><span data-stu-id="de7b1-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de7b1-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="de7b1-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="de7b1-118">int</span><span class="sxs-lookup"><span data-stu-id="de7b1-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de7b1-119">IDENTIFICAÇÃO do diagnóstico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de7b1-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de7b1-120"><strong>Callid</strong></span><span class="sxs-lookup"><span data-stu-id="de7b1-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="de7b1-121">Núm</span><span class="sxs-lookup"><span data-stu-id="de7b1-121">Int</span></span></p></td>
<td><p><span data-ttu-id="de7b1-122">Exterior</span><span class="sxs-lookup"><span data-stu-id="de7b1-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de7b1-123">Tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="de7b1-123">Type of the call.</span></span> <span data-ttu-id="de7b1-124">Consulte a <a href="lync-server-2013-calltype-table.md">tabela CallType no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de7b1-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de7b1-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="de7b1-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="de7b1-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="de7b1-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de7b1-127">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="de7b1-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="de7b1-128">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="de7b1-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de7b1-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="de7b1-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="de7b1-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="de7b1-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de7b1-131">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="de7b1-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="de7b1-132">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="de7b1-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

