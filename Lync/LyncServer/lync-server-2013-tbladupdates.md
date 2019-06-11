---
title: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f171d8346442f915cd71fb48d51bba80bcfa32ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="9558e-102">tblADUpdates no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9558e-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9558e-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9558e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9558e-104">o tblADUpdates contém alterações dos serviços de domínio Active Directory que ainda não foram processadas pelas etapas de sincronização posteriores do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9558e-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="9558e-105">Colunas</span><span class="sxs-lookup"><span data-stu-id="9558e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9558e-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="9558e-106">Column</span></span></th>
<th><span data-ttu-id="9558e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="9558e-107">Type</span></span></th>
<th><span data-ttu-id="9558e-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="9558e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9558e-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="9558e-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="9558e-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="9558e-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="9558e-111">O principal GUID do objeto que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="9558e-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9558e-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="9558e-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="9558e-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9558e-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="9558e-114">Nome diferenciado do objeto.</span><span class="sxs-lookup"><span data-stu-id="9558e-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9558e-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="9558e-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="9558e-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="9558e-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9558e-117">True se pelo menos um atributo do objeto foi alterado.</span><span class="sxs-lookup"><span data-stu-id="9558e-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9558e-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="9558e-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="9558e-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="9558e-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9558e-120">Verdadeiro se a associação for alterada.</span><span class="sxs-lookup"><span data-stu-id="9558e-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9558e-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="9558e-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="9558e-122">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="9558e-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9558e-123">Não usado.</span><span class="sxs-lookup"><span data-stu-id="9558e-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9558e-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="9558e-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="9558e-125">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="9558e-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9558e-126">Verdadeiro se o objeto foi excluído.</span><span class="sxs-lookup"><span data-stu-id="9558e-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9558e-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="9558e-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="9558e-128">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="9558e-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="9558e-129">Carimbo de data/hora de quando a linha foi inserida.</span><span class="sxs-lookup"><span data-stu-id="9558e-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

