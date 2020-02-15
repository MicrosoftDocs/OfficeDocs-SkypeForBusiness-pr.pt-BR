---
title: 'Lync Server 2013: relatório de lista de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53b462644e2334f428b8cd9a46c0ca07472f6ee2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="30773-102">Relatório de lista de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30773-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30773-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="30773-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="30773-104">O relatório de lista de chamadas fornece métricas de qualidade de experiência (QoE) para chamadas individuais feitas e recebidas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="30773-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="30773-105">Observe que as métricas reais relatadas dependem de como você acessa o relatório de lista de chamadas.</span><span class="sxs-lookup"><span data-stu-id="30773-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="30773-106">Por exemplo, se você abrir o relatório do [relatório de dispositivos no Lync Server 2013](lync-server-2013-device-report.md), verá métricas como as seguintes, métricas que também são relatadas no relatório de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="30773-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="30773-107">Microfone do chamador</span><span class="sxs-lookup"><span data-stu-id="30773-107">Caller's microphone</span></span>

  - <span data-ttu-id="30773-108">Alto-falante do chamador</span><span class="sxs-lookup"><span data-stu-id="30773-108">Caller's speaker</span></span>

  - <span data-ttu-id="30773-109">Microfone do receptor da chamada</span><span class="sxs-lookup"><span data-stu-id="30773-109">Callee's microphone</span></span>

  - <span data-ttu-id="30773-110">Alto-falante do receptor da chamada</span><span class="sxs-lookup"><span data-stu-id="30773-110">Callee's speaker</span></span>

  - <span data-ttu-id="30773-111">Tempo de troca da taxa de voz</span><span class="sxs-lookup"><span data-stu-id="30773-111">Ratio of voice switch time</span></span>

<span data-ttu-id="30773-112">No entanto, se você abrir o relatório de lista de chamadas do [relatório de localização no Lync Server 2013](lync-server-2013-location-report.md), não verá nenhuma dessas métricas; em vez disso, você verá métricas como estas:</span><span class="sxs-lookup"><span data-stu-id="30773-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="30773-113">Viagem de ida e volta (ms)</span><span class="sxs-lookup"><span data-stu-id="30773-113">Round trip (ms)</span></span>

  - <span data-ttu-id="30773-114">Degradação (MOS)</span><span class="sxs-lookup"><span data-stu-id="30773-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="30773-115">Perda de pacote</span><span class="sxs-lookup"><span data-stu-id="30773-115">Packet loss</span></span>

  - <span data-ttu-id="30773-116">Tremulação (ms)</span><span class="sxs-lookup"><span data-stu-id="30773-116">Jitter (ms)</span></span>

<span data-ttu-id="30773-117">Essas são as métricas relatadas no relatório de localização.</span><span class="sxs-lookup"><span data-stu-id="30773-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="30773-118">No entanto, no relatório de lista de chamadas, você sempre pode clicar na métrica de detalhes para fornecer informações completas de QoE para qualquer chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="30773-119">Acessar o relatório de lista de chamadas</span><span class="sxs-lookup"><span data-stu-id="30773-119">Accessing the Call List Report</span></span>

<span data-ttu-id="30773-120">O relatório de lista de chamadas pode ser acessado de qualquer um dos seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="30773-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="30773-121">O [relatório de localização no Lync Server 2013](lync-server-2013-location-report.md) (clicando na métrica de volume de chamada ou percentual de chamadas ruins)</span><span class="sxs-lookup"><span data-stu-id="30773-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="30773-122">O [relatório de dispositivo no Lync Server 2013](lync-server-2013-device-report.md) (clicando na métrica de volume de chamada ou percentual de chamadas ruins)</span><span class="sxs-lookup"><span data-stu-id="30773-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="30773-123">O [relatório de Resumo de qualidade de mídia no Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (clicando na métrica de volume de chamada ou percentual de chamadas ruins)</span><span class="sxs-lookup"><span data-stu-id="30773-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="30773-124">O [relatório de desempenho do servidor no Lync Server 2013](lync-server-2013-server-performance-report.md) (clicando no volume da chamada ou na métrica percentual de chamadas ruins)</span><span class="sxs-lookup"><span data-stu-id="30773-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="30773-125">No relatório de lista de chamadas, você pode acessar o [relatório de detalhes da chamada no Lync Server 2013](lync-server-2013-call-detail-report.md) clicando na métrica detalhe.</span><span class="sxs-lookup"><span data-stu-id="30773-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="30773-126">Fazendo o melhor uso do relatório de lista de chamadas</span><span class="sxs-lookup"><span data-stu-id="30773-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="30773-127">Se você não conseguir se lembrar do que algumas das métricas do relatório de lista de chamadas (como taxa de alternância de voz) realmente medem, segure o mouse sobre o rótulo da métrica; uma dica de ferramenta será exibida dando uma breve descrição da métrica.</span><span class="sxs-lookup"><span data-stu-id="30773-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="30773-128">Filtros</span><span class="sxs-lookup"><span data-stu-id="30773-128">Filters</span></span>

