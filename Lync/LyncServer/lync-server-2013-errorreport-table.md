---
title: 'Lync Server 2013: Tabela ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="b5cb0-102">Tabela ErrorReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5cb0-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5cb0-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b5cb0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b5cb0-104">A tabela ErrorReport armazena informações sobre erros ocorridos.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="b5cb0-105">Cada registro é uma ocorrência de um erro.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-105">Each record is one error occurrence.</span></span> <span data-ttu-id="b5cb0-106">Os erros são capturados pelo agente CDR executado no servidor front-end ou enviados do cliente.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5cb0-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="b5cb0-107">Column</span></span></th>
<th><span data-ttu-id="b5cb0-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b5cb0-108">Data Type</span></span></th>
<th><span data-ttu-id="b5cb0-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="b5cb0-109">Key/Index</span></span></th>
<th><span data-ttu-id="b5cb0-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b5cb0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b5cb0-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-113">Primária</span><span class="sxs-lookup"><span data-stu-id="b5cb0-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-114">Data e hora em que o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-116">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-116">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-117">Primária</span><span class="sxs-lookup"><span data-stu-id="b5cb0-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-118">Número de identificação para identificar o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-118">ID number to identify the error report.</span></span> <span data-ttu-id="b5cb0-119">Usado em conjunto com <strong>ErrorTime</strong> para identificar com exclusividade um relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-120"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-121">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-121">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-122">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-123">ID exclusiva do tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-123">Unique ID of the error type.</span></span> <span data-ttu-id="b5cb0-124">Consulte a <a href="lync-server-2013-errordef-table.md">tabela ErrorDef no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-126">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-126">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-127">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-128">Usuário que originou a solicitação que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="b5cb0-129">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-130"><strong>Parauserid</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-131">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-131">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-132">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-133">Usuário de destino para a solicitação que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="b5cb0-134">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-136">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-136">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-137">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-138">URL de conferência relacionada ao erro.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-138">Conference URI related to the error.</span></span> <span data-ttu-id="b5cb0-139">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b5cb0-140">Geralmente, se ConferenceUriId não for nulo, o FromUserId ou o parauserid será nulo.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-141"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-142">datetime</span><span class="sxs-lookup"><span data-stu-id="b5cb0-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-143">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-144">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b5cb0-145">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-147">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-147">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-148">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-149">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-149">ID number to identify the session.</span></span> <span data-ttu-id="b5cb0-150">Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b5cb0-151">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-152"><strong>SourceID</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-153">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-153">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-154">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-155">Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="b5cb0-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="b5cb0-156">Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="b5cb0-157">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-159">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-159">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-160">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-161">Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente de servidor).</span><span class="sxs-lookup"><span data-stu-id="b5cb0-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="b5cb0-162">Consulte a <a href="lync-server-2013-application-table.md">tabela de aplicativos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="b5cb0-163">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-165">imagem</span><span class="sxs-lookup"><span data-stu-id="b5cb0-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b5cb0-166">Mais informações sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-166">More information about the error.</span></span></p>
<p><span data-ttu-id="b5cb0-167">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="b5cb0-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-169">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-169">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-170">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-171">A versão do cliente do ponto de extremidade que envia o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="b5cb0-172">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-174">bit</span><span class="sxs-lookup"><span data-stu-id="b5cb0-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b5cb0-175">É o relatório de erros capturado pelo agente CDR em execução no servidor front-end ou enviado pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-176"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-177">smallint</span><span class="sxs-lookup"><span data-stu-id="b5cb0-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b5cb0-178">Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-179"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-180">Identificador</span><span class="sxs-lookup"><span data-stu-id="b5cb0-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b5cb0-181">Identificador exclusivo que correlaciona as informações de tempo de junção para os diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="b5cb0-182">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-184">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b5cb0-185">Tempo (em milissegundos) necessário para um componente específico entrar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="b5cb0-186">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5cb0-187"><strong>ServerID</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-188">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-188">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-189">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-190">Representa o nome de domínio totalmente qualificado do servidor que gerou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5cb0-191"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="b5cb0-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="b5cb0-192">int</span><span class="sxs-lookup"><span data-stu-id="b5cb0-192">int</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-193">Exterior</span><span class="sxs-lookup"><span data-stu-id="b5cb0-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b5cb0-194">Representa o nome de domínio totalmente qualificado do pool onde o relatório de erro foi gerado.</span><span class="sxs-lookup"><span data-stu-id="b5cb0-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

