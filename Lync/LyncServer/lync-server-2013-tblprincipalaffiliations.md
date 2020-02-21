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
ms.openlocfilehash: 0a57e4a3c7a5fdcc1825c140cb6e26f8cede8dc1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a><span data-ttu-id="58600-102">tblPrincipalAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58600-102">tblPrincipalAffiliations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58600-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="58600-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="58600-104">tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio do Active Directory, em contêineres do Active Directory, em domínios.</span><span class="sxs-lookup"><span data-stu-id="58600-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>

### <a name="columns"></a><span data-ttu-id="58600-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="58600-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58600-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="58600-106">Column</span></span></th>
<th><span data-ttu-id="58600-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="58600-107">Type</span></span></th>
<th><span data-ttu-id="58600-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="58600-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58600-109">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="58600-109">principalID</span></span></p></td>
<td><p><span data-ttu-id="58600-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="58600-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="58600-111">ID da entidade de segurança afiliada.</span><span class="sxs-lookup"><span data-stu-id="58600-111">ID of the affiliated principal.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58600-112">afiliaid</span><span class="sxs-lookup"><span data-stu-id="58600-112">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="58600-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="58600-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="58600-p101">ID da entidade de segurança que representa a afiliação. Cada entidade (exceto system-user-types) tem também uma autoafiliação.</span><span class="sxs-lookup"><span data-stu-id="58600-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58600-116">index</span><span class="sxs-lookup"><span data-stu-id="58600-116">index</span></span></p></td>
<td><p><span data-ttu-id="58600-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="58600-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="58600-118">Índice.</span><span class="sxs-lookup"><span data-stu-id="58600-118">Index.</span></span> <span data-ttu-id="58600-119">O valor para autoafiliações é-1 e para as outras afiliações que ela aumenta de forma seqüencial de 1 em cada &lt;entidade de segurança,&gt; BucketID.</span><span class="sxs-lookup"><span data-stu-id="58600-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each &lt;principalID, affiliationId&gt; bucket.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58600-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="58600-120">updatedBy</span></span></p></td>
<td><p><span data-ttu-id="58600-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="58600-121">int, not null</span></span></p></td>
<td><p><span data-ttu-id="58600-p103">Entidade de segurança que fez a atualização mais recente. Isso geralmente é 1, o que significa Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="58600-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="58600-124">Chaves</span><span class="sxs-lookup"><span data-stu-id="58600-124">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58600-125">Colunas</span><span class="sxs-lookup"><span data-stu-id="58600-125">Columns</span></span></th>
<th><span data-ttu-id="58600-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="58600-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58600-127">&lt;entidade de segurança, índice, afiliaid&gt;</span><span class="sxs-lookup"><span data-stu-id="58600-127">&lt;principalID, index, affiliationID&gt;</span></span></p></td>
<td><p><span data-ttu-id="58600-128">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="58600-128">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58600-129">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="58600-129">principalID</span></span></p></td>
<td><p><span data-ttu-id="58600-130">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="58600-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58600-131">afiliaid</span><span class="sxs-lookup"><span data-stu-id="58600-131">affiliationID</span></span></p></td>
<td><p><span data-ttu-id="58600-132">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="58600-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

