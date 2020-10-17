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
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509318"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="ab725-102">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab725-102">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab725-103">_**Última modificação do tópico:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="ab725-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="ab725-104">A tabela tblEnumValue é uma tabela embutida em código que contém os valores de Visibilidade e Comportamento dos atributos usados na tabela Nó.</span><span class="sxs-lookup"><span data-stu-id="ab725-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="ab725-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="ab725-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab725-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="ab725-106">Column</span></span></th>
<th><span data-ttu-id="ab725-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab725-107">Type</span></span></th>
<th><span data-ttu-id="ab725-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab725-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab725-109">valueid</span><span class="sxs-lookup"><span data-stu-id="ab725-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="ab725-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="ab725-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="ab725-111">ID do valor.</span><span class="sxs-lookup"><span data-stu-id="ab725-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab725-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="ab725-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="ab725-113">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="ab725-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="ab725-114">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="ab725-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab725-115">atributo AttributeValue</span><span class="sxs-lookup"><span data-stu-id="ab725-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="ab725-116">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="ab725-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ab725-117">Nome do valor.</span><span class="sxs-lookup"><span data-stu-id="ab725-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ab725-118">Chaves</span><span class="sxs-lookup"><span data-stu-id="ab725-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab725-119">Coluna</span><span class="sxs-lookup"><span data-stu-id="ab725-119">Column</span></span></th>
<th><span data-ttu-id="ab725-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab725-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab725-121">valueid</span><span class="sxs-lookup"><span data-stu-id="ab725-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="ab725-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="ab725-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab725-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="ab725-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="ab725-124">Chave estrangeira com pesquisa na tabela tblEnumAttribute.attributeID.</span><span class="sxs-lookup"><span data-stu-id="ab725-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="ab725-125">Valores da tabela</span><span class="sxs-lookup"><span data-stu-id="ab725-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab725-126">valueid</span><span class="sxs-lookup"><span data-stu-id="ab725-126">valueID</span></span></th>
<th><span data-ttu-id="ab725-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="ab725-127">attributeID</span></span></th>
<th><span data-ttu-id="ab725-128">atributo AttributeValue</span><span class="sxs-lookup"><span data-stu-id="ab725-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab725-129">duas</span><span class="sxs-lookup"><span data-stu-id="ab725-129">2</span></span></p></td>
<td><p><span data-ttu-id="ab725-130">1</span><span class="sxs-lookup"><span data-stu-id="ab725-130">1</span></span></p></td>
<td><p><span data-ttu-id="ab725-131">privada</span><span class="sxs-lookup"><span data-stu-id="ab725-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab725-132">3D</span><span class="sxs-lookup"><span data-stu-id="ab725-132">3</span></span></p></td>
<td><p><span data-ttu-id="ab725-133">1</span><span class="sxs-lookup"><span data-stu-id="ab725-133">1</span></span></p></td>
<td><p><span data-ttu-id="ab725-134">escopo</span><span class="sxs-lookup"><span data-stu-id="ab725-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab725-135">4 </span><span class="sxs-lookup"><span data-stu-id="ab725-135">4</span></span></p></td>
<td><p><span data-ttu-id="ab725-136">duas</span><span class="sxs-lookup"><span data-stu-id="ab725-136">2</span></span></p></td>
<td><p><span data-ttu-id="ab725-137">SS</span><span class="sxs-lookup"><span data-stu-id="ab725-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab725-138">5 </span><span class="sxs-lookup"><span data-stu-id="ab725-138">5</span></span></p></td>
<td><p><span data-ttu-id="ab725-139">duas</span><span class="sxs-lookup"><span data-stu-id="ab725-139">2</span></span></p></td>
<td><p><span data-ttu-id="ab725-140">Auditório</span><span class="sxs-lookup"><span data-stu-id="ab725-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab725-141">6 </span><span class="sxs-lookup"><span data-stu-id="ab725-141">6</span></span></p></td>
<td><p><span data-ttu-id="ab725-142">1</span><span class="sxs-lookup"><span data-stu-id="ab725-142">1</span></span></p></td>
<td><p><span data-ttu-id="ab725-143">Abre</span><span class="sxs-lookup"><span data-stu-id="ab725-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="ab725-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="ab725-144">See Also</span></span>


[<span data-ttu-id="ab725-145">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab725-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

