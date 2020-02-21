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
ms.openlocfilehash: 04ad0fbdb9a4e3bb2e5962089fe1c30f960bdc91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="da17b-102">tblPrincipalMeta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da17b-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da17b-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="da17b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="da17b-104">tblPrincipalMeta contém as entidades de segurança que precisam ser atualizadas dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="da17b-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="da17b-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="da17b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da17b-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="da17b-106">Column</span></span></th>
<th><span data-ttu-id="da17b-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="da17b-107">Type</span></span></th>
<th><span data-ttu-id="da17b-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="da17b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da17b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="da17b-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="da17b-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="da17b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="da17b-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="da17b-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da17b-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="da17b-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="da17b-113">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="da17b-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="da17b-114">Verdadeiro se as afiliações da entidade precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="da17b-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da17b-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="da17b-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="da17b-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="da17b-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="da17b-117">Verdadeiro se os atributos da entidade precisam ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="da17b-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da17b-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="da17b-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="da17b-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="da17b-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="da17b-120">Verdadeiro se a entidade foi excluída.</span><span class="sxs-lookup"><span data-stu-id="da17b-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da17b-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="da17b-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="da17b-122">int</span><span class="sxs-lookup"><span data-stu-id="da17b-122">int</span></span></p></td>
<td><p><span data-ttu-id="da17b-123">Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.</span><span class="sxs-lookup"><span data-stu-id="da17b-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da17b-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="da17b-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="da17b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="da17b-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="da17b-p101">Carimbo de data/hora da tentativa mais recente para atualizar a entidade. Pode ser nulo se ainda não houve tentativa de atualização.</span><span class="sxs-lookup"><span data-stu-id="da17b-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da17b-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="da17b-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="da17b-129">datetime</span><span class="sxs-lookup"><span data-stu-id="da17b-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="da17b-p102">Carimbo de data/hora para a próxima atualização agendada. Pode ser nulo se nenhuma atualização foi agendada.</span><span class="sxs-lookup"><span data-stu-id="da17b-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="da17b-132">Chaves</span><span class="sxs-lookup"><span data-stu-id="da17b-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da17b-133">Coluna</span><span class="sxs-lookup"><span data-stu-id="da17b-133">Column</span></span></th>
<th><span data-ttu-id="da17b-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="da17b-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da17b-135">prinID</span><span class="sxs-lookup"><span data-stu-id="da17b-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="da17b-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="da17b-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da17b-137">prinID</span><span class="sxs-lookup"><span data-stu-id="da17b-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="da17b-138">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="da17b-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

