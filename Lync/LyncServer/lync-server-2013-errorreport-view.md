---
title: 'Lync Server 2013: modo de exibição ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8792154c88c74049a785ddfb9ebbca55a52bc26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514448"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="64b4b-102">Exibição ErrorReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64b4b-102">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64b4b-103">_**Última modificação do tópico:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="64b4b-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="64b4b-104">A exibição ErrorReport armazena informações sobre erros relatados.</span><span class="sxs-lookup"><span data-stu-id="64b4b-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="64b4b-105">Cada registro é uma ocorrência de erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-105">Each record is one error occurrence.</span></span> <span data-ttu-id="64b4b-106">Os erros são capturados pelo agente CDR em execução no servidor front-end ou enviados do cliente.</span><span class="sxs-lookup"><span data-stu-id="64b4b-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="64b4b-107">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64b4b-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64b4b-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="64b4b-108">Column</span></span></th>
<th><span data-ttu-id="64b4b-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="64b4b-109">Data Type</span></span></th>
<th><span data-ttu-id="64b4b-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="64b4b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="64b4b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="64b4b-p102">Hora do erro. Usada com o ErrorReportSeq para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-116">int</span><span class="sxs-lookup"><span data-stu-id="64b4b-116">int</span></span></p></td>
<td><p><span data-ttu-id="64b4b-p103">Um número de ID para identificar o erro. Usado com ErrorTime para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-120">int</span><span class="sxs-lookup"><span data-stu-id="64b4b-120">int</span></span></p></td>
<td><p><span data-ttu-id="64b4b-121">ID de diagnóstico do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="64b4b-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-124">URI do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-127">Tipo de URI do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="64b4b-128">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64b4b-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-131">Locatário do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="64b4b-132">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64b4b-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="64b4b-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-135">URI do usuário que foi o destino do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="64b4b-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-138">Tipo de URI do usuário que é o destino do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="64b4b-139">Consulte o UriTypes Table para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64b4b-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-140"><strong>Tolocatário</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-142">Locatário do usuário que é o alvo do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="64b4b-143">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64b4b-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-144"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="64b4b-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-146">URI da conferência que foi o destino do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="64b4b-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-149">Tipo de URI da conferência que foi o destino do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="64b4b-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="64b4b-150">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64b4b-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-151"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-152">datetime</span><span class="sxs-lookup"><span data-stu-id="64b4b-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="64b4b-153">Hora da solicitação de sessão que originou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="64b4b-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="64b4b-154">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="64b4b-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="64b4b-155">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64b4b-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-157">int</span><span class="sxs-lookup"><span data-stu-id="64b4b-157">int</span></span></p></td>
<td><p><span data-ttu-id="64b4b-158">Número de identificação para identificar a solicitação de sessão que originou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="64b4b-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="64b4b-159">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="64b4b-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="64b4b-160">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64b4b-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-162">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="64b4b-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-163">ID da caixa de diálogo SIP da sessão que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="64b4b-164">O formato é:</span><span class="sxs-lookup"><span data-stu-id="64b4b-164">The format is:</span></span></p>
<p><span data-ttu-id="64b4b-165">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="64b4b-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="64b4b-166">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="64b4b-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="64b4b-167">Cast (Cast (externalId as varbinary (max)) como varchar (max))</span><span class="sxs-lookup"><span data-stu-id="64b4b-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-170">Versão do cliente usado pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-172">int</span><span class="sxs-lookup"><span data-stu-id="64b4b-172">int</span></span></p></td>
<td><p><span data-ttu-id="64b4b-173">Cliente usado pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="64b4b-174">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="64b4b-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="64b4b-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-177">Nome da categoria do cliente usado pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-178"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-180">Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="64b4b-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-181"><strong>Aplicação</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-183">Nome de um aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="64b4b-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-185">int</span><span class="sxs-lookup"><span data-stu-id="64b4b-185">int</span></span></p></td>
<td><p><span data-ttu-id="64b4b-186">Código de resposta SIP para a sessão da mensagem SIP que contém o relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="64b4b-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-189">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="64b4b-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="64b4b-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-192">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="64b4b-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="64b4b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-195">Tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="64b4b-195">Type of session.</span></span> <span data-ttu-id="64b4b-196">Consulte a <a href="lync-server-2013-calltype-table.md">tabela CallType no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64b4b-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-197"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-198">identificador</span><span class="sxs-lookup"><span data-stu-id="64b4b-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="64b4b-199">Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="64b4b-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-200"><strong>Setuptime</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-201">int</span><span class="sxs-lookup"><span data-stu-id="64b4b-201">int</span></span></p></td>
<td><p><span data-ttu-id="64b4b-202">Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="64b4b-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-204">bits</span><span class="sxs-lookup"><span data-stu-id="64b4b-204">bit</span></span></p></td>
<td><p><span data-ttu-id="64b4b-205">Indica se o relatório de erro foi capturado pelo agente de CDR em execução no servidor front-end ou enviado pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="64b4b-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-206"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-207">smallint</span><span class="sxs-lookup"><span data-stu-id="64b4b-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="64b4b-208">Reserved for future use.</span><span class="sxs-lookup"><span data-stu-id="64b4b-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="64b4b-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="64b4b-211">Informações adicionais sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="64b4b-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64b4b-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="64b4b-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="64b4b-214">Nome de domínio totalmente qualificado do servidor front-end que enviou o relatório.</span><span class="sxs-lookup"><span data-stu-id="64b4b-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64b4b-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="64b4b-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="64b4b-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="64b4b-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="64b4b-217">Nome de domínio totalmente qualificado do pool que contém o servidor front-end que enviou o relatório.</span><span class="sxs-lookup"><span data-stu-id="64b4b-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

