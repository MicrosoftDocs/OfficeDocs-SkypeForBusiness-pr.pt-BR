---
title: 'Lync Server 2013: tabela FocusJoinsAndLeaves'
description: 'Lync Server 2013: tabela FocusJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5796de16ed204ce4f33935d937cbaa425d63a67f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577437"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="65c8d-103">Tabela FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65c8d-103">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65c8d-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="65c8d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="65c8d-105">Cada registro desta tabela contém as informações de CDR sobre as informações de ingresso e saída de um usuário de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-105">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="65c8d-106">Cada conferência é representada nesta tabela por um registro para cada vez que um usuário ingressa e sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-106">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65c8d-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="65c8d-107">Column</span></span></th>
<th><span data-ttu-id="65c8d-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="65c8d-108">Data Type</span></span></th>
<th><span data-ttu-id="65c8d-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="65c8d-109">Key/Index</span></span></th>
<th><span data-ttu-id="65c8d-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="65c8d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65c8d-111"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="65c8d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="65c8d-113">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="65c8d-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="65c8d-114">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-114">Time of conference instance.</span></span> <span data-ttu-id="65c8d-115">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="65c8d-116">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="65c8d-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65c8d-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-118">int</span><span class="sxs-lookup"><span data-stu-id="65c8d-118">int</span></span></p></td>
<td><p><span data-ttu-id="65c8d-119">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="65c8d-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="65c8d-120">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="65c8d-121">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="65c8d-122">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="65c8d-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65c8d-123"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-123"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-124">datetime</span><span class="sxs-lookup"><span data-stu-id="65c8d-124">datetime</span></span></p></td>
<td><p><span data-ttu-id="65c8d-125">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="65c8d-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="65c8d-126">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="65c8d-126">Time of session request.</span></span> <span data-ttu-id="65c8d-127">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="65c8d-127">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="65c8d-128">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="65c8d-128">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65c8d-129"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-129"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-130">int</span><span class="sxs-lookup"><span data-stu-id="65c8d-130">int</span></span></p></td>
<td><p><span data-ttu-id="65c8d-131">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="65c8d-131">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="65c8d-132">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="65c8d-132">ID number to identify the session.</span></span> <span data-ttu-id="65c8d-133">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="65c8d-133">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="65c8d-134">consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="65c8d-134">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65c8d-135"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-135"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-136">int</span><span class="sxs-lookup"><span data-stu-id="65c8d-136">int</span></span></p></td>
<td><p><span data-ttu-id="65c8d-137">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="65c8d-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="65c8d-138">Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="65c8d-138">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65c8d-139"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-139"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-140">int</span><span class="sxs-lookup"><span data-stu-id="65c8d-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="65c8d-141">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, <strong>UserInstance</strong> será usada para identificar exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="65c8d-141">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65c8d-142"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-142"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-143">bits</span><span class="sxs-lookup"><span data-stu-id="65c8d-143">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="65c8d-144">Se o usuário fez logon de interno ou não.</span><span class="sxs-lookup"><span data-stu-id="65c8d-144">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65c8d-145"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-145"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-146">int</span><span class="sxs-lookup"><span data-stu-id="65c8d-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="65c8d-147">A função deste usuário na conferência, como apresentador ou participante.</span><span class="sxs-lookup"><span data-stu-id="65c8d-147">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65c8d-148"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-148"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-149">datetime</span><span class="sxs-lookup"><span data-stu-id="65c8d-149">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="65c8d-150">A hora em que esse usuário entra na conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-150">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65c8d-151"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-151"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-152">datetime</span><span class="sxs-lookup"><span data-stu-id="65c8d-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="65c8d-153">A hora em que esse usuário sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-153">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65c8d-154"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-154"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-155">int</span><span class="sxs-lookup"><span data-stu-id="65c8d-155">int</span></span></p></td>
<td><p><span data-ttu-id="65c8d-156">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="65c8d-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="65c8d-157">Versão do software cliente do usuário, referenciada na <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="65c8d-157">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65c8d-158"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="65c8d-158"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="65c8d-159">Identificador</span><span class="sxs-lookup"><span data-stu-id="65c8d-159">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="65c8d-160">GUID (identificador global exclusivo) do ponto de extremidade usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="65c8d-160">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="65c8d-161">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65c8d-161">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

