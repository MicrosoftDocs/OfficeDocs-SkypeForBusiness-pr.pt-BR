---
title: 'Lync Server 2013: visão geral do bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66c2484b656cce15a6f7d013060c1fc95047f49d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="c81ed-102">Visão geral do bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81ed-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c81ed-103">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c81ed-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c81ed-104">O bypass de mídia é útil quando você deseja minimizar o número de Servidores de Mediação implantados.</span><span class="sxs-lookup"><span data-stu-id="c81ed-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="c81ed-105">Geralmente, um pool de Servidores de Mediação será implantado em um site central e controlará os gateways em sites locais.</span><span class="sxs-lookup"><span data-stu-id="c81ed-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="c81ed-106">Habilitar o bypass de mídia permite que a mídia para chamadas PSTN de clientes em sites locais flua diretamente pelos gateways para estes sites.</span><span class="sxs-lookup"><span data-stu-id="c81ed-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="c81ed-107">Os roteamentos de chamadas de saída do Lync Server 2013 e as políticas do Enterprise Voice devem ser configurados corretamente para que chamadas PSTN de clientes em um site de filial sejam roteadas para o gateway apropriado.</span><span class="sxs-lookup"><span data-stu-id="c81ed-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="c81ed-p102">As redes Wi-Fi geralmente enfrentam uma maior perda de pacotes do que as redes com fio. A recuperação desta perda de pacotes não é algo que geralmente possa ser acomodado por gateways. Assim, recomendamos a avaliação da qualidade da rede Wi-Fi antes de determinar se o bypass deve estar habilitado para uma sub-rede sem fio. Há uma compensação na redução da latência contra a recuperação da perda de pacotes a considerar. RTAudio, um codec disponível para chamadas que não ignorem o Servidor de Mediação, é mais adequado para tratar da perda de pacotes.</span><span class="sxs-lookup"><span data-stu-id="c81ed-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="c81ed-113">Após a estrutura do seu Enterprise Voice estiver inserida, o planejamento do bypass de mídia é aberto.</span><span class="sxs-lookup"><span data-stu-id="c81ed-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="c81ed-114">Se você possui uma topologia centralizada sem links WAN para sites de filiais, é possível habilitar o bypass de mídia global, pois é necessário um ajuste refinado.</span><span class="sxs-lookup"><span data-stu-id="c81ed-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="c81ed-115">Se você não possui uma topologia distribuída que consiste de uma ou mais regiões de rede e seus sites de filiais associados, determine o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c81ed-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="c81ed-116">Se os seus colegas do Servidor de Mediação podem suportar as capacidades necessárias para bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="c81ed-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="c81ed-117">Quais sites em cada região de rede estão bem conectados.</span><span class="sxs-lookup"><span data-stu-id="c81ed-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="c81ed-118">Qual combinação de bypass de mídia e controle de admissão de chamada é adequada para sua rede.</span><span class="sxs-lookup"><span data-stu-id="c81ed-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="c81ed-p103">Quando o desvio de mídia é habilitado, um ID de desvio exclusivo é gerado automaticamente para uma região de rede e para todos os sites de rede sem limites de largura de banda nessa região. Os sites com limites de largura de banda na região e os sites conectados à região por links WAN com limites de largura de banda obtêm seus próprios IDs de desvio exclusivos.</span><span class="sxs-lookup"><span data-stu-id="c81ed-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="c81ed-121">Quando um usuário faz uma chamada para a PSTN, o servidor de mediação compara a ID de bypass da sub-rede do cliente com a ID de bypass da sub-rede do gateway.</span><span class="sxs-lookup"><span data-stu-id="c81ed-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="c81ed-122">Se os dois IDs de desvio forem correspondentes, o desvio de mídia será usado para a chamada.</span><span class="sxs-lookup"><span data-stu-id="c81ed-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="c81ed-123">Se as IDs de bypass não corresponderem, a mídia para a chamada deverá fluir pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c81ed-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="c81ed-124">Quando um usuário recebe uma chamada do PSTN, o cliente do usuário compara seu ID de desvio com aquele do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="c81ed-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="c81ed-125">Se as duas IDs de bypass corresponderem, a mídia fluirá diretamente do gateway para o cliente, ignorando o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c81ed-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="c81ed-126">Somente os clientes e dispositivos do Lync 2010 ou superior dão suporte à interações de bypass de mídia com um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="c81ed-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c81ed-p106">Além de habilitar o bypass de mídia globalmente, é necessário habilitar o bypass de mídia individualmente em cada tronco PSTN. Se o bypass estiver habilitado globalmente, mas não estiver habilitado para um determinado tronco PSTN, o bypass de mídia não será invocado para qualquer chamada envolvendo aquele tronco PSTN. Além disso, quando o bypass de mídia é definido para <STRONG>Usar a informação do site e da região</STRONG>, é necessário associar todas as sub-redes roteáveis com os sites nos quais estão localizadas. Se há sub-redes roteáveis dentro de um site no qual o bypass não é desejado, estas sub-redes devem ser agrupadas dentro de um novo site antes de habilitar o bypass de mídia. Fazer isso garantirá que as sub-redes não roteáveis sejam atribuídas com uma ID de bypass diferente.
</span><span class="sxs-lookup"><span data-stu-id="c81ed-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c81ed-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="c81ed-132">See Also</span></span>


[<span data-ttu-id="c81ed-133">Modos de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81ed-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="c81ed-134">Bypass de mídia e controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81ed-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="c81ed-135">Requisitos técnicos para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c81ed-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

