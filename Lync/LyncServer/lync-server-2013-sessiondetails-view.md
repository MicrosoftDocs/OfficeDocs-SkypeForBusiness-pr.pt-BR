---
title: 'Lync Server 2013: modo de exibição SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="c192d-102">Exibição SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c192d-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c192d-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c192d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c192d-104">A exibição SessionDetails armazena informações sobre sessões ponto a ponto, que podem ser chamadas telefônicas VoIP, VoIP, uma sessão de IM de duas partes ou outro tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="c192d-105">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c192d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c192d-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="c192d-106">Column</span></span></th>
<th><span data-ttu-id="c192d-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c192d-107">Data Type</span></span></th>
<th><span data-ttu-id="c192d-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="c192d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c192d-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="c192d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c192d-111">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-111">Time of session request.</span></span> <span data-ttu-id="c192d-112">Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c192d-113">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos na tabela do Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-115">int</span><span class="sxs-lookup"><span data-stu-id="c192d-115">int</span></span></p></td>
<td><p><span data-ttu-id="c192d-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-116">ID number to identify the session.</span></span> <span data-ttu-id="c192d-117">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="c192d-118">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-119"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-120">datetime</span><span class="sxs-lookup"><span data-stu-id="c192d-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="c192d-121">Hora da primeira solicitação INVITE.</span><span class="sxs-lookup"><span data-stu-id="c192d-121">Time of the first INVITE request.</span></span> <span data-ttu-id="c192d-122">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c192d-123">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="c192d-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="c192d-124">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c192d-125">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="c192d-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c192d-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c192d-128">URL do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c192d-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c192d-131">URL do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-134">Tipo de URI do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="c192d-135">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-138">Tipo de URI do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="c192d-139">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c192d-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c192d-142">Locatário do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="c192d-143">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-144"><strong>Tolocatário</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-146">O locatário do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="c192d-147">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-149">identificador</span><span class="sxs-lookup"><span data-stu-id="c192d-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c192d-150">Identificador exclusivo do ponto de extremidade do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-151"><strong>Toendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-152">identificador</span><span class="sxs-lookup"><span data-stu-id="c192d-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c192d-153">Identificador exclusivo do ponto de extremidade do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-155">datetime</span><span class="sxs-lookup"><span data-stu-id="c192d-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="c192d-156">Hora de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-158">int</span><span class="sxs-lookup"><span data-stu-id="c192d-158">int</span></span></p></td>
<td><p><span data-ttu-id="c192d-159">Número de mensagens enviadas pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-161">int</span><span class="sxs-lookup"><span data-stu-id="c192d-161">int</span></span></p></td>
<td><p><span data-ttu-id="c192d-162">Número de mensagens enviadas pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-165">Versão do cliente usada pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-167">int</span><span class="sxs-lookup"><span data-stu-id="c192d-167">int</span></span></p></td>
<td><p><span data-ttu-id="c192d-168">Cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-168">Client used by the user who started the session.</span></span> <span data-ttu-id="c192d-169">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="c192d-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c192d-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c192d-172">Nome da categoria do cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-175">Versão do cliente usada pelo usuário que ingressou na sessão</span><span class="sxs-lookup"><span data-stu-id="c192d-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-176"><strong>Toclientetype</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-177">int</span><span class="sxs-lookup"><span data-stu-id="c192d-177">int</span></span></p></td>
<td><p><span data-ttu-id="c192d-178">Cliente usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="c192d-179">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="c192d-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c192d-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c192d-182">Nome da categoria do cliente usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c192d-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c192d-185">URL do usuário de destino da sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c192d-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c192d-188">Tipo de URI do usuário de destino da sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="c192d-189">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c192d-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c192d-192">O URI do usuário em nome do qual a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="c192d-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-195">Tipo de URI do usuário em nome do qual a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="c192d-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="c192d-196">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-199">Locatário do usuário cujo nome da sessão foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="c192d-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="c192d-200">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c192d-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c192d-203">URL do usuário que fez a chamada para a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-206">Tipo de URI do usuário que a fez referência à sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="c192d-207">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-210">Locatário do usuário que fez a chamada para a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="c192d-211">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-212"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="c192d-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c192d-214">ID da caixa de diálogo SIP.</span><span class="sxs-lookup"><span data-stu-id="c192d-214">SIP dialog ID.</span></span> <span data-ttu-id="c192d-215">O formato é:</span><span class="sxs-lookup"><span data-stu-id="c192d-215">The format is:</span></span></p>
<p><span data-ttu-id="c192d-216">caixa de diálogo; de-marca; até-marca</span><span class="sxs-lookup"><span data-stu-id="c192d-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-218">identificador</span><span class="sxs-lookup"><span data-stu-id="c192d-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c192d-219">GUID usado para correlacionar várias sessões.</span><span class="sxs-lookup"><span data-stu-id="c192d-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-221">datetime</span><span class="sxs-lookup"><span data-stu-id="c192d-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="c192d-222">A hora da caixa de diálogo que foi substituída pela sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="c192d-223">Usado em conjunto com ReplaceDialogIdSeq para identificar exclusivamente uma caixa de diálogo que é substituída pela sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="c192d-224">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-226">int</span><span class="sxs-lookup"><span data-stu-id="c192d-226">int</span></span></p></td>
<td><p><span data-ttu-id="c192d-227">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-227">ID number to identify the session.</span></span> <span data-ttu-id="c192d-228">Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma caixa de diálogo que é substituída pela sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="c192d-229">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c192d-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="c192d-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c192d-232">ID da caixa de diálogo SIP a sessão substitui.</span><span class="sxs-lookup"><span data-stu-id="c192d-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="c192d-233">O formato é:</span><span class="sxs-lookup"><span data-stu-id="c192d-233">The format is:</span></span></p>
<p><span data-ttu-id="c192d-234">caixa de diálogo; de-marca; até-marca</span><span class="sxs-lookup"><span data-stu-id="c192d-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-236">datetime</span><span class="sxs-lookup"><span data-stu-id="c192d-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="c192d-237">Hora da resposta à primeira mensagem de convite.</span><span class="sxs-lookup"><span data-stu-id="c192d-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="c192d-238">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c192d-239">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="c192d-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-241">int</span><span class="sxs-lookup"><span data-stu-id="c192d-241">int</span></span></p></td>
<td><p><span data-ttu-id="c192d-242">Código de resposta SIP para o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="c192d-243">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c192d-244">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="c192d-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-245"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-246">int</span><span class="sxs-lookup"><span data-stu-id="c192d-246">int</span></span></p></td>
<td><p><span data-ttu-id="c192d-247">ID de diagnóstico capturada de cabeçalhos SIP.</span><span class="sxs-lookup"><span data-stu-id="c192d-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-250">Tipo de conteúdo da sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-253">FQDN do servidor de front-end que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-256">FQDN do pool que capturou os dados da sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-259">FQDN do servidor de borda usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-262">FQDN do servidor de borda usado pelo usuário que iniciou a sessão</span><span class="sxs-lookup"><span data-stu-id="c192d-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-264">bit</span><span class="sxs-lookup"><span data-stu-id="c192d-264">bit</span></span></p></td>
<td><p><span data-ttu-id="c192d-265">Indica se o usuário que iniciou a sessão está conectada a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="c192d-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-267">bit</span><span class="sxs-lookup"><span data-stu-id="c192d-267">bit</span></span></p></td>
<td><p><span data-ttu-id="c192d-268">Indica se o usuário que ingressou na sessão que se conectou na rede interna.</span><span class="sxs-lookup"><span data-stu-id="c192d-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c192d-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c192d-271">Prioridade da chamada da sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-273">smallint</span><span class="sxs-lookup"><span data-stu-id="c192d-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="c192d-274">Indica os atributos do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="c192d-275">As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="c192d-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="c192d-276">0x01-integrado ao telefone desktop</span><span class="sxs-lookup"><span data-stu-id="c192d-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-278">smallint</span><span class="sxs-lookup"><span data-stu-id="c192d-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="c192d-279">Indica os atributos do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="c192d-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="c192d-280">As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="c192d-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="c192d-281">0x01-integrado ao telefone desktop</span><span class="sxs-lookup"><span data-stu-id="c192d-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c192d-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-283">smallint</span><span class="sxs-lookup"><span data-stu-id="c192d-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="c192d-284">Indica os atributos da chamada.</span><span class="sxs-lookup"><span data-stu-id="c192d-284">Indicates the call attributes.</span></span> <span data-ttu-id="c192d-285">As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="c192d-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="c192d-286">0x01-sessão repetida</span><span class="sxs-lookup"><span data-stu-id="c192d-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="c192d-287">0x02-uma chamada feita pelo agente em nome de um grupo de resposta</span><span class="sxs-lookup"><span data-stu-id="c192d-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c192d-288"><strong>Local</strong></span><span class="sxs-lookup"><span data-stu-id="c192d-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="c192d-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="c192d-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="c192d-290">Local de chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="c192d-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

