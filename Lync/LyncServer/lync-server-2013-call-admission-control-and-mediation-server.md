---
title: 'Lync Server 2013: Controle de admissão de chamada e Servidor de Mediação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="1bf7e-102">Controle de admissão de chamada e Servidor de Mediação no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bf7e-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bf7e-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1bf7e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1bf7e-104">O controle de admissão de chamadas (CAC), apresentado primeiro no Lync Server 2010, gerencia a determinação da sessão em tempo real, com base na largura de banda disponível, para ajudar a evitar má qualidade da experiência (QoE) para usuários em redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="1bf7e-105">Para dar suporte a esse recurso, o servidor de mediação, que fornece sinalização e conversão de mídia entre a infraestrutura Enterprise Voice e um gateway ou provedor de entroncamento SIP, é responsável pelo gerenciamento de largura de banda para suas duas interações no Lync Lado do servidor e no lado do gateway.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="1bf7e-106">No controle de admissão de chamadas, a entidade de terminação de uma chamada lida com a reserva de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="1bf7e-107">Os pares de gateway (gateway PSTN, IP-PBX, SBC) com o qual o servidor de mediação interage no lado do gateway não dão suporte ao controle de admissão de chamadas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="1bf7e-108">Portanto, o servidor de mediação precisa manipular interações de largura de banda em nome de seu peer de gateway.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="1bf7e-109">Sempre que possível, o servidor de mediação reservará largura de banda antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="1bf7e-110">Se isso não for possível (por exemplo, se a localidade do ponto de extremidade de mídia final no lado do gateway for desconhecido de uma chamada de saída para o par de gateway), a largura de banda será reservada quando a chamada for feita.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="1bf7e-111">Esse comportamento poderá resultar em uma inscrição em excesso de assinatura da largura de banda, mas é a única maneira de impedir anéis falsos.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="1bf7e-112">O bypass de mídia e a reserva de largura de banda são mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="1bf7e-113">Se um bypass de mídia for empregado para uma chamada, o controle de admissão de chamadas não será executado para essa chamada.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="1bf7e-114">Presume-se que não haja links envolvidos na chamada com a largura de banda restrita.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="1bf7e-115">Se o controle de admissão de chamadas for usado para uma chamada específica que envolva o servidor de mediação, essa chamada não poderá empregar o bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="1bf7e-116">Para obter detalhes sobre o bypass de mídia ou o controle de admissão de chamadas, consulte [planejando a bypass de mídia no Lync server 2013](lync-server-2013-planning-for-media-bypass.md) ou [planejando o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="1bf7e-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

