---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3f0d881e26c3d26773b1b59feca3d1d02665dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="f15df-102">tblADUpdates no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f15df-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f15df-103">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f15df-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f15df-104">tblADUpdates contém alterações dos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f15df-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="f15df-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="f15df-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f15df-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="f15df-106">Column</span></span></th>
<th><span data-ttu-id="f15df-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="f15df-107">Type</span></span></th>
<th><span data-ttu-id="f15df-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="f15df-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f15df-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f15df-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="f15df-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="f15df-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="f15df-111">GUID da entidade do objeto que mudou.</span><span class="sxs-lookup"><span data-stu-id="f15df-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f15df-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="f15df-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="f15df-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="f15df-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="f15df-114">Nome distinto do objeto.</span><span class="sxs-lookup"><span data-stu-id="f15df-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f15df-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="f15df-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="f15df-116">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="f15df-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f15df-117">True se pelo menos um atributo do objeto tiver mudado.</span><span class="sxs-lookup"><span data-stu-id="f15df-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f15df-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="f15df-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="f15df-119">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="f15df-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f15df-120">True se a associação tiver sido alterada.</span><span class="sxs-lookup"><span data-stu-id="f15df-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f15df-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="f15df-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="f15df-122">bit, não vazio</span><span class="sxs-lookup"><span data-stu-id="f15df-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f15df-123">Não usado</span><span class="sxs-lookup"><span data-stu-id="f15df-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f15df-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f15df-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="f15df-125">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f15df-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="f15df-126">True se o objeto tiver sido excluído.</span><span class="sxs-lookup"><span data-stu-id="f15df-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f15df-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="f15df-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="f15df-128">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="f15df-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="f15df-129">Carimbo de hora de quando a linha foi inserida.</span><span class="sxs-lookup"><span data-stu-id="f15df-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

