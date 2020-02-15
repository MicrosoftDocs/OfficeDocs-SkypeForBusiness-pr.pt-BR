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
ms.openlocfilehash: 56f292a35f5e4f24ba5226e06a308e780ce5c687
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="24c9d-102">Exibição de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c9d-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24c9d-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="24c9d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="24c9d-104">A Exibição de Conferências armazena informações sobre as conferências.</span><span class="sxs-lookup"><span data-stu-id="24c9d-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="24c9d-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24c9d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24c9d-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="24c9d-106">Column</span></span></th>
<th><span data-ttu-id="24c9d-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="24c9d-107">Data Type</span></span></th>
<th><span data-ttu-id="24c9d-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="24c9d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24c9d-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="24c9d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="24c9d-111">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="24c9d-111">Time of session request.</span></span> <span data-ttu-id="24c9d-112">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="24c9d-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="24c9d-113">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="24c9d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c9d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-115">int</span><span class="sxs-lookup"><span data-stu-id="24c9d-115">int</span></span></p></td>
<td><p><span data-ttu-id="24c9d-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="24c9d-116">ID number to identify the session.</span></span> <span data-ttu-id="24c9d-117">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="24c9d-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="24c9d-118">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="24c9d-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24c9d-119"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="24c9d-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="24c9d-121">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="24c9d-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c9d-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="24c9d-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="24c9d-124">Tipo da URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="24c9d-124">Type of the conference URI.</span></span> <span data-ttu-id="24c9d-125">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="24c9d-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24c9d-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-127">identificador</span><span class="sxs-lookup"><span data-stu-id="24c9d-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="24c9d-p105">Usado para conferências recorrentes. Cada instância de uma conferência recorrente possui o mesmo ConferenceUri, mas um ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="24c9d-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c9d-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-131">datetime</span><span class="sxs-lookup"><span data-stu-id="24c9d-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="24c9d-132">Hora inicial da conferência.</span><span class="sxs-lookup"><span data-stu-id="24c9d-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24c9d-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-134">datetime</span><span class="sxs-lookup"><span data-stu-id="24c9d-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="24c9d-135">Hora final da conferência.</span><span class="sxs-lookup"><span data-stu-id="24c9d-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c9d-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="24c9d-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="24c9d-138">URI do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="24c9d-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24c9d-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="24c9d-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="24c9d-141">Tipo de URI do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="24c9d-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="24c9d-142">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="24c9d-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c9d-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="24c9d-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="24c9d-145">Inquilino do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="24c9d-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="24c9d-146">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="24c9d-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24c9d-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="24c9d-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="24c9d-149">Nome de domínio totalmente qualificado do pool que hospeda a conferência.</span><span class="sxs-lookup"><span data-stu-id="24c9d-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c9d-150"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="24c9d-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="24c9d-151">smallint</span><span class="sxs-lookup"><span data-stu-id="24c9d-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="24c9d-p108">Máscara de bits que contém os Atributos de Conferência. Os possíveis valores são:</span><span class="sxs-lookup"><span data-stu-id="24c9d-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="24c9d-154">0X01 – Transação Sintética</span><span class="sxs-lookup"><span data-stu-id="24c9d-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

