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
ms.openlocfilehash: ef6d8baf95cc99c342e18200f9a17e5ab03a7f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="d4acd-102">Exibição ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4acd-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4acd-103">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="d4acd-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="d4acd-104">O ConferenceSessionDetails visualiza as informações dos repositórios sobre sessões com vários participantes.</span><span class="sxs-lookup"><span data-stu-id="d4acd-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="d4acd-105">Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.</span><span class="sxs-lookup"><span data-stu-id="d4acd-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="d4acd-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4acd-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4acd-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="d4acd-107">Column</span></span></th>
<th><span data-ttu-id="d4acd-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d4acd-108">Data Type</span></span></th>
<th><span data-ttu-id="d4acd-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d4acd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d4acd-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4acd-112">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-112">Time of session request.</span></span> <span data-ttu-id="d4acd-113">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="d4acd-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-116">int</span><span class="sxs-lookup"><span data-stu-id="d4acd-116">int</span></span></p></td>
<td><p><span data-ttu-id="d4acd-117">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-117">ID number to identify the session.</span></span> <span data-ttu-id="d4acd-118">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="d4acd-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-120"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d4acd-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4acd-p104">Horário da primeira solicitação CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="d4acd-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-125"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4acd-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-127">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-130">Tipo de URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-130">Type of conference URI.</span></span> <span data-ttu-id="d4acd-131">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-133">identificador</span><span class="sxs-lookup"><span data-stu-id="d4acd-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d4acd-p106">Identificador que diferencia instâncias de conferências recorrentes. Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="d4acd-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4acd-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-138">URI do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-141">Tipo de URI de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-141">Type of conferencing server URI.</span></span> <span data-ttu-id="d4acd-142">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4acd-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-145">URI do usuário envolvido na sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-148">Tipo de URI do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="d4acd-149">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-150"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-152">Locatário do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="d4acd-153">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-154"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-155">identificador</span><span class="sxs-lookup"><span data-stu-id="d4acd-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d4acd-156">Identificador exclusivo do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-158">datetime</span><span class="sxs-lookup"><span data-stu-id="d4acd-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4acd-159">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-162">Versão do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-164">int</span><span class="sxs-lookup"><span data-stu-id="d4acd-164">int</span></span></p></td>
<td><p><span data-ttu-id="d4acd-165">Tipo de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-165">Type of conference server.</span></span> <span data-ttu-id="d4acd-166">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d4acd-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-169">Categoria do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-172">Versão do cliente utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-173"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-174">int</span><span class="sxs-lookup"><span data-stu-id="d4acd-174">int</span></span></p></td>
<td><p><span data-ttu-id="d4acd-175">Cliente utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="d4acd-176">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d4acd-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d4acd-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-179">Nome da categoria do cliente utilizado pelo usuário que foi parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4acd-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-182">URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="d4acd-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-185">Tipo de URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="d4acd-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="d4acd-186">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-189">Locatário do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="d4acd-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="d4acd-190">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4acd-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-193">URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-196">Tipo de URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="d4acd-197">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-200">Locatário do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="d4acd-201">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-203">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="d4acd-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-p116">Identificação da caixa de diálogo SIP. O formato é</span><span class="sxs-lookup"><span data-stu-id="d4acd-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="d4acd-206">:d ialog; from-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="d4acd-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-208">datetime</span><span class="sxs-lookup"><span data-stu-id="d4acd-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4acd-209">Número de identificação para identificar o diálogo que foi substituído pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d4acd-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="d4acd-210">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-212">int</span><span class="sxs-lookup"><span data-stu-id="d4acd-212">int</span></span></p></td>
<td><p><span data-ttu-id="d4acd-213">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-213">ID number to identify the session.</span></span> <span data-ttu-id="d4acd-214">Utilizado em conjunto com o ReplaceDialogIdTime para identificar de forma exclusiva a sessão que foi substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="d4acd-215">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d4acd-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="d4acd-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-p119">Identificação da caixa de diálogo SIP substitui a sessão. O formato dela é:</span><span class="sxs-lookup"><span data-stu-id="d4acd-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="d4acd-220">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="d4acd-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-222">bits</span><span class="sxs-lookup"><span data-stu-id="d4acd-222">bit</span></span></p></td>
<td><p><span data-ttu-id="d4acd-223">Indica se a sessão foi iniciada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-225">bits</span><span class="sxs-lookup"><span data-stu-id="d4acd-225">bit</span></span></p></td>
<td><p><span data-ttu-id="d4acd-226">Indica se a sessão foi finalizada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d4acd-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-228">bits</span><span class="sxs-lookup"><span data-stu-id="d4acd-228">bit</span></span></p></td>
<td><p><span data-ttu-id="d4acd-229">Indica se o usuário está conectado à rede interna.</span><span class="sxs-lookup"><span data-stu-id="d4acd-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-231">datetime</span><span class="sxs-lookup"><span data-stu-id="d4acd-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="d4acd-p120">O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="d4acd-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-236">int</span><span class="sxs-lookup"><span data-stu-id="d4acd-236">int</span></span></p></td>
<td><p><span data-ttu-id="d4acd-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="d4acd-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-240"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-241">int</span><span class="sxs-lookup"><span data-stu-id="d4acd-241">int</span></span></p></td>
<td><p><span data-ttu-id="d4acd-242">ID de diagnóstico capturada dos cabeçalhos SIP da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-245">Tipo de conteúdo para a sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-246"><strong>Front</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-248">FQDN do servidor de Front-End que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-251">FQDN do pool que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-254">Servidor de Mediação utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-257">Gateway usado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d4acd-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d4acd-260">FQDN do Servidor de Borda utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="d4acd-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4acd-261"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-262">smallint</span><span class="sxs-lookup"><span data-stu-id="d4acd-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="d4acd-p122">Indica os atributos do usuário que participou da sessão. As definições de atributos a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="d4acd-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="d4acd-265">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="d4acd-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4acd-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d4acd-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d4acd-267">smallint</span><span class="sxs-lookup"><span data-stu-id="d4acd-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="d4acd-p123">Indica os atributos da chamada. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="d4acd-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d4acd-270">0x01 - Sessão repetida0</span><span class="sxs-lookup"><span data-stu-id="d4acd-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="d4acd-271">x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="d4acd-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

