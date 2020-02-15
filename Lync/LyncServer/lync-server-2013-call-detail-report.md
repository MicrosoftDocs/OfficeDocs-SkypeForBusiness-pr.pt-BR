---
title: 'Lync Server 2013: relatório detalhado de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e14ca8565216efbdeaae3060587d5d18d919876
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="f8419-102">Relatório detalhado de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8419-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8419-103">_**Última modificação do tópico:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="f8419-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="f8419-104">O relatório detalhado de chamadas fornece uma visão detalhada de uma chamada individual; o relatório inclui quase todas as métricas e estatísticas de qualidade de experiência coletadas pelo Lync Server, divididas em seções de relatório, como:</span><span class="sxs-lookup"><span data-stu-id="f8419-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="f8419-105">Informações da chamada</span><span class="sxs-lookup"><span data-stu-id="f8419-105">Call Information</span></span>

  - <span data-ttu-id="f8419-106">Medição do dispositivo e do sinal do chamador</span><span class="sxs-lookup"><span data-stu-id="f8419-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="f8419-107">Medição do dispositivo e do sinal de quem é chamado</span><span class="sxs-lookup"><span data-stu-id="f8419-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="f8419-108">Evento do cliente do chamador</span><span class="sxs-lookup"><span data-stu-id="f8419-108">Caller Client Event</span></span>

  - <span data-ttu-id="f8419-109">Evento do cliente de quem é chamado</span><span class="sxs-lookup"><span data-stu-id="f8419-109">Callee Client Event</span></span>

  - <span data-ttu-id="f8419-110">Fluxo de áudio (do chamador para que é chamado)</span><span class="sxs-lookup"><span data-stu-id="f8419-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="f8419-111">Fluxo de vídeo (do chamador para que é chamado)</span><span class="sxs-lookup"><span data-stu-id="f8419-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="f8419-112">Fluxo de áudio (de quem é chamado para o chamador)</span><span class="sxs-lookup"><span data-stu-id="f8419-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="f8419-113">Fluxo de vídeo (de quem é chamado para o chamador)</span><span class="sxs-lookup"><span data-stu-id="f8419-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="f8419-p101">Lembre-se de que as categorias e medidas de um determinado relatório dependem de duas coisas: o tipo de sessão e o tipo de ponto de extremidade usados na sessão. Por exemplo, uma chamada com apenas áudio não reportará medidas de fluxo de vídeo; isso se deve ao fato de a chamada não ter um fluxo de vídeo. Da mesma forma, é possível ter um relatório que liste estatísticas do chamador, mas não de quem é chamado. Normalmente, isso ocorre quando quem foi chamado não usa um dispositivo compatível com SIP. Os pontos de extremidade são responsáveis por reportar estatísticas no final de uma chamada; no entanto, um telefone celular (que desconhece SIP ou as estatísticas de SIP) não pode reportar esse tipo de informação. Se você ligar para alguém e essa pessoa atender em um telefone celular, você não obterá um relatório desse telefone celular quando a chamada terminar.</span><span class="sxs-lookup"><span data-stu-id="f8419-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="f8419-120">O Relatório Detalhado de Chamadas é especialmente útil quando você está tentando determinar exatamente porque determinada chamada enfrentou problemas de qualidade de mídia.</span><span class="sxs-lookup"><span data-stu-id="f8419-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="f8419-121">Acessando o Relatório Detalhado de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f8419-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="f8419-122">O Relatório Detalhado de Chamadas pode ser acessado a partir de qualquer um dos seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="f8419-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="f8419-123">O [relatório de localização no Lync Server 2013](lync-server-2013-location-report.md) (clicando no volume da chamada ou na métrica porcentagem de chamadas ruins)</span><span class="sxs-lookup"><span data-stu-id="f8419-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="f8419-124">O [relatório de Resumo de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (clicando no volume da chamada ou na métrica percentual de chamadas ruins)</span><span class="sxs-lookup"><span data-stu-id="f8419-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="f8419-125">O [relatório de comparação de qualidade de mídia no Lync server 2013](lync-server-2013-media-quality-comparison-report.md) (clicando no [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) e, em seguida, clicando na métrica detalhes).</span><span class="sxs-lookup"><span data-stu-id="f8419-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="f8419-126">O [relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) (clicando no volume da chamada ou na métrica porcentagem de chamadas ruins)</span><span class="sxs-lookup"><span data-stu-id="f8419-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="f8419-127">O [relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) (clicando na métrica detalhes)</span><span class="sxs-lookup"><span data-stu-id="f8419-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="f8419-128">No relatório de detalhes das chamadas, você pode acessar o [relatório de dispositivos no Lync Server 2013](lync-server-2013-device-report.md) clicando em uma das seguintes métricas:</span><span class="sxs-lookup"><span data-stu-id="f8419-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="f8419-129">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="f8419-129">Capture device</span></span>

  - <span data-ttu-id="f8419-130">Dispositivo de renderização</span><span class="sxs-lookup"><span data-stu-id="f8419-130">Render device</span></span>

<span data-ttu-id="f8419-131">Também é possível acessar o Relatório de Tendências de Qualidade de Mídia clicando na medida Servidor de borda de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="f8419-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="f8419-132">Fazendo o melhor uso do Relatório Detalhado de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f8419-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="f8419-p102">O Relatório Detalhado de Chamadas normalmente contém 250 medidas diferentes, inclusive itens como Descompasso do carimbo de data/hora do microfone, Tempo de SNR baixo e Extremidade próxima ao tempo de eco. Se não conseguir se lembrar o que exatamente todas essas medidas avaliam, tente pousar o mouse sobre o nome da medida; na maioria das vezes, uma dica de ferramenta será exibida descrevendo a medida.</span><span class="sxs-lookup"><span data-stu-id="f8419-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="f8419-p103">Se tiver problemas para localizar uma medida, digite parte do nome da medida na caixa de pesquisa e clique em Localizar. Por exemplo, se não puder localizar a medida Tempo de SNR baixo, digite SNR na caixa de pesquisa e clique em Localizar.</span><span class="sxs-lookup"><span data-stu-id="f8419-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="f8419-137">Observe que o relatório controla apenas as informações sobre uma chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="f8419-138">A chamada em si não é registrada.</span><span class="sxs-lookup"><span data-stu-id="f8419-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f8419-139">Filtros</span><span class="sxs-lookup"><span data-stu-id="f8419-139">Filters</span></span>

<span data-ttu-id="f8419-p105">Nenhum. Você não pode filtrar o Relatório Detalhado de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="f8419-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="f8419-142">Métricas</span><span class="sxs-lookup"><span data-stu-id="f8419-142">Metrics</span></span>

<span data-ttu-id="f8419-143">A tabela a seguir lista as informações fornecidas no Relatório Detalhado de Chamadas para cada chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="f8419-144">Métricas do Relatório Detalhado de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f8419-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8419-145">Nome</span><span class="sxs-lookup"><span data-stu-id="f8419-145">Name</span></span></th>
<th><span data-ttu-id="f8419-146">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="f8419-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f8419-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="f8419-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8419-148"><strong>PAI do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-149">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-149">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-p106">O P-Asserted-Identity do usuário que iniciou a chamada. Essa identidade é usada para transportar a identidade comprovada de um usuário dentro de uma rede confiável.</span><span class="sxs-lookup"><span data-stu-id="f8419-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-152"><strong>URI do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-153">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-153">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-154">Endereço SIP do usuário que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-155"><strong>Ponto de extremidade do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-156">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-156">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-157">Dispositivo usado para efetuar a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-158"><strong>Agente do usuário do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-159">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-159">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-160">Software usado no dispositivo que fez a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-161"><strong>Início da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-162">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-162">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-163">Data e hora em que a chamada foi iniciada.</span><span class="sxs-lookup"><span data-stu-id="f8419-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-164"><strong>Chamada de desvio do Servidor de Mediação</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-165">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-165">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-166">Indica se a chamada conectou a um gateway de voz PSTN ou IP-PBX qualificado sem passar pelo Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="f8419-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-167"><strong>OS do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-168">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-168">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-169">Sistema operacional do computador do chamador.</span><span class="sxs-lookup"><span data-stu-id="f8419-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-170"><strong>CPU do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-171">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-171">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-172">CPU instalado no computador do usuário que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-173"><strong>Número de core do CPU do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-174">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-174">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-175">Número do processador no computador usado pela pessoa que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-176"><strong>Velocidade de CPU do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-177">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-177">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-178">Velocidade de relógio do CPU do computador usado pela pessoa que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-179"><strong>Virtualização de CPU do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-180">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-180">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-181">Virtualização (se houver) no computador usado pela pessoa que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-182"><strong>PAI do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-183">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-183">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-p107">O P-Asserted-Identity do usuário convidado a entrar na chamada. Essa identidade é usada para transportar a identidade comprovada de um usuário dentro de uma rede confiável.</span><span class="sxs-lookup"><span data-stu-id="f8419-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-186"><strong>URI do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-187">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-187">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-188">Endereço SIP do usuário que foi chamado.</span><span class="sxs-lookup"><span data-stu-id="f8419-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-189"><strong>Ponto de extremidade do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-190">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-190">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-191">Dispositivo usado para receber a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-192"><strong>Agente do usuário do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-193">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-193">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-194">Software usado no dispositivo que recebeu a chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-195"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-196">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-196">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-197">Tempo da chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-198"><strong>Sinalizador de aviso do desvio de mídia</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-199">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-199">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-200">Aviso emitido quando o Servidor de Mediação foi desviado.</span><span class="sxs-lookup"><span data-stu-id="f8419-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-201"><strong>OS do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-202">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-202">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-203">Sistema operacional do computador do usuário que foi chamado.</span><span class="sxs-lookup"><span data-stu-id="f8419-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-204"><strong>CPU do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-205">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-205">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-206">CPU instalado no computador do usuário que foi chamado.</span><span class="sxs-lookup"><span data-stu-id="f8419-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-207"><strong>Número de core do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-208">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-208">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-209">Número do processador no computador usado pela pessoa que foi chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8419-210"><strong>Velocidade de CPU do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-211">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-211">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-212">Velocidade de relógio do CPU do computador usado pela pessoa que foi chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8419-213"><strong>Virtualização de CPU do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="f8419-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="f8419-214">Não</span><span class="sxs-lookup"><span data-stu-id="f8419-214">No</span></span></p></td>
<td><p><span data-ttu-id="f8419-215">Virtualização (se houver) no computador usado pela pessoa que foi chamada.</span><span class="sxs-lookup"><span data-stu-id="f8419-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

