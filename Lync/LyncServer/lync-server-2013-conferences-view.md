---
title: 'Lync Server 2013: modo de exibição de conferências'
description: 'Lync Server 2013: modo de exibição de conferências.'
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
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561577"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="91e57-103">Exibição de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91e57-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91e57-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="91e57-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="91e57-105">A Exibição de Conferências armazena informações sobre as conferências.</span><span class="sxs-lookup"><span data-stu-id="91e57-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="91e57-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91e57-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91e57-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="91e57-107">Column</span></span></th>
<th><span data-ttu-id="91e57-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="91e57-108">Data Type</span></span></th>
<th><span data-ttu-id="91e57-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="91e57-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91e57-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-111">datetime</span><span class="sxs-lookup"><span data-stu-id="91e57-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="91e57-112">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="91e57-112">Time of session request.</span></span> <span data-ttu-id="91e57-113">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="91e57-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="91e57-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="91e57-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e57-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-116">int</span><span class="sxs-lookup"><span data-stu-id="91e57-116">int</span></span></p></td>
<td><p><span data-ttu-id="91e57-117">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="91e57-117">ID number to identify the session.</span></span> <span data-ttu-id="91e57-118">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="91e57-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="91e57-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="91e57-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e57-120"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91e57-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91e57-122">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="91e57-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e57-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91e57-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91e57-125">Tipo da URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="91e57-125">Type of the conference URI.</span></span> <span data-ttu-id="91e57-126">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="91e57-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e57-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-128">identificador</span><span class="sxs-lookup"><span data-stu-id="91e57-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="91e57-p105">Usado para conferências recorrentes. Cada instância de uma conferência recorrente possui o mesmo ConferenceUri, mas um ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="91e57-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e57-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-132">datetime</span><span class="sxs-lookup"><span data-stu-id="91e57-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="91e57-133">Hora inicial da conferência.</span><span class="sxs-lookup"><span data-stu-id="91e57-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e57-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-135">datetime</span><span class="sxs-lookup"><span data-stu-id="91e57-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="91e57-136">Hora final da conferência.</span><span class="sxs-lookup"><span data-stu-id="91e57-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e57-137"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="91e57-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="91e57-139">URI do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="91e57-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e57-140"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91e57-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91e57-142">Tipo de URI do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="91e57-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="91e57-143">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="91e57-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e57-144"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91e57-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91e57-146">Inquilino do usuário que organizou a conferência.</span><span class="sxs-lookup"><span data-stu-id="91e57-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="91e57-147">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="91e57-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91e57-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="91e57-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="91e57-150">Nome de domínio totalmente qualificado do pool que hospeda a conferência.</span><span class="sxs-lookup"><span data-stu-id="91e57-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91e57-151"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="91e57-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="91e57-152">smallint</span><span class="sxs-lookup"><span data-stu-id="91e57-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="91e57-p108">Máscara de bits que contém os Atributos de Conferência. Os possíveis valores são:</span><span class="sxs-lookup"><span data-stu-id="91e57-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="91e57-155">0X01 – Transação Sintética</span><span class="sxs-lookup"><span data-stu-id="91e57-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

