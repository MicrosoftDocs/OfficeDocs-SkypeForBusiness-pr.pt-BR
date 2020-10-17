---
title: 'Lync Server 2013: modo de exibição ErrorReport'
description: 'Lync Server 2013: modo de exibição ErrorReport.'
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
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572037"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="cc878-103">Exibição ErrorReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc878-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc878-104">_**Última modificação do tópico:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="cc878-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="cc878-105">A exibição ErrorReport armazena informações sobre erros relatados.</span><span class="sxs-lookup"><span data-stu-id="cc878-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="cc878-106">Cada registro é uma ocorrência de erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-106">Each record is one error occurrence.</span></span> <span data-ttu-id="cc878-107">Os erros são capturados pelo agente CDR em execução no servidor front-end ou enviados do cliente.</span><span class="sxs-lookup"><span data-stu-id="cc878-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="cc878-108">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc878-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc878-109">Coluna</span><span class="sxs-lookup"><span data-stu-id="cc878-109">Column</span></span></th>
<th><span data-ttu-id="cc878-110">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="cc878-110">Data Type</span></span></th>
<th><span data-ttu-id="cc878-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="cc878-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc878-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-113">datetime</span><span class="sxs-lookup"><span data-stu-id="cc878-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="cc878-p102">Hora do erro. Usada com o ErrorReportSeq para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-117">int</span><span class="sxs-lookup"><span data-stu-id="cc878-117">int</span></span></p></td>
<td><p><span data-ttu-id="cc878-p103">Um número de ID para identificar o erro. Usado com ErrorTime para identificar um erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-121">int</span><span class="sxs-lookup"><span data-stu-id="cc878-121">int</span></span></p></td>
<td><p><span data-ttu-id="cc878-122">ID de diagnóstico do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cc878-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cc878-125">URI do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-126"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-128">Tipo de URI do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="cc878-129">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc878-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-132">Locatário do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="cc878-133">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc878-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-134"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-135">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cc878-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cc878-136">URI do usuário que foi o destino do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="cc878-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-139">Tipo de URI do usuário que é o destino do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-139">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="cc878-140">Consulte o UriTypes Table para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc878-140">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-141"><strong>Tolocatário</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-143">Locatário do usuário que é o alvo do relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="cc878-144">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc878-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-145"><strong>Conferenceui</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cc878-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cc878-147">URI da conferência que foi o destino do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="cc878-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-150">Tipo de URI da conferência que foi o destino do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="cc878-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="cc878-151">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc878-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-152"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-153">datetime</span><span class="sxs-lookup"><span data-stu-id="cc878-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="cc878-154">Hora da solicitação de sessão que originou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="cc878-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="cc878-155">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cc878-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="cc878-156">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc878-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-157"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-158">int</span><span class="sxs-lookup"><span data-stu-id="cc878-158">int</span></span></p></td>
<td><p><span data-ttu-id="cc878-159">Número de identificação para identificar a solicitação de sessão que originou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="cc878-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="cc878-160">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="cc878-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="cc878-161">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc878-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-162"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-163">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="cc878-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="cc878-164">ID da caixa de diálogo SIP da sessão que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-164">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="cc878-165">O formato é:</span><span class="sxs-lookup"><span data-stu-id="cc878-165">The format is:</span></span></p>
<p><span data-ttu-id="cc878-166">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="cc878-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="cc878-167">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="cc878-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="cc878-168">Cast (Cast (externalId as varbinary (max)) como varchar (max))</span><span class="sxs-lookup"><span data-stu-id="cc878-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-169"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-170">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-171">Versão do cliente usado pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-173">int</span><span class="sxs-lookup"><span data-stu-id="cc878-173">int</span></span></p></td>
<td><p><span data-ttu-id="cc878-174">Cliente usado pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="cc878-175">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="cc878-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-177">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="cc878-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="cc878-178">Nome da categoria do cliente usado pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-179"><strong>Fonte</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-181">Nome do servidor que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="cc878-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-182"><strong>Aplicação</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-183">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-184">Nome de um aplicativo que originou o erro (se o relatório foi enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="cc878-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-186">int</span><span class="sxs-lookup"><span data-stu-id="cc878-186">int</span></span></p></td>
<td><p><span data-ttu-id="cc878-187">Código de resposta SIP para a sessão da mensagem SIP que contém o relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-189">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="cc878-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cc878-190">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="cc878-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-192">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="cc878-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cc878-193">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="cc878-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cc878-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cc878-196">Tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="cc878-196">Type of session.</span></span> <span data-ttu-id="cc878-197">Consulte a <a href="lync-server-2013-calltype-table.md">tabela CallType no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cc878-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-198"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-199">identificador</span><span class="sxs-lookup"><span data-stu-id="cc878-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="cc878-200">Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="cc878-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-201"><strong>Setuptime</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-202">int</span><span class="sxs-lookup"><span data-stu-id="cc878-202">int</span></span></p></td>
<td><p><span data-ttu-id="cc878-203">Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="cc878-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-205">bits</span><span class="sxs-lookup"><span data-stu-id="cc878-205">bit</span></span></p></td>
<td><p><span data-ttu-id="cc878-206">Indica se o relatório de erro foi capturado pelo agente de CDR em execução no servidor front-end ou enviado pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="cc878-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-207"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-208">smallint</span><span class="sxs-lookup"><span data-stu-id="cc878-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="cc878-209">Reserved for future use.</span><span class="sxs-lookup"><span data-stu-id="cc878-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-211">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="cc878-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cc878-212">Informações adicionais sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="cc878-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc878-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-214">nvarchar</span><span class="sxs-lookup"><span data-stu-id="cc878-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="cc878-215">Nome de domínio totalmente qualificado do servidor front-end que enviou o relatório.</span><span class="sxs-lookup"><span data-stu-id="cc878-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc878-216"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="cc878-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cc878-217">nvarchar</span><span class="sxs-lookup"><span data-stu-id="cc878-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="cc878-218">Nome de domínio totalmente qualificado do pool que contém o servidor front-end que enviou o relatório.</span><span class="sxs-lookup"><span data-stu-id="cc878-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

