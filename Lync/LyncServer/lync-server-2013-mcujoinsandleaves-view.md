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
ms.openlocfilehash: 9eae65a6f19e0eb73098ed5990d6881d0129b34e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="71984-102">Exibição McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71984-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71984-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="71984-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="71984-104">A exibição McuJoinsAndLeaves armazena informações sobre ingresso e saída de usuários de um servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="71984-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="71984-105">Cada registro nessa exibição inclui os detalhes da chamada sobre uma combinação da entrada ou saída de um usuário e o servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="71984-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="71984-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="71984-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71984-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="71984-107">Column</span></span></th>
<th><span data-ttu-id="71984-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="71984-108">Data Type</span></span></th>
<th><span data-ttu-id="71984-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="71984-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71984-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="71984-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-111">datetime</span><span class="sxs-lookup"><span data-stu-id="71984-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="71984-112">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="71984-112">Time of conference instance.</span></span> <span data-ttu-id="71984-113">Usada em conjunto com SessionIdSeq para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="71984-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="71984-114">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="71984-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71984-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="71984-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-116">int</span><span class="sxs-lookup"><span data-stu-id="71984-116">int</span></span></p></td>
<td><p><span data-ttu-id="71984-117">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="71984-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="71984-118">Usada em conjunto com SessionIdTime para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="71984-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="71984-119">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="71984-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71984-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="71984-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71984-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71984-122">URI do servidor de conferências ao qual o usuário está conectado.</span><span class="sxs-lookup"><span data-stu-id="71984-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71984-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="71984-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71984-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71984-125">URI do servidor de conferências ao qual o usuário está conectado.</span><span class="sxs-lookup"><span data-stu-id="71984-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="71984-126">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="71984-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71984-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="71984-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="71984-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="71984-129">URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="71984-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71984-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="71984-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71984-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71984-132">Tipo de URI do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="71984-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="71984-133">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="71984-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71984-134"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="71984-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71984-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71984-136">Locatário do usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="71984-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="71984-137">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="71984-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71984-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="71984-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="71984-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="71984-140">Versão do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="71984-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71984-141"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="71984-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-142">int</span><span class="sxs-lookup"><span data-stu-id="71984-142">int</span></span></p></td>
<td><p><span data-ttu-id="71984-143">Cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="71984-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="71984-144">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="71984-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71984-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="71984-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="71984-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="71984-147">Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída do servidor de conferências foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="71984-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71984-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="71984-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-149">int</span><span class="sxs-lookup"><span data-stu-id="71984-149">int</span></span></p></td>
<td><p><span data-ttu-id="71984-150">Identificador exclusivo da combinação de usuário/dispositivo para usuários que fizeram logon simultâneo em vários dispositivos.</span><span class="sxs-lookup"><span data-stu-id="71984-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71984-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="71984-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-152">bits</span><span class="sxs-lookup"><span data-stu-id="71984-152">bit</span></span></p></td>
<td><p><span data-ttu-id="71984-153">Bit que representa se o usuário é interno ou não.</span><span class="sxs-lookup"><span data-stu-id="71984-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71984-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="71984-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-155">datetime</span><span class="sxs-lookup"><span data-stu-id="71984-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="71984-156">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="71984-156">Time of session request.</span></span> <span data-ttu-id="71984-157">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="71984-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="71984-158">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="71984-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71984-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="71984-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-160">int</span><span class="sxs-lookup"><span data-stu-id="71984-160">int</span></span></p></td>
<td><p><span data-ttu-id="71984-161">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="71984-161">ID number to identify the session.</span></span> <span data-ttu-id="71984-162">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="71984-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="71984-163">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="71984-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71984-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="71984-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="71984-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="71984-p110">ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.</span><span class="sxs-lookup"><span data-stu-id="71984-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71984-168"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="71984-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-169">datetime</span><span class="sxs-lookup"><span data-stu-id="71984-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="71984-170">Hora em que o usuário ingressou no servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="71984-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71984-171"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="71984-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71984-172">datetime</span><span class="sxs-lookup"><span data-stu-id="71984-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="71984-173">Hora em que o usuário saiu do servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="71984-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

