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
ms.openlocfilehash: 984dd5f161b31c40de914f363c0722657d3194ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="5f7a7-102">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f7a7-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f7a7-103">_**Última modificação do tópico:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="5f7a7-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="5f7a7-104">A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.</span><span class="sxs-lookup"><span data-stu-id="5f7a7-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="5f7a7-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="5f7a7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7a7-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="5f7a7-106">Column</span></span></th>
<th><span data-ttu-id="5f7a7-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="5f7a7-107">Type</span></span></th>
<th><span data-ttu-id="5f7a7-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f7a7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7a7-109">valueid</span><span class="sxs-lookup"><span data-stu-id="5f7a7-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="5f7a7-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="5f7a7-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7a7-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="5f7a7-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="5f7a7-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="5f7a7-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f7a7-115">atributo AttributeValue</span><span class="sxs-lookup"><span data-stu-id="5f7a7-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="5f7a7-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="5f7a7-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5f7a7-118">Chaves</span><span class="sxs-lookup"><span data-stu-id="5f7a7-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7a7-119">Coluna</span><span class="sxs-lookup"><span data-stu-id="5f7a7-119">Column</span></span></th>
<th><span data-ttu-id="5f7a7-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f7a7-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7a7-121">valueid</span><span class="sxs-lookup"><span data-stu-id="5f7a7-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="5f7a7-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7a7-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="5f7a7-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-124">Chave estrangeira com pesquisa na tabela tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="5f7a7-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="5f7a7-125">Valores da tabela</span><span class="sxs-lookup"><span data-stu-id="5f7a7-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7a7-126">valueid</span><span class="sxs-lookup"><span data-stu-id="5f7a7-126">valueID</span></span></th>
<th><span data-ttu-id="5f7a7-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="5f7a7-127">attributeID</span></span></th>
<th><span data-ttu-id="5f7a7-128">atributo AttributeValue</span><span class="sxs-lookup"><span data-stu-id="5f7a7-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7a7-129">duas</span><span class="sxs-lookup"><span data-stu-id="5f7a7-129">2</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-130">1</span><span class="sxs-lookup"><span data-stu-id="5f7a7-130">1</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-131">privada</span><span class="sxs-lookup"><span data-stu-id="5f7a7-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7a7-132">3D</span><span class="sxs-lookup"><span data-stu-id="5f7a7-132">3</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-133">1</span><span class="sxs-lookup"><span data-stu-id="5f7a7-133">1</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-134">escopo</span><span class="sxs-lookup"><span data-stu-id="5f7a7-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f7a7-135">quatro</span><span class="sxs-lookup"><span data-stu-id="5f7a7-135">4</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-136">duas</span><span class="sxs-lookup"><span data-stu-id="5f7a7-136">2</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-137">SS</span><span class="sxs-lookup"><span data-stu-id="5f7a7-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7a7-138">0,5</span><span class="sxs-lookup"><span data-stu-id="5f7a7-138">5</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-139">duas</span><span class="sxs-lookup"><span data-stu-id="5f7a7-139">2</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-140">Auditório</span><span class="sxs-lookup"><span data-stu-id="5f7a7-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f7a7-141">6 </span><span class="sxs-lookup"><span data-stu-id="5f7a7-141">6</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-142">1</span><span class="sxs-lookup"><span data-stu-id="5f7a7-142">1</span></span></p></td>
<td><p><span data-ttu-id="5f7a7-143">Abre</span><span class="sxs-lookup"><span data-stu-id="5f7a7-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="5f7a7-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="5f7a7-144">See Also</span></span>


[<span data-ttu-id="5f7a7-145">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f7a7-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

