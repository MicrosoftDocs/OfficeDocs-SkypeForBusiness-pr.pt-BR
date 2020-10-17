---
title: 'Lync Server 2013: tabela McuJoinsAndLeaves'
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
ms.openlocfilehash: f4aa5fb14ff16d13b1cdff72f15c648f9e353922
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524728"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="f50f9-102">Tabela McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f50f9-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f50f9-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f50f9-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f50f9-104">Cada registro desta tabela contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de licença e de conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="f50f9-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="f50f9-105">Por exemplo, se um usuário ingressar em uma conferência que inclui a conferência da Web e os elementos de áudio/vídeo, um registro será criado para a associação de Webconferência do usuário, e outro registro será criado para a junção de conferência de áudio/vídeo do usuário.</span><span class="sxs-lookup"><span data-stu-id="f50f9-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f50f9-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="f50f9-106">Column</span></span></th>
<th><span data-ttu-id="f50f9-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f50f9-107">Data Type</span></span></th>
<th><span data-ttu-id="f50f9-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="f50f9-108">Key/Index</span></span></th>
<th><span data-ttu-id="f50f9-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f50f9-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f50f9-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f50f9-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f50f9-112">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="f50f9-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f50f9-113">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="f50f9-113">Time of conference instance.</span></span> <span data-ttu-id="f50f9-114">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="f50f9-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f50f9-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f50f9-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f50f9-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-117">int</span><span class="sxs-lookup"><span data-stu-id="f50f9-117">int</span></span></p></td>
<td><p><span data-ttu-id="f50f9-118">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="f50f9-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f50f9-119">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="f50f9-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="f50f9-120">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="f50f9-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f50f9-121">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f50f9-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f50f9-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-123">int</span><span class="sxs-lookup"><span data-stu-id="f50f9-123">int</span></span></p></td>
<td><p><span data-ttu-id="f50f9-124">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="f50f9-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f50f9-125">Número exclusivo identificando este usuário.</span><span class="sxs-lookup"><span data-stu-id="f50f9-125">Unique number identifying this user.</span></span> <span data-ttu-id="f50f9-126">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f50f9-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f50f9-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-128">int</span><span class="sxs-lookup"><span data-stu-id="f50f9-128">int</span></span></p></td>
<td><p><span data-ttu-id="f50f9-129">Primário</span><span class="sxs-lookup"><span data-stu-id="f50f9-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="f50f9-130">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, McuUserInstance identifica exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f50f9-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f50f9-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-132">bits</span><span class="sxs-lookup"><span data-stu-id="f50f9-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f50f9-133">Se o usuário está ingressando de uma PSTN ou não.</span><span class="sxs-lookup"><span data-stu-id="f50f9-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f50f9-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-135">int</span><span class="sxs-lookup"><span data-stu-id="f50f9-135">int</span></span></p></td>
<td><p><span data-ttu-id="f50f9-136">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="f50f9-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f50f9-137">Número exclusivo que identifica este servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="f50f9-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="f50f9-138">Consulte a <a href="lync-server-2013-mcus-table.md">tabela MCUs no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f50f9-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f50f9-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-140">datetime</span><span class="sxs-lookup"><span data-stu-id="f50f9-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="f50f9-141">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="f50f9-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f50f9-142">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="f50f9-142">Time of session request.</span></span> <span data-ttu-id="f50f9-143">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f50f9-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f50f9-144">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f50f9-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f50f9-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-146">int</span><span class="sxs-lookup"><span data-stu-id="f50f9-146">int</span></span></p></td>
<td><p><span data-ttu-id="f50f9-147">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="f50f9-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f50f9-148">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="f50f9-148">ID number to identify the session.</span></span> <span data-ttu-id="f50f9-149">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f50f9-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f50f9-150">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f50f9-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f50f9-151"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-152">datetime</span><span class="sxs-lookup"><span data-stu-id="f50f9-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f50f9-153">A hora em que este usuário ingressa neste servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="f50f9-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f50f9-154"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-155">datetime</span><span class="sxs-lookup"><span data-stu-id="f50f9-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f50f9-156">O horário em que este usuário deixa este servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="f50f9-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f50f9-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="f50f9-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f50f9-158">int</span><span class="sxs-lookup"><span data-stu-id="f50f9-158">int</span></span></p></td>
<td><p><span data-ttu-id="f50f9-159">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="f50f9-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f50f9-160">Identificador que especifica o número da versão do software cliente usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="f50f9-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="f50f9-161">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f50f9-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f50f9-162">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f50f9-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

