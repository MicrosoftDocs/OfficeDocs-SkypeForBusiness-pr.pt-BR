---
title: 'Lync Server 2013: bypass de mídia e controle de admissão de chamadas'
description: 'Lync Server 2013: bypass de mídia e controle de admissão de chamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d2c28000b7ca9a25fe87cf0d0b4fc59e0ac6e3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556467"
---
# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a93f1-103">Bypass de mídia e controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93f1-103">Media bypass and call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a93f1-104">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="a93f1-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="a93f1-p101">O desvio de mídia e o controle de admissão de chamadas trabalham juntos para gerenciar o controle de largura de banda da mídia de chamadas. O desvio de mídia facilita o fluxo da mídia por links bem conectados, enquanto o controle de admissão de chamadas gerencia o tráfego nos links com limites de largura de banda. Como o Desvio de Mídia e o controle de admissão de chamadas são mutuamente exclusivos, você deve estar atento a um quando estiver planejando o outro. Há suporte para as seguintes combinações:</span><span class="sxs-lookup"><span data-stu-id="a93f1-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="a93f1-p102">CAC e Desvio de Mídia estão habilitados. O Desvio de Mídia deve estar definido como **Usar informações de site e da região**. As informações do site e da região são as mesmas usadas para o CAC.</span><span class="sxs-lookup"><span data-stu-id="a93f1-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="a93f1-p103">Se você habilitar o CAC, não pode selecionar **Desviar Sempre** e vice-versa porque as duas configurações são mutuamente exclusivas. Ou seja, somente uma das duas irá se aplicar a qualquer chamada de PSTN determinada. Primeiro, é realizada uma verificação para determinar se o desvio de mídia se aplica à chamada e, em caso afirmativo, não se usa o CAC. Isso faz sentido, porque se uma ligação for apta para desvio, ela está, por definição, usando uma conexão em que um CAC não é necessário. Se o desvio não pode ser aplicado à chamada (ou seja, se os IDs do desvio do cliente e do gateway não corresponderem), o CAC é aplicado à chamada.</span><span class="sxs-lookup"><span data-stu-id="a93f1-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="a93f1-118">CAC não habilitado e Desvio de Mídia definido como **Desviar Sempre**.</span><span class="sxs-lookup"><span data-stu-id="a93f1-118">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="a93f1-119">Nesta configuração, as sub-redes do cliente e do tronco são mapeadas a um único ID de desvio, que é computado pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="a93f1-119">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="a93f1-120">CAC não habilitado e Desvio de Mídia definido é definido como **Usar Informações do Site e da Região**.</span><span class="sxs-lookup"><span data-stu-id="a93f1-120">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="a93f1-p104">Onde **Usar Informações do Site e da Região** estiver disponível, a determinação do desvio funciona essencialmente da mesma maneira, independente de o CAC estar habilitado ou não. Ou seja, para qualquer chamada de PSTN determinada, a sub-rede do cliente é mapeada a um site em particular, e a ID de desvio dessa sub-rede é extraída. De maneira semelhante, a sub-rede do gateway é mapeada a um site particular, e a ID do desvio dessa sub-rede é extraída. Somente se duas IDs de desvio forem idênticas o desvio acontecerá para a chamada. Caso não sejam idênticas, o desvio de chamada não irá acontecer.</span><span class="sxs-lookup"><span data-stu-id="a93f1-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="a93f1-p105">Ainda que o CAC esteja desabilitado globalmente, a política de largura de banda precisa ser definida para cada site e link se você quiser usar a configuração site-e-região para controlar a decisão de desvio. O valor real da restrição da largura de banda ou da sua modalidade não importa. O objetivo final é que o sistema calcule automaticamente as IDs diferentes de desvio para associar aos locais diferentes que não estão bem conectados. Definir a restrição da largura de banda por definição significa que um link não está bem conectado.</span><span class="sxs-lookup"><span data-stu-id="a93f1-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="a93f1-130">O CAC está habilitado, mas o desvio de mídia não.</span><span class="sxs-lookup"><span data-stu-id="a93f1-130">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="a93f1-131">Isso se aplica apenas onde todos os gateways e IP-PBXs não estão bem conectados ou não atendem outros requisitos para desvio de mídia.</span><span class="sxs-lookup"><span data-stu-id="a93f1-131">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="a93f1-132">Para obter detalhes sobre os requisitos para bypass de mídia, consulte [Technical Requirements for Media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a93f1-132">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a93f1-133">Confira também</span><span class="sxs-lookup"><span data-stu-id="a93f1-133">See Also</span></span>


[<span data-ttu-id="a93f1-134">Visão geral do bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93f1-134">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="a93f1-135">Modos de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93f1-135">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="a93f1-136">Requisitos técnicos para bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a93f1-136">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

