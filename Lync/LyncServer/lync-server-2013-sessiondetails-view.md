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
ms.openlocfilehash: 3f7a143a0812b19a840c7eb339e80611720a08b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="daa3a-102">Exibição SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="daa3a-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="daa3a-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="daa3a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="daa3a-104">A visualização de SessionDetails armazena informações sobre sessões ponto a ponto, que pode ser uma chamada de telefone VoIP a VoIP, sessão de mensagens instantâneas entre duas partes ou outro tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="daa3a-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="daa3a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="daa3a-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="daa3a-106">Column</span></span></th>
<th><span data-ttu-id="daa3a-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="daa3a-107">Data Type</span></span></th>
<th><span data-ttu-id="daa3a-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="daa3a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="daa3a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="daa3a-111">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-111">Time of session request.</span></span> <span data-ttu-id="daa3a-112">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="daa3a-113">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de caixas de diálogo na tabela do Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-115">int</span><span class="sxs-lookup"><span data-stu-id="daa3a-115">int</span></span></p></td>
<td><p><span data-ttu-id="daa3a-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-116">ID number to identify the session.</span></span> <span data-ttu-id="daa3a-117">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="daa3a-118">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-119"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-120">datetime</span><span class="sxs-lookup"><span data-stu-id="daa3a-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="daa3a-p104">Horário da primeira solicitação INVITE. Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO). Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO).</span><span class="sxs-lookup"><span data-stu-id="daa3a-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="daa3a-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-128">URI do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="daa3a-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-131">URI do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-134">Tipo do URI do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="daa3a-135">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-138">Tipo do URI do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="daa3a-139">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="daa3a-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-142">Locatário do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="daa3a-143">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-144"><strong>Tolocatário</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-146">O locatário do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="daa3a-147">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-149">identificador</span><span class="sxs-lookup"><span data-stu-id="daa3a-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="daa3a-150">Identificador exclusivo do ponto de extremidade do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-151"><strong>Toendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-152">identificador</span><span class="sxs-lookup"><span data-stu-id="daa3a-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="daa3a-153">Identificador exclusivo do ponto de extremidade do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-155">datetime</span><span class="sxs-lookup"><span data-stu-id="daa3a-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="daa3a-156">Horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-158">int</span><span class="sxs-lookup"><span data-stu-id="daa3a-158">int</span></span></p></td>
<td><p><span data-ttu-id="daa3a-159">Número de mensagens enviadas pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-161">int</span><span class="sxs-lookup"><span data-stu-id="daa3a-161">int</span></span></p></td>
<td><p><span data-ttu-id="daa3a-162">Número de mensagens evniadas pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-165">Versão do cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-167">int</span><span class="sxs-lookup"><span data-stu-id="daa3a-167">int</span></span></p></td>
<td><p><span data-ttu-id="daa3a-168">Cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-168">Client used by the user who started the session.</span></span> <span data-ttu-id="daa3a-169">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="daa3a-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="daa3a-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-172">Nome da categoria do cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-175">Versão do cliente usado pelo usuário que ingressou na sessão</span><span class="sxs-lookup"><span data-stu-id="daa3a-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-176"><strong>Toclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-177">int</span><span class="sxs-lookup"><span data-stu-id="daa3a-177">int</span></span></p></td>
<td><p><span data-ttu-id="daa3a-178">Cliente usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="daa3a-179">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="daa3a-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="daa3a-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-182">Nome da categoria do cliente usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="daa3a-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-185">URI do usuário de destino da sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="daa3a-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-188">Tipo do URI do usuário de destino da sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="daa3a-189">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="daa3a-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-192">URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="daa3a-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-195">Tipo de URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="daa3a-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="daa3a-196">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-199">Locatário do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="daa3a-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="daa3a-200">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="daa3a-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-203">URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-206">Tipo de URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="daa3a-207">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-210">Locatário do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="daa3a-211">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="daa3a-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-p116">ID de diálogo do SIP. O formato é:</span><span class="sxs-lookup"><span data-stu-id="daa3a-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="daa3a-216">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="daa3a-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-218">identificador</span><span class="sxs-lookup"><span data-stu-id="daa3a-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="daa3a-219">GUID usadoo para correlacionar múltiplas sessões.</span><span class="sxs-lookup"><span data-stu-id="daa3a-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-221">datetime</span><span class="sxs-lookup"><span data-stu-id="daa3a-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="daa3a-222">Horário do diálogo que foi substituído pela sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="daa3a-223">Usado em conjunto com ReplaceDialogIdSeq para identificar exclusivamente um diálogo que foi substituído pela sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="daa3a-224">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-226">int</span><span class="sxs-lookup"><span data-stu-id="daa3a-226">int</span></span></p></td>
<td><p><span data-ttu-id="daa3a-227">Número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-227">ID number to identify the session.</span></span> <span data-ttu-id="daa3a-228">Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="daa3a-229">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="daa3a-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="daa3a-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-p119">ID do diálogo do SIP substituído pela sessão. O formato é:</span><span class="sxs-lookup"><span data-stu-id="daa3a-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="daa3a-234">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="daa3a-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-236">datetime</span><span class="sxs-lookup"><span data-stu-id="daa3a-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="daa3a-p120">O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="daa3a-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-241">int</span><span class="sxs-lookup"><span data-stu-id="daa3a-241">int</span></span></p></td>
<td><p><span data-ttu-id="daa3a-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="daa3a-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-245"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-246">int</span><span class="sxs-lookup"><span data-stu-id="daa3a-246">int</span></span></p></td>
<td><p><span data-ttu-id="daa3a-247">ID de diagnóstico capturado dos cabeçalhos do SIP.</span><span class="sxs-lookup"><span data-stu-id="daa3a-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-250">Tipo de conteúdo para a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-251"><strong>Front</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-253">FQDN do servidor de Front-End que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-256">FQDN do pool que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-259">FQDN do servidor de Borda usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-262">FQDN do servidor de Borda usado pelo usuário que iniciou a sessão</span><span class="sxs-lookup"><span data-stu-id="daa3a-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-264">bits</span><span class="sxs-lookup"><span data-stu-id="daa3a-264">bit</span></span></p></td>
<td><p><span data-ttu-id="daa3a-265">Indica se o usuário que iniciou a sessão fez logon a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="daa3a-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-267">bits</span><span class="sxs-lookup"><span data-stu-id="daa3a-267">bit</span></span></p></td>
<td><p><span data-ttu-id="daa3a-268">Indica se o usuário que ingressou na sessão fez logon a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="daa3a-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="daa3a-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-271">Prioridade de chamada da sessão.</span><span class="sxs-lookup"><span data-stu-id="daa3a-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-273">smallint</span><span class="sxs-lookup"><span data-stu-id="daa3a-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="daa3a-p122">Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="daa3a-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="daa3a-276">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="daa3a-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-278">smallint</span><span class="sxs-lookup"><span data-stu-id="daa3a-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="daa3a-p123">Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="daa3a-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="daa3a-281">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="daa3a-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="daa3a-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-283">smallint</span><span class="sxs-lookup"><span data-stu-id="daa3a-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="daa3a-p124">Indica os atributos de chamada. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="daa3a-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="daa3a-286">0x01 - Sessão repetida</span><span class="sxs-lookup"><span data-stu-id="daa3a-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="daa3a-287">0x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="daa3a-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="daa3a-288"><strong>Localização</strong></span><span class="sxs-lookup"><span data-stu-id="daa3a-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="daa3a-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="daa3a-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="daa3a-290">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="daa3a-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

