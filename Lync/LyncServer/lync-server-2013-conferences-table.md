---
title: 'Lync Server 2013: Tabela Conferences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="1d0f9-102">Tabela Conferences no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d0f9-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d0f9-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1d0f9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1d0f9-104">Cada registro desta tabela contém detalhes da chamada sobre uma conferência.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d0f9-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="1d0f9-105">Column</span></span></th>
<th><span data-ttu-id="1d0f9-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="1d0f9-106">Data Type</span></span></th>
<th><span data-ttu-id="1d0f9-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="1d0f9-107">Key/Index</span></span></th>
<th><span data-ttu-id="1d0f9-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="1d0f9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d0f9-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1d0f9-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-111">Primária</span><span class="sxs-lookup"><span data-stu-id="1d0f9-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-112">Hora em que a solicitação de conferência foi capturada pelo agente de CDR.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="1d0f9-113">Usado apenas como uma chave primária para identificar uma instância de conferência de forma exclusiva.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d0f9-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-115">int</span><span class="sxs-lookup"><span data-stu-id="1d0f9-115">int</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-116">Primária</span><span class="sxs-lookup"><span data-stu-id="1d0f9-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-117">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-117">ID number to identify the session.</span></span> <span data-ttu-id="1d0f9-118">Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d0f9-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-120">int</span><span class="sxs-lookup"><span data-stu-id="1d0f9-120">int</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="1d0f9-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-122">URL da conferência.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-122">Conference URI.</span></span> <span data-ttu-id="1d0f9-123">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d0f9-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-125">identificador</span><span class="sxs-lookup"><span data-stu-id="1d0f9-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d0f9-126">Útil para conferências recorrentes; cada instância de uma conferência recorrente tem o mesmo <strong>ConferenceUri</strong>, mas terá um <strong>ConfInstance</strong>diferente.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d0f9-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-128">datetime</span><span class="sxs-lookup"><span data-stu-id="1d0f9-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d0f9-129">Hora de início da conferência.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d0f9-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-131">datetime</span><span class="sxs-lookup"><span data-stu-id="1d0f9-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1d0f9-132">Hora de início da conferência.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d0f9-133"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-134">int</span><span class="sxs-lookup"><span data-stu-id="1d0f9-134">int</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-135">Exterior</span><span class="sxs-lookup"><span data-stu-id="1d0f9-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-136">Número de identificação para identificar o pool no qual a conferência foi capturada.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="1d0f9-137">Consulte a <a href="lync-server-2013-pools-table.md">tabela de grupos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d0f9-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-139">Núm</span><span class="sxs-lookup"><span data-stu-id="1d0f9-139">Int</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-140">Exterior</span><span class="sxs-lookup"><span data-stu-id="1d0f9-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1d0f9-141">Número de identificação para identificar o URI do organizador dessa conferência.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="1d0f9-142">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d0f9-143"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-144">smallint</span><span class="sxs-lookup"><span data-stu-id="1d0f9-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d0f9-145">Uma máscara de bits que contém atributos de conferência.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="1d0f9-146">Os valores possíveis são:</span><span class="sxs-lookup"><span data-stu-id="1d0f9-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1d0f9-147">0X01</span><span class="sxs-lookup"><span data-stu-id="1d0f9-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="1d0f9-148">Sintética</span><span class="sxs-lookup"><span data-stu-id="1d0f9-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="1d0f9-149">Transação</span><span class="sxs-lookup"><span data-stu-id="1d0f9-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d0f9-150"><strong>Processe</strong></span><span class="sxs-lookup"><span data-stu-id="1d0f9-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="1d0f9-151">bit</span><span class="sxs-lookup"><span data-stu-id="1d0f9-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d0f9-152">Campo interno usado pelo serviço de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="1d0f9-153">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1d0f9-154">\*Para a maioria das sessões, o SessionIdSeq terá o valor de 1.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="1d0f9-155">Se duas sessões começarem exatamente ao mesmo tempo, o SessionIdSeq de uma será 1 e, para a outra, será 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="1d0f9-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

