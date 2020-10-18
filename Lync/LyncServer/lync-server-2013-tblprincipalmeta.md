---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta.'
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
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573637"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="f0f7a-103">tblPrincipalMeta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0f7a-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0f7a-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f0f7a-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f0f7a-105">tblPrincipalMeta contém as entidades de segurança que precisam ser atualizadas dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="f0f7a-106">Colunas</span><span class="sxs-lookup"><span data-stu-id="f0f7a-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0f7a-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="f0f7a-107">Column</span></span></th>
<th><span data-ttu-id="f0f7a-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="f0f7a-108">Type</span></span></th>
<th><span data-ttu-id="f0f7a-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0f7a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0f7a-110">prinID</span><span class="sxs-lookup"><span data-stu-id="f0f7a-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-111">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f0f7a-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-112">ID principal.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0f7a-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="f0f7a-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-114">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f0f7a-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-115">Verdadeiro se as afiliações da entidade precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0f7a-116">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="f0f7a-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-117">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f0f7a-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-118">Verdadeiro se os atributos da entidade precisam ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0f7a-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f0f7a-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-120">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f0f7a-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-121">Verdadeiro se a entidade foi excluída.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0f7a-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="f0f7a-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-123">int</span><span class="sxs-lookup"><span data-stu-id="f0f7a-123">int</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-124">Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0f7a-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="f0f7a-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-126">datetime</span><span class="sxs-lookup"><span data-stu-id="f0f7a-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-p101">Carimbo de data/hora da tentativa mais recente para atualizar a entidade. Pode ser nulo se ainda não houve tentativa de atualização.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0f7a-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="f0f7a-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-130">datetime</span><span class="sxs-lookup"><span data-stu-id="f0f7a-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-p102">Carimbo de data/hora para a próxima atualização agendada. Pode ser nulo se nenhuma atualização foi agendada.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="f0f7a-133">Chaves</span><span class="sxs-lookup"><span data-stu-id="f0f7a-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0f7a-134">Coluna</span><span class="sxs-lookup"><span data-stu-id="f0f7a-134">Column</span></span></th>
<th><span data-ttu-id="f0f7a-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="f0f7a-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0f7a-136">prinID</span><span class="sxs-lookup"><span data-stu-id="f0f7a-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-137">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0f7a-138">prinID</span><span class="sxs-lookup"><span data-stu-id="f0f7a-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="f0f7a-139">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f0f7a-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

