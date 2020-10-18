---
title: 'Lync Server 2013: tabela de sessão'
description: 'Lync Server 2013: tabela de sessão.'
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
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576447"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="255b8-103">Tabela de sessão no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="255b8-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="255b8-104">_**Última modificação do tópico:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="255b8-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="255b8-105">Cada registro representa uma sessão que envolve áudio ou áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="255b8-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="255b8-106">Ele contém informações gerais sobre a sessão.</span><span class="sxs-lookup"><span data-stu-id="255b8-106">It contains overall information about the session.</span></span> <span data-ttu-id="255b8-107">Uma sessão é definida como uma caixa de diálogo de áudio ou protocolo SIP entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="255b8-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="255b8-108"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="255b8-109"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="255b8-110"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="255b8-111"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="255b8-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-113">datetime</span><span class="sxs-lookup"><span data-stu-id="255b8-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="255b8-114">Primário</span><span class="sxs-lookup"><span data-stu-id="255b8-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="255b8-115">Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de diálogo no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-117">int</span><span class="sxs-lookup"><span data-stu-id="255b8-117">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-118">Primário</span><span class="sxs-lookup"><span data-stu-id="255b8-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="255b8-119">Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de diálogo no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-121">int</span><span class="sxs-lookup"><span data-stu-id="255b8-121">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-122">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-123">Chave de conferência.</span><span class="sxs-lookup"><span data-stu-id="255b8-123">Conference key.</span></span> <span data-ttu-id="255b8-124">Referenciado da <a href="lync-server-2013-conference-table.md">tabela de conferência no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-126">int</span><span class="sxs-lookup"><span data-stu-id="255b8-126">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-127">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-128">Chave de correlação.</span><span class="sxs-lookup"><span data-stu-id="255b8-128">Correlation key.</span></span> <span data-ttu-id="255b8-129">Referenciado da <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-130"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-131">bits</span><span class="sxs-lookup"><span data-stu-id="255b8-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="255b8-132">Categoria da caixa de diálogo; 0 é o servidor do Lync Server para o trecho do servidor de mediação; 1 é o servidor de mediação para o segmento de gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="255b8-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-134">bits</span><span class="sxs-lookup"><span data-stu-id="255b8-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="255b8-135">Sinalizador que indica se a chamada foi ignorada ou não.</span><span class="sxs-lookup"><span data-stu-id="255b8-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-136"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-137">int</span><span class="sxs-lookup"><span data-stu-id="255b8-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="255b8-138">Caso presente, este campo indica o motivo de uma chamada não ter sido ignorada, mesmo se as IDs de bypass correspondessem.</span><span class="sxs-lookup"><span data-stu-id="255b8-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="255b8-139">Para o Lync Server, apenas um valor é definido.</span><span class="sxs-lookup"><span data-stu-id="255b8-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="255b8-140">0x0001 - ID de desvio desconhecida ao adaptador de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="255b8-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-142">datetime</span><span class="sxs-lookup"><span data-stu-id="255b8-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="255b8-143">Hora do início da chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-145">datetime</span><span class="sxs-lookup"><span data-stu-id="255b8-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="255b8-146">Hora da finalização da chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-148">int</span><span class="sxs-lookup"><span data-stu-id="255b8-148">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-149">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-150">O pool do chamador.</span><span class="sxs-lookup"><span data-stu-id="255b8-150">The pool of the caller.</span></span> <span data-ttu-id="255b8-151">Referenciado da <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-153">int</span><span class="sxs-lookup"><span data-stu-id="255b8-153">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-154">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-155">O pool do receptor de chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-155">The pool of the call receiver.</span></span> <span data-ttu-id="255b8-156">Referenciado da <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-158">int</span><span class="sxs-lookup"><span data-stu-id="255b8-158">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-159">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-160">O URI do SIP na PAI (identidade do SIP p-Asserted) do ponto de extremidade de recebimento.</span><span class="sxs-lookup"><span data-stu-id="255b8-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="255b8-161">Referenciado da <a href="lync-server-2013-user-table.md">tabela user no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-163">int</span><span class="sxs-lookup"><span data-stu-id="255b8-163">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-164">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-165">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="255b8-165">Caller’s URI.</span></span> <span data-ttu-id="255b8-166">Referenciado da <a href="lync-server-2013-user-table.md">tabela user no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-168">int</span><span class="sxs-lookup"><span data-stu-id="255b8-168">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-169">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-170">Ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="255b8-170">Caller’s endpoint.</span></span> <span data-ttu-id="255b8-171">Referenciado da <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-173">bits</span><span class="sxs-lookup"><span data-stu-id="255b8-173">bit</span></span></p></td>
<td><p><span data-ttu-id="255b8-174">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-175">Agente do usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="255b8-175">Caller’s user agent.</span></span> <span data-ttu-id="255b8-176">Referenciado da <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="255b8-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-178">smallint</span><span class="sxs-lookup"><span data-stu-id="255b8-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="255b8-179">A prioridade desta chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-181">bits</span><span class="sxs-lookup"><span data-stu-id="255b8-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="255b8-182">Esta coluna foi preterida e não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="255b8-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="255b8-183">Em vez disso, essas informações são relatadas em uma base de linha por mídia.</span><span class="sxs-lookup"><span data-stu-id="255b8-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="255b8-184">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídia no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="255b8-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-186">int</span><span class="sxs-lookup"><span data-stu-id="255b8-186">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-187">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-188">P-Asserted-Identity do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="255b8-189">O P-Asserted-Identity (PAI) é usado para transmitir a identidade real do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-191">int</span><span class="sxs-lookup"><span data-stu-id="255b8-191">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-192">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-193">Ponto de extremidade que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="255b8-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-195">int</span><span class="sxs-lookup"><span data-stu-id="255b8-195">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-196">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-197">O agente do usuário empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="255b8-198">Os agentes de usuário representam o dispositivo de ponto de extremidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="255b8-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="255b8-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="255b8-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="255b8-200">int</span><span class="sxs-lookup"><span data-stu-id="255b8-200">int</span></span></p></td>
<td><p><span data-ttu-id="255b8-201">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="255b8-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="255b8-202">URI do SIP do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="255b8-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

