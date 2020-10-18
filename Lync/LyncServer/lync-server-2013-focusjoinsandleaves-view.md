---
title: 'Lync Server 2013: modo de exibição FocusJoinsAndLeaves'
description: 'Lync Server 2013: modo de exibição FocusJoinsAndLeaves.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577447"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="e5508-103">Exibição FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5508-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5508-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e5508-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e5508-105">O modo de exibição FocusJoinsAndLeaves armazena informações sobre as informações de ingresso e saída de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="e5508-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="e5508-106">Cada conferência é representada por um registro escrito a cada vez que um usuário entra e sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="e5508-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="e5508-107">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5508-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5508-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="e5508-108">Column</span></span></th>
<th><span data-ttu-id="e5508-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e5508-109">Data Type</span></span></th>
<th><span data-ttu-id="e5508-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="e5508-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5508-111"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e5508-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5508-113">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="e5508-113">Time of conference instance.</span></span> <span data-ttu-id="e5508-114">Usada em conjunto com SessionIdSeq para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="e5508-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="e5508-115">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e5508-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5508-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-117">int</span><span class="sxs-lookup"><span data-stu-id="e5508-117">int</span></span></p></td>
<td><p><span data-ttu-id="e5508-118">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="e5508-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="e5508-119">Usada em conjunto com SessionIdTime para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="e5508-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="e5508-120">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e5508-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5508-121"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-122">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5508-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5508-123">URI do usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e5508-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5508-124"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5508-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5508-126">Tipo de URI do usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e5508-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="e5508-127">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e5508-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5508-128"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5508-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5508-130">Locatário do usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e5508-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="e5508-131">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e5508-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5508-132"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-133">identificador</span><span class="sxs-lookup"><span data-stu-id="e5508-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e5508-134">Identificador exclusivo do usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e5508-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5508-135"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5508-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5508-137">Versão do cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e5508-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5508-138"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-139">int</span><span class="sxs-lookup"><span data-stu-id="e5508-139">int</span></span></p></td>
<td><p><span data-ttu-id="e5508-140">Cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e5508-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="e5508-141">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="e5508-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5508-142"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-143">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e5508-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5508-144">Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="e5508-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5508-145"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-146">int</span><span class="sxs-lookup"><span data-stu-id="e5508-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5508-147"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-148">bits</span><span class="sxs-lookup"><span data-stu-id="e5508-148">bit</span></span></p></td>
<td><p><span data-ttu-id="e5508-149">Bit que representa se o usuário é interno ou não.</span><span class="sxs-lookup"><span data-stu-id="e5508-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5508-150"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-151">datetime</span><span class="sxs-lookup"><span data-stu-id="e5508-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5508-152">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="e5508-152">Time of session request.</span></span> <span data-ttu-id="e5508-153">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="e5508-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e5508-154">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e5508-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5508-155"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-156">int</span><span class="sxs-lookup"><span data-stu-id="e5508-156">int</span></span></p></td>
<td><p><span data-ttu-id="e5508-157">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, UserInstance será usada para identificar exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5508-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5508-158"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-159">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="e5508-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e5508-p108">ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.</span><span class="sxs-lookup"><span data-stu-id="e5508-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5508-162"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-163">datetime</span><span class="sxs-lookup"><span data-stu-id="e5508-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5508-164">Hora em que o usuário entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="e5508-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5508-165"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-166">datetime</span><span class="sxs-lookup"><span data-stu-id="e5508-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5508-167">Hora em que o usuário saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="e5508-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5508-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="e5508-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="e5508-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5508-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5508-170">Função do usuário na conferência, como apresentador ou participante.</span><span class="sxs-lookup"><span data-stu-id="e5508-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

