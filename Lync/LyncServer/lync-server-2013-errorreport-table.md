---
title: 'Lync Server 2013: tabela ErrorReport'
description: 'Lync Server 2013: tabela ErrorReport.'
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572007"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="18b2d-103">Tabela ErrorReport no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18b2d-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18b2d-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="18b2d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="18b2d-105">A tabela ErrorReport armazena informações sobre erros que ocorreram.</span><span class="sxs-lookup"><span data-stu-id="18b2d-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="18b2d-106">Cada registro é uma ocorrência de erro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-106">Each record is one error occurrence.</span></span> <span data-ttu-id="18b2d-107">Os erros são capturados pelo agente CDR em execução no servidor front-end ou enviados do cliente.</span><span class="sxs-lookup"><span data-stu-id="18b2d-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18b2d-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="18b2d-108">Column</span></span></th>
<th><span data-ttu-id="18b2d-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="18b2d-109">Data Type</span></span></th>
<th><span data-ttu-id="18b2d-110">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="18b2d-110">Key/Index</span></span></th>
<th><span data-ttu-id="18b2d-111">Detalhes</span><span class="sxs-lookup"><span data-stu-id="18b2d-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="18b2d-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="18b2d-114">Primário</span><span class="sxs-lookup"><span data-stu-id="18b2d-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="18b2d-115">Data e hora em que o erro ocorreu.</span><span class="sxs-lookup"><span data-stu-id="18b2d-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-117">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-117">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-118">Primário</span><span class="sxs-lookup"><span data-stu-id="18b2d-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="18b2d-119">Número de identificação para identificar o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="18b2d-119">ID number to identify the error report.</span></span> <span data-ttu-id="18b2d-120">Usado em conjunto com <strong>ErrorTime</strong> para identificar exclusivamente um relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-121"><strong>ErrorID</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-122">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-122">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-123">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-124">ID exclusiva do tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-124">Unique ID of the error type.</span></span> <span data-ttu-id="18b2d-125">Consulte a <a href="lync-server-2013-errordef-table.md">tabela ErrorDef no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-127">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-127">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-128">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-129">Usuário que originou a solicitação que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="18b2d-130">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-131"><strong>Touserid</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-132">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-132">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-133">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-134">O usuário de destino para a solicitação que causou o erro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="18b2d-135">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-137">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-137">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-138">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-139">URI de conferência relacionado ao erro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-139">Conference URI related to the error.</span></span> <span data-ttu-id="18b2d-140">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="18b2d-141">Normalmente, se ConferenceUriId não for nulo, FromUserId ou touserid será NULL.</span><span class="sxs-lookup"><span data-stu-id="18b2d-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-142"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-143">datetime</span><span class="sxs-lookup"><span data-stu-id="18b2d-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="18b2d-144">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-145">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="18b2d-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="18b2d-146">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-147"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-148">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-148">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-149">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-150">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="18b2d-150">ID number to identify the session.</span></span> <span data-ttu-id="18b2d-151">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="18b2d-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="18b2d-152">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-154">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-154">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-155">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-156">Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="18b2d-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="18b2d-157">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="18b2d-158">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18b2d-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-160">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-160">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-161">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-162">Servidor que enviou o relatório de erro (se o relatório estiver sendo enviado de um componente do servidor).</span><span class="sxs-lookup"><span data-stu-id="18b2d-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="18b2d-163">Consulte a <a href="lync-server-2013-application-table.md">tabela de aplicativos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="18b2d-164">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18b2d-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-166">imagem</span><span class="sxs-lookup"><span data-stu-id="18b2d-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="18b2d-167">Mais informações sobre o erro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-167">More information about the error.</span></span></p>
<p><span data-ttu-id="18b2d-168">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="18b2d-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-170">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-170">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-171">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-172">A versão do cliente do ponto de extremidade que envia o relatório de erro.</span><span class="sxs-lookup"><span data-stu-id="18b2d-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="18b2d-173">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="18b2d-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-175">bits</span><span class="sxs-lookup"><span data-stu-id="18b2d-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="18b2d-176">É o relatório de erros capturado pelo agente de CDR em execução no servidor front-end ou enviado pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="18b2d-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-177"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-178">smallint</span><span class="sxs-lookup"><span data-stu-id="18b2d-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="18b2d-179">Reserved for future use.</span><span class="sxs-lookup"><span data-stu-id="18b2d-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-180"><strong>Telemetria</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-181">Identificador</span><span class="sxs-lookup"><span data-stu-id="18b2d-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="18b2d-182">Identificador exclusivo correlacionando as informações da hora de ingresso dos diferentes componentes envolvidos em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="18b2d-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="18b2d-183">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18b2d-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-184"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-185">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="18b2d-186">Tempo (em milissegundos) necessário para que um componentes específico ingresse em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="18b2d-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="18b2d-187">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18b2d-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18b2d-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-189">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-189">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-190">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-191">Representa o nome de domínio totalmente qualificado do servidor que gerou o relatório de erros.</span><span class="sxs-lookup"><span data-stu-id="18b2d-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18b2d-192"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="18b2d-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="18b2d-193">int</span><span class="sxs-lookup"><span data-stu-id="18b2d-193">int</span></span></p></td>
<td><p><span data-ttu-id="18b2d-194">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="18b2d-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="18b2d-195">Representa o nome de domínio totalmente qualificado do pool onde o relatório de erro foi gerado.</span><span class="sxs-lookup"><span data-stu-id="18b2d-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

