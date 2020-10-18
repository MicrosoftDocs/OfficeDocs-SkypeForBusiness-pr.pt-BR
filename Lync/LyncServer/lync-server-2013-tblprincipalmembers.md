---
title: 'Lync Server 2013: tblPrincipalMembers'
description: 'Lync Server 2013: tblPrincipalMembers.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMembers
ms:assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615022(v=OCS.15)
ms:contentKeyID: 48184965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bbb8be0b83d09b1bd54ea98655558581e6df834
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573177"
---
# <a name="tblprincipalmembers-in-lync-server-2013"></a><span data-ttu-id="6cf38-103">tblPrincipalMembers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cf38-103">tblPrincipalMembers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cf38-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6cf38-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6cf38-105">tblPrincipalMembers contém associações de entidade.</span><span class="sxs-lookup"><span data-stu-id="6cf38-105">tblPrincipalMembers contains principal memberships.</span></span>

### <a name="columns"></a><span data-ttu-id="6cf38-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="6cf38-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cf38-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="6cf38-107">Column</span></span></th>
<th><span data-ttu-id="6cf38-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="6cf38-108">Type</span></span></th>
<th><span data-ttu-id="6cf38-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="6cf38-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cf38-110">prinID</span><span class="sxs-lookup"><span data-stu-id="6cf38-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="6cf38-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6cf38-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6cf38-112">ID principal.</span><span class="sxs-lookup"><span data-stu-id="6cf38-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf38-113">memberADPath</span><span class="sxs-lookup"><span data-stu-id="6cf38-113">memberADPath</span></span></p></td>
<td><p><span data-ttu-id="6cf38-114">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="6cf38-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="6cf38-115">Nome distinto de um membro.</span><span class="sxs-lookup"><span data-stu-id="6cf38-115">Distinguished name of a member.</span></span> <span data-ttu-id="6cf38-116">Um membro não precisa ser uma entidade (na tabela tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="6cf38-116">A member does not have to be a principal (in tblPrincipal table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6cf38-117">Chaves</span><span class="sxs-lookup"><span data-stu-id="6cf38-117">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cf38-118">Coluna</span><span class="sxs-lookup"><span data-stu-id="6cf38-118">Column</span></span></th>
<th><span data-ttu-id="6cf38-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="6cf38-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cf38-120">&lt;imprimir, memberADPath&gt;</span><span class="sxs-lookup"><span data-stu-id="6cf38-120">&lt;prinID, memberADPath&gt;</span></span></p></td>
<td><p><span data-ttu-id="6cf38-121">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6cf38-121">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cf38-122">prinID</span><span class="sxs-lookup"><span data-stu-id="6cf38-122">prinID</span></span></p></td>
<td><p><span data-ttu-id="6cf38-123">Chave estrangeira com pesquisa em tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="6cf38-123">Foreign key with lookup in tblPrincipal.prinID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

