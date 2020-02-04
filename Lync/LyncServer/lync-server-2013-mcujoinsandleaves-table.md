---
title: 'Lync Server 2013: Tabela McuJoinsAndLeaves'
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
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="de0c0-102">Tabela McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de0c0-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de0c0-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="de0c0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="de0c0-104">Cada registro desta tabela contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de saída e conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="de0c0-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="de0c0-105">Por exemplo, se um usuário ingressar em uma conferência que inclui a conferência da Web e os elementos de áudio/vídeo, um registro seria criado para a sua associação de Webconferência do usuário e outro registro será criado para a reunião de conferência de áudio/vídeo do usuário.</span><span class="sxs-lookup"><span data-stu-id="de0c0-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de0c0-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="de0c0-106">Column</span></span></th>
<th><span data-ttu-id="de0c0-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="de0c0-107">Data Type</span></span></th>
<th><span data-ttu-id="de0c0-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="de0c0-108">Key/Index</span></span></th>
<th><span data-ttu-id="de0c0-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="de0c0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de0c0-110"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-111">datetime</span><span class="sxs-lookup"><span data-stu-id="de0c0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="de0c0-112">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="de0c0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="de0c0-113">Hora da ocorrência da conferência.</span><span class="sxs-lookup"><span data-stu-id="de0c0-113">Time of conference instance.</span></span> <span data-ttu-id="de0c0-114">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar uma instância de conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="de0c0-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="de0c0-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de0c0-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de0c0-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-117">int</span><span class="sxs-lookup"><span data-stu-id="de0c0-117">int</span></span></p></td>
<td><p><span data-ttu-id="de0c0-118">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="de0c0-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="de0c0-119">Número de identificação para identificar a instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="de0c0-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="de0c0-120">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="de0c0-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="de0c0-121">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de0c0-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de0c0-122"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-123">int</span><span class="sxs-lookup"><span data-stu-id="de0c0-123">int</span></span></p></td>
<td><p><span data-ttu-id="de0c0-124">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="de0c0-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="de0c0-125">Número exclusivo que identifica esse usuário.</span><span class="sxs-lookup"><span data-stu-id="de0c0-125">Unique number identifying this user.</span></span> <span data-ttu-id="de0c0-126">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de0c0-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de0c0-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-128">int</span><span class="sxs-lookup"><span data-stu-id="de0c0-128">int</span></span></p></td>
<td><p><span data-ttu-id="de0c0-129">Primária</span><span class="sxs-lookup"><span data-stu-id="de0c0-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="de0c0-130">Se um usuário estiver conectado em vários computadores ou dispositivos de uma vez, o McuUserInstance identifica exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de0c0-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de0c0-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-132">bit</span><span class="sxs-lookup"><span data-stu-id="de0c0-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de0c0-133">Se o usuário está ingressando de uma PSTN ou não.</span><span class="sxs-lookup"><span data-stu-id="de0c0-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de0c0-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-135">int</span><span class="sxs-lookup"><span data-stu-id="de0c0-135">int</span></span></p></td>
<td><p><span data-ttu-id="de0c0-136">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="de0c0-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="de0c0-137">Número exclusivo que identifica esse servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="de0c0-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="de0c0-138">Consulte a <a href="lync-server-2013-mcus-table.md">tabela MCUs no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de0c0-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de0c0-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-140">datetime</span><span class="sxs-lookup"><span data-stu-id="de0c0-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="de0c0-141">Exterior</span><span class="sxs-lookup"><span data-stu-id="de0c0-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de0c0-142">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="de0c0-142">Time of session request.</span></span> <span data-ttu-id="de0c0-143">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="de0c0-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="de0c0-144">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de0c0-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de0c0-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-146">int</span><span class="sxs-lookup"><span data-stu-id="de0c0-146">int</span></span></p></td>
<td><p><span data-ttu-id="de0c0-147">Exterior</span><span class="sxs-lookup"><span data-stu-id="de0c0-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de0c0-148">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="de0c0-148">ID number to identify the session.</span></span> <span data-ttu-id="de0c0-149">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="de0c0-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="de0c0-150">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de0c0-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de0c0-151"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-152">datetime</span><span class="sxs-lookup"><span data-stu-id="de0c0-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de0c0-153">A hora em que este usuário entra neste servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="de0c0-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de0c0-154"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-155">datetime</span><span class="sxs-lookup"><span data-stu-id="de0c0-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de0c0-156">O horário em que este usuário sai deste servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="de0c0-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de0c0-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="de0c0-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="de0c0-158">int</span><span class="sxs-lookup"><span data-stu-id="de0c0-158">int</span></span></p></td>
<td><p><span data-ttu-id="de0c0-159">Exterior</span><span class="sxs-lookup"><span data-stu-id="de0c0-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de0c0-160">Identificador que especifica o número da versão do software cliente usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="de0c0-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="de0c0-161">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="de0c0-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="de0c0-162">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de0c0-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

