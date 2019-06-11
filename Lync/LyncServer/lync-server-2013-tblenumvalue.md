---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1758daf16575491960415647e4c9bc4b43920d26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="a84e0-102">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a84e0-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a84e0-103">_**Tópico da última modificação:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="a84e0-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="a84e0-104">tblEnumValue é uma tabela codificada que contém os valores de visibilidade e comportamento dos atributos usados na tabela de nós.</span><span class="sxs-lookup"><span data-stu-id="a84e0-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="a84e0-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="a84e0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a84e0-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="a84e0-106">Column</span></span></th>
<th><span data-ttu-id="a84e0-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="a84e0-107">Type</span></span></th>
<th><span data-ttu-id="a84e0-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="a84e0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a84e0-109">valueid</span><span class="sxs-lookup"><span data-stu-id="a84e0-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="a84e0-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="a84e0-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a84e0-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="a84e0-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e0-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="a84e0-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="a84e0-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="a84e0-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="a84e0-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="a84e0-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e0-115">atributovalue</span><span class="sxs-lookup"><span data-stu-id="a84e0-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="a84e0-116">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="a84e0-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="a84e0-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="a84e0-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="a84e0-118">As</span><span class="sxs-lookup"><span data-stu-id="a84e0-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a84e0-119">Coluna</span><span class="sxs-lookup"><span data-stu-id="a84e0-119">Column</span></span></th>
<th><span data-ttu-id="a84e0-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="a84e0-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a84e0-121">valueid</span><span class="sxs-lookup"><span data-stu-id="a84e0-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="a84e0-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="a84e0-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e0-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="a84e0-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="a84e0-124">Chave estrangeira com pesquisa na tabela tblEnumAttribute. attributeID.</span><span class="sxs-lookup"><span data-stu-id="a84e0-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="a84e0-125">Valores da tabela</span><span class="sxs-lookup"><span data-stu-id="a84e0-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a84e0-126">valueid</span><span class="sxs-lookup"><span data-stu-id="a84e0-126">valueID</span></span></th>
<th><span data-ttu-id="a84e0-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="a84e0-127">attributeID</span></span></th>
<th><span data-ttu-id="a84e0-128">atributovalue</span><span class="sxs-lookup"><span data-stu-id="a84e0-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a84e0-129">2</span><span class="sxs-lookup"><span data-stu-id="a84e0-129">2</span></span></p></td>
<td><p><span data-ttu-id="a84e0-130">1</span><span class="sxs-lookup"><span data-stu-id="a84e0-130">1</span></span></p></td>
<td><p><span data-ttu-id="a84e0-131">private</span><span class="sxs-lookup"><span data-stu-id="a84e0-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e0-132">3</span><span class="sxs-lookup"><span data-stu-id="a84e0-132">3</span></span></p></td>
<td><p><span data-ttu-id="a84e0-133">1</span><span class="sxs-lookup"><span data-stu-id="a84e0-133">1</span></span></p></td>
<td><p><span data-ttu-id="a84e0-134">com</span><span class="sxs-lookup"><span data-stu-id="a84e0-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e0-135">4</span><span class="sxs-lookup"><span data-stu-id="a84e0-135">4</span></span></p></td>
<td><p><span data-ttu-id="a84e0-136">2</span><span class="sxs-lookup"><span data-stu-id="a84e0-136">2</span></span></p></td>
<td><p><span data-ttu-id="a84e0-137">Normalmente</span><span class="sxs-lookup"><span data-stu-id="a84e0-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a84e0-138">5</span><span class="sxs-lookup"><span data-stu-id="a84e0-138">5</span></span></p></td>
<td><p><span data-ttu-id="a84e0-139">2</span><span class="sxs-lookup"><span data-stu-id="a84e0-139">2</span></span></p></td>
<td><p><span data-ttu-id="a84e0-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="a84e0-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a84e0-141">6</span><span class="sxs-lookup"><span data-stu-id="a84e0-141">6</span></span></p></td>
<td><p><span data-ttu-id="a84e0-142">1</span><span class="sxs-lookup"><span data-stu-id="a84e0-142">1</span></span></p></td>
<td><p><span data-ttu-id="a84e0-143">abriu</span><span class="sxs-lookup"><span data-stu-id="a84e0-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="a84e0-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="a84e0-144">See Also</span></span>


[<span data-ttu-id="a84e0-145">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a84e0-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

