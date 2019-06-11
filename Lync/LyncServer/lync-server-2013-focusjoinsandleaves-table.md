---
title: 'Lync Server 2013: Tabela FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ead6fc2ce79f7ab1206476ee420bd2ba5a7711f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="6b901-102">Tabela FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b901-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b901-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6b901-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6b901-104">Cada registro desta tabela contém as informações de CDR sobre o ingresso de um usuário e as informações de licença de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="6b901-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="6b901-105">Cada conferência é representada por um registro por cada vez que um usuário entra e sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="6b901-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b901-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="6b901-106">Column</span></span></th>
<th><span data-ttu-id="6b901-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="6b901-107">Data Type</span></span></th>
<th><span data-ttu-id="6b901-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="6b901-108">Key/Index</span></span></th>
<th><span data-ttu-id="6b901-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="6b901-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b901-110"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-111">datetime</span><span class="sxs-lookup"><span data-stu-id="6b901-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6b901-112">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6b901-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6b901-113">Hora da ocorrência da conferência.</span><span class="sxs-lookup"><span data-stu-id="6b901-113">Time of conference instance.</span></span> <span data-ttu-id="6b901-114">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar uma instância de conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="6b901-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="6b901-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6b901-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b901-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-117">int</span><span class="sxs-lookup"><span data-stu-id="6b901-117">int</span></span></p></td>
<td><p><span data-ttu-id="6b901-118">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6b901-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6b901-119">Número de identificação para identificar a instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="6b901-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="6b901-120">Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="6b901-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="6b901-121">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6b901-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b901-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-123">datetime</span><span class="sxs-lookup"><span data-stu-id="6b901-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="6b901-124">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6b901-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6b901-125">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="6b901-125">Time of session request.</span></span> <span data-ttu-id="6b901-126">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6b901-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6b901-127">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6b901-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b901-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-129">int</span><span class="sxs-lookup"><span data-stu-id="6b901-129">int</span></span></p></td>
<td><p><span data-ttu-id="6b901-130">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6b901-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6b901-131">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="6b901-131">ID number to identify the session.</span></span> <span data-ttu-id="6b901-132">Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6b901-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6b901-133">consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6b901-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b901-134"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-135">int</span><span class="sxs-lookup"><span data-stu-id="6b901-135">int</span></span></p></td>
<td><p><span data-ttu-id="6b901-136">Exterior</span><span class="sxs-lookup"><span data-stu-id="6b901-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6b901-137">Número exclusivo que identifica esse usuário, referenciado pela <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6b901-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b901-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-139">int</span><span class="sxs-lookup"><span data-stu-id="6b901-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b901-140">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, o <strong>UserInstance</strong> será usado para identificar exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6b901-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b901-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-142">bit</span><span class="sxs-lookup"><span data-stu-id="6b901-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6b901-143">Se o usuário está conectado de interno ou não.</span><span class="sxs-lookup"><span data-stu-id="6b901-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b901-144"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-145">int</span><span class="sxs-lookup"><span data-stu-id="6b901-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6b901-146">A função deste usuário na conferência, como apresentador ou participante.</span><span class="sxs-lookup"><span data-stu-id="6b901-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b901-147"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-148">datetime</span><span class="sxs-lookup"><span data-stu-id="6b901-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6b901-149">A hora em que este usuário entra na conferência.</span><span class="sxs-lookup"><span data-stu-id="6b901-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b901-150"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-151">datetime</span><span class="sxs-lookup"><span data-stu-id="6b901-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6b901-152">A hora em que esse usuário sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="6b901-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b901-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-154">int</span><span class="sxs-lookup"><span data-stu-id="6b901-154">int</span></span></p></td>
<td><p><span data-ttu-id="6b901-155">Exterior</span><span class="sxs-lookup"><span data-stu-id="6b901-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6b901-156">Versão do software cliente do usuário, referenciada à <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="6b901-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b901-157"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="6b901-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="6b901-158">Identificador</span><span class="sxs-lookup"><span data-stu-id="6b901-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6b901-159">Identificador global exclusivo (GUID) do ponto de extremidade usado na conferência.</span><span class="sxs-lookup"><span data-stu-id="6b901-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="6b901-160">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b901-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

