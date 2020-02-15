---
title: 'Lync Server 2013: tabela FocusJoinsAndLeaves'
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
ms.openlocfilehash: 385279d422827b689561902becbd512f4e9261ab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="27756-102">Tabela FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27756-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27756-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="27756-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="27756-104">Cada registro desta tabela contém as informações de CDR sobre as informações de ingresso e saída de um usuário de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="27756-105">Cada conferência é representada nesta tabela por um registro para cada vez que um usuário ingressa e sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27756-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="27756-106">Column</span></span></th>
<th><span data-ttu-id="27756-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="27756-107">Data Type</span></span></th>
<th><span data-ttu-id="27756-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="27756-108">Key/Index</span></span></th>
<th><span data-ttu-id="27756-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="27756-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27756-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="27756-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-111">datetime</span><span class="sxs-lookup"><span data-stu-id="27756-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="27756-112">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="27756-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="27756-113">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-113">Time of conference instance.</span></span> <span data-ttu-id="27756-114">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="27756-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="27756-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27756-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="27756-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-117">int</span><span class="sxs-lookup"><span data-stu-id="27756-117">int</span></span></p></td>
<td><p><span data-ttu-id="27756-118">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="27756-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="27756-119">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="27756-120">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="27756-121">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="27756-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27756-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="27756-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-123">datetime</span><span class="sxs-lookup"><span data-stu-id="27756-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="27756-124">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="27756-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="27756-125">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="27756-125">Time of session request.</span></span> <span data-ttu-id="27756-126">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="27756-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="27756-127">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="27756-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27756-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="27756-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-129">int</span><span class="sxs-lookup"><span data-stu-id="27756-129">int</span></span></p></td>
<td><p><span data-ttu-id="27756-130">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="27756-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="27756-131">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="27756-131">ID number to identify the session.</span></span> <span data-ttu-id="27756-132">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="27756-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="27756-133">consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="27756-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27756-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="27756-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-135">int</span><span class="sxs-lookup"><span data-stu-id="27756-135">int</span></span></p></td>
<td><p><span data-ttu-id="27756-136">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="27756-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="27756-137">Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="27756-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27756-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="27756-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-139">int</span><span class="sxs-lookup"><span data-stu-id="27756-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27756-140">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, <strong>UserInstance</strong> será usada para identificar exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="27756-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27756-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="27756-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-142">bits</span><span class="sxs-lookup"><span data-stu-id="27756-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27756-143">Se o usuário fez logon de interno ou não.</span><span class="sxs-lookup"><span data-stu-id="27756-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27756-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="27756-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-145">int</span><span class="sxs-lookup"><span data-stu-id="27756-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27756-146">A função deste usuário na conferência, como apresentador ou participante.</span><span class="sxs-lookup"><span data-stu-id="27756-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27756-147"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="27756-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-148">datetime</span><span class="sxs-lookup"><span data-stu-id="27756-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27756-149">A hora em que esse usuário entra na conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27756-150"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="27756-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-151">datetime</span><span class="sxs-lookup"><span data-stu-id="27756-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27756-152">A hora em que esse usuário sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27756-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="27756-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-154">int</span><span class="sxs-lookup"><span data-stu-id="27756-154">int</span></span></p></td>
<td><p><span data-ttu-id="27756-155">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="27756-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="27756-156">Versão do software cliente do usuário, referenciada na <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="27756-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27756-157"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="27756-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="27756-158">Identificador</span><span class="sxs-lookup"><span data-stu-id="27756-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27756-159">GUID (identificador global exclusivo) do ponto de extremidade usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="27756-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="27756-160">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="27756-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

