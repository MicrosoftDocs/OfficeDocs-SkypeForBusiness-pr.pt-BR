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
ms.openlocfilehash: 7bc6d1888753edbeb076d60d6725b6d9cffc509e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="b5d23-102">Exibição ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5d23-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5d23-103">_**Última modificação do tópico:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="b5d23-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="b5d23-104">O ConferenceSessionDetails visualiza as informações dos repositórios sobre sessões com vários participantes.</span><span class="sxs-lookup"><span data-stu-id="b5d23-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="b5d23-105">Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.</span><span class="sxs-lookup"><span data-stu-id="b5d23-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="b5d23-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5d23-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5d23-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="b5d23-107">Column</span></span></th>
<th><span data-ttu-id="b5d23-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b5d23-108">Data Type</span></span></th>
<th><span data-ttu-id="b5d23-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b5d23-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-111">datetime</span><span class="sxs-lookup"><span data-stu-id="b5d23-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d23-112">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-112">Time of session request.</span></span> <span data-ttu-id="b5d23-113">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b5d23-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-116">int</span><span class="sxs-lookup"><span data-stu-id="b5d23-116">int</span></span></p></td>
<td><p><span data-ttu-id="b5d23-117">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-117">ID number to identify the session.</span></span> <span data-ttu-id="b5d23-118">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b5d23-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-120"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b5d23-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d23-p104">Horário da primeira solicitação CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b5d23-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-125"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d23-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-127">URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-130">Tipo de URI da conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-130">Type of conference URI.</span></span> <span data-ttu-id="b5d23-131">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-133">identificador</span><span class="sxs-lookup"><span data-stu-id="b5d23-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b5d23-p106">Identificador que diferencia instâncias de conferências recorrentes. Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="b5d23-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d23-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-138">URI do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-141">Tipo de URI de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-141">Type of conferencing server URI.</span></span> <span data-ttu-id="b5d23-142">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d23-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-145">URI do usuário envolvido na sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-148">Tipo de URI do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="b5d23-149">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-150"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-152">Locatário do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="b5d23-153">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-154"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-155">identificador</span><span class="sxs-lookup"><span data-stu-id="b5d23-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b5d23-156">Identificador exclusivo do usuário que fez parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-158">datetime</span><span class="sxs-lookup"><span data-stu-id="b5d23-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d23-159">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-162">Versão do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-164">int</span><span class="sxs-lookup"><span data-stu-id="b5d23-164">int</span></span></p></td>
<td><p><span data-ttu-id="b5d23-165">Tipo de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-165">Type of conference server.</span></span> <span data-ttu-id="b5d23-166">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b5d23-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-169">Categoria do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-172">Versão do cliente utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-173"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-174">int</span><span class="sxs-lookup"><span data-stu-id="b5d23-174">int</span></span></p></td>
<td><p><span data-ttu-id="b5d23-175">Cliente utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="b5d23-176">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b5d23-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b5d23-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-179">Nome da categoria do cliente utilizado pelo usuário que foi parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d23-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-182">URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="b5d23-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-185">Tipo de URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="b5d23-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="b5d23-186">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-189">Locatário do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="b5d23-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="b5d23-190">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b5d23-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-193">URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-196">Tipo de URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="b5d23-197">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-200">Locatário do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="b5d23-201">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-203">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="b5d23-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-p116">Identificação da caixa de diálogo SIP. O formato é</span><span class="sxs-lookup"><span data-stu-id="b5d23-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="b5d23-206">:d ialog; from-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="b5d23-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-208">datetime</span><span class="sxs-lookup"><span data-stu-id="b5d23-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d23-209">Número de identificação para identificar o diálogo que foi substituído pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="b5d23-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="b5d23-210">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-212">int</span><span class="sxs-lookup"><span data-stu-id="b5d23-212">int</span></span></p></td>
<td><p><span data-ttu-id="b5d23-213">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-213">ID number to identify the session.</span></span> <span data-ttu-id="b5d23-214">Utilizado em conjunto com o ReplaceDialogIdTime para identificar de forma exclusiva a sessão que foi substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="b5d23-215">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5d23-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b5d23-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-p119">Identificação da caixa de diálogo SIP substitui a sessão. O formato dela é:</span><span class="sxs-lookup"><span data-stu-id="b5d23-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="b5d23-220">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="b5d23-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-222">bits</span><span class="sxs-lookup"><span data-stu-id="b5d23-222">bit</span></span></p></td>
<td><p><span data-ttu-id="b5d23-223">Indica se a sessão foi iniciada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-225">bits</span><span class="sxs-lookup"><span data-stu-id="b5d23-225">bit</span></span></p></td>
<td><p><span data-ttu-id="b5d23-226">Indica se a sessão foi finalizada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="b5d23-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-228">bits</span><span class="sxs-lookup"><span data-stu-id="b5d23-228">bit</span></span></p></td>
<td><p><span data-ttu-id="b5d23-229">Indica se o usuário está conectado à rede interna.</span><span class="sxs-lookup"><span data-stu-id="b5d23-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-231">datetime</span><span class="sxs-lookup"><span data-stu-id="b5d23-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5d23-p120">O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b5d23-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-236">int</span><span class="sxs-lookup"><span data-stu-id="b5d23-236">int</span></span></p></td>
<td><p><span data-ttu-id="b5d23-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="b5d23-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-240"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-241">int</span><span class="sxs-lookup"><span data-stu-id="b5d23-241">int</span></span></p></td>
<td><p><span data-ttu-id="b5d23-242">ID de diagnóstico capturada dos cabeçalhos SIP da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-245">Tipo de conteúdo para a sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-246"><strong>Front</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-248">FQDN do servidor de Front-End que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-251">FQDN do pool que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-254">Servidor de Mediação utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-257">Gateway usado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5d23-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b5d23-260">FQDN do Servidor de Borda utilizado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="b5d23-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5d23-261"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-262">smallint</span><span class="sxs-lookup"><span data-stu-id="b5d23-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="b5d23-p122">Indica os atributos do usuário que participou da sessão. As definições de atributos a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="b5d23-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="b5d23-265">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="b5d23-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5d23-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b5d23-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b5d23-267">smallint</span><span class="sxs-lookup"><span data-stu-id="b5d23-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="b5d23-p123">Indica os atributos da chamada. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="b5d23-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="b5d23-270">0x01 - Sessão repetida0</span><span class="sxs-lookup"><span data-stu-id="b5d23-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="b5d23-271">x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="b5d23-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

