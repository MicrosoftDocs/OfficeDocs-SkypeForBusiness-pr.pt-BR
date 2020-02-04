---
title: 'Lync Server 2013: tblEnumAttribute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73ac5a7cf26c97b31daf5785a90fac102c50e480
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="f9ac5-102">tblEnumAttribute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9ac5-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9ac5-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f9ac5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f9ac5-104">tblEnumAttribute é uma tabela codificada que contém os atributos de visibilidade e comportamento usados na tabela de nós.</span><span class="sxs-lookup"><span data-stu-id="f9ac5-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="f9ac5-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="f9ac5-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9ac5-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="f9ac5-106">Column</span></span></th>
<th><span data-ttu-id="f9ac5-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f9ac5-107">Type</span></span></th>
<th><span data-ttu-id="f9ac5-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="f9ac5-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9ac5-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="f9ac5-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="f9ac5-110">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="f9ac5-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="f9ac5-111">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="f9ac5-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9ac5-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="f9ac5-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="f9ac5-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="f9ac5-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f9ac5-114">Nome do atributo.</span><span class="sxs-lookup"><span data-stu-id="f9ac5-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f9ac5-115">Chave</span><span class="sxs-lookup"><span data-stu-id="f9ac5-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9ac5-116">Coluna</span><span class="sxs-lookup"><span data-stu-id="f9ac5-116">Column</span></span></th>
<th><span data-ttu-id="f9ac5-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="f9ac5-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9ac5-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="f9ac5-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="f9ac5-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f9ac5-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="f9ac5-120">Valores da tabela</span><span class="sxs-lookup"><span data-stu-id="f9ac5-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9ac5-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="f9ac5-121">attributeID</span></span></th>
<th><span data-ttu-id="f9ac5-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="f9ac5-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9ac5-123">1</span><span class="sxs-lookup"><span data-stu-id="f9ac5-123">1</span></span></p></td>
<td><p><span data-ttu-id="f9ac5-124">Visibilidade.</span><span class="sxs-lookup"><span data-stu-id="f9ac5-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9ac5-125">2</span><span class="sxs-lookup"><span data-stu-id="f9ac5-125">2</span></span></p></td>
<td><p><span data-ttu-id="f9ac5-126">Funcionamento.</span><span class="sxs-lookup"><span data-stu-id="f9ac5-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="f9ac5-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="f9ac5-127">See Also</span></span>


[<span data-ttu-id="f9ac5-128">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9ac5-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

