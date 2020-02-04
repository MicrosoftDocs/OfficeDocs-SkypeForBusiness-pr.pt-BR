---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
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
ms.openlocfilehash: baaf336013ec09b17b8e688889fdf27aa29ef644
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="9aaa3-102">tblPrincipalMemberDifference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9aaa3-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9aaa3-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9aaa3-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9aaa3-104">tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processados pelas etapas de sincronização dos serviços de domínio Active Directory mais recentes.</span><span class="sxs-lookup"><span data-stu-id="9aaa3-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="9aaa3-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="9aaa3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9aaa3-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="9aaa3-106">Column</span></span></th>
<th><span data-ttu-id="9aaa3-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="9aaa3-107">Type</span></span></th>
<th><span data-ttu-id="9aaa3-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="9aaa3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9aaa3-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="9aaa3-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="9aaa3-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="9aaa3-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="9aaa3-111">O principal GUID do grupo que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="9aaa3-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9aaa3-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="9aaa3-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="9aaa3-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9aaa3-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="9aaa3-114">Nome diferenciado do membro.</span><span class="sxs-lookup"><span data-stu-id="9aaa3-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9aaa3-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="9aaa3-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="9aaa3-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="9aaa3-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9aaa3-117">Falso se o membro tiver sido adicionado.</span><span class="sxs-lookup"><span data-stu-id="9aaa3-117">False if the member was added.</span></span> <span data-ttu-id="9aaa3-118">Verdadeiro se o membro tiver sido removido.</span><span class="sxs-lookup"><span data-stu-id="9aaa3-118">True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="9aaa3-119">Chave</span><span class="sxs-lookup"><span data-stu-id="9aaa3-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9aaa3-120">Coluna</span><span class="sxs-lookup"><span data-stu-id="9aaa3-120">Column</span></span></th>
<th><span data-ttu-id="9aaa3-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="9aaa3-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9aaa3-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="9aaa3-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="9aaa3-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="9aaa3-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

