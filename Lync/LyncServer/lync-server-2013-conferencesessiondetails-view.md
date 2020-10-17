---
title: 'Lync Server 2013: modo de exibição ConferenceSessionDetails'
description: 'Lync Server 2013: modo de exibição ConferenceSessionDetails.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566767"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="343f9-103">Exibição ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="343f9-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="343f9-104">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="343f9-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="343f9-105">O ConferenceSessionDetails visualiza as informações dos repositórios sobre sessões com vários participantes.</span><span class="sxs-lookup"><span data-stu-id="343f9-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="343f9-106">Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.</span><span class="sxs-lookup"><span data-stu-id="343f9-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="343f9-107">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="343f9-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="343f9-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="343f9-108">Column</span></span></th>
<th><span data-ttu-id="343f9-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="343f9-109">Data Type</span></span></th>
<th><span data-ttu-id="343f9-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="343f9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="343f9-111"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-112">datetime</span><span class="sxs-lookup"><span data-stu-id="343f9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="343f9-113">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-113">Time of session request.</span></span> <span data-ttu-id="343f9-114">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="343f9-115">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-117">int</span><span class="sxs-lookup"><span data-stu-id="343f9-117">int</span></span></p></td>
<td><p><span data-ttu-id="343f9-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-118">ID number to identify the session.</span></span> <span data-ttu-id="343f9-119">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="343f9-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-121"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-122">datetime</span><span class="sxs-lookup"><span data-stu-id="343f9-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="343f9-p104">Horário da primeira solicitação CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="343f9-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-126"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="343f9-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="343f9-128">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-131">Tipo de URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-131">Type of conference URI.</span></span> <span data-ttu-id="343f9-132">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-133"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-134">identificador</span><span class="sxs-lookup"><span data-stu-id="343f9-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="343f9-p106">Identificador que diferencia instâncias de conferências recorrentes. Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="343f9-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="343f9-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="343f9-139">URI do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-142">Tipo de URI de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-142">Type of conferencing server URI.</span></span> <span data-ttu-id="343f9-143">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="343f9-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="343f9-146">URI do usuário envolvido na sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-147"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-149">Tipo de URI do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="343f9-150">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-151"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-153">Locatário do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="343f9-154">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-155"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-156">identificador</span><span class="sxs-lookup"><span data-stu-id="343f9-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="343f9-157">Identificador exclusivo do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-159">datetime</span><span class="sxs-lookup"><span data-stu-id="343f9-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="343f9-160">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-163">Versão do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-165">int</span><span class="sxs-lookup"><span data-stu-id="343f9-165">int</span></span></p></td>
<td><p><span data-ttu-id="343f9-166">Tipo de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-166">Type of conference server.</span></span> <span data-ttu-id="343f9-167">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="343f9-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="343f9-170">Categoria do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-172">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-173">Versão do cliente utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-174"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-175">int</span><span class="sxs-lookup"><span data-stu-id="343f9-175">int</span></span></p></td>
<td><p><span data-ttu-id="343f9-176">Cliente utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="343f9-177">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="343f9-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-179">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="343f9-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="343f9-180">Nome da categoria do cliente utilizado pelo usuário que foi parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-182">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="343f9-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="343f9-183">URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="343f9-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-185">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-186">Tipo de URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="343f9-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="343f9-187">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-189">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-190">Locatário do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="343f9-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="343f9-191">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-192"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-193">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="343f9-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="343f9-194">URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-195"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-196">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-197">Tipo de URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="343f9-198">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-199"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-200">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-201">Locatário do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="343f9-202">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-203"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-204">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="343f9-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="343f9-p116">Identificação da caixa de diálogo SIP. O formato é</span><span class="sxs-lookup"><span data-stu-id="343f9-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="343f9-207">:d ialog; from-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="343f9-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-208"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-209">datetime</span><span class="sxs-lookup"><span data-stu-id="343f9-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="343f9-210">Número de identificação para identificar o diálogo que foi substituído pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="343f9-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="343f9-211">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-212"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-213">int</span><span class="sxs-lookup"><span data-stu-id="343f9-213">int</span></span></p></td>
<td><p><span data-ttu-id="343f9-214">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-214">ID number to identify the session.</span></span> <span data-ttu-id="343f9-215">Utilizado em conjunto com o ReplaceDialogIdTime para identificar de forma exclusiva a sessão que foi substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="343f9-216">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="343f9-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-217"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-218">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="343f9-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="343f9-p119">Identificação da caixa de diálogo SIP substitui a sessão. O formato dela é:</span><span class="sxs-lookup"><span data-stu-id="343f9-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="343f9-221">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="343f9-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-223">bits</span><span class="sxs-lookup"><span data-stu-id="343f9-223">bit</span></span></p></td>
<td><p><span data-ttu-id="343f9-224">Indica se a sessão foi iniciada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-226">bits</span><span class="sxs-lookup"><span data-stu-id="343f9-226">bit</span></span></p></td>
<td><p><span data-ttu-id="343f9-227">Indica se a sessão foi finalizada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="343f9-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-229">bits</span><span class="sxs-lookup"><span data-stu-id="343f9-229">bit</span></span></p></td>
<td><p><span data-ttu-id="343f9-230">Indica se o usuário está conectado à rede interna.</span><span class="sxs-lookup"><span data-stu-id="343f9-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-232">datetime</span><span class="sxs-lookup"><span data-stu-id="343f9-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="343f9-p120">O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="343f9-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-237">int</span><span class="sxs-lookup"><span data-stu-id="343f9-237">int</span></span></p></td>
<td><p><span data-ttu-id="343f9-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="343f9-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-241"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-242">int</span><span class="sxs-lookup"><span data-stu-id="343f9-242">int</span></span></p></td>
<td><p><span data-ttu-id="343f9-243">ID de diagnóstico capturada dos cabeçalhos SIP da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-245">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-246">Tipo de conteúdo para a sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-248">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-249">FQDN do servidor de Front-End que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-251">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-252">FQDN do pool que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-254">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-255">Servidor de Mediação utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-256"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-257">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-258">Gateway usado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-260">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="343f9-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="343f9-261">FQDN do Servidor de Borda utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="343f9-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="343f9-262"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-263">smallint</span><span class="sxs-lookup"><span data-stu-id="343f9-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="343f9-p122">Indica os atributos do usuário que participou da sessão. As definições de atributos a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="343f9-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="343f9-266">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="343f9-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="343f9-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="343f9-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="343f9-268">smallint</span><span class="sxs-lookup"><span data-stu-id="343f9-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="343f9-p123">Indica os atributos da chamada. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="343f9-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="343f9-271">0x01 - Sessão repetida0</span><span class="sxs-lookup"><span data-stu-id="343f9-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="343f9-272">x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="343f9-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

