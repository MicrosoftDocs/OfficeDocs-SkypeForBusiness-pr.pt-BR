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
ms.openlocfilehash: 9f7691a008dae1fc822b6632a60f5324bb4e80fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500828"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="58ff8-102">Tabela FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58ff8-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58ff8-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="58ff8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="58ff8-104">Cada registro desta tabela contém as informações de CDR sobre as informações de ingresso e saída de um usuário de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="58ff8-105">Cada conferência é representada nesta tabela por um registro para cada vez que um usuário ingressa e sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="58ff8-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="58ff8-106">Column</span></span></th>
<th><span data-ttu-id="58ff8-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="58ff8-107">Data Type</span></span></th>
<th><span data-ttu-id="58ff8-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="58ff8-108">Key/Index</span></span></th>
<th><span data-ttu-id="58ff8-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="58ff8-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="58ff8-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="58ff8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="58ff8-112">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="58ff8-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="58ff8-113">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-113">Time of conference instance.</span></span> <span data-ttu-id="58ff8-114">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="58ff8-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="58ff8-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ff8-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-117">int</span><span class="sxs-lookup"><span data-stu-id="58ff8-117">int</span></span></p></td>
<td><p><span data-ttu-id="58ff8-118">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="58ff8-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="58ff8-119">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="58ff8-120">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="58ff8-121">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="58ff8-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58ff8-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-123">datetime</span><span class="sxs-lookup"><span data-stu-id="58ff8-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="58ff8-124">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="58ff8-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="58ff8-125">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="58ff8-125">Time of session request.</span></span> <span data-ttu-id="58ff8-126">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="58ff8-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="58ff8-127">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="58ff8-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ff8-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-129">int</span><span class="sxs-lookup"><span data-stu-id="58ff8-129">int</span></span></p></td>
<td><p><span data-ttu-id="58ff8-130">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="58ff8-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="58ff8-131">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="58ff8-131">ID number to identify the session.</span></span> <span data-ttu-id="58ff8-132">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="58ff8-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="58ff8-133">consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="58ff8-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58ff8-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-135">int</span><span class="sxs-lookup"><span data-stu-id="58ff8-135">int</span></span></p></td>
<td><p><span data-ttu-id="58ff8-136">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="58ff8-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="58ff8-137">Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="58ff8-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ff8-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-139">int</span><span class="sxs-lookup"><span data-stu-id="58ff8-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58ff8-140">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, <strong>UserInstance</strong> será usada para identificar exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="58ff8-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58ff8-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-142">bits</span><span class="sxs-lookup"><span data-stu-id="58ff8-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="58ff8-143">Se o usuário fez logon de interno ou não.</span><span class="sxs-lookup"><span data-stu-id="58ff8-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ff8-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-145">int</span><span class="sxs-lookup"><span data-stu-id="58ff8-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="58ff8-146">A função deste usuário na conferência, como apresentador ou participante.</span><span class="sxs-lookup"><span data-stu-id="58ff8-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58ff8-147"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-148">datetime</span><span class="sxs-lookup"><span data-stu-id="58ff8-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="58ff8-149">A hora em que esse usuário entra na conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ff8-150"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-151">datetime</span><span class="sxs-lookup"><span data-stu-id="58ff8-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="58ff8-152">A hora em que esse usuário sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="58ff8-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-154">int</span><span class="sxs-lookup"><span data-stu-id="58ff8-154">int</span></span></p></td>
<td><p><span data-ttu-id="58ff8-155">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="58ff8-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="58ff8-156">Versão do software cliente do usuário, referenciada na <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="58ff8-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="58ff8-157"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="58ff8-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="58ff8-158">Identificador</span><span class="sxs-lookup"><span data-stu-id="58ff8-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="58ff8-159">GUID (identificador global exclusivo) do ponto de extremidade usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="58ff8-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="58ff8-160">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58ff8-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

