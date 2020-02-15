---
title: 'Lync Server 2013: tblEnumValue'
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
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="997bc-102">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="997bc-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="997bc-103">_**Última modificação do tópico:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="997bc-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="997bc-104">A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.</span><span class="sxs-lookup"><span data-stu-id="997bc-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="997bc-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="997bc-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="997bc-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="997bc-106">Column</span></span></th>
<th><span data-ttu-id="997bc-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="997bc-107">Type</span></span></th>
<th><span data-ttu-id="997bc-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="997bc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997bc-109">valueid</span><span class="sxs-lookup"><span data-stu-id="997bc-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="997bc-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="997bc-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="997bc-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="997bc-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997bc-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="997bc-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="997bc-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="997bc-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="997bc-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="997bc-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997bc-115">atributo AttributeValue</span><span class="sxs-lookup"><span data-stu-id="997bc-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="997bc-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="997bc-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="997bc-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="997bc-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="997bc-118">Chaves</span><span class="sxs-lookup"><span data-stu-id="997bc-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="997bc-119">Coluna</span><span class="sxs-lookup"><span data-stu-id="997bc-119">Column</span></span></th>
<th><span data-ttu-id="997bc-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="997bc-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997bc-121">valueid</span><span class="sxs-lookup"><span data-stu-id="997bc-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="997bc-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="997bc-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997bc-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="997bc-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="997bc-124">Chave estrangeira com pesquisa na tabela tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="997bc-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="997bc-125">Valores da tabela</span><span class="sxs-lookup"><span data-stu-id="997bc-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="997bc-126">valueid</span><span class="sxs-lookup"><span data-stu-id="997bc-126">valueID</span></span></th>
<th><span data-ttu-id="997bc-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="997bc-127">attributeID</span></span></th>
<th><span data-ttu-id="997bc-128">atributo AttributeValue</span><span class="sxs-lookup"><span data-stu-id="997bc-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="997bc-129">2 </span><span class="sxs-lookup"><span data-stu-id="997bc-129">2</span></span></p></td>
<td><p><span data-ttu-id="997bc-130">1 </span><span class="sxs-lookup"><span data-stu-id="997bc-130">1</span></span></p></td>
<td><p><span data-ttu-id="997bc-131">privada</span><span class="sxs-lookup"><span data-stu-id="997bc-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997bc-132">3 </span><span class="sxs-lookup"><span data-stu-id="997bc-132">3</span></span></p></td>
<td><p><span data-ttu-id="997bc-133">1 </span><span class="sxs-lookup"><span data-stu-id="997bc-133">1</span></span></p></td>
<td><p><span data-ttu-id="997bc-134">escopo</span><span class="sxs-lookup"><span data-stu-id="997bc-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997bc-135">4 </span><span class="sxs-lookup"><span data-stu-id="997bc-135">4</span></span></p></td>
<td><p><span data-ttu-id="997bc-136">2 </span><span class="sxs-lookup"><span data-stu-id="997bc-136">2</span></span></p></td>
<td><p><span data-ttu-id="997bc-137">SS</span><span class="sxs-lookup"><span data-stu-id="997bc-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="997bc-138">5 </span><span class="sxs-lookup"><span data-stu-id="997bc-138">5</span></span></p></td>
<td><p><span data-ttu-id="997bc-139">2 </span><span class="sxs-lookup"><span data-stu-id="997bc-139">2</span></span></p></td>
<td><p><span data-ttu-id="997bc-140">Auditório</span><span class="sxs-lookup"><span data-stu-id="997bc-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="997bc-141">6 </span><span class="sxs-lookup"><span data-stu-id="997bc-141">6</span></span></p></td>
<td><p><span data-ttu-id="997bc-142">1 </span><span class="sxs-lookup"><span data-stu-id="997bc-142">1</span></span></p></td>
<td><p><span data-ttu-id="997bc-143">Abre</span><span class="sxs-lookup"><span data-stu-id="997bc-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="997bc-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="997bc-144">See Also</span></span>


[<span data-ttu-id="997bc-145">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="997bc-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

