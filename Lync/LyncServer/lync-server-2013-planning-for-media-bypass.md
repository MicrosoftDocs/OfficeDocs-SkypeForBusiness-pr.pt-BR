---
title: 'Lync Server 2013: Planejamento de bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa60b6658eca7a73e509a7f6c707c3cf48c7f16e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="e1e31-102">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1e31-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1e31-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e1e31-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e1e31-104">O bypass de mídia se refere a remover o servidor de mediação do caminho de mídia sempre que possível para chamadas cujo sinal percorre o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="e1e31-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="e1e31-105">O bypass de mídia pode aprimorar a qualidade da voz reduzindo a latência, conversões desnecessárias, possibilidade de perda de pacotes e o número de pontos de falha possíveis.</span><span class="sxs-lookup"><span data-stu-id="e1e31-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="e1e31-106">A escalabilidade pode ser aprimorada, pois a eliminação do processamento de mídia para chamadas ignoradas reduz a carga no servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="e1e31-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="e1e31-107">Essa redução na carga complementa a capacidade do servidor de mediação para controlar vários gateways.</span><span class="sxs-lookup"><span data-stu-id="e1e31-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="e1e31-108">Onde um site de filiais sem um servidor de mediação está conectado a um site central por um ou mais links WAN com largura de banda restrita, o bypass de mídia reduz a necessidade de largura de banda ao permitir que a mídia de um cliente em um site de filiais flua diretamente para seu gateway local sem Primeiro, é necessário fluir pelo link de WAN para um servidor de mediação no site central e para trás.</span><span class="sxs-lookup"><span data-stu-id="e1e31-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="e1e31-109">Ao enliberar o servidor de mediação do processamento de mídia, o bypass da mídia também pode reduzir o número de servidores de mediação que uma infraestrutura Enterprise Voice requer.</span><span class="sxs-lookup"><span data-stu-id="e1e31-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="e1e31-110">A figura a seguir exibe caminhos de mídia e sinalização básicos em topologias com e sem bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="e1e31-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="e1e31-111">**Caminhos de mídia e sinalização com e sem desvio de mídia**</span><span class="sxs-lookup"><span data-stu-id="e1e31-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="e1e31-112">![Aplicação de voz do CAC ignorando] a imposição de conexão (images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicação de voz do CAC ignorando") a imposição de conexão</span><span class="sxs-lookup"><span data-stu-id="e1e31-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="e1e31-113">Como regra geral, habilite o bypass de mídia sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="e1e31-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e1e31-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e1e31-114">In This Section</span></span>

  - [<span data-ttu-id="e1e31-115">Visão geral do bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1e31-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="e1e31-116">Modos de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1e31-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="e1e31-117">Bypass de mídia e controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1e31-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="e1e31-118">Requisitos técnicos para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1e31-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="e1e31-119">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="e1e31-119">Related Sections</span></span>

[<span data-ttu-id="e1e31-120">Implantação de recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1e31-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e1e31-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="e1e31-121">See Also</span></span>


[<span data-ttu-id="e1e31-122">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1e31-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="e1e31-123">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1e31-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

