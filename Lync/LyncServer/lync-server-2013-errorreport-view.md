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
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="703ed-102">Exibição ErrorReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="703ed-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="703ed-103">_**Tópico da última modificação:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="703ed-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="703ed-104">A exibição ErrorReport armazena informações sobre erros relatados.</span><span class="sxs-lookup"><span data-stu-id="703ed-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="703ed-105">Cada registro é uma ocorrência de um erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-105">Each record is one error occurrence.</span></span> <span data-ttu-id="703ed-106">Os erros são capturados pelo agente CDR executado no servidor front-end ou enviados do cliente.</span><span class="sxs-lookup"><span data-stu-id="703ed-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="703ed-107">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="703ed-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="703ed-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="703ed-108">Column</span></span></th>
<th><span data-ttu-id="703ed-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="703ed-109">Data Type</span></span></th>
<th><span data-ttu-id="703ed-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="703ed-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="703ed-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-112">datetime</span><span class="sxs-lookup"><span data-stu-id="703ed-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="703ed-113">Ocorreu um erro de hora.</span><span class="sxs-lookup"><span data-stu-id="703ed-113">Time of error occurred.</span></span> <span data-ttu-id="703ed-114">Usado em conjunto com ErrorReportSeq para identificar um erro exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="703ed-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-116">int</span><span class="sxs-lookup"><span data-stu-id="703ed-116">int</span></span></p></td>
<td><p><span data-ttu-id="703ed-117">Número de identificação para identificar o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-117">ID number to identify the error.</span></span> <span data-ttu-id="703ed-118">Usado em conjunto com ErrorTime para identificar um erro com exclusividade.</span><span class="sxs-lookup"><span data-stu-id="703ed-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-120">int</span><span class="sxs-lookup"><span data-stu-id="703ed-120">int</span></span></p></td>
<td><p><span data-ttu-id="703ed-121">ID de diagnóstico do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="703ed-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="703ed-124">URL do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-127">Tipo de URI do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="703ed-128">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="703ed-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-131">Locatário do usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="703ed-132">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="703ed-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="703ed-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="703ed-135">URI do usuário que foi o destino do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-138">Tipo de URI do usuário que direciona o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="703ed-139">Consulte a tabela UriTypes para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="703ed-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-140"><strong>Tolocatário</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-142">Locatário do usuário que direciona o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="703ed-143">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="703ed-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="703ed-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="703ed-146">URL da conferência que foi o alvo do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-149">Tipo de URI da conferência que foi o destino do relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="703ed-150">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="703ed-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-151"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-152">datetime</span><span class="sxs-lookup"><span data-stu-id="703ed-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="703ed-153">Tempo de solicitação de sessão que originou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="703ed-154">Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="703ed-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="703ed-155">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="703ed-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-157">int</span><span class="sxs-lookup"><span data-stu-id="703ed-157">int</span></span></p></td>
<td><p><span data-ttu-id="703ed-158">Número de identificação para identificar a solicitação de sessão que originou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="703ed-159">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="703ed-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="703ed-160">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="703ed-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-161"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-162">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="703ed-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="703ed-163">ID da caixa de diálogo SIP da sessão que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="703ed-164">O formato é:</span><span class="sxs-lookup"><span data-stu-id="703ed-164">The format is:</span></span></p>
<p><span data-ttu-id="703ed-165">caixa de diálogo; de-marca; até-marca</span><span class="sxs-lookup"><span data-stu-id="703ed-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="703ed-166">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="703ed-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="703ed-167">Cast (castid (externalId como varbinary (max)) como varchar (max))</span><span class="sxs-lookup"><span data-stu-id="703ed-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-170">Versão do cliente usada pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-172">int</span><span class="sxs-lookup"><span data-stu-id="703ed-172">int</span></span></p></td>
<td><p><span data-ttu-id="703ed-173">Cliente usado pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="703ed-174">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="703ed-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="703ed-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="703ed-177">Nome da categoria do cliente usado pelo usuário que originou o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-178"><strong>Origem</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-180">Nome do servidor que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="703ed-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-181"><strong>Aplicativo</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-183">Nome do aplicativo que originou o erro (se o relatório foi enviado a partir de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="703ed-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-185">int</span><span class="sxs-lookup"><span data-stu-id="703ed-185">int</span></span></p></td>
<td><p><span data-ttu-id="703ed-186">Código de resposta SIP para a sessão da mensagem SIP que contém o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="703ed-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="703ed-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="703ed-189">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="703ed-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="703ed-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="703ed-192">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="703ed-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="703ed-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="703ed-195">Tipo de sessão.</span><span class="sxs-lookup"><span data-stu-id="703ed-195">Type of session.</span></span> <span data-ttu-id="703ed-196">Consulte a <a href="lync-server-2013-calltype-table.md">tabela CallType no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="703ed-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-197"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-198">identificador</span><span class="sxs-lookup"><span data-stu-id="703ed-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="703ed-199">Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="703ed-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-200"><strong>Setuptime</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-201">int</span><span class="sxs-lookup"><span data-stu-id="703ed-201">int</span></span></p></td>
<td><p><span data-ttu-id="703ed-202">Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="703ed-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-204">bit</span><span class="sxs-lookup"><span data-stu-id="703ed-204">bit</span></span></p></td>
<td><p><span data-ttu-id="703ed-205">Indica se o relatório de erros foi capturado pelo agente CDR em execução no servidor front-end ou enviado pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="703ed-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-206"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-207">smallint</span><span class="sxs-lookup"><span data-stu-id="703ed-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="703ed-208">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="703ed-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="703ed-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="703ed-211">Informações adicionais sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="703ed-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="703ed-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="703ed-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="703ed-214">Nome de domínio totalmente qualificado do servidor front-end que enviou o relatório.</span><span class="sxs-lookup"><span data-stu-id="703ed-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="703ed-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="703ed-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="703ed-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="703ed-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="703ed-217">Nome de domínio totalmente qualificado do pool que contém o servidor front-end que enviou o relatório.</span><span class="sxs-lookup"><span data-stu-id="703ed-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

