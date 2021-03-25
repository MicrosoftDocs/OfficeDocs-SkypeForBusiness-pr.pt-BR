---
title: Componentes e topologias para controle de admissão de chamadas no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planejando o controle de admissão de chamada (CAC) se você tiver uma rede MPLS, um tronco SIP ou um gateway PSTN de terceiros ou PBX. Aplica-se ao Skype for Business Server Enterprise Voice.
ms.openlocfilehash: 771b98e10c28248bc917bff2b8128b6258c140c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109187"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="6c963-104">Componentes e topologias para controle de admissão de chamadas no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6c963-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="6c963-105">Planejando o controle de admissão de chamada (CAC) se você tiver uma rede MPLS, um tronco SIP ou um gateway PSTN de terceiros ou PBX.</span><span class="sxs-lookup"><span data-stu-id="6c963-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="6c963-106">Aplica-se ao Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6c963-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="6c963-107">Os tópicos nesta seção fornecem informações sobre considerações especiais para implantar o CAC (controle de admissão de chamada) com vários tipos de topologias de rede.</span><span class="sxs-lookup"><span data-stu-id="6c963-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="6c963-108">Controle de admissão de chamada em uma rede MPLS</span><span class="sxs-lookup"><span data-stu-id="6c963-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="6c963-p103">Em uma rede de Comutação de Rótulo Multiprotocolo (MPLS), todos os sites são conectados por uma malha completa. Isto é, todos os sites são conectados diretamente à nuvem MPLS, e cada site é provisionado com largura de banda a ser usada em um link WAN para a nuvem MPLS. Não existe hub de rede nem local central para controlar o roteamento IP. A figura abaixo mostra uma rede simples com base na tecnologia MPLS.</span><span class="sxs-lookup"><span data-stu-id="6c963-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="6c963-113">**Exemplo de rede MPLS**</span><span class="sxs-lookup"><span data-stu-id="6c963-113">**Example MPLS network**</span></span>

