---
title: 'Lync Server 2013: modo de exibição ConferenceSessionDetails'
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
ms.openlocfilehash: cf8023408990b7f0243aaf0e937e2d1095dff0c2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529178"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="b3894-102">Exibição ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3894-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3894-103">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="b3894-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="b3894-104">O ConferenceSessionDetails visualiza as informações dos repositórios sobre sessões com vários participantes.</span><span class="sxs-lookup"><span data-stu-id="b3894-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="b3894-105">Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.</span><span class="sxs-lookup"><span data-stu-id="b3894-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="b3894-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3894-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3894-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="b3894-107">Column</span></span></th>
<th><span data-ttu-id="b3894-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b3894-108">Data Type</span></span></th>
<th><span data-ttu-id="b3894-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b3894-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3894-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b3894-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3894-112">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-112">Time of session request.</span></span> <span data-ttu-id="b3894-113">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b3894-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-116">int</span><span class="sxs-lookup"><span data-stu-id="b3894-116">int</span></span></p></td>
<td><p><span data-ttu-id="b3894-117">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-117">ID number to identify the session.</span></span> <span data-ttu-id="b3894-118">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b3894-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-120"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b3894-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3894-p104">Horário da primeira solicitação CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b3894-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-125"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3894-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3894-127">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-130">Tipo de URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-130">Type of conference URI.</span></span> <span data-ttu-id="b3894-131">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-133">identificador</span><span class="sxs-lookup"><span data-stu-id="b3894-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b3894-p106">Identificador que diferencia instâncias de conferências recorrentes. Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="b3894-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3894-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3894-138">URI do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-141">Tipo de URI de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-141">Type of conferencing server URI.</span></span> <span data-ttu-id="b3894-142">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3894-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3894-145">URI do usuário envolvido na sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-148">Tipo de URI do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="b3894-149">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-150"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-152">Locatário do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="b3894-153">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-154"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-155">identificador</span><span class="sxs-lookup"><span data-stu-id="b3894-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b3894-156">Identificador exclusivo do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-158">datetime</span><span class="sxs-lookup"><span data-stu-id="b3894-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3894-159">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-162">Versão do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-164">int</span><span class="sxs-lookup"><span data-stu-id="b3894-164">int</span></span></p></td>
<td><p><span data-ttu-id="b3894-165">Tipo de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-165">Type of conference server.</span></span> <span data-ttu-id="b3894-166">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b3894-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b3894-169">Categoria do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-172">Versão do cliente utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-173"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-174">int</span><span class="sxs-lookup"><span data-stu-id="b3894-174">int</span></span></p></td>
<td><p><span data-ttu-id="b3894-175">Cliente utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="b3894-176">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b3894-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b3894-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b3894-179">Nome da categoria do cliente utilizado pelo usuário que foi parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3894-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3894-182">URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="b3894-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-185">Tipo de URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="b3894-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="b3894-186">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-189">Locatário do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="b3894-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="b3894-190">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3894-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3894-193">URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-196">Tipo de URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="b3894-197">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-200">Locatário do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="b3894-201">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-203">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="b3894-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="b3894-p116">Identificação da caixa de diálogo SIP. O formato é</span><span class="sxs-lookup"><span data-stu-id="b3894-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="b3894-206">:d ialog; from-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="b3894-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-208">datetime</span><span class="sxs-lookup"><span data-stu-id="b3894-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3894-209">Número de identificação para identificar o diálogo que foi substituído pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b3894-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="b3894-210">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-212">int</span><span class="sxs-lookup"><span data-stu-id="b3894-212">int</span></span></p></td>
<td><p><span data-ttu-id="b3894-213">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-213">ID number to identify the session.</span></span> <span data-ttu-id="b3894-214">Utilizado em conjunto com o ReplaceDialogIdTime para identificar de forma exclusiva a sessão que foi substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="b3894-215">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3894-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b3894-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b3894-p119">Identificação da caixa de diálogo SIP substitui a sessão. O formato dela é:</span><span class="sxs-lookup"><span data-stu-id="b3894-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="b3894-220">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="b3894-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-222">bits</span><span class="sxs-lookup"><span data-stu-id="b3894-222">bit</span></span></p></td>
<td><p><span data-ttu-id="b3894-223">Indica se a sessão foi iniciada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-225">bits</span><span class="sxs-lookup"><span data-stu-id="b3894-225">bit</span></span></p></td>
<td><p><span data-ttu-id="b3894-226">Indica se a sessão foi finalizada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b3894-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-228">bits</span><span class="sxs-lookup"><span data-stu-id="b3894-228">bit</span></span></p></td>
<td><p><span data-ttu-id="b3894-229">Indica se o usuário está conectado à rede interna.</span><span class="sxs-lookup"><span data-stu-id="b3894-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-231">datetime</span><span class="sxs-lookup"><span data-stu-id="b3894-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3894-p120">O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b3894-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-236">int</span><span class="sxs-lookup"><span data-stu-id="b3894-236">int</span></span></p></td>
<td><p><span data-ttu-id="b3894-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b3894-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-240"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-241">int</span><span class="sxs-lookup"><span data-stu-id="b3894-241">int</span></span></p></td>
<td><p><span data-ttu-id="b3894-242">ID de diagnóstico capturada dos cabeçalhos SIP da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-245">Tipo de conteúdo para a sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-248">FQDN do servidor de Front-End que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-251">FQDN do pool que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-254">Servidor de Mediação utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-257">Gateway usado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3894-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3894-260">FQDN do Servidor de Borda utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b3894-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3894-261"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-262">smallint</span><span class="sxs-lookup"><span data-stu-id="b3894-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="b3894-p122">Indica os atributos do usuário que participou da sessão. As definições de atributos a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="b3894-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="b3894-265">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="b3894-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3894-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b3894-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b3894-267">smallint</span><span class="sxs-lookup"><span data-stu-id="b3894-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="b3894-p123">Indica os atributos da chamada. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="b3894-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b3894-270">0x01 - Sessão repetida0</span><span class="sxs-lookup"><span data-stu-id="b3894-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="b3894-271">x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="b3894-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

