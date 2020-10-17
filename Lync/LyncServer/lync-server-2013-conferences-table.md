---
title: 'Lync Server 2013: tabela de conferências'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5e8811ad4b0adaccd8964e2f0bca718ca531e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529258"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="18847-102">Tabela de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18847-102">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18847-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="18847-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="18847-104">Cada registro desta tabela contém os detalhes da chamada de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="18847-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18847-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="18847-105">Column</span></span></th>
<th><span data-ttu-id="18847-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="18847-106">Data Type</span></span></th>
<th><span data-ttu-id="18847-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="18847-107">Key/Index</span></span></th>
<th><span data-ttu-id="18847-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="18847-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18847-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="18847-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-110">datetime</span><span class="sxs-lookup"><span data-stu-id="18847-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="18847-111">Primário</span><span class="sxs-lookup"><span data-stu-id="18847-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="18847-112">Hora em que a solicitação de conferência foi capturada pelo agente CDR.</span><span class="sxs-lookup"><span data-stu-id="18847-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="18847-113">Usado apenas como uma chave primária para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="18847-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18847-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="18847-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-115">int</span><span class="sxs-lookup"><span data-stu-id="18847-115">int</span></span></p></td>
<td><p><span data-ttu-id="18847-116">Primário</span><span class="sxs-lookup"><span data-stu-id="18847-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="18847-117">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="18847-117">ID number to identify the session.</span></span> <span data-ttu-id="18847-118">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="18847-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18847-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="18847-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-120">int</span><span class="sxs-lookup"><span data-stu-id="18847-120">int</span></span></p></td>
<td><p><span data-ttu-id="18847-121">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18847-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18847-122">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="18847-122">Conference URI.</span></span> <span data-ttu-id="18847-123">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18847-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18847-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="18847-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-125">identificador</span><span class="sxs-lookup"><span data-stu-id="18847-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="18847-126">Útil para conferências recorrentes; cada instância de uma conferência recorrente tem o mesmo <strong>conferenceui</strong>, mas terá um <strong>ConfInstance</strong>diferente.</span><span class="sxs-lookup"><span data-stu-id="18847-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18847-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="18847-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-128">datetime</span><span class="sxs-lookup"><span data-stu-id="18847-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="18847-129">Hora de início da conferência.</span><span class="sxs-lookup"><span data-stu-id="18847-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18847-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="18847-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-131">datetime</span><span class="sxs-lookup"><span data-stu-id="18847-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="18847-132">Hora de início da conferência.</span><span class="sxs-lookup"><span data-stu-id="18847-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18847-133"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="18847-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-134">int</span><span class="sxs-lookup"><span data-stu-id="18847-134">int</span></span></p></td>
<td><p><span data-ttu-id="18847-135">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18847-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18847-136">Número de identificação para identificar o pool no qual a conferência foi capturada.</span><span class="sxs-lookup"><span data-stu-id="18847-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="18847-137">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18847-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18847-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="18847-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-139">Int</span><span class="sxs-lookup"><span data-stu-id="18847-139">Int</span></span></p></td>
<td><p><span data-ttu-id="18847-140">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18847-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18847-141">Número de identificação para identificar o URI do organizador desta conferência.</span><span class="sxs-lookup"><span data-stu-id="18847-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="18847-142">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18847-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18847-143"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="18847-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-144">smallint</span><span class="sxs-lookup"><span data-stu-id="18847-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="18847-145">Uma máscara de bits que contém atributos de conferência.</span><span class="sxs-lookup"><span data-stu-id="18847-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="18847-146">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="18847-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="18847-147">0X01</span><span class="sxs-lookup"><span data-stu-id="18847-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="18847-148">Sintética</span><span class="sxs-lookup"><span data-stu-id="18847-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="18847-149">Transação</span><span class="sxs-lookup"><span data-stu-id="18847-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18847-150"><strong>Processa</strong></span><span class="sxs-lookup"><span data-stu-id="18847-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="18847-151">bits</span><span class="sxs-lookup"><span data-stu-id="18847-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="18847-152">Campo interno usado pelo serviço de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="18847-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="18847-153">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18847-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18847-154">\* Para a maioria das sessões, SessionIdSeq terá o valor 1.</span><span class="sxs-lookup"><span data-stu-id="18847-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="18847-155">Se duas sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de um será 1 e o outro será 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="18847-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

