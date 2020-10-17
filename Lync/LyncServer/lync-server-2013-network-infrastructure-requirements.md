---
title: Requisitos de infraestrutura de rede do Lync Server 2013
description: Requisitos de infraestrutura de rede do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7ff21c2f936ef8e048f6831d55408994055400
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561497"
---
# <a name="network-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="9faf5-103">Requisitos de infraestrutura de rede para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9faf5-103">Network infrastructure requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9faf5-104">_**Última modificação do tópico:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="9faf5-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="9faf5-105">A placa de adaptador de rede de cada servidor na topologia do Lync Server 2013 deve suportar pelo menos 1 gigabit por segundo (Gbps).</span><span class="sxs-lookup"><span data-stu-id="9faf5-105">The network adapter card of each server in the Lync Server 2013 topology must support at least 1 gigabit per second (Gbps).</span></span> <span data-ttu-id="9faf5-106">Em geral, você deve conectar todas as funções de servidor dentro da topologia do Lync Server usando uma rede local de baixa latência e alta largura de banda (LAN).</span><span class="sxs-lookup"><span data-stu-id="9faf5-106">In general, you should connect all server roles within the Lync Server topology using a low latency and high bandwidth local area network (LAN).</span></span> <span data-ttu-id="9faf5-107">O tamanho da LAN depende do tamanho da topologia:</span><span class="sxs-lookup"><span data-stu-id="9faf5-107">The size of the LAN is dependent on the size of the topology:</span></span>

  - <span data-ttu-id="9faf5-108">Nas topologias do Standard Edition, os servidores devem estar em uma rede que ofereça suporte a Ethernet de 1 Gbps ou equivalente.</span><span class="sxs-lookup"><span data-stu-id="9faf5-108">In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.</span></span>

  - <span data-ttu-id="9faf5-109">Nas topologias do pool de front-ends, a maioria dos servidores deve estar em uma rede que ofereça suporte a mais de 1 Gbps, especialmente quando houver suporte para conferência de áudio/vídeo (A/V) e compartilhamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="9faf5-109">In Front End pool topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.</span></span>

<span data-ttu-id="9faf5-110">Para a integração com PSTN, você pode usar linhas T1/E1 ou troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="9faf5-110">For public switched telephone network (PSTN) integration, you can integrate by using either T1/E1 lines or SIP trunking.</span></span>

<div>

## <a name="audiovideo-network-requirements"></a><span data-ttu-id="9faf5-111">Requisitos de rede para áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="9faf5-111">Audio/Video Network Requirements</span></span>

