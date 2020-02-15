---
title: 'Lync Server 2013: modo de exibição FocusJoinsAndLeaves'
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
ms.openlocfilehash: 8c5c10cc90064e9ed3237dcd4cd4cbed1021d1b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="5b02d-102">Exibição FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b02d-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b02d-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5b02d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5b02d-104">O modo de exibição FocusJoinsAndLeaves armazena informações sobre as informações de ingresso e saída de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="5b02d-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="5b02d-105">Cada conferência é representada por um registro escrito a cada vez que um usuário entra e sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="5b02d-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="5b02d-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5b02d-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b02d-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="5b02d-107">Column</span></span></th>
<th><span data-ttu-id="5b02d-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="5b02d-108">Data Type</span></span></th>
<th><span data-ttu-id="5b02d-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="5b02d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5b02d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5b02d-112">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="5b02d-112">Time of conference instance.</span></span> <span data-ttu-id="5b02d-113">Usada em conjunto com SessionIdSeq para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="5b02d-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="5b02d-114">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5b02d-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b02d-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-116">int</span><span class="sxs-lookup"><span data-stu-id="5b02d-116">int</span></span></p></td>
<td><p><span data-ttu-id="5b02d-117">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="5b02d-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="5b02d-118">Usada em conjunto com SessionIdTime para identificar uma instância da conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="5b02d-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="5b02d-119">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5b02d-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5b02d-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5b02d-122">URI do usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="5b02d-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b02d-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5b02d-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b02d-125">Tipo de URI do usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="5b02d-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5b02d-126">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5b02d-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-127"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5b02d-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b02d-129">Locatário do usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="5b02d-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5b02d-130">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5b02d-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b02d-131"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-132">identificador</span><span class="sxs-lookup"><span data-stu-id="5b02d-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5b02d-133">Identificador exclusivo do usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="5b02d-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5b02d-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b02d-136">Versão do cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="5b02d-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b02d-137"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-138">int</span><span class="sxs-lookup"><span data-stu-id="5b02d-138">int</span></span></p></td>
<td><p><span data-ttu-id="5b02d-139">Cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="5b02d-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5b02d-140">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="5b02d-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5b02d-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5b02d-143">Nome da categoria do cliente usado pelo usuário cujas informações de ingresso/saída da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="5b02d-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b02d-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-145">int</span><span class="sxs-lookup"><span data-stu-id="5b02d-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-147">bits</span><span class="sxs-lookup"><span data-stu-id="5b02d-147">bit</span></span></p></td>
<td><p><span data-ttu-id="5b02d-148">Bit que representa se o usuário é interno ou não.</span><span class="sxs-lookup"><span data-stu-id="5b02d-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b02d-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-150">datetime</span><span class="sxs-lookup"><span data-stu-id="5b02d-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="5b02d-151">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="5b02d-151">Time of session request.</span></span> <span data-ttu-id="5b02d-152">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="5b02d-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5b02d-153">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5b02d-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-155">int</span><span class="sxs-lookup"><span data-stu-id="5b02d-155">int</span></span></p></td>
<td><p><span data-ttu-id="5b02d-156">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, UserInstance será usada para identificar exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5b02d-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b02d-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="5b02d-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5b02d-p108">ID de diálogo SIP da sessão. O formato é: diálogo;de-marca;para-marca.</span><span class="sxs-lookup"><span data-stu-id="5b02d-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-161"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-162">datetime</span><span class="sxs-lookup"><span data-stu-id="5b02d-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="5b02d-163">Hora em que o usuário entrou na conferência.</span><span class="sxs-lookup"><span data-stu-id="5b02d-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b02d-164"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-165">datetime</span><span class="sxs-lookup"><span data-stu-id="5b02d-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="5b02d-166">Hora em que o usuário saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="5b02d-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b02d-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="5b02d-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="5b02d-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5b02d-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5b02d-169">Função do usuário na conferência, como apresentador ou participante.</span><span class="sxs-lookup"><span data-stu-id="5b02d-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

