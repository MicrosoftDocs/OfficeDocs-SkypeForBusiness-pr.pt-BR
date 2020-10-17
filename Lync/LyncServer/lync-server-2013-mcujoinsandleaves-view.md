---
title: 'Lync Server 2013: modo de exibição McuJoinsAndLeaves'
description: 'Lync Server 2013: modo de exibição McuJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556487"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="ff38d-103">Exibição McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff38d-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff38d-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ff38d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ff38d-105">A exibição McuJoinsAndLeaves armazena informações sobre ingresso e saída de usuários de um servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="ff38d-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="ff38d-106">Cada registro nessa exibição inclui os detalhes da chamada sobre uma combinação da entrada ou saída de um usuário e o servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="ff38d-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="ff38d-107">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ff38d-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff38d-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="ff38d-108">Column</span></span></th>
<th><span data-ttu-id="ff38d-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ff38d-109">Data Type</span></span></th>
<th><span data-ttu-id="ff38d-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ff38d-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-111"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ff38d-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff38d-113">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="ff38d-113">Time of conference instance.</span></span> <span data-ttu-id="ff38d-114">Usada em conjunto com SessionIdSeq para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="ff38d-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="ff38d-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ff38d-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff38d-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-117">int</span><span class="sxs-lookup"><span data-stu-id="ff38d-117">int</span></span></p></td>
<td><p><span data-ttu-id="ff38d-118">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="ff38d-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="ff38d-119">Usada em conjunto com SessionIdTime para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="ff38d-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="ff38d-120">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ff38d-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff38d-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff38d-123">URI do servidor de conferências ao qual o usuário está conectado.</span><span class="sxs-lookup"><span data-stu-id="ff38d-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff38d-124"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff38d-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff38d-126">URI do servidor de conferências ao qual o usuário está conectado.</span><span class="sxs-lookup"><span data-stu-id="ff38d-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="ff38d-127">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ff38d-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-129">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ff38d-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ff38d-130">URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ff38d-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff38d-131"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff38d-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff38d-133">Tipo de URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ff38d-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="ff38d-134">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ff38d-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-135"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff38d-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff38d-137">Locatário do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ff38d-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="ff38d-138">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ff38d-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff38d-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ff38d-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ff38d-141">Versão do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ff38d-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-142"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-143">int</span><span class="sxs-lookup"><span data-stu-id="ff38d-143">int</span></span></p></td>
<td><p><span data-ttu-id="ff38d-144">Cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ff38d-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="ff38d-145">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ff38d-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff38d-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-147">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ff38d-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ff38d-148">Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ff38d-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-150">int</span><span class="sxs-lookup"><span data-stu-id="ff38d-150">int</span></span></p></td>
<td><p><span data-ttu-id="ff38d-151">Identificador exclusivo da combinação de usuário/dispositivo para usuários que fizeram logon simultâneo em vários dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ff38d-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff38d-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-153">bits</span><span class="sxs-lookup"><span data-stu-id="ff38d-153">bit</span></span></p></td>
<td><p><span data-ttu-id="ff38d-154">Bit que representa se o usuário é interno ou não.</span><span class="sxs-lookup"><span data-stu-id="ff38d-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-156">datetime</span><span class="sxs-lookup"><span data-stu-id="ff38d-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff38d-157">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="ff38d-157">Time of session request.</span></span> <span data-ttu-id="ff38d-158">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ff38d-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ff38d-159">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ff38d-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff38d-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-161">int</span><span class="sxs-lookup"><span data-stu-id="ff38d-161">int</span></span></p></td>
<td><p><span data-ttu-id="ff38d-162">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="ff38d-162">ID number to identify the session.</span></span> <span data-ttu-id="ff38d-163">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ff38d-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ff38d-164">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ff38d-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-165"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-166">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="ff38d-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ff38d-p110">ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.</span><span class="sxs-lookup"><span data-stu-id="ff38d-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff38d-169"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-170">datetime</span><span class="sxs-lookup"><span data-stu-id="ff38d-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff38d-171">Hora em que o usuário ingressou no servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="ff38d-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff38d-172"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="ff38d-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff38d-173">datetime</span><span class="sxs-lookup"><span data-stu-id="ff38d-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff38d-174">Hora em que o usuário saiu do servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="ff38d-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