![CAC com MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="6c963-p104">Para implantar um controle de admissão de chamada (CAC) em uma rede MPLS, é preciso criar uma região de rede para representar a nuvem MPLS, bem como criar um site de rede para representar cada site de satélite MPLS. A figura a seguir ilustra como a região de rede e os sites de rede devem ser configurados para representar a rede MPLS de exemplo na figura anterior. Os limites gerais da largura de banda e os limites de sessão da largura de banda têm base na capacidade do link WAN a partir de cada site de rede até a região de rede que representa a nuvem MPLS.</span><span class="sxs-lookup"><span data-stu-id="6c963-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="6c963-118">**Região de rede e sites de rede para uma rede MPLS**</span><span class="sxs-lookup"><span data-stu-id="6c963-118">**Network region and network sites for an MPLS network**</span></span>

![Cac (Controle de Admissão de Chamada) com diagrama MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="6c963-120">Controle de admissão de chamada em um tronco SIP</span><span class="sxs-lookup"><span data-stu-id="6c963-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="6c963-p105">Para implantar o controle de admissão de chamadas em um tronco SIP, crie um local de rede para representar o ITSP (provedor de serviço de telefonia da Internet). Para aplicar valores de política de largura de banda no tronco SIP, crie uma política entre locais entre o local de rede na sua empresa e o local de rede criado para representar o ITSP.</span><span class="sxs-lookup"><span data-stu-id="6c963-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="6c963-123">A figura a seguir mostra um exemplo de implantação do CAC em um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="6c963-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="6c963-124">**Configuração do CAC em um tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="6c963-124">**CAC configuration on a SIP trunk**</span></span>

![Diagrama de tronco SIP do Controle de Admissão de Chamada](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="6c963-126">Para configurar o CAC em um tronco SIP, você terá que executar as seguintes tarefas durante a implantação do CAC:</span><span class="sxs-lookup"><span data-stu-id="6c963-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="6c963-127">Crie um site de rede para representar o ITSP.</span><span class="sxs-lookup"><span data-stu-id="6c963-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="6c963-128">Associe o site de rede a uma região de rede apropriada e aloque a largura de banda de zero para áudio e vídeo para este site de rede.</span><span class="sxs-lookup"><span data-stu-id="6c963-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="6c963-129">Para obter detalhes, consulte [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6c963-129">For details, see [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6c963-130">Para o ITSP, essa configuração de site de rede não funciona.</span><span class="sxs-lookup"><span data-stu-id="6c963-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="6c963-131">Os valores da política de largura de banda são, na verdade, aplicados na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="6c963-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="6c963-132">Crie um link entre sites para o tronco SIP usando os valores de parâmetro relevantes para o site criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="6c963-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="6c963-133">Por exemplo, use o nome do site de rede na sua empresa como o valor do parâmetro NetworkSiteID1 e o site de rede ITSP como o valor do parâmetro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="6c963-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="6c963-134">Para obter detalhes, [consulte Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6c963-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="6c963-135">Obter o endereço IP do Ponto de Terminação de Mídia do Controlador de Borda de Sessão (SCB) de seu ITSP.</span><span class="sxs-lookup"><span data-stu-id="6c963-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="6c963-136">Adicione o endereço IP com uma máscara de sub-rede de 32 para o site de rede que representa o ITSP.</span><span class="sxs-lookup"><span data-stu-id="6c963-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="6c963-137">Para obter detalhes, consulte [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span><span class="sxs-lookup"><span data-stu-id="6c963-137">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="6c963-138">Controle de admissão de chamada com um gateway PSTN de terceiros ou PBX</span><span class="sxs-lookup"><span data-stu-id="6c963-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="6c963-139">Este tópico descreve exemplos de como o controle de admissão de chamadas (CAC) pode ser implantado no link entre a interface de gateway do Servidor de Mediação e um gateway PSTN (rede telefônica pública comutado) de terceiros ou pbx (private branch exchange).</span><span class="sxs-lookup"><span data-stu-id="6c963-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="6c963-140">Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="6c963-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="6c963-141">O CAC pode ser implantado no link WAN da interface de gateway do Servidor de Mediação para um PBX ou gateway PSTN de terceiros.</span><span class="sxs-lookup"><span data-stu-id="6c963-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="6c963-142">**Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN**</span><span class="sxs-lookup"><span data-stu-id="6c963-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Caso 1: CAC entre Gateway PSTN do Servidor de Mediação](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="6c963-144">Neste exemplo, o CAC é aplicado entre o Servidor de Mediação e um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="6c963-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="6c963-145">Se um usuário cliente do Skype for Business no Site da Rede 1 fazer uma chamada PSTN por meio do gateway PSTN no Site da Rede 2, a mídia flui pelo link WAN.</span><span class="sxs-lookup"><span data-stu-id="6c963-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="6c963-146">Portanto, duas verificações CAC são executadas para cada sessão PSTN:</span><span class="sxs-lookup"><span data-stu-id="6c963-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="6c963-147">Entre o aplicativo cliente Skype for Business e o Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="6c963-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="6c963-148">Entre o Servidor de Mediação e o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="6c963-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="6c963-149">Isto funciona para as chamadas PSTN de entrada para um cliente no Local de Rede 1 e para chamadas PSTN de saída provenientes de um aplicativo cliente no Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="6c963-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-150">Certifique-se de que a sub-rede do IP ao qual o gateway PSTN pertence está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="6c963-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-151">Certifique-se de que a sub-rede do IP à qual ambas as interfaces do Servidor de Mediação pertencem está configurada e associada ao Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="6c963-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-152">Para obter detalhes, consulte [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span><span class="sxs-lookup"><span data-stu-id="6c963-152">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="6c963-153">Caso 2: CAC entre o Servidor de Mediação e um PBX de terceiros com Ponto de Terminação de Mídia</span><span class="sxs-lookup"><span data-stu-id="6c963-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="6c963-p111">Esta configuração é similar ao Caso 1. Em ambos os casos, o Servidor de Mediação sabe qual dispositivo termina mídia no ponto oposto do link WAN e o endereço IP do gateway PSTN ou PBX com Ponto de Terminação de Mídia (MTP) está configurado no Servidor de Mediação como próximo salto.</span><span class="sxs-lookup"><span data-stu-id="6c963-p111">This configuration is similar to Case 1. In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="6c963-156">**Caso 2: CAC entre o Servidor de Mediação e um PBX de terceiros com MTP**</span><span class="sxs-lookup"><span data-stu-id="6c963-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Caso 2: CAC entre o PBX do Servidor de Mediação com MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="6c963-158">Neste exemplo, o CAC é aplicado entre o Servidor de Mediação e o PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="6c963-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="6c963-159">Se um usuário cliente do Skype for Business no Site da Rede 1 faz uma chamada PSTN por meio do PBX/MTP localizado no Site da Rede 2, a mídia flui através do link WAN.</span><span class="sxs-lookup"><span data-stu-id="6c963-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="6c963-160">Portanto, para cada sessão PSTN duas verificações CAC são executadas:</span><span class="sxs-lookup"><span data-stu-id="6c963-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="6c963-161">Entre o aplicativo cliente Skype for Business e o Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="6c963-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="6c963-162">Entre o Servidor de Mediação e o PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="6c963-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="6c963-163">Isto funciona para ambas, chamadas PSTN de entrada para um cliente no Local de Rede 1 e chamadas PSTN de saída provenientes de um cliente no Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="6c963-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-164">Certifique-se de que a sub-rede do IP à qual o MTP pertence está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="6c963-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-165">Certifique-se de que a sub-rede do IP à qual ambas as interfaces do Servidor de Mediação pertencem está configurada e associada ao Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="6c963-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-166">Para obter detalhes, consulte [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span><span class="sxs-lookup"><span data-stu-id="6c963-166">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="6c963-167">Caso 3: CAC entre o Servidor de Mediação e um PBX de terceiros sem um Ponto de Terminação de Mídia</span><span class="sxs-lookup"><span data-stu-id="6c963-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="6c963-p113">O Caso 3 é um ligeiramente diferente dos dois primeiros. Se não houver MTP no PBX de terceiros para uma solicitação de sessão de saída para o PBX de terceiros, o Servidor de Mediação não saberá onde a mídia terminará no limite do PBX. Neste caso, a mídia flui diretamente entre o Servidor de Mediação e o dispositivo de ponto de extremidade de terceiros.</span><span class="sxs-lookup"><span data-stu-id="6c963-p113">Case 3 is slightly different from the first two cases. If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary. In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="6c963-171">**Caso 3: CAC entre o Servidor de Mediação e um PBX de terceiros sem MTP**</span><span class="sxs-lookup"><span data-stu-id="6c963-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Caso 3: CAC entre o SERVIDOR de Mediação PBX sem MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="6c963-173">Neste exemplo, se um usuário cliente do Skype for Business no Site da Rede 1 faz uma chamada para um usuário por meio do PBX, o Servidor de Mediação poderá executar verificações de CAC somente na etapa proxy (entre o aplicativo cliente skype for Business e o Servidor de Mediação).</span><span class="sxs-lookup"><span data-stu-id="6c963-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="6c963-174">Como o Servidor de Mediação não tem informações sobre o dispositivo de ponto de extremidade enquanto a sessão está sendo solicitada, verificações CAC não podem ser executadas no link WAN (entre o Servidor de Mediação e um ponto de extremidade de terceiros) antes do estabelecimento da chamada.</span><span class="sxs-lookup"><span data-stu-id="6c963-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="6c963-175">Depois que a sessão é estabelecida, no entanto, o Servidor de Mediação facilita na contabilização da largura de banda usada no tronco.</span><span class="sxs-lookup"><span data-stu-id="6c963-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="6c963-176">Para chamadas provenientes do ponto de extremidade de terceiros, a informação sobre este dispositivo está disponível no momento da solicitação da sessão e a verificação CAC pode ser executada em ambos os lados do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="6c963-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-177">Certifique-se de que a sub-rede do IP à qual os dispositivos de ponto de extremidade pertencem está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="6c963-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-178">Certifique-se de que a sub-rede do IP à qual ambas as interfaces do Servidor de Mediação pertencem está configurada e associada ao Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="6c963-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="6c963-179">Para obter detalhes, consulte [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span><span class="sxs-lookup"><span data-stu-id="6c963-179">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>