---
title: 'Lync Server 2013: modo de exibição de conferências'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="e01c8-102">Modo de exibição conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e01c8-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e01c8-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e01c8-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e01c8-104">O modo de exibição conferências armazena informações sobre as conferências.</span><span class="sxs-lookup"><span data-stu-id="e01c8-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="e01c8-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e01c8-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e01c8-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="e01c8-106">Column</span></span></th>
<th><span data-ttu-id="e01c8-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e01c8-107">Data Type</span></span></th>
<th><span data-ttu-id="e01c8-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e01c8-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e01c8-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e01c8-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e01c8-111">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="e01c8-111">Time of session request.</span></span> <span data-ttu-id="e01c8-112">Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e01c8-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e01c8-113">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e01c8-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01c8-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-115">int</span><span class="sxs-lookup"><span data-stu-id="e01c8-115">int</span></span></p></td>
<td><p><span data-ttu-id="e01c8-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="e01c8-116">ID number to identify the session.</span></span> <span data-ttu-id="e01c8-117">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e01c8-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e01c8-118">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e01c8-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01c8-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e01c8-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e01c8-121">URL para a conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01c8-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e01c8-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e01c8-124">Tipo de URL da conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-124">Type of the conference URI.</span></span> <span data-ttu-id="e01c8-125">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e01c8-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01c8-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-127">identificador</span><span class="sxs-lookup"><span data-stu-id="e01c8-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e01c8-128">Usado para conferências recorrentes.</span><span class="sxs-lookup"><span data-stu-id="e01c8-128">Used for recurring conferences.</span></span> <span data-ttu-id="e01c8-129">Cada instância de uma conferência recorrente tem o mesmo ConferenceUri, mas um ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="e01c8-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01c8-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-131">datetime</span><span class="sxs-lookup"><span data-stu-id="e01c8-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="e01c8-132">Hora de início da conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01c8-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-134">datetime</span><span class="sxs-lookup"><span data-stu-id="e01c8-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="e01c8-135">Hora de término da conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01c8-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e01c8-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e01c8-138">URI do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01c8-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e01c8-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e01c8-141">Tipo de URI do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="e01c8-142">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e01c8-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01c8-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e01c8-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e01c8-145">Locatário do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="e01c8-146">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e01c8-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e01c8-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e01c8-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e01c8-149">Nome de domínio totalmente qualificado do pool que hospeda a conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e01c8-150"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="e01c8-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e01c8-151">smallint</span><span class="sxs-lookup"><span data-stu-id="e01c8-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="e01c8-152">Máscara de bits que contém atributos de conferência.</span><span class="sxs-lookup"><span data-stu-id="e01c8-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="e01c8-153">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="e01c8-153">Possible values are:</span></span></p>
<p><span data-ttu-id="e01c8-154">0X01 – transação sintética</span><span class="sxs-lookup"><span data-stu-id="e01c8-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

