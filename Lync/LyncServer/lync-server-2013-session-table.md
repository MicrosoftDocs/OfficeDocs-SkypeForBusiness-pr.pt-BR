---
title: 'Lync Server 2013: Tabela Session'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="4a045-102">Tabela Session no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a045-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a045-103">_**Tópico da última modificação:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="4a045-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="4a045-104">Cada registro representa uma sessão que envolve áudio ou áudio e vídeo.</span><span class="sxs-lookup"><span data-stu-id="4a045-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="4a045-105">Ele contém informações gerais sobre a sessão.</span><span class="sxs-lookup"><span data-stu-id="4a045-105">It contains overall information about the session.</span></span> <span data-ttu-id="4a045-106">Uma sessão é definida como uma caixa de diálogo de protocolo de iniciação de sessão de áudio ou de vídeo (SIP) entre dois pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="4a045-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a045-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4a045-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4a045-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4a045-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a045-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4a045-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4a045-113">Primária</span><span class="sxs-lookup"><span data-stu-id="4a045-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4a045-114">Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de caixa de diálogo no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-116">int</span><span class="sxs-lookup"><span data-stu-id="4a045-116">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-117">Primária</span><span class="sxs-lookup"><span data-stu-id="4a045-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="4a045-118">Referenciado pela <a href="lync-server-2013-dialog-table.md">tabela de caixa de diálogo no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-120">int</span><span class="sxs-lookup"><span data-stu-id="4a045-120">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-122">Chave de conferência.</span><span class="sxs-lookup"><span data-stu-id="4a045-122">Conference key.</span></span> <span data-ttu-id="4a045-123">Referenciado na <a href="lync-server-2013-conference-table.md">tabela de conferências no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-125">int</span><span class="sxs-lookup"><span data-stu-id="4a045-125">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-126">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-127">Chave de correlação.</span><span class="sxs-lookup"><span data-stu-id="4a045-127">Correlation key.</span></span> <span data-ttu-id="4a045-128">Referenciado pela <a href="lync-server-2013-sessioncorrelation-table.md">tabela SessionCorrelation no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-130">bit</span><span class="sxs-lookup"><span data-stu-id="4a045-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4a045-131">Categoria da caixa de diálogo; 0 é o servidor do Lync para o segmento do servidor de mediação; 1 é o servidor de mediação para a perna do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="4a045-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-133">bit</span><span class="sxs-lookup"><span data-stu-id="4a045-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a045-134">Sinalizador que indica se a chamada foi ignorada ou não.</span><span class="sxs-lookup"><span data-stu-id="4a045-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-136">int</span><span class="sxs-lookup"><span data-stu-id="4a045-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a045-137">Esse campo, se presente, indicará por que uma chamada não foi ignorada mesmo se as IDs de bypass forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="4a045-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="4a045-138">Para o Lync Server, somente um valor é definido.</span><span class="sxs-lookup"><span data-stu-id="4a045-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="4a045-139">0x0001 – ID de bypass desconhecido para o adaptador de rede padrão.</span><span class="sxs-lookup"><span data-stu-id="4a045-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-140"><strong>StartTime </strong></span><span class="sxs-lookup"><span data-stu-id="4a045-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-141">datetime</span><span class="sxs-lookup"><span data-stu-id="4a045-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4a045-142">Hora de início da chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-144">datetime</span><span class="sxs-lookup"><span data-stu-id="4a045-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4a045-145">Hora de término da chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-147">int</span><span class="sxs-lookup"><span data-stu-id="4a045-147">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-148">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-149">O pool do chamador.</span><span class="sxs-lookup"><span data-stu-id="4a045-149">The pool of the caller.</span></span> <span data-ttu-id="4a045-150">Referenciado na <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-152">int</span><span class="sxs-lookup"><span data-stu-id="4a045-152">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-153">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-154">O pool do receptor da chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-154">The pool of the call receiver.</span></span> <span data-ttu-id="4a045-155">Referenciado na <a href="lync-server-2013-pool-table.md">tabela pool no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-157">int</span><span class="sxs-lookup"><span data-stu-id="4a045-157">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-158">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-159">O URI de SIP na identidade SIP p-declarated (PAI) do ponto de extremidade de recebimento.</span><span class="sxs-lookup"><span data-stu-id="4a045-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="4a045-160">Referenciado da <a href="lync-server-2013-user-table.md">tabela de usuário no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-162">int</span><span class="sxs-lookup"><span data-stu-id="4a045-162">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-163">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-164">URI do chamador.</span><span class="sxs-lookup"><span data-stu-id="4a045-164">Caller’s URI.</span></span> <span data-ttu-id="4a045-165">Referenciado da <a href="lync-server-2013-user-table.md">tabela de usuário no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-167">int</span><span class="sxs-lookup"><span data-stu-id="4a045-167">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-168">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-169">Ponto de extremidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="4a045-169">Caller’s endpoint.</span></span> <span data-ttu-id="4a045-170">Referenciado na <a href="lync-server-2013-endpoint-table.md">tabela de pontos de extremidade no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-172">bit</span><span class="sxs-lookup"><span data-stu-id="4a045-172">bit</span></span></p></td>
<td><p><span data-ttu-id="4a045-173">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-174">Agente de usuário do chamador.</span><span class="sxs-lookup"><span data-stu-id="4a045-174">Caller’s user agent.</span></span> <span data-ttu-id="4a045-175">Referenciado na <a href="lync-server-2013-useragent-table.md">tabela UserAgent no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="4a045-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-177">smallint</span><span class="sxs-lookup"><span data-stu-id="4a045-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a045-178">A prioridade desta chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-180">bit</span><span class="sxs-lookup"><span data-stu-id="4a045-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a045-181">Esta coluna foi preterida e não é usada no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a045-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4a045-182">Em vez disso, essas informações são relatadas em bases de linhas por mídia.</span><span class="sxs-lookup"><span data-stu-id="4a045-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="4a045-183">Consulte a <a href="lync-server-2013-medialine-table.md">tabela de mídias no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="4a045-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-185">int</span><span class="sxs-lookup"><span data-stu-id="4a045-185">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-186">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-187">P-declarado-identidade do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="4a045-188">A identidade de P-declarada (PAI) é usada para transmitir a verdadeira identidade do usuário que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-190">int</span><span class="sxs-lookup"><span data-stu-id="4a045-190">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-191">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-192">Ponto de extremidade que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a045-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-194">int</span><span class="sxs-lookup"><span data-stu-id="4a045-194">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-195">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-196">Agente de usuário empregado pelo usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="4a045-197">Os agentes de usuário representam o dispositivo de ponto de extremidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="4a045-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a045-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="4a045-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4a045-199">int</span><span class="sxs-lookup"><span data-stu-id="4a045-199">int</span></span></p></td>
<td><p><span data-ttu-id="4a045-200">Exterior</span><span class="sxs-lookup"><span data-stu-id="4a045-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a045-201">O URI SIP do usuário que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="4a045-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