<span data-ttu-id="30773-129">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="30773-129">None.</span></span> <span data-ttu-id="30773-130">Você não pode filtrar o relatório de lista de chamadas.</span><span class="sxs-lookup"><span data-stu-id="30773-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="30773-131">Métricas</span><span class="sxs-lookup"><span data-stu-id="30773-131">Metrics</span></span>

<span data-ttu-id="30773-132">A tabela a seguir lista as informações fornecidas no relatório de lista de chamadas para cada chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="30773-133">Métricas do relatório de lista de chamadas</span><span class="sxs-lookup"><span data-stu-id="30773-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30773-134">Nome</span><span class="sxs-lookup"><span data-stu-id="30773-134">Name</span></span></th>
<th><span data-ttu-id="30773-135">É possível classificar este item?</span><span class="sxs-lookup"><span data-stu-id="30773-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="30773-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="30773-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30773-137"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="30773-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-138">Não</span><span class="sxs-lookup"><span data-stu-id="30773-138">No</span></span></p></td>
<td><p><span data-ttu-id="30773-139">Quando você clica nesse item, o relatório mostra informações adicionais sobre a chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30773-140"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="30773-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-141">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-142">Endereço SIP da pessoa que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30773-143"><strong>Receptor</strong></span><span class="sxs-lookup"><span data-stu-id="30773-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-144">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-145">Endereço SIP da pessoa que foi chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30773-146"><strong>Hora de início</strong></span><span class="sxs-lookup"><span data-stu-id="30773-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-147">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-148">Data e horário em que a chamada teve início.</span><span class="sxs-lookup"><span data-stu-id="30773-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30773-149"><strong>Hora de término</strong></span><span class="sxs-lookup"><span data-stu-id="30773-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-150">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-151">Data e horário em que a chamada terminou.</span><span class="sxs-lookup"><span data-stu-id="30773-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30773-152"><strong>Agente do usuário do chamador</strong></span><span class="sxs-lookup"><span data-stu-id="30773-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-153">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-154">Software usado pelo ponto de extremidade da pessoa que iniciou a chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30773-155"><strong>Agente do usuário do receptor da chamada</strong></span><span class="sxs-lookup"><span data-stu-id="30773-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-156">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-157">Software usado pelo ponto de extremidade da pessoa que foi chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30773-158"><strong>Viagem de ida e volta (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="30773-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-159">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-p104">Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="30773-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="30773-p105">Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.</span><span class="sxs-lookup"><span data-stu-id="30773-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30773-164"><strong>Degradação (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="30773-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-165">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-166">Quantidade média da degradação MOS enfrentada durante uma chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="30773-167">Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0.</span><span class="sxs-lookup"><span data-stu-id="30773-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="30773-168">Um valor de 0,5 ou menos representa degradação aceitável.</span><span class="sxs-lookup"><span data-stu-id="30773-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="30773-169">Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5.</span><span class="sxs-lookup"><span data-stu-id="30773-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="30773-170">No Lync Server, o Lync Server usa um conjunto de algoritmos para prever como os usuários classificaram uma chamada.</span><span class="sxs-lookup"><span data-stu-id="30773-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="30773-p107">Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="30773-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30773-173"><strong>Perda de pacote </strong></span><span class="sxs-lookup"><span data-stu-id="30773-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-174">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-p108">Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="30773-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30773-178"><strong>Torção</strong></span><span class="sxs-lookup"><span data-stu-id="30773-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-179">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-180">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="30773-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="30773-181">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="30773-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30773-182"><strong>Taxa de correção oculta</strong></span><span class="sxs-lookup"><span data-stu-id="30773-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-183">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-p110">Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.</span><span class="sxs-lookup"><span data-stu-id="30773-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30773-186"><strong>Taxa de correção estendida</strong></span><span class="sxs-lookup"><span data-stu-id="30773-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-187">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-p111">Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="30773-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30773-190"><strong>Taxa de correção compactada</strong></span><span class="sxs-lookup"><span data-stu-id="30773-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-191">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-p112">Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.</span><span class="sxs-lookup"><span data-stu-id="30773-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30773-194"><strong>Conectividade</strong></span><span class="sxs-lookup"><span data-stu-id="30773-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="30773-195">Sim</span><span class="sxs-lookup"><span data-stu-id="30773-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="30773-196">Tipo de link de comunicação sem fio.</span><span class="sxs-lookup"><span data-stu-id="30773-196">Type of wireless communication link.</span></span> <span data-ttu-id="30773-197">Normalmente, este é um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="30773-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="30773-198">Transmit</span><span class="sxs-lookup"><span data-stu-id="30773-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="30773-199">Orientar</span><span class="sxs-lookup"><span data-stu-id="30773-199">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

