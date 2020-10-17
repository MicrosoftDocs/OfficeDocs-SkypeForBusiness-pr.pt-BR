---
title: 'Lync Server 2013: alterações feitas pela preparação do domínio'
description: 'Lync Server 2013: alterações feitas pela preparação do domínio.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543687"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="9ca3e-103">Alterações feitas pela preparação do domínio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9ca3e-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ca3e-104">_**Última modificação do tópico:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="9ca3e-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="9ca3e-p101">A tabela a seguir lista as ACEs (entradas de controle de acesso) que a preparação de domínio cria na raiz do domínio. Todas as ACEs serão herdadas, salvo indicação em contrário.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="9ca3e-107">ACEs adicionadas à raiz do domínio</span><span class="sxs-lookup"><span data-stu-id="9ca3e-107">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ca3e-108">ACE</span><span class="sxs-lookup"><span data-stu-id="9ca3e-108">ACE</span></span></th>
<th><span data-ttu-id="9ca3e-109">RTCUniversal-userreadonly-Group</span><span class="sxs-lookup"><span data-stu-id="9ca3e-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="9ca3e-110">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="9ca3e-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="9ca3e-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="9ca3e-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="9ca3e-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="9ca3e-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="9ca3e-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="9ca3e-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ca3e-114">Ler contêiner (não herdado)</span><span class="sxs-lookup"><span data-stu-id="9ca3e-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-115"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="9ca3e-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-116">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-117">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-117">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-118">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-118">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-119">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca3e-120">Ler User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="9ca3e-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-121">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-122">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-122">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-123">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-123">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-124">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-124">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-125">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca3e-126">Ler User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="9ca3e-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-127">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-128">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-128">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-129">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-129">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-130">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-130">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-131">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca3e-132">Ler User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="9ca3e-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-133">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-134">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-134">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-135">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-135">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-136">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-136">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-137">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca3e-138">Ler User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="9ca3e-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-139">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-140">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-140">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-141">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-141">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-142">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-142">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-143">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca3e-144">Ler User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="9ca3e-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-145">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-146">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-146">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-147">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-147">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-148">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-148">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-149">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca3e-150">Ler User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ca3e-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-151">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-152">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-152">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-153">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-153">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-154">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-154">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-155">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca3e-156">Gravar User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="9ca3e-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-157">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-157">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-158">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-158">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-159">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-160">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-160">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-161">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca3e-162">Gravar User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="9ca3e-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-163">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-163">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-164">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-164">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-165">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-166">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-166">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-167">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ca3e-168">Gravar User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="9ca3e-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-169">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-169">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-170">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-170">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-171">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-172">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-172">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-173">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ca3e-174">Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="9ca3e-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-175">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-175">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-176">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-176">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-177">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-177">No</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-178">Sim</span><span class="sxs-lookup"><span data-stu-id="9ca3e-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-179">Não</span><span class="sxs-lookup"><span data-stu-id="9ca3e-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9ca3e-p102">A tabela a seguir lista as ACEs que a preparação do domínio cria nos três contêineres internos: Usuários, Computadores e Controladores de Domínio. Todas as ACEs são herdadas, a menos que especificado de outra forma.</span><span class="sxs-lookup"><span data-stu-id="9ca3e-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="9ca3e-182">ACEs adicionadas à contêineres internos</span><span class="sxs-lookup"><span data-stu-id="9ca3e-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ca3e-183">ACE</span><span class="sxs-lookup"><span data-stu-id="9ca3e-183">ACE</span></span></th>
<th><span data-ttu-id="9ca3e-184">RTCUniversal-userreadonly-Group</span><span class="sxs-lookup"><span data-stu-id="9ca3e-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="9ca3e-185">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="9ca3e-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ca3e-186">Ler contêiner (não herdado)</span><span class="sxs-lookup"><span data-stu-id="9ca3e-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="9ca3e-187"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="9ca3e-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="9ca3e-188"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="9ca3e-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

