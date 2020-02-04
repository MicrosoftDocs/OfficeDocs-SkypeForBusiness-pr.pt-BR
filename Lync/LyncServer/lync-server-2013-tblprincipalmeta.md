---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="38127-102">tblPrincipalMeta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38127-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38127-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="38127-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="38127-104">tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas a partir dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38127-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="38127-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="38127-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38127-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="38127-106">Column</span></span></th>
<th><span data-ttu-id="38127-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="38127-107">Type</span></span></th>
<th><span data-ttu-id="38127-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="38127-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38127-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="38127-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="38127-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="38127-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="38127-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="38127-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38127-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="38127-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="38127-113">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="38127-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="38127-114">Verdadeiro se as afiliações principais precisarem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="38127-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38127-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="38127-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="38127-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="38127-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="38127-117">Verdadeiro se os atributos principais precisarem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="38127-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38127-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="38127-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="38127-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="38127-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="38127-120">Verdadeiro se o capital foi excluído.</span><span class="sxs-lookup"><span data-stu-id="38127-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38127-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="38127-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="38127-122">int</span><span class="sxs-lookup"><span data-stu-id="38127-122">int</span></span></p></td>
<td><p><span data-ttu-id="38127-123">Número de tentativas de atualizar a entidade de segurança do AD DS que aconteceram até agora.</span><span class="sxs-lookup"><span data-stu-id="38127-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38127-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="38127-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="38127-125">datetime</span><span class="sxs-lookup"><span data-stu-id="38127-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="38127-126">Carimbo de data/hora da tentativa mais recente de atualizar a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="38127-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="38127-127">Pode ser NULL se ainda não houver uma tentativa de atualização.</span><span class="sxs-lookup"><span data-stu-id="38127-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38127-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="38127-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="38127-129">datetime</span><span class="sxs-lookup"><span data-stu-id="38127-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="38127-130">Carimbo de data/hora para a próxima atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="38127-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="38127-131">Pode ser NULL se não houver mais nenhuma atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="38127-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="38127-132">As</span><span class="sxs-lookup"><span data-stu-id="38127-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38127-133">Coluna</span><span class="sxs-lookup"><span data-stu-id="38127-133">Column</span></span></th>
<th><span data-ttu-id="38127-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="38127-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38127-135">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="38127-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="38127-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="38127-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38127-137">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="38127-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="38127-138">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="38127-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

