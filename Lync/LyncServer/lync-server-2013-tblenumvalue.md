---
title: 'Lync Server 2013: tblEnumValue'
description: 'Lync Server 2013: tblEnumValue.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571367"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="33b1d-103">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33b1d-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33b1d-104">_**Última modificação do tópico:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="33b1d-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="33b1d-105">A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.</span><span class="sxs-lookup"><span data-stu-id="33b1d-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="33b1d-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="33b1d-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33b1d-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="33b1d-107">Column</span></span></th>
<th><span data-ttu-id="33b1d-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="33b1d-108">Type</span></span></th>
<th><span data-ttu-id="33b1d-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="33b1d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33b1d-110">valueid</span><span class="sxs-lookup"><span data-stu-id="33b1d-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="33b1d-111">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="33b1d-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="33b1d-112">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="33b1d-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33b1d-113">attributeID</span><span class="sxs-lookup"><span data-stu-id="33b1d-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="33b1d-114">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="33b1d-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="33b1d-115">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="33b1d-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33b1d-116">atributo AttributeValue</span><span class="sxs-lookup"><span data-stu-id="33b1d-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="33b1d-117">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="33b1d-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="33b1d-118">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="33b1d-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="33b1d-119">Chaves</span><span class="sxs-lookup"><span data-stu-id="33b1d-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33b1d-120">Coluna</span><span class="sxs-lookup"><span data-stu-id="33b1d-120">Column</span></span></th>
<th><span data-ttu-id="33b1d-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="33b1d-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33b1d-122">valueid</span><span class="sxs-lookup"><span data-stu-id="33b1d-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="33b1d-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="33b1d-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33b1d-124">attributeID</span><span class="sxs-lookup"><span data-stu-id="33b1d-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="33b1d-125">Chave estrangeira com pesquisa na tabela tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="33b1d-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="33b1d-126">Valores da tabela</span><span class="sxs-lookup"><span data-stu-id="33b1d-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33b1d-127">valueid</span><span class="sxs-lookup"><span data-stu-id="33b1d-127">valueID</span></span></th>
<th><span data-ttu-id="33b1d-128">attributeID</span><span class="sxs-lookup"><span data-stu-id="33b1d-128">attributeID</span></span></th>
<th><span data-ttu-id="33b1d-129">atributo AttributeValue</span><span class="sxs-lookup"><span data-stu-id="33b1d-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33b1d-130">duas</span><span class="sxs-lookup"><span data-stu-id="33b1d-130">2</span></span></p></td>
<td><p><span data-ttu-id="33b1d-131">1</span><span class="sxs-lookup"><span data-stu-id="33b1d-131">1</span></span></p></td>
<td><p><span data-ttu-id="33b1d-132">privada</span><span class="sxs-lookup"><span data-stu-id="33b1d-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33b1d-133">3D</span><span class="sxs-lookup"><span data-stu-id="33b1d-133">3</span></span></p></td>
<td><p><span data-ttu-id="33b1d-134">1</span><span class="sxs-lookup"><span data-stu-id="33b1d-134">1</span></span></p></td>
<td><p><span data-ttu-id="33b1d-135">escopo</span><span class="sxs-lookup"><span data-stu-id="33b1d-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33b1d-136">4 </span><span class="sxs-lookup"><span data-stu-id="33b1d-136">4</span></span></p></td>
<td><p><span data-ttu-id="33b1d-137">duas</span><span class="sxs-lookup"><span data-stu-id="33b1d-137">2</span></span></p></td>
<td><p><span data-ttu-id="33b1d-138">SS</span><span class="sxs-lookup"><span data-stu-id="33b1d-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33b1d-139">5 </span><span class="sxs-lookup"><span data-stu-id="33b1d-139">5</span></span></p></td>
<td><p><span data-ttu-id="33b1d-140">duas</span><span class="sxs-lookup"><span data-stu-id="33b1d-140">2</span></span></p></td>
<td><p><span data-ttu-id="33b1d-141">Auditório</span><span class="sxs-lookup"><span data-stu-id="33b1d-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33b1d-142">6 </span><span class="sxs-lookup"><span data-stu-id="33b1d-142">6</span></span></p></td>
<td><p><span data-ttu-id="33b1d-143">1</span><span class="sxs-lookup"><span data-stu-id="33b1d-143">1</span></span></p></td>
<td><p><span data-ttu-id="33b1d-144">Abre</span><span class="sxs-lookup"><span data-stu-id="33b1d-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="33b1d-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="33b1d-145">See Also</span></span>


[<span data-ttu-id="33b1d-146">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33b1d-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

