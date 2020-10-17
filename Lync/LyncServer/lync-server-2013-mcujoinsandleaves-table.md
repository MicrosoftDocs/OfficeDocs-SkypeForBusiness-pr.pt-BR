---
title: 'Lync Server 2013: tabela McuJoinsAndLeaves'
description: 'Lync Server 2013: tabela McuJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556497"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="4956f-103">Tabela McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4956f-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4956f-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4956f-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4956f-105">Cada registro desta tabela contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de licença e de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="4956f-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="4956f-106">Por exemplo, se um usuário ingressar em uma conferência que inclui a conferência da Web e os elementos de áudio/vídeo, um registro será criado para a associação de Webconferência do usuário, e outro registro será criado para a junção de conferência de áudio/vídeo do usuário.</span><span class="sxs-lookup"><span data-stu-id="4956f-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4956f-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="4956f-107">Column</span></span></th>
<th><span data-ttu-id="4956f-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4956f-108">Data Type</span></span></th>
<th><span data-ttu-id="4956f-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="4956f-109">Key/Index</span></span></th>
<th><span data-ttu-id="4956f-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4956f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4956f-111"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4956f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4956f-113">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="4956f-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4956f-114">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="4956f-114">Time of conference instance.</span></span> <span data-ttu-id="4956f-115">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="4956f-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="4956f-116">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4956f-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4956f-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-118">int</span><span class="sxs-lookup"><span data-stu-id="4956f-118">int</span></span></p></td>
<td><p><span data-ttu-id="4956f-119">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="4956f-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4956f-120">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="4956f-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="4956f-121">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="4956f-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="4956f-122">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4956f-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4956f-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-124">int</span><span class="sxs-lookup"><span data-stu-id="4956f-124">int</span></span></p></td>
<td><p><span data-ttu-id="4956f-125">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="4956f-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4956f-126">Número exclusivo identificando este usuário.</span><span class="sxs-lookup"><span data-stu-id="4956f-126">Unique number identifying this user.</span></span> <span data-ttu-id="4956f-127">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4956f-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4956f-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-129">int</span><span class="sxs-lookup"><span data-stu-id="4956f-129">int</span></span></p></td>
<td><p><span data-ttu-id="4956f-130">Primário</span><span class="sxs-lookup"><span data-stu-id="4956f-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="4956f-131">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, McuUserInstance identifica exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4956f-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4956f-132"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-133">bits</span><span class="sxs-lookup"><span data-stu-id="4956f-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4956f-134">Se o usuário está ingressando de uma PSTN ou não.</span><span class="sxs-lookup"><span data-stu-id="4956f-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4956f-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-136">int</span><span class="sxs-lookup"><span data-stu-id="4956f-136">int</span></span></p></td>
<td><p><span data-ttu-id="4956f-137">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="4956f-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="4956f-138">Número exclusivo que identifica este servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="4956f-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="4956f-139">Consulte a <a href="lync-server-2013-mcus-table.md">tabela MCUs no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4956f-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4956f-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-141">datetime</span><span class="sxs-lookup"><span data-stu-id="4956f-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="4956f-142">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4956f-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4956f-143">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="4956f-143">Time of session request.</span></span> <span data-ttu-id="4956f-144">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="4956f-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4956f-145">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4956f-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4956f-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-147">int</span><span class="sxs-lookup"><span data-stu-id="4956f-147">int</span></span></p></td>
<td><p><span data-ttu-id="4956f-148">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4956f-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4956f-149">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="4956f-149">ID number to identify the session.</span></span> <span data-ttu-id="4956f-150">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="4956f-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4956f-151">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4956f-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4956f-152"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-153">datetime</span><span class="sxs-lookup"><span data-stu-id="4956f-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4956f-154">A hora em que este usuário ingressa neste servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="4956f-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4956f-155"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-156">datetime</span><span class="sxs-lookup"><span data-stu-id="4956f-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4956f-157">O horário em que este usuário deixa este servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="4956f-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4956f-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="4956f-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4956f-159">int</span><span class="sxs-lookup"><span data-stu-id="4956f-159">int</span></span></p></td>
<td><p><span data-ttu-id="4956f-160">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="4956f-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4956f-161">Identificador que especifica o número da versão do software cliente usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="4956f-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="4956f-162">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4956f-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4956f-163">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4956f-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

