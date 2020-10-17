---
title: 'Lync Server 2013: tabela de sessão'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d74d2732d2f8ad293450f4945eef00bccb9a572d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510078"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="b6022-102">Tabela de sessão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6022-102">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6022-103">_**Última modificação do tópico:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="b6022-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="b6022-104">Cada registro representa uma sessão que envolve áudio ou áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="b6022-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="b6022-105">Ele contém informações gerais sobre a sessão.</span><span class="sxs-lookup"><span data-stu-id="b6022-105">It contains overall information about the session.</span></span> <span data-ttu-id="b6022-106">Uma sessão é definida como uma caixa de diálogo de áudio ou protocolo SIP entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b6022-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b6022-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b6022-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b6022-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b6022-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b6022-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b6022-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b6022-113">Primário</span><span class="sxs-lookup"><span data-stu-id="b6022-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6022-114">Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de diálogo no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-116">int</span><span class="sxs-lookup"><span data-stu-id="b6022-116">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-117">Primário</span><span class="sxs-lookup"><span data-stu-id="b6022-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b6022-118">Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de diálogo no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-120">int</span><span class="sxs-lookup"><span data-stu-id="b6022-120">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-121">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-122">Chave de conferência.</span><span class="sxs-lookup"><span data-stu-id="b6022-122">Conference key.</span></span> <span data-ttu-id="b6022-123">Referenciado da <a href="lync-server-2013-conference-table.md">tabela de conferência no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-125">int</span><span class="sxs-lookup"><span data-stu-id="b6022-125">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-126">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-127">Chave de correlação.</span><span class="sxs-lookup"><span data-stu-id="b6022-127">Correlation key.</span></span> <span data-ttu-id="b6022-128">Referenciado da <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-130">bits</span><span class="sxs-lookup"><span data-stu-id="b6022-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6022-131">Categoria da caixa de diálogo; 0 é o servidor do Lync Server para o trecho do servidor de mediação; 1 é o servidor de mediação para o segmento de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="b6022-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-133">bits</span><span class="sxs-lookup"><span data-stu-id="b6022-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6022-134">Sinalizador que indica se a chamada foi ignorada ou não.</span><span class="sxs-lookup"><span data-stu-id="b6022-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-136">int</span><span class="sxs-lookup"><span data-stu-id="b6022-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6022-137">Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem.</span><span class="sxs-lookup"><span data-stu-id="b6022-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b6022-138">Para o Lync Server, apenas um valor é definido.</span><span class="sxs-lookup"><span data-stu-id="b6022-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="b6022-139">0x0001 - ID de desvio desconhecida ao adaptador de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="b6022-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-141">datetime</span><span class="sxs-lookup"><span data-stu-id="b6022-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6022-142">Hora do início da chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-144">datetime</span><span class="sxs-lookup"><span data-stu-id="b6022-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b6022-145">Hora da finalização da chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-147">int</span><span class="sxs-lookup"><span data-stu-id="b6022-147">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-148">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-149">O pool do chamador.</span><span class="sxs-lookup"><span data-stu-id="b6022-149">The pool of the caller.</span></span> <span data-ttu-id="b6022-150">Referenciado da <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-152">int</span><span class="sxs-lookup"><span data-stu-id="b6022-152">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-153">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-154">O pool do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-154">The pool of the call receiver.</span></span> <span data-ttu-id="b6022-155">Referenciado da <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-157">int</span><span class="sxs-lookup"><span data-stu-id="b6022-157">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-158">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-159">O URI do SIP na PAI (identidade do SIP p-Asserted) do ponto de extremidade de recebimento.</span><span class="sxs-lookup"><span data-stu-id="b6022-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="b6022-160">Referenciado da <a href="lync-server-2013-user-table.md">tabela user no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-162">int</span><span class="sxs-lookup"><span data-stu-id="b6022-162">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-163">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-164">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="b6022-164">Caller’s URI.</span></span> <span data-ttu-id="b6022-165">Referenciado da <a href="lync-server-2013-user-table.md">tabela user no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-167">int</span><span class="sxs-lookup"><span data-stu-id="b6022-167">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-168">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-169">Ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="b6022-169">Caller’s endpoint.</span></span> <span data-ttu-id="b6022-170">Referenciado da <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-172">bits</span><span class="sxs-lookup"><span data-stu-id="b6022-172">bit</span></span></p></td>
<td><p><span data-ttu-id="b6022-173">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-174">Agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="b6022-174">Caller’s user agent.</span></span> <span data-ttu-id="b6022-175">Referenciado da <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="b6022-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-177">smallint</span><span class="sxs-lookup"><span data-stu-id="b6022-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6022-178">A prioridade desta chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-180">bits</span><span class="sxs-lookup"><span data-stu-id="b6022-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b6022-181">Esta coluna foi preterida e não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6022-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b6022-182">Em vez disso, essas informações são relatadas em uma base de linha por mídia.</span><span class="sxs-lookup"><span data-stu-id="b6022-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="b6022-183">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b6022-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-185">int</span><span class="sxs-lookup"><span data-stu-id="b6022-185">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-186">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-187">P-Asserted-Identity do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="b6022-188">O P-Asserted-Identity (PAI) é usado para transmitir a identidade real do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-190">int</span><span class="sxs-lookup"><span data-stu-id="b6022-190">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-191">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-192">Ponto de extremidade que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b6022-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-194">int</span><span class="sxs-lookup"><span data-stu-id="b6022-194">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-195">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-196">O agente do usuário empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="b6022-197">Os agentes de usuário representam o dispositivo de ponto de extremidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="b6022-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b6022-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="b6022-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b6022-199">int</span><span class="sxs-lookup"><span data-stu-id="b6022-199">int</span></span></p></td>
<td><p><span data-ttu-id="b6022-200">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="b6022-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b6022-201">URI do SIP do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="b6022-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

