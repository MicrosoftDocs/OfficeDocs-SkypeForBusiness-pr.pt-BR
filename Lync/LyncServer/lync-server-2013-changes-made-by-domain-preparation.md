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
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="d83f1-102">Alterações feitas pela preparação do domínio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d83f1-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d83f1-103">_**Última modificação do tópico:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="d83f1-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="d83f1-p101">A tabela a seguir lista as ACEs (entradas de controle de acesso) que a preparação de domínio cria na raiz do domínio. Todas as ACEs serão herdadas, salvo indicação em contrário.</span><span class="sxs-lookup"><span data-stu-id="d83f1-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="d83f1-106">ACEs adicionadas à raiz do domínio</span><span class="sxs-lookup"><span data-stu-id="d83f1-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="d83f1-107">ACE</span><span class="sxs-lookup"><span data-stu-id="d83f1-107">ACE</span></span></th>
<th><span data-ttu-id="d83f1-108">RTCUniversal-userreadonly-Group</span><span class="sxs-lookup"><span data-stu-id="d83f1-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="d83f1-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d83f1-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="d83f1-110">RTCUniversal-useradmins</span><span class="sxs-lookup"><span data-stu-id="d83f1-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="d83f1-111">RTCHSUniversal-serviços</span><span class="sxs-lookup"><span data-stu-id="d83f1-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="d83f1-112">Usuários autenticados</span><span class="sxs-lookup"><span data-stu-id="d83f1-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d83f1-113">Ler contêiner (não herdado)</span><span class="sxs-lookup"><span data-stu-id="d83f1-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="d83f1-114">Sim</span><span class="sxs-lookup"><span data-stu-id="d83f1-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-115"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-116">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-116">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-117">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-117">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-118">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d83f1-119">Ler User PropertySet User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="d83f1-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="d83f1-120"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-121">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-121">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-122">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-122">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-123">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-123">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-124">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d83f1-125">Ler User PropertySet Personal-Information</span><span class="sxs-lookup"><span data-stu-id="d83f1-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="d83f1-126"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-127">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-127">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-128">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-128">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-129">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-129">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-130">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d83f1-131">Ler User PropertySet General-Information</span><span class="sxs-lookup"><span data-stu-id="d83f1-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="d83f1-132"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-133">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-133">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-134">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-134">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-135">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-135">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-136">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d83f1-137">Ler User PropertySet Public-Information</span><span class="sxs-lookup"><span data-stu-id="d83f1-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="d83f1-138"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-139">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-139">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-140">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-140">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-141">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-141">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-142">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d83f1-143">Ler User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="d83f1-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="d83f1-144"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-145">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-145">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-146">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-146">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-147">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-147">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-148">Sim</span><span class="sxs-lookup"><span data-stu-id="d83f1-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d83f1-149">Ler User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d83f1-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="d83f1-150"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-151">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-151">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-152">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-152">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-153">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-153">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-154">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d83f1-155">Gravar User Property Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="d83f1-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="d83f1-156">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-156">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-157">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-157">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-158"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-159">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-159">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-160">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d83f1-161">Gravar User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="d83f1-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="d83f1-162">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-162">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-163">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-163">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-164"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-165">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-165">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-166">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d83f1-167">Gravar User PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="d83f1-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="d83f1-168">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-168">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-169">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-169">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-170"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-171">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-171">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-172">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d83f1-173">Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="d83f1-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="d83f1-174">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-174">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-175">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-175">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-176">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-176">No</span></span></p></td>
<td><p><span data-ttu-id="d83f1-177"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-178">Não</span><span class="sxs-lookup"><span data-stu-id="d83f1-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d83f1-p102">A tabela a seguir lista as ACEs que a preparação do domínio cria nos três contêineres internos: Usuários, Computadores e Controladores de Domínio. Todas as ACEs são herdadas, a menos que especificado de outra forma.</span><span class="sxs-lookup"><span data-stu-id="d83f1-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="d83f1-181">ACEs adicionadas à contêineres internos</span><span class="sxs-lookup"><span data-stu-id="d83f1-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d83f1-182">ACE</span><span class="sxs-lookup"><span data-stu-id="d83f1-182">ACE</span></span></th>
<th><span data-ttu-id="d83f1-183">RTCUniversal-userreadonly-Group</span><span class="sxs-lookup"><span data-stu-id="d83f1-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="d83f1-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="d83f1-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d83f1-185">Ler contêiner (não herdado)</span><span class="sxs-lookup"><span data-stu-id="d83f1-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="d83f1-186">Sim</span><span class="sxs-lookup"><span data-stu-id="d83f1-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="d83f1-187"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="d83f1-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

