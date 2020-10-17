---
title: 'Lync Server 2013: modo de exibição SessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8baf67ce72103ef0dda64a9b0b43a8f6dd6402f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510058"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="a71be-102">Exibição SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a71be-102">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a71be-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a71be-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a71be-104">A visualização de SessionDetails armazena informações sobre sessões ponto a ponto, que pode ser uma chamada de telefone VoIP a VoIP, sessão de mensagens instantâneas entre duas partes ou outro tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="a71be-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a71be-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a71be-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="a71be-106">Column</span></span></th>
<th><span data-ttu-id="a71be-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="a71be-107">Data Type</span></span></th>
<th><span data-ttu-id="a71be-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a71be-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a71be-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a71be-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a71be-111">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-111">Time of session request.</span></span> <span data-ttu-id="a71be-112">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a71be-113">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de caixas de diálogo na tabela do Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-115">int</span><span class="sxs-lookup"><span data-stu-id="a71be-115">int</span></span></p></td>
<td><p><span data-ttu-id="a71be-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-116">ID number to identify the session.</span></span> <span data-ttu-id="a71be-117">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a71be-118">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-119"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-120">datetime</span><span class="sxs-lookup"><span data-stu-id="a71be-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="a71be-p104">Horário da primeira solicitação INVITE. Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO). Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO).</span><span class="sxs-lookup"><span data-stu-id="a71be-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a71be-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a71be-128">URI do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a71be-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a71be-131">URI do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-134">Tipo do URI do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="a71be-135">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-138">Tipo do URI do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="a71be-139">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a71be-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a71be-142">Locatário do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="a71be-143">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-144"><strong>Tolocatário</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-146">O locatário do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="a71be-147">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-149">identificador</span><span class="sxs-lookup"><span data-stu-id="a71be-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a71be-150">Identificador exclusivo do ponto de extremidade do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-151"><strong>Toendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-152">identificador</span><span class="sxs-lookup"><span data-stu-id="a71be-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a71be-153">Identificador exclusivo do ponto de extremidade do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-155">datetime</span><span class="sxs-lookup"><span data-stu-id="a71be-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="a71be-156">Horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-158">int</span><span class="sxs-lookup"><span data-stu-id="a71be-158">int</span></span></p></td>
<td><p><span data-ttu-id="a71be-159">Número de mensagens enviadas pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-161">int</span><span class="sxs-lookup"><span data-stu-id="a71be-161">int</span></span></p></td>
<td><p><span data-ttu-id="a71be-162">Número de mensagens evniadas pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-165">Versão do cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-167">int</span><span class="sxs-lookup"><span data-stu-id="a71be-167">int</span></span></p></td>
<td><p><span data-ttu-id="a71be-168">Cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-168">Client used by the user who started the session.</span></span> <span data-ttu-id="a71be-169">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="a71be-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a71be-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a71be-172">Nome da categoria do cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-175">Versão do cliente usado pelo usuário que ingressou na sessão</span><span class="sxs-lookup"><span data-stu-id="a71be-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-176"><strong>Toclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-177">int</span><span class="sxs-lookup"><span data-stu-id="a71be-177">int</span></span></p></td>
<td><p><span data-ttu-id="a71be-178">Cliente usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="a71be-179">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="a71be-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a71be-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a71be-182">Nome da categoria do cliente usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a71be-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a71be-185">URI do usuário de destino da sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a71be-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a71be-188">Tipo do URI do usuário de destino da sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="a71be-189">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a71be-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a71be-192">URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="a71be-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-195">Tipo de URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="a71be-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="a71be-196">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-199">Locatário do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="a71be-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="a71be-200">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a71be-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a71be-203">URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-206">Tipo de URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="a71be-207">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-210">Locatário do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="a71be-211">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="a71be-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a71be-p116">ID de diálogo do SIP. O formato é:</span><span class="sxs-lookup"><span data-stu-id="a71be-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="a71be-216">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="a71be-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-218">identificador</span><span class="sxs-lookup"><span data-stu-id="a71be-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a71be-219">GUID usadoo para correlacionar múltiplas sessões.</span><span class="sxs-lookup"><span data-stu-id="a71be-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-221">datetime</span><span class="sxs-lookup"><span data-stu-id="a71be-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="a71be-222">Horário do diálogo que foi substituído pela sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="a71be-223">Usado em conjunto com ReplaceDialogIdSeq para identificar exclusivamente um diálogo que foi substituído pela sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="a71be-224">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-226">int</span><span class="sxs-lookup"><span data-stu-id="a71be-226">int</span></span></p></td>
<td><p><span data-ttu-id="a71be-227">Número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-227">ID number to identify the session.</span></span> <span data-ttu-id="a71be-228">Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="a71be-229">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a71be-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="a71be-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="a71be-p119">ID do diálogo do SIP substituído pela sessão. O formato é:</span><span class="sxs-lookup"><span data-stu-id="a71be-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="a71be-234">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="a71be-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-236">datetime</span><span class="sxs-lookup"><span data-stu-id="a71be-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="a71be-p120">O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="a71be-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-241">int</span><span class="sxs-lookup"><span data-stu-id="a71be-241">int</span></span></p></td>
<td><p><span data-ttu-id="a71be-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="a71be-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-245"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-246">int</span><span class="sxs-lookup"><span data-stu-id="a71be-246">int</span></span></p></td>
<td><p><span data-ttu-id="a71be-247">ID de diagnóstico capturado dos cabeçalhos do SIP.</span><span class="sxs-lookup"><span data-stu-id="a71be-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-250">Tipo de conteúdo para a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-253">FQDN do servidor de Front-End que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-256">FQDN do pool que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-259">FQDN do servidor de Borda usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-262">FQDN do servidor de Borda usado pelo usuário que iniciou a sessão</span><span class="sxs-lookup"><span data-stu-id="a71be-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-264">bits</span><span class="sxs-lookup"><span data-stu-id="a71be-264">bit</span></span></p></td>
<td><p><span data-ttu-id="a71be-265">Indica se o usuário que iniciou a sessão fez logon a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="a71be-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-267">bits</span><span class="sxs-lookup"><span data-stu-id="a71be-267">bit</span></span></p></td>
<td><p><span data-ttu-id="a71be-268">Indica se o usuário que ingressou na sessão fez logon a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="a71be-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a71be-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a71be-271">Prioridade de chamada da sessão.</span><span class="sxs-lookup"><span data-stu-id="a71be-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-273">smallint</span><span class="sxs-lookup"><span data-stu-id="a71be-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="a71be-p122">Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="a71be-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a71be-276">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="a71be-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-278">smallint</span><span class="sxs-lookup"><span data-stu-id="a71be-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="a71be-p123">Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="a71be-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a71be-281">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="a71be-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71be-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-283">smallint</span><span class="sxs-lookup"><span data-stu-id="a71be-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="a71be-p124">Indica os atributos de chamada. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="a71be-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="a71be-286">0x01 - Sessão repetida</span><span class="sxs-lookup"><span data-stu-id="a71be-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="a71be-287">0x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="a71be-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71be-288"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="a71be-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="a71be-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="a71be-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="a71be-290">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="a71be-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

