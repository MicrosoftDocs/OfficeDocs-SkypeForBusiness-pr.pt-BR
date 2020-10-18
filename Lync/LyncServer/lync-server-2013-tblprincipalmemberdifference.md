---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
description: 'Lync Server 2013: tblPrincipalMemberDifference.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce7c770a6fed02dc27d2493816fae58943d391a6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573217"
---
# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="bc07f-103">tblPrincipalMemberDifference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc07f-103">tblPrincipalMemberDifference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc07f-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bc07f-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bc07f-105">tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processados pelas etapas de sincronização dos serviços de domínio do Active Directory posteriores.</span><span class="sxs-lookup"><span data-stu-id="bc07f-105">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="bc07f-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="bc07f-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc07f-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="bc07f-107">Column</span></span></th>
<th><span data-ttu-id="bc07f-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="bc07f-108">Type</span></span></th>
<th><span data-ttu-id="bc07f-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc07f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc07f-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="bc07f-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="bc07f-111">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="bc07f-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="bc07f-112">GUID principal do grupo que mudou.</span><span class="sxs-lookup"><span data-stu-id="bc07f-112">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc07f-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="bc07f-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="bc07f-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bc07f-114">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="bc07f-115">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="bc07f-115">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc07f-116">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="bc07f-116">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="bc07f-117">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="bc07f-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="bc07f-p101">Falso se o membro tiver sido adicionado. Verdadeiro se o membro tiver sido removido.</span><span class="sxs-lookup"><span data-stu-id="bc07f-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="bc07f-120">Chave</span><span class="sxs-lookup"><span data-stu-id="bc07f-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc07f-121">Coluna</span><span class="sxs-lookup"><span data-stu-id="bc07f-121">Column</span></span></th>
<th><span data-ttu-id="bc07f-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="bc07f-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc07f-123">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="bc07f-123">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="bc07f-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="bc07f-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

