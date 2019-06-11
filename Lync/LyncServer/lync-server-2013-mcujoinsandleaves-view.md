---
title: 'Lync Server 2013: modo de exibição McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="b50da-102">Exibição McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b50da-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b50da-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b50da-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b50da-104">A exibição McuJoinsAndLeaves armazena informações sobre como os usuários unem e deixam informações para um servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b50da-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="b50da-105">Cada registro nesse modo de exibição contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de saída e conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="b50da-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="b50da-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b50da-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b50da-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="b50da-107">Column</span></span></th>
<th><span data-ttu-id="b50da-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b50da-108">Data Type</span></span></th>
<th><span data-ttu-id="b50da-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b50da-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b50da-110"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b50da-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b50da-112">Hora da ocorrência da conferência.</span><span class="sxs-lookup"><span data-stu-id="b50da-112">Time of conference instance.</span></span> <span data-ttu-id="b50da-113">Usado em conjunto com SessionIdSeq para identificar uma instância de conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="b50da-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="b50da-114">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b50da-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b50da-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-116">int</span><span class="sxs-lookup"><span data-stu-id="b50da-116">int</span></span></p></td>
<td><p><span data-ttu-id="b50da-117">Número de identificação para identificar a instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="b50da-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="b50da-118">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="b50da-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="b50da-119">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b50da-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b50da-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b50da-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b50da-122">O URI do servidor de conferência ao qual o usuário se conectou.</span><span class="sxs-lookup"><span data-stu-id="b50da-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b50da-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b50da-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b50da-125">O URI do servidor de conferência ao qual o usuário se conectou.</span><span class="sxs-lookup"><span data-stu-id="b50da-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="b50da-126">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b50da-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b50da-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b50da-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b50da-129">O URI do usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="b50da-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b50da-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b50da-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b50da-132">O tipo de URI do usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="b50da-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="b50da-133">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b50da-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b50da-134"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b50da-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b50da-136">O locatário do usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="b50da-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="b50da-137">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b50da-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b50da-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b50da-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b50da-140">A versão do cliente usada pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="b50da-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b50da-141"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-142">int</span><span class="sxs-lookup"><span data-stu-id="b50da-142">int</span></span></p></td>
<td><p><span data-ttu-id="b50da-143">O cliente usado pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="b50da-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="b50da-144">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b50da-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b50da-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b50da-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b50da-147">O nome da categoria do cliente usado pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="b50da-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b50da-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-149">int</span><span class="sxs-lookup"><span data-stu-id="b50da-149">int</span></span></p></td>
<td><p><span data-ttu-id="b50da-150">Identifica exclusivamente a combinação de usuário/dispositivo para usuários conectados simultaneamente a vários dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b50da-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b50da-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-152">bit</span><span class="sxs-lookup"><span data-stu-id="b50da-152">bit</span></span></p></td>
<td><p><span data-ttu-id="b50da-153">Bit que representa se o usuário é um usuário interno ou não.</span><span class="sxs-lookup"><span data-stu-id="b50da-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b50da-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-155">datetime</span><span class="sxs-lookup"><span data-stu-id="b50da-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="b50da-156">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="b50da-156">Time of session request.</span></span> <span data-ttu-id="b50da-157">Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b50da-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b50da-158">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b50da-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b50da-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-160">int</span><span class="sxs-lookup"><span data-stu-id="b50da-160">int</span></span></p></td>
<td><p><span data-ttu-id="b50da-161">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="b50da-161">ID number to identify the session.</span></span> <span data-ttu-id="b50da-162">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b50da-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b50da-163">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b50da-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b50da-164"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b50da-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b50da-166">ID da caixa de diálogo SIP da sessão.</span><span class="sxs-lookup"><span data-stu-id="b50da-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="b50da-167">O formato é: caixa de diálogo; de-marca; para-marca.</span><span class="sxs-lookup"><span data-stu-id="b50da-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b50da-168"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-169">datetime</span><span class="sxs-lookup"><span data-stu-id="b50da-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="b50da-170">Vez que o usuário ingressou no servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b50da-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b50da-171"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="b50da-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b50da-172">datetime</span><span class="sxs-lookup"><span data-stu-id="b50da-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="b50da-173">Vez que o usuário saiu do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b50da-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

