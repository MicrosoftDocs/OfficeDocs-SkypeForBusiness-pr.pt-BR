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
ms.openlocfilehash: 49021f6b03481ccb5661c85cec87e5786a8d83dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="f312c-102">Tabela FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f312c-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f312c-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f312c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f312c-104">Cada registro desta tabela contém as informações de CDR sobre as informações de ingresso e saída de um usuário de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="f312c-105">Cada conferência é representada nesta tabela por um registro para cada vez que um usuário ingressa e sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f312c-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="f312c-106">Column</span></span></th>
<th><span data-ttu-id="f312c-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f312c-107">Data Type</span></span></th>
<th><span data-ttu-id="f312c-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="f312c-108">Key/Index</span></span></th>
<th><span data-ttu-id="f312c-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f312c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f312c-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f312c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f312c-112">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="f312c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f312c-113">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-113">Time of conference instance.</span></span> <span data-ttu-id="f312c-114">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f312c-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f312c-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f312c-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-117">int</span><span class="sxs-lookup"><span data-stu-id="f312c-117">int</span></span></p></td>
<td><p><span data-ttu-id="f312c-118">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="f312c-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f312c-119">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="f312c-120">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="f312c-121">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f312c-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f312c-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-123">datetime</span><span class="sxs-lookup"><span data-stu-id="f312c-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="f312c-124">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="f312c-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f312c-125">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="f312c-125">Time of session request.</span></span> <span data-ttu-id="f312c-126">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f312c-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f312c-127">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f312c-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f312c-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-129">int</span><span class="sxs-lookup"><span data-stu-id="f312c-129">int</span></span></p></td>
<td><p><span data-ttu-id="f312c-130">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="f312c-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f312c-131">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="f312c-131">ID number to identify the session.</span></span> <span data-ttu-id="f312c-132">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f312c-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="f312c-133">consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f312c-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f312c-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-135">int</span><span class="sxs-lookup"><span data-stu-id="f312c-135">int</span></span></p></td>
<td><p><span data-ttu-id="f312c-136">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="f312c-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f312c-137">Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f312c-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f312c-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-139">int</span><span class="sxs-lookup"><span data-stu-id="f312c-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f312c-140">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, <strong>UserInstance</strong> será usada para identificar exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f312c-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f312c-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-142">bits</span><span class="sxs-lookup"><span data-stu-id="f312c-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f312c-143">Se o usuário fez logon de interno ou não.</span><span class="sxs-lookup"><span data-stu-id="f312c-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f312c-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-145">int</span><span class="sxs-lookup"><span data-stu-id="f312c-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f312c-146">A função deste usuário na conferência, como apresentador ou participante.</span><span class="sxs-lookup"><span data-stu-id="f312c-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f312c-147"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-148">datetime</span><span class="sxs-lookup"><span data-stu-id="f312c-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f312c-149">A hora em que esse usuário entra na conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f312c-150"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-151">datetime</span><span class="sxs-lookup"><span data-stu-id="f312c-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f312c-152">A hora em que esse usuário sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f312c-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-154">int</span><span class="sxs-lookup"><span data-stu-id="f312c-154">int</span></span></p></td>
<td><p><span data-ttu-id="f312c-155">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="f312c-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f312c-156">Versão do software cliente do usuário, referenciada na <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="f312c-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f312c-157"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="f312c-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f312c-158">Identificador</span><span class="sxs-lookup"><span data-stu-id="f312c-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f312c-159">GUID (identificador global exclusivo) do ponto de extremidade usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="f312c-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="f312c-160">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f312c-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

