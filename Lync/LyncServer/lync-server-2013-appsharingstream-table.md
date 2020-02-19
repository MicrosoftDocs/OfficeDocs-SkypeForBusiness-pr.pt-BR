---
title: 'Lync Server 2013: tabela AppSharingStream'
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
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="fa7dc-102">Tabela AppSharingStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa7dc-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa7dc-103">_**Última modificação do tópico:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="fa7dc-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="fa7dc-104">A tabela AppSharingStream contém medidas de qualidade da experiência dos fluxos de rede usados no compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="fa7dc-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa7dc-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fa7dc-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fa7dc-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fa7dc-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="fa7dc-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="fa7dc-112">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="fa7dc-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa7dc-113">Data e hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-115">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-115">int</span></span></p></td>
<td><p><span data-ttu-id="fa7dc-116">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="fa7dc-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa7dc-117">Identificador sequencial usado para distinguir entre sessões que foram iniciadas na mesma data e na mesma hora.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="fa7dc-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fa7dc-120">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="fa7dc-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa7dc-p102">Representa o tipo de linha de vídeo usada na chamada. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="fa7dc-123">0 – áudio</span><span class="sxs-lookup"><span data-stu-id="fa7dc-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="fa7dc-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="fa7dc-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="fa7dc-125">2 – Vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="fa7dc-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="fa7dc-126">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="fa7dc-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-127"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-128">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-128">int</span></span></p></td>
<td><p><span data-ttu-id="fa7dc-129">Primário</span><span class="sxs-lookup"><span data-stu-id="fa7dc-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="fa7dc-130">Identificador exclusivo do fluxo de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-132">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-133">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="fa7dc-134">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-136">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-137">Tremulação máxima detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="fa7dc-138">(Tremulação é uma medida do &quot;tremula&quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-139"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-140">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p105">Quantidade média (em milissegundos) exigida para que um pacote de protocolo de transporte em tempo real viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="fa7dc-p106">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-146">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p107">Quantidade máxima (em milissegundos) exigida para que um pacote de protocolo de transporte em tempo real viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="fa7dc-p108">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-152">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p109">Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-157">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p110">Taxa máxima de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-162">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-163">Número de pacotes enviados.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-164"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-165">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p111">Largura de banda unidirecional estimada disponível no final da sessão. Reportada em bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-169">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-170">Descrição da carga do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-172">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p112">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-176">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p113">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-180">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p114">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-184">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p115">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-189">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p116">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-194">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p117">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-199">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p118">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-204">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p119">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-209">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p120">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-215">Função do aplicativo (participante do compartilhamento ou visualizador) e tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-217">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p121">O tempo total de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-221">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p122">Tempo médio de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-225">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p123">Tempo máximo de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-229">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p124">Ocorrências de intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-233">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p125">Densidade da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-237">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p126">Duração da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-241">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-242">Ocorrências de intervalos no tempo de processamento de blocos de protocolo RDP (RDP).</span><span class="sxs-lookup"><span data-stu-id="fa7dc-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-244">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p127">Densidade do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Uma baixa densidade do intervalo significa uma melhor experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-248">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-p128">Duração do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Uma baixa densidade de intervalo significa uma melhor experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-252">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-253">Taxa total de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-255">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-256">Taxa média de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-258">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-259">Taxa máxima de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-261">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-262">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-264">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-265">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-267">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-268">Duração da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-270">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-271">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-273">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-274">Densidade do intervalo na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-276">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-277">Duração do intervalo na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="fa7dc-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-279">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-280">Porcentagem total do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-282">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-283">Porcentagem média do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-285">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-286">Porcentagem máxima do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-288">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-289">Ocorrências de intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-291">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-292">Densidade da intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-294">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-295">Duração da intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-297">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-298">Ocorrências de intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-300">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-301">Densidade do intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-303">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-304">Duração do intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-306">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-307">Número total de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-309">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-310">Número médio de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-312">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-313">Número máximo de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-315">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-316">Ocorrências de intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-318">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-319">Densidade da intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-321">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-322">Duração da intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-324">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-325">Ocorrências de intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-327">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-328">Densidade do intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-330">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-331">Duração do intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-333">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-334">Taxa de quadros total de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-336">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-337">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-339">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-340">Taxa de blocos máxima de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-342">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-343">Ocorrências de intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-345">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-346">Densidade da intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-348">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-349">Duração da intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-351">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-352">Ocorrências de intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-354">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-355">Densidade do intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-357">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-358">Duração do intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-360">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-361">Taxa de quadros total de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-363">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-364">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-366">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-367">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-369">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-370">Ocorrências de intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-372">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-373">Densidade da intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-375">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-376">Duração da intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-378">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-379">Ocorrências de intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-381">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-382">Densidade do intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-384">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-385">Duração do intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-387">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-388">Taxa de blocos total de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-390">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-391">Taxa de blocos média de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-393">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-394">Taxa de blocos máxima de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-396">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-397">Ocorrências de intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-399">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-400">Densidade da intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-402">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-403">Duração da intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-405">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-406">Ocorrências de intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-408">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-409">Densidade do intervalo na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-411">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-412">Duração do intervalo na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-414">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-415">Taxa de quadros total de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-417">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-418">Taxa de quadros média de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-420">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-421">Taxa de quadros máxima de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-423">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-424">Ocorrências de intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-426">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-427">Densidade da intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-429">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-430">Duração da intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-432">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-433">Ocorrências de intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-435">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-436">Densidade do intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-438">float</span><span class="sxs-lookup"><span data-stu-id="fa7dc-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-439">Duração do intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-441">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-442">Altura média da resolução de vídeo em pixels.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-444">int</span><span class="sxs-lookup"><span data-stu-id="fa7dc-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-445">Largura média da resolução de vídeo em pixels.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-446"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-447">bits</span><span class="sxs-lookup"><span data-stu-id="fa7dc-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-448">Taxa de quadros média (em quadros por segundo) para transmissões de entrada.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa7dc-449"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-450">bits</span><span class="sxs-lookup"><span data-stu-id="fa7dc-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-451">Taxa de quadros média (em quadros por segundo) para transmissões de saída.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa7dc-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="fa7dc-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="fa7dc-453">bits</span><span class="sxs-lookup"><span data-stu-id="fa7dc-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa7dc-454">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="fa7dc-455">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

