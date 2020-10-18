---
title: 'Lync Server 2013: modo de exibição SessionDetails'
description: 'Lync Server 2013: modo de exibição SessionDetails.'
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
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573237"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="083f5-103">Exibição SessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="083f5-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="083f5-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="083f5-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="083f5-105">A visualização de SessionDetails armazena informações sobre sessões ponto a ponto, que pode ser uma chamada de telefone VoIP a VoIP, sessão de mensagens instantâneas entre duas partes ou outro tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="083f5-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="083f5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="083f5-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="083f5-107">Column</span></span></th>
<th><span data-ttu-id="083f5-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="083f5-108">Data Type</span></span></th>
<th><span data-ttu-id="083f5-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="083f5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="083f5-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-111">datetime</span><span class="sxs-lookup"><span data-stu-id="083f5-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="083f5-112">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-112">Time of session request.</span></span> <span data-ttu-id="083f5-113">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="083f5-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de caixas de diálogo na tabela do Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-116">int</span><span class="sxs-lookup"><span data-stu-id="083f5-116">int</span></span></p></td>
<td><p><span data-ttu-id="083f5-117">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-117">ID number to identify the session.</span></span> <span data-ttu-id="083f5-118">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="083f5-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-120"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-121">datetime</span><span class="sxs-lookup"><span data-stu-id="083f5-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="083f5-p104">Horário da primeira solicitação INVITE. Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO). Este campo é normalmente preenchido pelos dados gerados a partir da mensagem INVITE inicial na sessão. Caso não exista uma mensagem INVITE então o campo é preenchido com a data e horário da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE, ou INFO).</span><span class="sxs-lookup"><span data-stu-id="083f5-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="083f5-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="083f5-129">URI do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-130"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-131">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="083f5-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="083f5-132">URI do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-133"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-135">Tipo do URI do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="083f5-136">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-139">Tipo do URI do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="083f5-140">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="083f5-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="083f5-143">Locatário do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="083f5-144">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-145"><strong>Tolocatário</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-147">O locatário do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="083f5-148">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-150">identificador</span><span class="sxs-lookup"><span data-stu-id="083f5-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="083f5-151">Identificador exclusivo do ponto de extremidade do usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-152"><strong>Toendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-153">identificador</span><span class="sxs-lookup"><span data-stu-id="083f5-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="083f5-154">Identificador exclusivo do ponto de extremidade do usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-156">datetime</span><span class="sxs-lookup"><span data-stu-id="083f5-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="083f5-157">Horário de término da sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-159">int</span><span class="sxs-lookup"><span data-stu-id="083f5-159">int</span></span></p></td>
<td><p><span data-ttu-id="083f5-160">Número de mensagens enviadas pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-162">int</span><span class="sxs-lookup"><span data-stu-id="083f5-162">int</span></span></p></td>
<td><p><span data-ttu-id="083f5-163">Número de mensagens evniadas pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-166">Versão do cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-168">int</span><span class="sxs-lookup"><span data-stu-id="083f5-168">int</span></span></p></td>
<td><p><span data-ttu-id="083f5-169">Cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-169">Client used by the user who started the session.</span></span> <span data-ttu-id="083f5-170">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="083f5-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="083f5-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="083f5-173">Nome da categoria do cliente usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-175">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-176">Versão do cliente usado pelo usuário que ingressou na sessão</span><span class="sxs-lookup"><span data-stu-id="083f5-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-177"><strong>Toclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-178">int</span><span class="sxs-lookup"><span data-stu-id="083f5-178">int</span></span></p></td>
<td><p><span data-ttu-id="083f5-179">Cliente usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="083f5-180">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="083f5-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-182">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="083f5-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="083f5-183">Nome da categoria do cliente usado pelo usuário que ingressou na sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-185">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="083f5-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="083f5-186">URI do usuário de destino da sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-188">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="083f5-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="083f5-189">Tipo do URI do usuário de destino da sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="083f5-190">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="083f5-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="083f5-193">URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="083f5-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-196">Tipo de URI do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="083f5-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="083f5-197">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-200">Locatário do usuário em cujo nome a sessão foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="083f5-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="083f5-201">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-202"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-203">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="083f5-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="083f5-204">URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-205"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-206">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-207">Tipo de URI do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="083f5-208">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-209"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-210">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-211">Locatário do usuário que se refere à sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="083f5-212">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-213"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-214">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="083f5-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="083f5-p116">ID de diálogo do SIP. O formato é:</span><span class="sxs-lookup"><span data-stu-id="083f5-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="083f5-217">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="083f5-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-218"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-219">identificador</span><span class="sxs-lookup"><span data-stu-id="083f5-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="083f5-220">GUID usadoo para correlacionar múltiplas sessões.</span><span class="sxs-lookup"><span data-stu-id="083f5-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-221"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-222">datetime</span><span class="sxs-lookup"><span data-stu-id="083f5-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="083f5-223">Horário do diálogo que foi substituído pela sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="083f5-224">Usado em conjunto com ReplaceDialogIdSeq para identificar exclusivamente um diálogo que foi substituído pela sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="083f5-225">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-226"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-227">int</span><span class="sxs-lookup"><span data-stu-id="083f5-227">int</span></span></p></td>
<td><p><span data-ttu-id="083f5-228">Número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-228">ID number to identify the session.</span></span> <span data-ttu-id="083f5-229">Usado em conjunto com ReplaceDialogIdTime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="083f5-230">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="083f5-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-231"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-232">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="083f5-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="083f5-p119">ID do diálogo do SIP substituído pela sessão. O formato é:</span><span class="sxs-lookup"><span data-stu-id="083f5-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="083f5-235">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="083f5-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-236"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-237">datetime</span><span class="sxs-lookup"><span data-stu-id="083f5-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="083f5-p120">O tempo de resposta para a primeira mensagem CONVIDAR. Este campo é, geralmente, preenchido por dados gerados a partir da mensagem CONVIDAR inicial na sessão. Se não houver nenhuma mensagem CONVIDAR, então o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="083f5-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-242">int</span><span class="sxs-lookup"><span data-stu-id="083f5-242">int</span></span></p></td>
<td><p><span data-ttu-id="083f5-p121">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="083f5-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-246"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-247">int</span><span class="sxs-lookup"><span data-stu-id="083f5-247">int</span></span></p></td>
<td><p><span data-ttu-id="083f5-248">ID de diagnóstico capturado dos cabeçalhos do SIP.</span><span class="sxs-lookup"><span data-stu-id="083f5-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-251">Tipo de conteúdo para a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-254">FQDN do servidor de Front-End que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-255"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-257">FQDN do pool que capturou os dados para a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-260">FQDN do servidor de Borda usado pelo usuário que iniciou a sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-262">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-263">FQDN do servidor de Borda usado pelo usuário que iniciou a sessão</span><span class="sxs-lookup"><span data-stu-id="083f5-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-265">bits</span><span class="sxs-lookup"><span data-stu-id="083f5-265">bit</span></span></p></td>
<td><p><span data-ttu-id="083f5-266">Indica se o usuário que iniciou a sessão fez logon a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="083f5-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-268">bits</span><span class="sxs-lookup"><span data-stu-id="083f5-268">bit</span></span></p></td>
<td><p><span data-ttu-id="083f5-269">Indica se o usuário que ingressou na sessão fez logon a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="083f5-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-271">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="083f5-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="083f5-272">Prioridade de chamada da sessão.</span><span class="sxs-lookup"><span data-stu-id="083f5-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-274">smallint</span><span class="sxs-lookup"><span data-stu-id="083f5-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="083f5-p122">Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="083f5-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="083f5-277">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="083f5-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-279">smallint</span><span class="sxs-lookup"><span data-stu-id="083f5-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="083f5-p123">Indica os atributos do usuário que iniciou a sessão. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="083f5-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="083f5-282">0x01 - Integrado com telefone de mesa</span><span class="sxs-lookup"><span data-stu-id="083f5-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="083f5-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-284">smallint</span><span class="sxs-lookup"><span data-stu-id="083f5-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="083f5-p124">Indica os atributos de chamada. As definições de atributo a seguir são permitidas:</span><span class="sxs-lookup"><span data-stu-id="083f5-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="083f5-287">0x01 - Sessão repetida</span><span class="sxs-lookup"><span data-stu-id="083f5-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="083f5-288">0x02 - Uma chamada feita por um agente em nome de um Grupo de Resposta</span><span class="sxs-lookup"><span data-stu-id="083f5-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="083f5-289"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="083f5-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="083f5-290">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="083f5-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="083f5-291">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="083f5-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

