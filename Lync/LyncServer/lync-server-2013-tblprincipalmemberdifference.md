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
ms.openlocfilehash: 8965a842adba2e1f0f3b1197ee392aec3ef10566
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a><span data-ttu-id="213c3-102">tblPrincipalMemberDifference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="213c3-102">tblPrincipalMemberDifference in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="213c3-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="213c3-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="213c3-104">tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processados pelas etapas de sincronização dos serviços de domínio do Active Directory posteriores.</span><span class="sxs-lookup"><span data-stu-id="213c3-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="213c3-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="213c3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="213c3-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="213c3-106">Column</span></span></th>
<th><span data-ttu-id="213c3-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="213c3-107">Type</span></span></th>
<th><span data-ttu-id="213c3-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="213c3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="213c3-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="213c3-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="213c3-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="213c3-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="213c3-111">GUID principal do grupo que mudou.</span><span class="sxs-lookup"><span data-stu-id="213c3-111">Principal GUID of the group that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="213c3-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="213c3-112">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="213c3-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="213c3-113">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="213c3-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="213c3-114">Distinguished name of the member.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="213c3-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="213c3-115">memberRemoved</span></span></p></td>
<td><p><span data-ttu-id="213c3-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="213c3-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="213c3-p101">Falso se o membro tiver sido adicionado. Verdadeiro se o membro tiver sido removido.</span><span class="sxs-lookup"><span data-stu-id="213c3-p101">False if the member was added. True if the member was removed.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="213c3-119">Chave</span><span class="sxs-lookup"><span data-stu-id="213c3-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="213c3-120">Coluna</span><span class="sxs-lookup"><span data-stu-id="213c3-120">Column</span></span></th>
<th><span data-ttu-id="213c3-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="213c3-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="213c3-122">&lt;prinGuid, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="213c3-122">&lt;prinGuid, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="213c3-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="213c3-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

