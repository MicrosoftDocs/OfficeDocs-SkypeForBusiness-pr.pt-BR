---
title: 'Lync Server 2013: tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06269ede55a46757f78595d7573f3cd77414d1d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a><span data-ttu-id="781c0-102">tblSkippedAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="781c0-102">tblSkippedAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="781c0-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="781c0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="781c0-104">tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos serviços de domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="781c0-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>

### <a name="columns"></a><span data-ttu-id="781c0-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="781c0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="781c0-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="781c0-106">Column</span></span></th>
<th><span data-ttu-id="781c0-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="781c0-107">Type</span></span></th>
<th><span data-ttu-id="781c0-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="781c0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="781c0-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="781c0-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="781c0-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="781c0-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="781c0-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="781c0-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781c0-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="781c0-112">affDescription</span></span></p></td>
<td><p><span data-ttu-id="781c0-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="781c0-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="781c0-114">Uma cadeia de caracteres que identifica a afiliação.</span><span class="sxs-lookup"><span data-stu-id="781c0-114">A string identifying the affiliation.</span></span></p>
<p><span data-ttu-id="781c0-115">O formato é: GUID: {0} URI: {1} &gt; ID:{2}</span><span class="sxs-lookup"><span data-stu-id="781c0-115">The format is: guid: {0} uri: {1}&gt; id: {2}</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781c0-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="781c0-116">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="781c0-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="781c0-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="781c0-118">ID da entidade de segurança que atualizou esta linha.</span><span class="sxs-lookup"><span data-stu-id="781c0-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="781c0-119">É sempre 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="781c0-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="781c0-120">As</span><span class="sxs-lookup"><span data-stu-id="781c0-120">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="781c0-121">Coluna (s)</span><span class="sxs-lookup"><span data-stu-id="781c0-121">Column(s)</span></span></th>
<th><span data-ttu-id="781c0-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="781c0-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="781c0-123">&lt;affDescription&gt;</span><span class="sxs-lookup"><span data-stu-id="781c0-123">&lt;prinID, affDescription&gt;</span></span></p></td>
<td><p><span data-ttu-id="781c0-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="781c0-124">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781c0-125">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="781c0-125">prinID</span></span></p></td>
<td><p><span data-ttu-id="781c0-126">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="781c0-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

