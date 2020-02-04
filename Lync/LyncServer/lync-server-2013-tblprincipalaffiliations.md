---
title: 'Lync Server 2013: tblPrincipalAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="0697f-102">tblPrincipalAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0697f-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0697f-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0697f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0697f-104">tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio Active Directory, em contêineres do Active Directory, em domínios.</span><span class="sxs-lookup"><span data-stu-id="0697f-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="0697f-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="0697f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0697f-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="0697f-106">Column</span></span></th>
<th><span data-ttu-id="0697f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="0697f-107">Type</span></span></th>
<th><span data-ttu-id="0697f-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="0697f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0697f-109">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="0697f-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="0697f-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="0697f-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0697f-111">ID do objeto associado.</span><span class="sxs-lookup"><span data-stu-id="0697f-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0697f-112">afiliaid</span><span class="sxs-lookup"><span data-stu-id="0697f-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="0697f-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="0697f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0697f-114">ID da entidade de segurança que representa a afiliada.</span><span class="sxs-lookup"><span data-stu-id="0697f-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="0697f-115">Cada entidade de segurança (exceto tipos de usuário do sistema) também tem uma afiliada.</span><span class="sxs-lookup"><span data-stu-id="0697f-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0697f-116">dedo</span><span class="sxs-lookup"><span data-stu-id="0697f-116">index</span></span></p></td>
<td><p><span data-ttu-id="0697f-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="0697f-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0697f-118">Dedo.</span><span class="sxs-lookup"><span data-stu-id="0697f-118">Index.</span></span> <span data-ttu-id="0697f-119">O valor para autoafiliações é-1 e para as outras afiliações que ele aumenta sequencialmente de 1 dentro de cada &lt;objeto de entidade de segurança&gt; , o BucketID.</span><span class="sxs-lookup"><span data-stu-id="0697f-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0697f-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="0697f-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="0697f-121">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="0697f-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0697f-122">Entidade de segurança que fez a atualização mais recente.</span><span class="sxs-lookup"><span data-stu-id="0697f-122">Principal that did the latest update.</span></span> <span data-ttu-id="0697f-123">Geralmente, isso é 1, o que significa sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0697f-123">This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="0697f-124">As</span><span class="sxs-lookup"><span data-stu-id="0697f-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0697f-125">Colunas</span><span class="sxs-lookup"><span data-stu-id="0697f-125">Columns</span></span></th>
<th><span data-ttu-id="0697f-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="0697f-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0697f-127">&lt;entidade de segurança, índice, afiliaid&gt;</span><span class="sxs-lookup"><span data-stu-id="0697f-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="0697f-128">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="0697f-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0697f-129">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="0697f-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="0697f-130">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="0697f-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0697f-131">afiliaid</span><span class="sxs-lookup"><span data-stu-id="0697f-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="0697f-132">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="0697f-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

