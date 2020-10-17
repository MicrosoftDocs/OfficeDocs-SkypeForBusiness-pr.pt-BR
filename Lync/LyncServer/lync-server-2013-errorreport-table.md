---
title: 'Lync Server 2013: tabela ErrorReport'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 321a975e9461e39de882d9620cdded9d2554e8ed
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533134"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="40b6f-102">Tabela ErrorReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40b6f-102">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40b6f-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="40b6f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="40b6f-104">A tabela ErrorReport armazena informações sobre erros que ocorreram.</span><span class="sxs-lookup"><span data-stu-id="40b6f-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="40b6f-105">Cada registro é uma ocorrência de erro.</span><span class="sxs-lookup"><span data-stu-id="40b6f-105">Each record is one error occurrence.</span></span> <span data-ttu-id="40b6f-106">Os erros são capturados pelo agente CDR em execução no servidor front-end ou enviados do cliente.</span><span class="sxs-lookup"><span data-stu-id="40b6f-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40b6f-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="40b6f-107">Column</span></span></th>
<th><span data-ttu-id="40b6f-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="40b6f-108">Data Type</span></span></th>
<th><span data-ttu-id="40b6f-109">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="40b6f-109">Key/Index</span></span></th>
<th><span data-ttu-id="40b6f-110">Detalhes</span><span class="sxs-lookup"><span data-stu-id="40b6f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="40b6f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="40b6f-113">Primário</span><span class="sxs-lookup"><span data-stu-id="40b6f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="40b6f-114">Data e hora em que o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="40b6f-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-116">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-116">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-117">Primário</span><span class="sxs-lookup"><span data-stu-id="40b6f-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="40b6f-118">Número de identificação para identificar o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="40b6f-118">ID number to identify the error report.</span></span> <span data-ttu-id="40b6f-119">Usado em conjunto com <strong>ErrorTime</strong> para identificar exclusivamente um relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="40b6f-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-120"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-121">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-121">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-122">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-123">ID exclusiva do tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="40b6f-123">Unique ID of the error type.</span></span> <span data-ttu-id="40b6f-124">Consulte a <a href="lync-server-2013-errordef-table.md">tabela ErrorDef no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-126">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-126">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-127">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-128">Usuário que originou a solicitação que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="40b6f-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="40b6f-129">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-130"><strong>Touserid</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-131">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-131">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-132">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-133">O usuário de destino para a solicitação que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="40b6f-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="40b6f-134">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-136">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-136">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-137">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-138">URI de conferência relacionado ao erro.</span><span class="sxs-lookup"><span data-stu-id="40b6f-138">Conference URI related to the error.</span></span> <span data-ttu-id="40b6f-139">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="40b6f-140">Normalmente, se ConferenceUriId não for nulo, FromUserId ou touserid será NULL.</span><span class="sxs-lookup"><span data-stu-id="40b6f-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-141"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-142">datetime</span><span class="sxs-lookup"><span data-stu-id="40b6f-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="40b6f-143">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-144">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="40b6f-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="40b6f-145">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-147">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-147">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-148">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-149">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="40b6f-149">ID number to identify the session.</span></span> <span data-ttu-id="40b6f-150">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="40b6f-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="40b6f-151">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-153">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-153">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-154">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-155">Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="40b6f-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="40b6f-156">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="40b6f-157">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40b6f-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-159">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-159">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-160">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-161">Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="40b6f-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="40b6f-162">Consulte a <a href="lync-server-2013-application-table.md">tabela de aplicativos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="40b6f-163">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40b6f-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-165">imagem</span><span class="sxs-lookup"><span data-stu-id="40b6f-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="40b6f-166">Mais informações sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="40b6f-166">More information about the error.</span></span></p>
<p><span data-ttu-id="40b6f-167">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="40b6f-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-169">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-169">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-170">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-171">A versão do cliente do ponto de extremidade que envia o relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="40b6f-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="40b6f-172">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="40b6f-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-174">bits</span><span class="sxs-lookup"><span data-stu-id="40b6f-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40b6f-175">É o relatório de erros capturado pelo agente de CDR em execução no servidor front-end ou enviado pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="40b6f-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-176"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-177">smallint</span><span class="sxs-lookup"><span data-stu-id="40b6f-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40b6f-178">Reserved for future use.</span><span class="sxs-lookup"><span data-stu-id="40b6f-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-179"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-180">Identificador</span><span class="sxs-lookup"><span data-stu-id="40b6f-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40b6f-181">Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="40b6f-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="40b6f-182">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40b6f-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-184">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="40b6f-185">Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="40b6f-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="40b6f-186">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40b6f-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40b6f-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-188">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-188">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-189">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-190">Representa o nome de domínio totalmente qualificado do servidor que gerou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="40b6f-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b6f-191"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="40b6f-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="40b6f-192">int</span><span class="sxs-lookup"><span data-stu-id="40b6f-192">int</span></span></p></td>
<td><p><span data-ttu-id="40b6f-193">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="40b6f-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40b6f-194">Representa o nome de domínio totalmente qualificado do pool onde o relatório de erro foi gerado.</span><span class="sxs-lookup"><span data-stu-id="40b6f-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

