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
ms.openlocfilehash: 3cac704c6f62903c502ae5a4345ee0848c775d6f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536208"
---
# <a name="tblsiopwhitelist-in-lync-server-2013"></a><span data-ttu-id="f1e40-102">tblSiopWhiteList no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1e40-102">tblSiopWhiteList in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1e40-103">_**Última modificação do tópico:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="f1e40-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="f1e40-104">A tabela SiopWhiteList é a lista de suplementos registrados que podem ser associados aos nós.</span><span class="sxs-lookup"><span data-stu-id="f1e40-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="f1e40-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="f1e40-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1e40-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="f1e40-106">Column</span></span></th>
<th><span data-ttu-id="f1e40-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f1e40-107">Type</span></span></th>
<th><span data-ttu-id="f1e40-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="f1e40-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1e40-109">siopID</span><span class="sxs-lookup"><span data-stu-id="f1e40-109">siopID</span></span></p></td>
<td><p><span data-ttu-id="f1e40-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="f1e40-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f1e40-111">GUID do suplemento.</span><span class="sxs-lookup"><span data-stu-id="f1e40-111">GUID of the add-in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1e40-112">siopName</span><span class="sxs-lookup"><span data-stu-id="f1e40-112">siopName</span></span></p></td>
<td><p><span data-ttu-id="f1e40-113">nvarchar (50), não nulo</span><span class="sxs-lookup"><span data-stu-id="f1e40-113">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="f1e40-114">Nome de exibição do suplemento.</span><span class="sxs-lookup"><span data-stu-id="f1e40-114">Display-name of the add-in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1e40-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="f1e40-115">siopUrl</span></span></p></td>
<td><p><span data-ttu-id="f1e40-116">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="f1e40-116">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="f1e40-117">URL do suplemento.</span><span class="sxs-lookup"><span data-stu-id="f1e40-117">URL of the add-in.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f1e40-118">Chave</span><span class="sxs-lookup"><span data-stu-id="f1e40-118">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1e40-119">Coluna</span><span class="sxs-lookup"><span data-stu-id="f1e40-119">Column</span></span></th>
<th><span data-ttu-id="f1e40-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="f1e40-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1e40-121">siopID</span><span class="sxs-lookup"><span data-stu-id="f1e40-121">siopID</span></span></p></td>
<td><p><span data-ttu-id="f1e40-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f1e40-122">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

