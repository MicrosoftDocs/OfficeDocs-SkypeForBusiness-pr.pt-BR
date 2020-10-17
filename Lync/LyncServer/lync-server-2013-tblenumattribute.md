---
title: 'Lync Server 2013: tblEnumAttribute'
description: 'Lync Server 2013: tblEnumAttribute.'
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
ms.openlocfilehash: ca979a68e758ad47b691ac704f24c68c1841938a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571387"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="86b2b-103">tblEnumAttribute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b2b-103">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86b2b-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="86b2b-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="86b2b-105">tblEnumAttribute é uma tabela embutida em código que inclui os atributos de Visibilidade e Comportamento usados na tabela Node.</span><span class="sxs-lookup"><span data-stu-id="86b2b-105">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="86b2b-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="86b2b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86b2b-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="86b2b-107">Column</span></span></th>
<th><span data-ttu-id="86b2b-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="86b2b-108">Type</span></span></th>
<th><span data-ttu-id="86b2b-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="86b2b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86b2b-110">attributeID</span><span class="sxs-lookup"><span data-stu-id="86b2b-110">attributeID</span></span></p></td>
<td><p><span data-ttu-id="86b2b-111">smallint, não nulo</span><span class="sxs-lookup"><span data-stu-id="86b2b-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="86b2b-112">ID do atributo.</span><span class="sxs-lookup"><span data-stu-id="86b2b-112">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b2b-113">attributeName</span><span class="sxs-lookup"><span data-stu-id="86b2b-113">attributeName</span></span></p></td>
<td><p><span data-ttu-id="86b2b-114">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="86b2b-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="86b2b-115">Nome do atributo.</span><span class="sxs-lookup"><span data-stu-id="86b2b-115">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="86b2b-116">Chave</span><span class="sxs-lookup"><span data-stu-id="86b2b-116">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86b2b-117">Coluna</span><span class="sxs-lookup"><span data-stu-id="86b2b-117">Column</span></span></th>
<th><span data-ttu-id="86b2b-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="86b2b-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86b2b-119">attributeID</span><span class="sxs-lookup"><span data-stu-id="86b2b-119">attributeID</span></span></p></td>
<td><p><span data-ttu-id="86b2b-120">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="86b2b-120">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="86b2b-121">Valores de Tablea</span><span class="sxs-lookup"><span data-stu-id="86b2b-121">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86b2b-122">attributeID</span><span class="sxs-lookup"><span data-stu-id="86b2b-122">attributeID</span></span></th>
<th><span data-ttu-id="86b2b-123">attributeName</span><span class="sxs-lookup"><span data-stu-id="86b2b-123">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86b2b-124">1</span><span class="sxs-lookup"><span data-stu-id="86b2b-124">1</span></span></p></td>
<td><p><span data-ttu-id="86b2b-125">Capacidade.</span><span class="sxs-lookup"><span data-stu-id="86b2b-125">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86b2b-126">duas</span><span class="sxs-lookup"><span data-stu-id="86b2b-126">2</span></span></p></td>
<td><p><span data-ttu-id="86b2b-127">Comportamental.</span><span class="sxs-lookup"><span data-stu-id="86b2b-127">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="86b2b-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="86b2b-128">See Also</span></span>


[<span data-ttu-id="86b2b-129">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86b2b-129">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

