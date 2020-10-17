---
title: 'Lync Server 2013: tabela de conferências'
description: 'Lync Server 2013: tabela de conferências.'
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
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561597"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="bfeeb-103">Tabela de conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfeeb-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfeeb-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bfeeb-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bfeeb-105">Cada registro desta tabela contém os detalhes da chamada de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfeeb-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="bfeeb-106">Column</span></span></th>
<th><span data-ttu-id="bfeeb-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="bfeeb-107">Data Type</span></span></th>
<th><span data-ttu-id="bfeeb-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="bfeeb-108">Key/Index</span></span></th>
<th><span data-ttu-id="bfeeb-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bfeeb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfeeb-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-111">datetime</span><span class="sxs-lookup"><span data-stu-id="bfeeb-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-112">Primário</span><span class="sxs-lookup"><span data-stu-id="bfeeb-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-113">Hora em que a solicitação de conferência foi capturada pelo agente CDR.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="bfeeb-114">Usado apenas como uma chave primária para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfeeb-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-116">int</span><span class="sxs-lookup"><span data-stu-id="bfeeb-116">int</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-117">Primário</span><span class="sxs-lookup"><span data-stu-id="bfeeb-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-118">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-118">ID number to identify the session.</span></span> <span data-ttu-id="bfeeb-119">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfeeb-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-121">int</span><span class="sxs-lookup"><span data-stu-id="bfeeb-121">int</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-122">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="bfeeb-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-123">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-123">Conference URI.</span></span> <span data-ttu-id="bfeeb-124">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfeeb-125"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-126">identificador</span><span class="sxs-lookup"><span data-stu-id="bfeeb-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bfeeb-127">Útil para conferências recorrentes; cada instância de uma conferência recorrente tem o mesmo <strong>conferenceui</strong>, mas terá um <strong>ConfInstance</strong>diferente.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfeeb-128"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-129">datetime</span><span class="sxs-lookup"><span data-stu-id="bfeeb-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bfeeb-130">Hora de início da conferência.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfeeb-131"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-132">datetime</span><span class="sxs-lookup"><span data-stu-id="bfeeb-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bfeeb-133">Hora de início da conferência.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfeeb-134"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-135">int</span><span class="sxs-lookup"><span data-stu-id="bfeeb-135">int</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-136">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="bfeeb-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-137">Número de identificação para identificar o pool no qual a conferência foi capturada.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="bfeeb-138">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfeeb-139"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-140">Int</span><span class="sxs-lookup"><span data-stu-id="bfeeb-140">Int</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-141">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="bfeeb-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="bfeeb-142">Número de identificação para identificar o URI do organizador desta conferência.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="bfeeb-143">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfeeb-144"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-145">smallint</span><span class="sxs-lookup"><span data-stu-id="bfeeb-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bfeeb-146">Uma máscara de bits que contém atributos de conferência.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="bfeeb-147">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="bfeeb-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="bfeeb-148">0X01</span><span class="sxs-lookup"><span data-stu-id="bfeeb-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="bfeeb-149">Sintética</span><span class="sxs-lookup"><span data-stu-id="bfeeb-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="bfeeb-150">Transação</span><span class="sxs-lookup"><span data-stu-id="bfeeb-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfeeb-151"><strong>Processa</strong></span><span class="sxs-lookup"><span data-stu-id="bfeeb-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="bfeeb-152">bits</span><span class="sxs-lookup"><span data-stu-id="bfeeb-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bfeeb-153">Campo interno usado pelo serviço de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="bfeeb-154">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bfeeb-155">\* Para a maioria das sessões, SessionIdSeq terá o valor 1.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="bfeeb-156">Se duas sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de um será 1 e o outro será 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

