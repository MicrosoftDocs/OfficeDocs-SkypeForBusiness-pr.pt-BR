---
title: 'Lync Server 2013: planejamento para bypass de mídia'
description: 'Lync Server 2013: planejamento para bypass de mídia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549437"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="b57ff-103">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57ff-103">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b57ff-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b57ff-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b57ff-105">Desvio de mídia refere-se à remoção do Servidor de Mediação do caminho da mídia, sempre que possível para chamadas cuja sinalização percorre o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="b57ff-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="b57ff-106">O desvio de mídia pode aprimorar a qualidade da voz reduzindo latência, conversões desnecessárias, possibilidade de perda de pacotes e o número de pontos de falha possíveis.</span><span class="sxs-lookup"><span data-stu-id="b57ff-106">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="b57ff-107">A escalabilidade pode ser aprimorada, porque a eliminação do processamento de mídia para chamadas desviadas reduz a carga no Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="b57ff-107">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="b57ff-108">Essa redução no carregamento complementa a capacidade do servidor de mediação controlar vários gateways.</span><span class="sxs-lookup"><span data-stu-id="b57ff-108">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="b57ff-109">Quando um site de filial sem um servidor de mediação estiver conectado a um site central por um ou mais links WAN com largura de banda restrita, o bypass de mídia reduzirá a necessidade de largura de banda permitindo que a mídia de um cliente em um site de filial flua diretamente para seu gateway local sem antes ter que fluir pelo link WAN para um servidor de mediação no site central e voltar</span><span class="sxs-lookup"><span data-stu-id="b57ff-109">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="b57ff-110">Ao aliviar o servidor de mediação do processamento de mídia, o bypass de mídia também pode reduzir o número de servidores de mediação exigidos por uma infraestrutura do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b57ff-110">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="b57ff-111">A figura a seguir exibe caminhos de mídia e sinalização básicos em topologias com e sem desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="b57ff-111">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="b57ff-112">**Caminhos de mídia e sinalização com e sem desvio de mídia**</span><span class="sxs-lookup"><span data-stu-id="b57ff-112">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="b57ff-113">![Imposição de conexão de mídia do CAC de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Imposição de conexão de mídia do CAC de voz")</span><span class="sxs-lookup"><span data-stu-id="b57ff-113">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="b57ff-114">Como regra geral, habilite o desvio de mídia onde possível.</span><span class="sxs-lookup"><span data-stu-id="b57ff-114">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b57ff-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b57ff-115">In This Section</span></span>

  - [<span data-ttu-id="b57ff-116">Visão geral do bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57ff-116">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="b57ff-117">Modos de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57ff-117">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="b57ff-118">Bypass de mídia e controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57ff-118">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="b57ff-119">Requisitos técnicos para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57ff-119">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="b57ff-120">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="b57ff-120">Related Sections</span></span>

[<span data-ttu-id="b57ff-121">Implantando recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57ff-121">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b57ff-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="b57ff-122">See Also</span></span>


[<span data-ttu-id="b57ff-123">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57ff-123">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="b57ff-124">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b57ff-124">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

