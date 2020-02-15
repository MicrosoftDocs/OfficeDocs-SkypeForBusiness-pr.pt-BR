---
title: 'Lync Server 2013: alterações feitas pela preparação do domínio'
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
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="a273f-102">Alterações feitas pela preparação do domínio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a273f-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a273f-103">_**Última modificação do tópico:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="a273f-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="a273f-p101">A tabela a seguir lista as ACEs (entradas de controle de acesso) que a preparação de domínio cria na raiz do domínio. Todas as ACEs serão herdadas, salvo indicação em contrário.</span><span class="sxs-lookup"><span data-stu-id="a273f-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="a273f-106">ACEs adicionadas à raiz do domínio</span><span class="sxs-lookup"><span data-stu-id="a273f-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="a273f-107">ACE</span><span class="sxs-lookup"><span data-stu-id="a273f-107">ACE</span></span></th>
<th><span data-ttu-id="a273f-108">RTCUniversal-userreadonly-Group</span><span class="sxs-lookup"><span data-stu-id="a273f-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="a273f-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="a273f-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="a273f-110">RTCUniversal-useradmins</span><span class="sxs-lookup"><span data-stu-id="a273f-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="a273f-111">RTCHSUniversal-serviços</span><span class="sxs-lookup"><span data-stu-id="a273f-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="a273f-112">Usuários autenticados</span><span class="sxs-lookup"><span data-stu-id="a273f-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a273f-113">Ler contêiner (não herdado)</span><span class="sxs-lookup"><span data-stu-id="a273f-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="a273f-114">Sim</span><span class="sxs-lookup"><span data-stu-id="a273f-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-115"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-116">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-116">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-117">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-117">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-118">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a273f-119">Ler User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="a273f-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a273f-120"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-121">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-121">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-122">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-122">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-123">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-123">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-124">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a273f-125">Ler User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="a273f-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="a273f-126"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-127">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-127">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-128">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-128">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-129">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-129">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-130">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a273f-131">Ler User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="a273f-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="a273f-132"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-133">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-133">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-134">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-134">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-135">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-135">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-136">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a273f-137">Ler User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="a273f-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="a273f-138"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-139">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-139">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-140">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-140">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-141">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-141">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-142">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a273f-143">Ler User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="a273f-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="a273f-144"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-145">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-145">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-146">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-146">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-147">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-147">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-148">Sim</span><span class="sxs-lookup"><span data-stu-id="a273f-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a273f-149">Ler User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a273f-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="a273f-150"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-151">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-151">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-152">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-152">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-153">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-153">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-154">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a273f-155">Gravar User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="a273f-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="a273f-156">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-156">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-157">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-157">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-158"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-159">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-159">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-160">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a273f-161">Gravar User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="a273f-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="a273f-162">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-162">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-163">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-163">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-164"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-165">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-165">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-166">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a273f-167">Gravar User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="a273f-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="a273f-168">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-168">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-169">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-169">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-170"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-171">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-171">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-172">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a273f-173">Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="a273f-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="a273f-174">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-174">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-175">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-175">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-176">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-176">No</span></span></p></td>
<td><p><span data-ttu-id="a273f-177"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-178">Não</span><span class="sxs-lookup"><span data-stu-id="a273f-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a273f-p102">A tabela a seguir lista as ACEs que a preparação do domínio cria nos três contêineres internos: Usuários, Computadores e Controladores de Domínio. Todas as ACEs são herdadas, a menos que especificado de outra forma.</span><span class="sxs-lookup"><span data-stu-id="a273f-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="a273f-181">ACEs adicionadas à contêineres internos</span><span class="sxs-lookup"><span data-stu-id="a273f-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a273f-182">ACE</span><span class="sxs-lookup"><span data-stu-id="a273f-182">ACE</span></span></th>
<th><span data-ttu-id="a273f-183">RTCUniversal-userreadonly-Group</span><span class="sxs-lookup"><span data-stu-id="a273f-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="a273f-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="a273f-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a273f-185">Ler contêiner (não herdado)</span><span class="sxs-lookup"><span data-stu-id="a273f-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="a273f-186">Sim</span><span class="sxs-lookup"><span data-stu-id="a273f-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a273f-187"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a273f-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

