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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="a0900-102">Alterações feitas por preparação do domínio no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0900-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0900-103">_**Tópico da última modificação:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="a0900-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="a0900-104">A tabela a seguir lista as entradas de controle de acesso (ACEs) que a preparação do domínio cria na raiz do domínio.</span><span class="sxs-lookup"><span data-stu-id="a0900-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="a0900-105">Todas as ACEs são herdadas, a menos que indicado de outra forma.</span><span class="sxs-lookup"><span data-stu-id="a0900-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="a0900-106">ACEs adicionadas à raiz do domínio</span><span class="sxs-lookup"><span data-stu-id="a0900-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="a0900-107">ACE</span><span class="sxs-lookup"><span data-stu-id="a0900-107">ACE</span></span></th>
<th><span data-ttu-id="a0900-108">RTCUniversal-userreadonly-Group</span><span class="sxs-lookup"><span data-stu-id="a0900-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="a0900-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="a0900-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="a0900-110">RTCUniversal-administradores do useradmin</span><span class="sxs-lookup"><span data-stu-id="a0900-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="a0900-111">RTCHSUniversal-serviços</span><span class="sxs-lookup"><span data-stu-id="a0900-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="a0900-112">Usuários autenticados</span><span class="sxs-lookup"><span data-stu-id="a0900-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0900-113">Contêiner de leitura (não herdado)</span><span class="sxs-lookup"><span data-stu-id="a0900-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="a0900-114"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-115"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-116">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-116">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-117">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-117">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-118">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0900-119">Ler propriedades do usuário-User-Restriction-restrições de conta</span><span class="sxs-lookup"><span data-stu-id="a0900-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a0900-120"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-121">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-121">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-122">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-122">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-123">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-123">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-124">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0900-125">Ler propriedades do usuário pessoal-informações</span><span class="sxs-lookup"><span data-stu-id="a0900-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="a0900-126"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-127">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-127">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-128">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-128">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-129">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-129">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-130">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0900-131">Ler propriedades do usuário – informações gerais-informações</span><span class="sxs-lookup"><span data-stu-id="a0900-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="a0900-132"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-133">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-133">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-134">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-134">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-135">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-135">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-136">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0900-137">Ler as informações públicas de propriedades do usuário</span><span class="sxs-lookup"><span data-stu-id="a0900-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="a0900-138"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-139">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-139">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-140">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-140">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-141">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-141">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-142">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0900-143">Ler conjunto de RTCUserSearchProperty de propriedades do usuário</span><span class="sxs-lookup"><span data-stu-id="a0900-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="a0900-144"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-145">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-145">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-146">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-146">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-147">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-147">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-148"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0900-149">Ler RTCPropertySet de propriedades do usuário</span><span class="sxs-lookup"><span data-stu-id="a0900-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="a0900-150"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-151">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-151">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-152">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-152">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-153">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-153">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-154">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0900-155">Gravar endereços de proxy de propriedade de usuário</span><span class="sxs-lookup"><span data-stu-id="a0900-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="a0900-156">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-156">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-157">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-157">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-158"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-159">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-159">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-160">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0900-161">Gravar RTCUserSearchProperty de propriedades do usuário-definir</span><span class="sxs-lookup"><span data-stu-id="a0900-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="a0900-162">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-162">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-163">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-163">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-164"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-165">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-165">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-166">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0900-167">Gravar usuário do RTCPropertySet de propriedades</span><span class="sxs-lookup"><span data-stu-id="a0900-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="a0900-168">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-168">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-169">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-169">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-170"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-171">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-171">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-172">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0900-173">Ler PropertySet DS-Replication-Get-Changes de todos os objetos do Active Directory</span><span class="sxs-lookup"><span data-stu-id="a0900-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="a0900-174">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-174">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-175">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-175">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-176">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-176">No</span></span></p></td>
<td><p><span data-ttu-id="a0900-177"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-178">Não</span><span class="sxs-lookup"><span data-stu-id="a0900-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a0900-179">A tabela a seguir lista as ACEs que a preparação do domínio cria nos três contêineres internos: usuários, computadores e controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="a0900-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="a0900-180">Todas as ACEs são herdadas, a menos que indicado de outra forma.</span><span class="sxs-lookup"><span data-stu-id="a0900-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="a0900-181">ACEs adicionadas a contêineres internos</span><span class="sxs-lookup"><span data-stu-id="a0900-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0900-182">ACE</span><span class="sxs-lookup"><span data-stu-id="a0900-182">ACE</span></span></th>
<th><span data-ttu-id="a0900-183">RTCUniversal-userreadonly-Group</span><span class="sxs-lookup"><span data-stu-id="a0900-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="a0900-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="a0900-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0900-185">Contêiner de leitura (não herdado)</span><span class="sxs-lookup"><span data-stu-id="a0900-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="a0900-186"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="a0900-187"><strong>Sim</strong></span><span class="sxs-lookup"><span data-stu-id="a0900-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