<span data-ttu-id="9faf5-112">Os requisitos de rede para áudio/vídeo (A/V) em uma implantação do Lync Server incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9faf5-112">Network requirements for audio/video (A/V) in a Lync Server deployment include the following:</span></span>

  - <span data-ttu-id="9faf5-113">Se você estiver implantando um único servidor de borda ou um pool de borda usando o balanceamento de carga DNS, é possível configurar o firewall externo como NAT.</span><span class="sxs-lookup"><span data-stu-id="9faf5-113">If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the external firewall as a NAT.</span></span> <span data-ttu-id="9faf5-114">Você não pode configurar o firewall interno como NAT.</span><span class="sxs-lookup"><span data-stu-id="9faf5-114">You cannot configure the internal firewall as a NAT.</span></span> <span data-ttu-id="9faf5-115">Para obter detalhes sobre esses requisitos, consulte [determine external A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="9faf5-115">For details about these requirements, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in the Planning documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9faf5-116">Se você tiver um pool de borda e estiver usando um balanceador de carga de hardware, você deverá usar endereços IP públicos em cada um dos servidores de borda e não poderá usar o NAT para os servidores ou o pool no seu dispositivo NAT (por exemplo, o firewall ou outro dispositivo de infraestrutura que iria fazer o tráfego de entrada ou saída).</span><span class="sxs-lookup"><span data-stu-id="9faf5-116">If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on each of the Edge Servers and you cannot use NAT for the servers or the pool at your NAT device (for example, the firewall, or other infrastructure device that would NAT inbound or outbound traffic).</span></span> <span data-ttu-id="9faf5-117">Para obter detalhes, consulte <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">port SUMMARY-escalada Consolidated Edge with hardware Load balancers in Lync Server 2013</A> na documentação Planning for External User Access.</span><span class="sxs-lookup"><span data-stu-id="9faf5-117">For details, see <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A> in the Planning for External User Access documentation.</span></span>

    
    </div>

  - <span data-ttu-id="9faf5-118">Caso sua organização use uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia estará projetado para operar dentro dessa infraestrutura existente.</span><span class="sxs-lookup"><span data-stu-id="9faf5-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span>

  - <span data-ttu-id="9faf5-119">Caso você utilize o protocolo IPsec, é recomendável desabilitá-lo nos intervalos de portas usados para o tráfego de A/V.</span><span class="sxs-lookup"><span data-stu-id="9faf5-119">If you use Internet Protocol security (IPsec), we recommend disabling IPsec over the port ranges used for A/V traffic.</span></span> <span data-ttu-id="9faf5-120">Para obter detalhes, consulte [exceções de IPsec no Lync Server 2013](lync-server-2013-ipsec-exceptions.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="9faf5-120">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

<span data-ttu-id="9faf5-121">Para garantir a melhor qualidade da mídia, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="9faf5-121">To ensure optimal media quality, do the following:</span></span>

  - <span data-ttu-id="9faf5-p105">Provisione os vínculos da rede para dar suporte a uma taxa de transferência de 65 Kbps (quilobits por segundo) por fluxo de áudio e 500 Kbps por fluxo de vídeo, se estiver habilitado, durante os períodos de uso máximo. Uma sessão de áudio ou vídeo bidirecional consiste em dois fluxos.</span><span class="sxs-lookup"><span data-stu-id="9faf5-p105">Provision your network links to support throughput of 65 kilobits per second (Kbps) per audio stream and 500 Kbps per video stream, if enabled, during peak usage periods. A bidirectional audio or video session consists of two streams.</span></span>

  - <span data-ttu-id="9faf5-124">Para lidar com picos inesperados no tráfego acima desse nível e maior uso com o passar do tempo, os pontos de extremidade de mídia do Lync Server podem se adaptar às diferentes condições de rede e às cargas de suporte de três vezes a taxa de transferência (consulte o parágrafo anterior) para áudio e vídeo enquanto ainda mantém a qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="9faf5-124">To cope with unexpected spikes in traffic above this level and increased usage over time, Lync Server media endpoints can adapt to varying network conditions and support loads of three times the throughput (see previous paragraph) for audio and video while still retaining acceptable quality.</span></span> <span data-ttu-id="9faf5-125">No entanto, não presuma que essa adaptabilidade suportará uma rede subprovisionada.</span><span class="sxs-lookup"><span data-stu-id="9faf5-125">However, do not assume that this adaptability will support an under-provisioned network.</span></span> <span data-ttu-id="9faf5-126">Em uma rede subvisionada, a capacidade dos pontos de extremidade de mídia do Lync Server de lidar dinamicamente com condições de rede variáveis (por exemplo, perda de pacote de alta capacidade temporária) é reduzida.</span><span class="sxs-lookup"><span data-stu-id="9faf5-126">In an under-provisioned network, the ability of the Lync Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.</span></span>

  - <span data-ttu-id="9faf5-127">Para vínculos de rede em que o provisionamento envolve altíssimo custo e dificuldade, considere a opção de provisionar para um volume menor de tráfego.</span><span class="sxs-lookup"><span data-stu-id="9faf5-127">For network links where provisioning is extremely costly and difficult, you may need to consider provisioning for a lower volume of traffic.</span></span> <span data-ttu-id="9faf5-128">Neste cenário, deixe a elasticidade dos pontos de extremidade de mídia do Lync Server absorver a diferença entre o volume de tráfego e o nível de tráfego de pico, ao custo de alguma redução na qualidade de voz.</span><span class="sxs-lookup"><span data-stu-id="9faf5-128">In this scenario, let the elasticity of the Lync Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality.</span></span> <span data-ttu-id="9faf5-129">Além disso, há uma diminuição na reserva dinâmica que, de outra forma, estaria disponível para absorver picos súbitos de tráfego.</span><span class="sxs-lookup"><span data-stu-id="9faf5-129">Also, there is a decrease in the headroom otherwise available to absorb sudden peaks in traffic.</span></span>

  - <span data-ttu-id="9faf5-130">Para os vínculos que não podem ser provisionados corretamente a curto prazo (por exemplo, um local com vínculos de WAN de péssima qualidade), considere a possibilidade de desabilitar o vídeo para determinados usuários.</span><span class="sxs-lookup"><span data-stu-id="9faf5-130">For links that cannot be correctly provisioned in the short term (for example, a site with very poor WAN links), consider disabling video for certain users.</span></span>

  - <span data-ttu-id="9faf5-131">Provisione sua rede para assegurar um atraso máximo de ponta a ponta (latência) de 150 ms (milissegundos) sob carga máxima.</span><span class="sxs-lookup"><span data-stu-id="9faf5-131">Provision your network to ensure a maximum end-to-end delay (latency) of 150 milliseconds (ms) under peak load.</span></span> <span data-ttu-id="9faf5-132">Latência é a única deficiência da rede que os componentes de mídia do Lync Server não podem reduzir e é importante encontrar e eliminar os pontos fracos.</span><span class="sxs-lookup"><span data-stu-id="9faf5-132">Latency is the one network impairment that Lync Server media components cannot reduce, and it is important to find and eliminate the weak points.</span></span>

  - <span data-ttu-id="9faf5-133">Para servidores que executam software antivírus, inclua todos os servidores que executam o Lync Server na lista de exceções a fim de fornecer desempenho e qualidade de áudio ideais.</span><span class="sxs-lookup"><span data-stu-id="9faf5-133">For servers running antivirus software, include all servers running Lync Server in the exception list in order to provide optimal performance and audio quality.</span></span>

</div>

<div>

## <a name="conferencing-network-requirements"></a><span data-ttu-id="9faf5-134">Requisitos da Rede de Conferência</span><span class="sxs-lookup"><span data-stu-id="9faf5-134">Conferencing Network Requirements</span></span>

<span data-ttu-id="9faf5-135">A largura de banda usada para baixar o conteúdo da conferência do servidor de serviços de informações da Internet (IIS) depende do tamanho do conteúdo carregado.</span><span class="sxs-lookup"><span data-stu-id="9faf5-135">The bandwidth that is used to download conference content from the Internet Information Services (IIS) server depends on the size of the content that is uploaded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

