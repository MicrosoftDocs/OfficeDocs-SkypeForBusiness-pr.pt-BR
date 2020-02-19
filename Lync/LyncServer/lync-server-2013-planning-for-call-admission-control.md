---
title: 'Lync Server 2013: planejamento para controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c89b289158b36aa811e09e9db628850693dac5a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a66cb-102">Planejando o controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66cb-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a66cb-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a66cb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a66cb-104">Para aplicativos UC (comunicações unificadas) que são baseados em IP, como telefonia, vídeo e compartilhamento de aplicativos, a largura de banda disponível de redes corporativas não é geralmente considerada um fator de limitação em ambientes de LAN.</span><span class="sxs-lookup"><span data-stu-id="a66cb-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="a66cb-105">No entanto, nos links WAN que interconectam sites, a largura de banda da rede pode ser limitada.</span><span class="sxs-lookup"><span data-stu-id="a66cb-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="a66cb-106">Quando um influxo de tráfego de rede se inscreve em um link de WAN, mecanismos atuais, como enfileiramento, armazenamento em buffer e descarte de pacotes, são usados para resolver o congestionamento.</span><span class="sxs-lookup"><span data-stu-id="a66cb-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="a66cb-107">O tráfego extra costuma atrasar até que o congestionamento da rede facilite ou, se necessário, o tráfego seja Descartado.</span><span class="sxs-lookup"><span data-stu-id="a66cb-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="a66cb-108">Para o tráfego de dados convencionais nessas situações, o cliente de recebimento pode se recuperar.</span><span class="sxs-lookup"><span data-stu-id="a66cb-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="a66cb-109">Para tráfego em tempo real, como comunicação unificada, o congestionamento da rede não pode ser resolvido dessa maneira, porque o tráfego de comunicação unificado é confidencial para a latência e perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="a66cb-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="a66cb-110">O congestionamento na WAN pode resultar em má qualidade da experiência (QoE) para os usuários.</span><span class="sxs-lookup"><span data-stu-id="a66cb-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="a66cb-111">Para tráfego em tempo real em condições congestionadas, é melhor negar chamadas do que fornecer conexões com qualidade ruim.</span><span class="sxs-lookup"><span data-stu-id="a66cb-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="a66cb-112">O CAC (controle de admissão de chamadas) determina se há largura de banda de rede suficiente para estabelecer uma sessão em tempo real de qualidade aceitável.</span><span class="sxs-lookup"><span data-stu-id="a66cb-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="a66cb-113">No Lync Server 2013, o CAC controla o tráfego em tempo real somente para áudio e vídeo, mas não afeta o tráfego de dados.</span><span class="sxs-lookup"><span data-stu-id="a66cb-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="a66cb-114">Se o caminho de WAN padrão não tiver a largura de banda necessária, o CAC pode tentar rotear a chamada através de um caminho da Internet ou da rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="a66cb-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="a66cb-115">O CAC está disponível somente no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a66cb-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="a66cb-116">Esta seção descreve a funcionalidade de controle de admissão de chamada e explica como planejar o CAC.</span><span class="sxs-lookup"><span data-stu-id="a66cb-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a66cb-117">O Lync Server tem três recursos avançados do Enterprise Voice: controle de admissão de chamadas (CAC), serviços de emergência (E9-1-1) e bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="a66cb-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="a66cb-118">Para obter uma visão geral das informações de planejamento comuns a todos os três recursos, consulte <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configurações de rede para os recursos avançados do Enterprise Voice no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a66cb-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a66cb-119">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a66cb-119">In This Section</span></span>

  - [<span data-ttu-id="a66cb-120">Visão geral do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66cb-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="a66cb-121">Definindo seus requisitos de controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66cb-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="a66cb-122">Exemplo: coletando seus requisitos para controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66cb-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="a66cb-123">Componentes e topologias para CAC no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66cb-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="a66cb-124">Práticas recomendadas para controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66cb-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="a66cb-125">Lista de verificação de implantação para controle de admissão de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a66cb-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

