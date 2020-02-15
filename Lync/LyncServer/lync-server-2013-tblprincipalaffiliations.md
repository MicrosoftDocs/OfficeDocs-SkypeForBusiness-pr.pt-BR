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
ms.openlocfilehash: ee16c492a42cb98ff3b5f326bd6f43a57c4d3f56
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="e487a-102">tblPrincipalAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e487a-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e487a-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e487a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e487a-104">tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio do Active Directory, em contêineres do Active Directory, em domínios.</span><span class="sxs-lookup"><span data-stu-id="e487a-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="e487a-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="e487a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e487a-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="e487a-106">Column</span></span></th>
<th><span data-ttu-id="e487a-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e487a-107">Type</span></span></th>
<th><span data-ttu-id="e487a-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="e487a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e487a-109">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="e487a-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="e487a-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e487a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e487a-111">ID da entidade de segurança afiliada.</span><span class="sxs-lookup"><span data-stu-id="e487a-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e487a-112">afiliaid</span><span class="sxs-lookup"><span data-stu-id="e487a-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="e487a-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e487a-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e487a-p101">ID da entidade de segurança que representa a afiliação. Cada entidade (exceto system-user-types) tem também uma autoafiliação.</span><span class="sxs-lookup"><span data-stu-id="e487a-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e487a-116">index</span><span class="sxs-lookup"><span data-stu-id="e487a-116">index</span></span></p></td>
<td><p><span data-ttu-id="e487a-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="e487a-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e487a-118">Índice.</span><span class="sxs-lookup"><span data-stu-id="e487a-118">Index.</span></span> <span data-ttu-id="e487a-119">O valor para autoafiliações é-1 e para as outras afiliações que ela aumenta de forma seqüencial de 1 em cada &lt;entidade de segurança,&gt; BucketID.</span><span class="sxs-lookup"><span data-stu-id="e487a-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e487a-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e487a-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="e487a-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="e487a-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e487a-p103">Entidade de segurança que fez a atualização mais recente. Isso geralmente é 1, o que significa Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e487a-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e487a-124">Chaves</span><span class="sxs-lookup"><span data-stu-id="e487a-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e487a-125">Colunas</span><span class="sxs-lookup"><span data-stu-id="e487a-125">Columns</span></span></th>
<th><span data-ttu-id="e487a-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="e487a-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e487a-127">&lt;entidade de segurança, índice, afiliaid&gt;</span><span class="sxs-lookup"><span data-stu-id="e487a-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e487a-128">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="e487a-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e487a-129">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="e487a-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="e487a-130">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e487a-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e487a-131">afiliaid</span><span class="sxs-lookup"><span data-stu-id="e487a-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="e487a-132">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="e487a-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

