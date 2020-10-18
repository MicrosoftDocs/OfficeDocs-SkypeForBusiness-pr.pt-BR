---
title: 'Lync Server 2013: tabela AppSharingStream'
description: 'Lync Server 2013: tabela AppSharingStream.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574717"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="6bd9a-103">Tabela AppSharingStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bd9a-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bd9a-104">_**Última modificação do tópico:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="6bd9a-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="6bd9a-105">A tabela AppSharingStream contém medidas de qualidade da experiência dos fluxos de rede usados no compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="6bd9a-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6bd9a-107"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6bd9a-108"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6bd9a-109"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6bd9a-110"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="6bd9a-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="6bd9a-113">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="6bd9a-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6bd9a-114">Data e hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-116">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-116">int</span></span></p></td>
<td><p><span data-ttu-id="6bd9a-117">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="6bd9a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6bd9a-118">Identificador sequencial usado para distinguir entre sessões que foram iniciadas na mesma data e na mesma hora.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="6bd9a-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6bd9a-121">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="6bd9a-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6bd9a-p102">Representa o tipo de linha de vídeo usada na chamada. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6bd9a-124">0 – áudio</span><span class="sxs-lookup"><span data-stu-id="6bd9a-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="6bd9a-125">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="6bd9a-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="6bd9a-126">2 – Vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="6bd9a-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="6bd9a-127">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="6bd9a-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-128"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-129">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-129">int</span></span></p></td>
<td><p><span data-ttu-id="6bd9a-130">Primário</span><span class="sxs-lookup"><span data-stu-id="6bd9a-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="6bd9a-131">Identificador exclusivo do fluxo de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-133">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-134">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="6bd9a-135">(Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-137">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-138">Tremulação máxima detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="6bd9a-139">(Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-140"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-141">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p105">Quantidade média (em milissegundos) exigida para que um pacote de protocolo de transporte em tempo real viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="6bd9a-p106">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-147">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p107">Quantidade máxima (em milissegundos) exigida para que um pacote de protocolo de transporte em tempo real viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="6bd9a-p108">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-153">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p109">Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-158">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p110">Taxa máxima de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-163">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-164">Número de pacotes enviados.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-165"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-166">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p111">Largura de banda unidirecional estimada disponível no final da sessão. Reportada em bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-170">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-171">Descrição da carga do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-173">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p112">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-177">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p113">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-181">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p114">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-185">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p115">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-190">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p116">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-195">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p117">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-200">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p118">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-205">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p119">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-210">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p120">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-215">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-216">Função do aplicativo (participante do compartilhamento ou visualizador) e tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-218">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p121">O tempo total de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-222">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p122">Tempo médio de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-226">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p123">Tempo máximo de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-230">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p124">Ocorrências de intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-234">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p125">Densidade da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-238">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p126">Duração da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-242">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-243">Ocorrências de intervalos no tempo de processamento de blocos de protocolo RDP (RDP).</span><span class="sxs-lookup"><span data-stu-id="6bd9a-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-245">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p127">Densidade do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Uma baixa densidade do intervalo significa uma melhor experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-249">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-p128">Duração do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Uma baixa densidade de intervalo significa uma melhor experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-253">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-254">Taxa total de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-256">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-257">Taxa média de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-259">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-260">Taxa máxima de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-262">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-263">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-265">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-266">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-268">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-269">Duração da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-271">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-272">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-274">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-275">Densidade do intervalo na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-277">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-278">Duração do intervalo na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="6bd9a-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-280">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-281">Porcentagem total do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-283">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-284">Porcentagem média do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-286">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-287">Porcentagem máxima do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-289">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-290">Ocorrências de intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-292">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-293">Densidade da intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-295">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-296">Duração da intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-298">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-299">Ocorrências de intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-301">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-302">Densidade do intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-304">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-305">Duração do intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-307">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-308">Número total de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-310">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-311">Número médio de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-313">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-314">Número máximo de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-316">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-317">Ocorrências de intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-319">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-320">Densidade da intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-322">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-323">Duração da intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-325">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-326">Ocorrências de intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-328">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-329">Densidade do intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-331">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-332">Duração do intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-334">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-335">Taxa de quadros total de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-337">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-338">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-340">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-341">Taxa de blocos máxima de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-343">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-344">Ocorrências de intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-346">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-347">Densidade da intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-349">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-350">Duração da intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-352">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-353">Ocorrências de intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-355">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-356">Densidade do intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-358">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-359">Duração do intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-361">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-362">Taxa de quadros total de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-364">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-365">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-367">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-368">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-370">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-371">Ocorrências de intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-373">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-374">Densidade da intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-376">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-377">Duração da intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-379">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-380">Ocorrências de intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-382">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-383">Densidade do intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-385">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-386">Duração do intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-388">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-389">Taxa de blocos total de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-391">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-392">Taxa de blocos média de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-394">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-395">Taxa de blocos máxima de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-397">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-398">Ocorrências de intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-400">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-401">Densidade da intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-403">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-404">Duração da intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-406">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-407">Ocorrências de intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-409">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-410">Densidade do intervalo na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-412">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-413">Duração do intervalo na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-415">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-416">Taxa de quadros total de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-418">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-419">Taxa de quadros média de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-421">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-422">Taxa de quadros máxima de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-424">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-425">Ocorrências de intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-427">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-428">Densidade da intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-430">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-431">Duração da intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-433">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-434">Ocorrências de intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-436">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-437">Densidade do intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-439">flutuação</span><span class="sxs-lookup"><span data-stu-id="6bd9a-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-440">Duração do intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-442">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-443">Altura média da resolução de vídeo em pixels.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-445">int</span><span class="sxs-lookup"><span data-stu-id="6bd9a-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-446">Largura média da resolução de vídeo em pixels.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-447"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-448">bits</span><span class="sxs-lookup"><span data-stu-id="6bd9a-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-449">Taxa de quadros média (em quadros por segundo) para transmissões de entrada.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6bd9a-450"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-451">bits</span><span class="sxs-lookup"><span data-stu-id="6bd9a-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-452">Taxa de quadros média (em quadros por segundo) para transmissões de saída.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6bd9a-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="6bd9a-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="6bd9a-454">bits</span><span class="sxs-lookup"><span data-stu-id="6bd9a-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6bd9a-455">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="6bd9a-456">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="6bd9a-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

