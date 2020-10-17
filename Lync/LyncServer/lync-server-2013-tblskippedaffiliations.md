---
title: 'Lync Server 2013: tblSkippedAffiliations'
description: 'Lync Server 2013: tblSkippedAffiliations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31746cee7302d34a1d19b3059ca1da6beab9345d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563797"
---
# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="6e880-103">tblSkippedAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e880-103">tblSkippedAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e880-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6e880-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6e880-105">tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido aos erros de acesso dos serviços de domínio do Active Directory).</span><span class="sxs-lookup"><span data-stu-id="6e880-105">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="6e880-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="6e880-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e880-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="6e880-107">Column</span></span></th>
<th><span data-ttu-id="6e880-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="6e880-108">Type</span></span></th>
<th><span data-ttu-id="6e880-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e880-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e880-110">prinID</span><span class="sxs-lookup"><span data-stu-id="6e880-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="6e880-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6e880-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6e880-112">ID principal.</span><span class="sxs-lookup"><span data-stu-id="6e880-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e880-113">affDescription</span><span class="sxs-lookup"><span data-stu-id="6e880-113">affDescription</span></span></p></td>
<td><p><span data-ttu-id="6e880-114">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="6e880-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="6e880-115">Uma cadeia identificando a afiliação.</span><span class="sxs-lookup"><span data-stu-id="6e880-115">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="6e880-116">O formato é: GUID: {0} URI: {1} &gt; ID:{2}</span><span class="sxs-lookup"><span data-stu-id="6e880-116">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e880-117">updatedBy</span><span class="sxs-lookup"><span data-stu-id="6e880-117">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="6e880-118">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6e880-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6e880-p101">ID da principal que atualizou essa linha. É sempre 1 (usuário do sistema) porque a Sincronização do Active Directory é a única origem dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="6e880-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6e880-121">Chaves</span><span class="sxs-lookup"><span data-stu-id="6e880-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e880-122">Coluna (s)</span><span class="sxs-lookup"><span data-stu-id="6e880-122">Column(s)</span></span></th>
<th><span data-ttu-id="6e880-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="6e880-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e880-124">&lt;imprimir, affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="6e880-124">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="6e880-125">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6e880-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e880-126">prinID</span><span class="sxs-lookup"><span data-stu-id="6e880-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="6e880-127">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="6e880-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

