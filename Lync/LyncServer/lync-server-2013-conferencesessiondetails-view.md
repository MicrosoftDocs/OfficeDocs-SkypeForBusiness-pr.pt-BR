---
title: 'Lync Server 2013: modo de exibição ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="aa6e5-102">Exibição ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa6e5-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa6e5-103">_**Tópico da última modificação:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="aa6e5-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="aa6e5-104">A exibição ConferenceSessionDetails armazena informações sobre sessões com vários participantes.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="aa6e5-105">Cada registro representa uma sessão de conferência, que pode ser a sessão com foco ou a sessão com um servidor de conferência específico.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="aa6e5-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa6e5-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="aa6e5-107">Column</span></span></th>
<th><span data-ttu-id="aa6e5-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="aa6e5-108">Data Type</span></span></th>
<th><span data-ttu-id="aa6e5-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="aa6e5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-110"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="aa6e5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-112">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-112">Time of session request.</span></span> <span data-ttu-id="aa6e5-113">Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="aa6e5-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-116">int</span><span class="sxs-lookup"><span data-stu-id="aa6e5-116">int</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-117">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-117">ID number to identify the session.</span></span> <span data-ttu-id="aa6e5-118">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="aa6e5-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-120"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-121">datetime</span><span class="sxs-lookup"><span data-stu-id="aa6e5-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-122">Hora da primeira solicitação INVITE.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-122">Time of the first INVITE request.</span></span> <span data-ttu-id="aa6e5-123">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="aa6e5-124">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="aa6e5-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-127">URL da conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-130">Tipo de URI de conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-130">Type of conference URI.</span></span> <span data-ttu-id="aa6e5-131">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-133">identificador</span><span class="sxs-lookup"><span data-stu-id="aa6e5-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-134">Identificador que diferencia as instâncias de conferências recorrentes.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="aa6e5-135">Cada instância de conferência recorrente tem o mesmo ConferenceURI, mas um valor ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-138">URL do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-141">Tipo de URI do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-141">Type of conferencing server URI.</span></span> <span data-ttu-id="aa6e5-142">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-145">O URI do usuário envolvido na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-148">Tipo de URI do usuário cuja parte da sessão faz parte.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="aa6e5-149">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-150"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-152">Locatário do usuário cuja parte da sessão faz parte.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="aa6e5-153">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-154"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-155">identificador</span><span class="sxs-lookup"><span data-stu-id="aa6e5-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-156">Identificador exclusivo do usuário cuja parte da sessão faz parte.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-158">datetime</span><span class="sxs-lookup"><span data-stu-id="aa6e5-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-159">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-162">Versão do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-164">int</span><span class="sxs-lookup"><span data-stu-id="aa6e5-164">int</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-165">Tipo de servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-165">Type of conference server.</span></span> <span data-ttu-id="aa6e5-166">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-169">Categoria do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-172">Versão do cliente usada pelo usuário que participou na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-173"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-174">int</span><span class="sxs-lookup"><span data-stu-id="aa6e5-174">int</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-175">Cliente usado pelo usuário que participou na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="aa6e5-176">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-179">Nome da categoria do cliente usado pelo usuário que fazia parte da sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-182">O URI do usuário em nome do qual a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-185">Tipo de URI do usuário em nome do qual a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="aa6e5-186">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-189">Locatário do usuário cujo nome da sessão foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="aa6e5-190">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-193">URL do usuário que fez a chamada para a sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-196">Tipo de URI do usuário que a fez referência à sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="aa6e5-197">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-200">Locatário do usuário que fez a chamada para a sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="aa6e5-201">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-202"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-203">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-204">ID da caixa de diálogo SIP.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-204">SIP dialog ID.</span></span> <span data-ttu-id="aa6e5-205">O formato é</span><span class="sxs-lookup"><span data-stu-id="aa6e5-205">The format is</span></span></p>
<p><span data-ttu-id="aa6e5-206">:d ialog; de-marca; até-marca</span><span class="sxs-lookup"><span data-stu-id="aa6e5-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-208">datetime</span><span class="sxs-lookup"><span data-stu-id="aa6e5-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-209">Número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="aa6e5-210">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-212">int</span><span class="sxs-lookup"><span data-stu-id="aa6e5-212">int</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-213">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-213">ID number to identify the session.</span></span> <span data-ttu-id="aa6e5-214">Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma sessão substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="aa6e5-215">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-218">ID da caixa de diálogo SIP a sessão substitui.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="aa6e5-219">O formato do é:</span><span class="sxs-lookup"><span data-stu-id="aa6e5-219">The format of the is:</span></span></p>
<p><span data-ttu-id="aa6e5-220">caixa de diálogo; de-marca; até-marca</span><span class="sxs-lookup"><span data-stu-id="aa6e5-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-222">bit</span><span class="sxs-lookup"><span data-stu-id="aa6e5-222">bit</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-223">Indica se a sessão foi iniciada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-225">bit</span><span class="sxs-lookup"><span data-stu-id="aa6e5-225">bit</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-226">Indica se a sessão foi encerrada pelo servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-228">bit</span><span class="sxs-lookup"><span data-stu-id="aa6e5-228">bit</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-229">Indica se o usuário está conectado à rede interna.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-231">datetime</span><span class="sxs-lookup"><span data-stu-id="aa6e5-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-232">Hora da resposta à primeira mensagem de convite.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="aa6e5-233">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="aa6e5-234">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="aa6e5-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-236">int</span><span class="sxs-lookup"><span data-stu-id="aa6e5-236">int</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-237">Código de resposta SIP para o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="aa6e5-238">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="aa6e5-239">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="aa6e5-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-240"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-241">int</span><span class="sxs-lookup"><span data-stu-id="aa6e5-241">int</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-242">ID do diagnóstico capturada dos cabeçalhos SIP da sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-245">Tipo de conteúdo da sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-248">FQDN do servidor de front-end que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-251">FQDN do pool que capturou os dados da sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-254">Servidor de mediação usado pelo usuário que participou na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-255"><strong>Gateway</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-257">O gateway usado pelo usuário que participou da sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-260">FQDN do servidor de borda usado pelo usuário que participou na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa6e5-261"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-262">smallint</span><span class="sxs-lookup"><span data-stu-id="aa6e5-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-263">Indica os atributos do usuário que participou na sessão.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="aa6e5-264">As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="aa6e5-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="aa6e5-265">0x01-integrado ao telefone desktop</span><span class="sxs-lookup"><span data-stu-id="aa6e5-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa6e5-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="aa6e5-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="aa6e5-267">smallint</span><span class="sxs-lookup"><span data-stu-id="aa6e5-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="aa6e5-268">Indica os atributos da chamada.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-268">Indicates the call attributes.</span></span> <span data-ttu-id="aa6e5-269">As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="aa6e5-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="aa6e5-270">0x01-repetidas Session0</span><span class="sxs-lookup"><span data-stu-id="aa6e5-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="aa6e5-271">X02-uma chamada feita pelo agente em nome de um grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="aa6e5-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

