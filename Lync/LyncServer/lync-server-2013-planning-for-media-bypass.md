---
title: 'Lync Server 2013: planejamento para bypass de mídia'
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
ms.openlocfilehash: de3d5132d7307f48de905f5bb6d28e53cbec14a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="2b2a3-102">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2a3-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b2a3-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2b2a3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2b2a3-104">Desvio de mídia refere-se à remoção do Servidor de Mediação do caminho da mídia, sempre que possível para chamadas cuja sinalização percorre o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="2b2a3-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="2b2a3-105">O desvio de mídia pode aprimorar a qualidade da voz reduzindo latência, conversões desnecessárias, possibilidade de perda de pacotes e o número de pontos de falha possíveis.</span><span class="sxs-lookup"><span data-stu-id="2b2a3-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="2b2a3-106">A escalabilidade pode ser aprimorada, porque a eliminação do processamento de mídia para chamadas desviadas reduz a carga no Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="2b2a3-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="2b2a3-107">Essa redução no carregamento complementa a capacidade do servidor de mediação controlar vários gateways.</span><span class="sxs-lookup"><span data-stu-id="2b2a3-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="2b2a3-108">Quando um site de filial sem um servidor de mediação estiver conectado a um site central por um ou mais links WAN com largura de banda restrita, o bypass de mídia reduzirá a necessidade de largura de banda permitindo que a mídia de um cliente em um site de filial flua diretamente para seu gateway local sem Primeiro, é necessário fluir através do link WAN para um servidor de mediação no site central e para trás.</span><span class="sxs-lookup"><span data-stu-id="2b2a3-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="2b2a3-109">Ao aliviar o servidor de mediação do processamento de mídia, o bypass de mídia também pode reduzir o número de servidores de mediação exigidos por uma infraestrutura do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2b2a3-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="2b2a3-110">A figura a seguir exibe caminhos de mídia e sinalização básicos em topologias com e sem desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="2b2a3-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="2b2a3-111">**Caminhos de mídia e sinalização com e sem desvio de mídia**</span><span class="sxs-lookup"><span data-stu-id="2b2a3-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="2b2a3-112">![Imposição de conexão de mídia do CAC de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Imposição de conexão de mídia do CAC de voz")</span><span class="sxs-lookup"><span data-stu-id="2b2a3-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="2b2a3-113">Como regra geral, habilite o desvio de mídia onde possível.</span><span class="sxs-lookup"><span data-stu-id="2b2a3-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2b2a3-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2b2a3-114">In This Section</span></span>

  - [<span data-ttu-id="2b2a3-115">Visão geral do bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2a3-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="2b2a3-116">Modos de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2a3-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="2b2a3-117">Bypass de mídia e controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2a3-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="2b2a3-118">Requisitos técnicos para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2a3-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="2b2a3-119">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="2b2a3-119">Related Sections</span></span>

[<span data-ttu-id="2b2a3-120">Implantando recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2a3-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b2a3-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="2b2a3-121">See Also</span></span>


[<span data-ttu-id="2b2a3-122">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2a3-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="2b2a3-123">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b2a3-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

