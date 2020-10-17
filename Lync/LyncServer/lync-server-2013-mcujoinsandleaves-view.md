---
title: 'Lync Server 2013: modo de exibição McuJoinsAndLeaves'
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
ms.openlocfilehash: 329396549a02a354939b166c8785b875faee2f78
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524718"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="e31ac-102">Exibição McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e31ac-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e31ac-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e31ac-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e31ac-104">A exibição McuJoinsAndLeaves armazena informações sobre ingresso e saída de usuários de um servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="e31ac-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="e31ac-105">Cada registro nessa exibição inclui os detalhes da chamada sobre uma combinação da entrada ou saída de um usuário e o servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="e31ac-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="e31ac-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e31ac-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e31ac-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="e31ac-107">Column</span></span></th>
<th><span data-ttu-id="e31ac-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e31ac-108">Data Type</span></span></th>
<th><span data-ttu-id="e31ac-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e31ac-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e31ac-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e31ac-112">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="e31ac-112">Time of conference instance.</span></span> <span data-ttu-id="e31ac-113">Usada em conjunto com SessionIdSeq para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="e31ac-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="e31ac-114">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e31ac-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31ac-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-116">int</span><span class="sxs-lookup"><span data-stu-id="e31ac-116">int</span></span></p></td>
<td><p><span data-ttu-id="e31ac-117">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="e31ac-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="e31ac-118">Usada em conjunto com SessionIdTime para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="e31ac-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="e31ac-119">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e31ac-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e31ac-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e31ac-122">URI do servidor de conferências ao qual o usuário está conectado.</span><span class="sxs-lookup"><span data-stu-id="e31ac-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31ac-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e31ac-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e31ac-125">URI do servidor de conferências ao qual o usuário está conectado.</span><span class="sxs-lookup"><span data-stu-id="e31ac-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="e31ac-126">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e31ac-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e31ac-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e31ac-129">URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e31ac-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31ac-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e31ac-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e31ac-132">Tipo de URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e31ac-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e31ac-133">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e31ac-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-134"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e31ac-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e31ac-136">Locatário do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e31ac-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e31ac-137">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e31ac-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31ac-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e31ac-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e31ac-140">Versão do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e31ac-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-141"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-142">int</span><span class="sxs-lookup"><span data-stu-id="e31ac-142">int</span></span></p></td>
<td><p><span data-ttu-id="e31ac-143">Cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e31ac-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="e31ac-144">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="e31ac-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31ac-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e31ac-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e31ac-147">Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e31ac-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-149">int</span><span class="sxs-lookup"><span data-stu-id="e31ac-149">int</span></span></p></td>
<td><p><span data-ttu-id="e31ac-150">Identificador exclusivo da combinação de usuário/dispositivo para usuários que fizeram logon simultâneo em vários dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e31ac-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31ac-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-152">bits</span><span class="sxs-lookup"><span data-stu-id="e31ac-152">bit</span></span></p></td>
<td><p><span data-ttu-id="e31ac-153">Bit que representa se o usuário é interno ou não.</span><span class="sxs-lookup"><span data-stu-id="e31ac-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-155">datetime</span><span class="sxs-lookup"><span data-stu-id="e31ac-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="e31ac-156">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="e31ac-156">Time of session request.</span></span> <span data-ttu-id="e31ac-157">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e31ac-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e31ac-158">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e31ac-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31ac-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-160">int</span><span class="sxs-lookup"><span data-stu-id="e31ac-160">int</span></span></p></td>
<td><p><span data-ttu-id="e31ac-161">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="e31ac-161">ID number to identify the session.</span></span> <span data-ttu-id="e31ac-162">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e31ac-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e31ac-163">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e31ac-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="e31ac-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e31ac-p110">ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.</span><span class="sxs-lookup"><span data-stu-id="e31ac-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e31ac-168"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-169">datetime</span><span class="sxs-lookup"><span data-stu-id="e31ac-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="e31ac-170">Hora em que o usuário ingressou no servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="e31ac-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e31ac-171"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="e31ac-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e31ac-172">datetime</span><span class="sxs-lookup"><span data-stu-id="e31ac-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="e31ac-173">Hora em que o usuário saiu do servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="e31ac-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

