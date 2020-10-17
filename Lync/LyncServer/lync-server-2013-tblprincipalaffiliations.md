---
title: 'Lync Server 2013: tblPrincipalAffiliations'
description: 'Lync Server 2013: tblPrincipalAffiliations.'
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
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547477"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="ef7b3-103">tblPrincipalAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef7b3-103">tblPrincipalAffiliations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef7b3-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ef7b3-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ef7b3-105">tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio do Active Directory, em contêineres do Active Directory, em domínios.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-105">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="ef7b3-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="ef7b3-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef7b3-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="ef7b3-107">Column</span></span></th>
<th><span data-ttu-id="ef7b3-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="ef7b3-108">Type</span></span></th>
<th><span data-ttu-id="ef7b3-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="ef7b3-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef7b3-110">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="ef7b3-110">principalID</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="ef7b3-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-112">ID da entidade de segurança afiliada.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-112">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef7b3-113">afiliaid</span><span class="sxs-lookup"><span data-stu-id="ef7b3-113">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="ef7b3-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-p101">ID da entidade de segurança que representa a afiliação. Cada entidade (exceto system-user-types) tem também uma autoafiliação.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef7b3-117">index</span><span class="sxs-lookup"><span data-stu-id="ef7b3-117">index</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-118">int, not null</span><span class="sxs-lookup"><span data-stu-id="ef7b3-118">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-119">Índice.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-119">Index.</span></span> <span data-ttu-id="ef7b3-120">O valor para autoafiliações é-1 e para as outras afiliações que ela aumenta de forma seqüencial de 1 em cada &lt; entidade de segurança, &gt; BucketID.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-120">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef7b3-121">updatedBy</span><span class="sxs-lookup"><span data-stu-id="ef7b3-121">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-122">int, not null</span><span class="sxs-lookup"><span data-stu-id="ef7b3-122">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-p103">Entidade de segurança que fez a atualização mais recente. Isso geralmente é 1, o que significa Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ef7b3-125">Chaves</span><span class="sxs-lookup"><span data-stu-id="ef7b3-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef7b3-126">Colunas</span><span class="sxs-lookup"><span data-stu-id="ef7b3-126">Columns</span></span></th>
<th><span data-ttu-id="ef7b3-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="ef7b3-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef7b3-128">&lt;entidade de segurança, índice, afiliaid&gt;</span><span class="sxs-lookup"><span data-stu-id="ef7b3-128">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-129">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef7b3-130">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="ef7b3-130">principalID</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-131">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef7b3-132">afiliaid</span><span class="sxs-lookup"><span data-stu-id="ef7b3-132">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="ef7b3-133">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="ef7b3-133">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

