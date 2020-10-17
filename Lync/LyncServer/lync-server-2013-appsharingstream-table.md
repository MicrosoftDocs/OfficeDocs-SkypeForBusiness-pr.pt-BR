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
ms.openlocfilehash: 9b729112aa0fb064a518c50212a6a041a6661be3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499498"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="dbd24-102">Tabela AppSharingStream no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbd24-102">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbd24-103">_**Última modificação do tópico:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="dbd24-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="dbd24-104">A tabela AppSharingStream contém medidas de qualidade da experiência dos fluxos de rede usados no compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="dbd24-105">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbd24-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbd24-106"><strong>Coluna</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dbd24-107"><strong>Tipo de dados</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dbd24-108"><strong>Chave/índice</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dbd24-109"><strong>Detalhes</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="dbd24-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="dbd24-112">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="dbd24-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd24-113">Data e hora de início da sessão.</span><span class="sxs-lookup"><span data-stu-id="dbd24-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-115">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-115">int</span></span></p></td>
<td><p><span data-ttu-id="dbd24-116">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="dbd24-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd24-117">Identificador sequencial usado para distinguir entre sessões que foram iniciadas na mesma data e na mesma hora.</span><span class="sxs-lookup"><span data-stu-id="dbd24-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="dbd24-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dbd24-120">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="dbd24-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd24-p102">Representa o tipo de linha de vídeo usada na chamada. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="dbd24-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbd24-123">0 – áudio</span><span class="sxs-lookup"><span data-stu-id="dbd24-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="dbd24-124">1 – vídeo</span><span class="sxs-lookup"><span data-stu-id="dbd24-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="dbd24-125">2 – Vídeo panorâmico</span><span class="sxs-lookup"><span data-stu-id="dbd24-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="dbd24-126">3 – compartilhamento de aplicativos/área de trabalho</span><span class="sxs-lookup"><span data-stu-id="dbd24-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-127"><strong>Streamid</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-128">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-128">int</span></span></p></td>
<td><p><span data-ttu-id="dbd24-129">Primário</span><span class="sxs-lookup"><span data-stu-id="dbd24-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="dbd24-130">Identificador exclusivo do fluxo de compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-132">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-133">Tremulação média detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="dbd24-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="dbd24-134">(Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="dbd24-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-136">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-137">Tremulação máxima detectada entre chegadas de pacote RTP.</span><span class="sxs-lookup"><span data-stu-id="dbd24-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="dbd24-138">(Tremulação é uma medida do &quot; tremula &quot; de uma chamada.) Os valores de variação alta geralmente são causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em um áudio distorcido ou perdido.</span><span class="sxs-lookup"><span data-stu-id="dbd24-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-139"><strong>Aproxima</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-140">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p105">Quantidade média (em milissegundos) exigida para que um pacote de protocolo de transporte em tempo real viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="dbd24-p106">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-146">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p107">Quantidade máxima (em milissegundos) exigida para que um pacote de protocolo de transporte em tempo real viaje até outro ponto de extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="dbd24-p108">Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-152">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p109">Taxa média de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-157">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p110">Taxa máxima de perda de pacotes de RTP (protocolo de transporte em tempo real). (A perda de pacotes ocorre quando pacotes de RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-162">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-163">Número de pacotes enviados.</span><span class="sxs-lookup"><span data-stu-id="dbd24-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-164"><strong>Mais largura de banda</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-165">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p111">Largura de banda unidirecional estimada disponível no final da sessão. Reportada em bits por segundo.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-169">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-170">Descrição da carga do compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-172">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p112">Quantidade total de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-176">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p113">Quantidade média de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-180">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p114">Quantidade máxima de latência unidirecional. A latência relativa unidirecional mede o atraso entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-184">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p115">Total de ocorrências de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-189">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p116">Densidade total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-194">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p117">Duração total de intermitências unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-199">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p118">Total de ocorrências de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-204">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p119">Densidade total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-209">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p120">Duração total de intervalos unidirecionais. Uma transmissão "intermitente" ocorre quando os fluxos de dados sofrem intermitências imprevisíveis, em oposição a um fluxo contínuo: os intervalos indicam os atrasos entre essas intermitências. Esta medida avalia o fluxo de dados entre o cliente e o servidor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="dbd24-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-215">Função do aplicativo (participante do compartilhamento ou visualizador) e tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="dbd24-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-217">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p121">O tempo total de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-221">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p122">Tempo médio de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-225">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p123">Tempo máximo de processamento de blocos de protocolo RDP (RDP). Um total mais alto significa uma demora mais longa na experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-229">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p124">Ocorrências de intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-233">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p125">Densidade da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-237">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p126">Duração da intermitência no tempo de processamento de blocos de protocolo RDP (RDP). Uma transmissão "intermitente" é uma transmissão em que os fluxos de dados são imprevisivelmente intermitentes, em oposição a um fluxo contínuo.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-241">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-242">Ocorrências de intervalos no tempo de processamento de blocos de protocolo RDP (RDP).</span><span class="sxs-lookup"><span data-stu-id="dbd24-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-244">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p127">Densidade do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Uma baixa densidade do intervalo significa uma melhor experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-248">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-p128">Duração do intervalo no tempo de processamento de blocos de protocolo RDP (RDP). Uma baixa densidade de intervalo significa uma melhor experiência de exibição.</span><span class="sxs-lookup"><span data-stu-id="dbd24-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-252">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-253">Taxa total de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-255">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-256">Taxa média de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-258">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-259">Taxa máxima de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-261">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-262">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-264">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-265">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-267">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-268">Duração da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-270">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-271">Densidade da intermitência na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-273">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-274">Densidade do intervalo na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-276">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-277">Duração do intervalo na taxa de blocos capturados (em blocos por segundo)</span><span class="sxs-lookup"><span data-stu-id="dbd24-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-279">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-280">Porcentagem total do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-282">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-283">Porcentagem média do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-285">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-286">Porcentagem máxima do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-288">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-289">Ocorrências de intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-291">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-292">Densidade da intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-294">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-295">Duração da intermitência do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-297">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-298">Ocorrências de intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-300">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-301">Densidade do intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-303">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-304">Duração do intervalo do conteúdo que não chegou ao visualizador, mas que foi descartado e substituído por conteúdo recente.</span><span class="sxs-lookup"><span data-stu-id="dbd24-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-306">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-307">Número total de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-309">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-310">Número médio de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-312">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-313">Número máximo de quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-315">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-316">Ocorrências de intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-318">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-319">Densidade da intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-321">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-322">Duração da intermitência nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-324">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-325">Ocorrências de intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-327">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-328">Densidade do intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-330">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-331">Duração do intervalo nos quadros retirados da origem de gráficos.</span><span class="sxs-lookup"><span data-stu-id="dbd24-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-333">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-334">Taxa de quadros total de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-336">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-337">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-339">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-340">Taxa de blocos máxima de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-342">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-343">Ocorrências de intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-345">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-346">Densidade da intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-348">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-349">Duração da intermitência na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-351">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-352">Ocorrências de intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-354">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-355">Densidade do intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-357">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-358">Duração do intervalo na taxa de blocos de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-360">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-361">Taxa de quadros total de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-363">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-364">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-366">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-367">Taxa de quadros média de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-369">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-370">Ocorrências de intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-372">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-373">Densidade da intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-375">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-376">Duração da intermitência na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-378">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-379">Ocorrências de intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-381">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-382">Densidade do intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-384">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-385">Duração do intervalo na taxa de quadros de entrada como recebida pelo visualizador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-387">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-388">Taxa de blocos total de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-390">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-391">Taxa de blocos média de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-393">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-394">Taxa de blocos máxima de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-396">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-397">Ocorrências de intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-399">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-400">Densidade da intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-402">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-403">Duração da intermitência na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-405">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-406">Ocorrências de intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-408">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-409">Densidade do intervalo na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-411">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-412">Duração do intervalo na taxa de blocos de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-414">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-415">Taxa de quadros total de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-417">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-418">Taxa de quadros média de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-420">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-421">Taxa de quadros máxima de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-423">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-424">Ocorrências de intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-426">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-427">Densidade da intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-429">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-430">Duração da intermitência na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-432">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-433">Ocorrências de intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-435">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-436">Densidade do intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-438">flutuação</span><span class="sxs-lookup"><span data-stu-id="dbd24-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-439">Duração do intervalo na taxa de quadros de saída para o emissor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-441">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-442">Altura média da resolução de vídeo em pixels.</span><span class="sxs-lookup"><span data-stu-id="dbd24-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-444">int</span><span class="sxs-lookup"><span data-stu-id="dbd24-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-445">Largura média da resolução de vídeo em pixels.</span><span class="sxs-lookup"><span data-stu-id="dbd24-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-446"><strong>Entrada</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-447">bits</span><span class="sxs-lookup"><span data-stu-id="dbd24-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-448">Taxa de quadros média (em quadros por segundo) para transmissões de entrada.</span><span class="sxs-lookup"><span data-stu-id="dbd24-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd24-449"><strong>Saída</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-450">bits</span><span class="sxs-lookup"><span data-stu-id="dbd24-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-451">Taxa de quadros média (em quadros por segundo) para transmissões de saída.</span><span class="sxs-lookup"><span data-stu-id="dbd24-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd24-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="dbd24-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd24-453">bits</span><span class="sxs-lookup"><span data-stu-id="dbd24-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd24-454">1 significa que a direção do fluxo é do chamador para o receptor.</span><span class="sxs-lookup"><span data-stu-id="dbd24-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="dbd24-455">0 significa que a direção do fluxo é do receptor para o chamador.</span><span class="sxs-lookup"><span data-stu-id="dbd24-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

