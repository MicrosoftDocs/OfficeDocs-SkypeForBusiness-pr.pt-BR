---
title: 'Lync Server 2013: tblSiopWhiteList'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSiopWhiteList
ms:assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558607(v=OCS.15)
ms:contentKeyID: 48183310
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4233989b9b8e00afdda389f468539da2ac7f61f2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="5d34c-102">tblSiopWhiteList no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d34c-102">tblSiopWhiteList in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d34c-103">_**Última modificação do tópico:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="5d34c-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="5d34c-104">A tabela SiopWhiteList é a lista de suplementos registrados que podem ser associados aos nós.</span><span class="sxs-lookup"><span data-stu-id="5d34c-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="5d34c-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="5d34c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d34c-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="5d34c-106">Column</span></span></th>
<th><span data-ttu-id="5d34c-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="5d34c-107">Type</span></span></th>
<th><span data-ttu-id="5d34c-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d34c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d34c-109">siopID</span><span class="sxs-lookup"><span data-stu-id="5d34c-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="5d34c-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="5d34c-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5d34c-111">GUID do suplemento.</span><span class="sxs-lookup"><span data-stu-id="5d34c-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d34c-112">siopName</span><span class="sxs-lookup"><span data-stu-id="5d34c-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="5d34c-113">nvarchar (50), não nulo</span><span class="sxs-lookup"><span data-stu-id="5d34c-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="5d34c-114">Nome de exibição do suplemento.</span><span class="sxs-lookup"><span data-stu-id="5d34c-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d34c-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="5d34c-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="5d34c-116">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="5d34c-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="5d34c-117">URL do suplemento.</span><span class="sxs-lookup"><span data-stu-id="5d34c-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="5d34c-118">Chave</span><span class="sxs-lookup"><span data-stu-id="5d34c-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d34c-119">Coluna</span><span class="sxs-lookup"><span data-stu-id="5d34c-119">Column</span></span></th>
<th><span data-ttu-id="5d34c-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="5d34c-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d34c-121">siopID</span><span class="sxs-lookup"><span data-stu-id="5d34c-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="5d34c-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="5d34c-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

