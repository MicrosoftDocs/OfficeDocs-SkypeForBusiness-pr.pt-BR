---
title: Componentes e topologias para chamar o controle de admissão no Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: Planejamento do CAC (controle de admissão de chamadas) se você tiver uma rede MPLS, um tronco SIP ou um gateway PSTN de terceiros ou PBX. Aplica-se à Skype para o Business Server Enterprise Voice.
ms.openlocfilehash: f43b111d0ef3260c34b53e27a903de20fdf676ef
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887669"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="86a50-104">Componentes e topologias para chamar o controle de admissão no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="86a50-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="86a50-105">Planejamento do CAC (controle de admissão de chamadas) se você tiver uma rede MPLS, um tronco SIP ou um gateway PSTN de terceiros ou PBX.</span><span class="sxs-lookup"><span data-stu-id="86a50-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="86a50-106">Aplica-se à Skype para o Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="86a50-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="86a50-107">Os tópicos desta seção oferecem informações sobre considerações especiais para implantar o serviço de controle de admissão de chamadas (CAC) em vários tipos de topologias de rede.</span><span class="sxs-lookup"><span data-stu-id="86a50-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="86a50-108">Controle de admissão de chamadas em uma rede MPLS</span><span class="sxs-lookup"><span data-stu-id="86a50-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="86a50-p103">Em uma rede de Comutação de Rótulo Multiprotocolo (MPLS), todos os sites são conectados por uma malha completa. Isto é, todos os sites são conectados diretamente à nuvem MPLS, e cada site é provisionado com a largura de banda a ser usada em um link WAN para a nuvem MPLS. Não existe hub de rede nem local central para controlar o roteamento IP. A figura abaixo mostra uma rede simples baseada na tecnologia MPLS.</span><span class="sxs-lookup"><span data-stu-id="86a50-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="86a50-113">**Exemplo de rede MPLS**</span><span class="sxs-lookup"><span data-stu-id="86a50-113">**Example MPLS network**</span></span>

![CAC com MPLS](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="86a50-p104">Para implantar um controle de admissão de chamada (CAC) em uma rede MPLS, é preciso criar uma região de rede para representar a nuvem MPLS, bem como criar um site de rede para representar cada site de satélite MPLS. A figura a seguir ilustra como a região de rede e os sites de rede devem ser configurados para representar a rede MPLS de exemplo na figura anterior. Os limites gerais da largura de banda e os limites de sessão da largura de banda têm base na capacidade do link WAN a partir de cada site de rede até a região de rede que representa a nuvem MPLS.</span><span class="sxs-lookup"><span data-stu-id="86a50-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="86a50-118">**Região de rede e sites de rede para uma rede MPLS**</span><span class="sxs-lookup"><span data-stu-id="86a50-118">**Network region and network sites for an MPLS network**</span></span>

![Diagrama do Controle de Admissão de Chamadas (CAC) com MPLS](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="86a50-120">Controle de admissão de chamada em um tronco SIP</span><span class="sxs-lookup"><span data-stu-id="86a50-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="86a50-p105">Para implantar o controle de admissão de chamadas em um tronco SIP, crie um local de rede para representar o ITSP (provedor de serviço de telefonia da Internet). Para aplicar valores de política de largura de banda no tronco SIP, crie uma política entre locais entre o local de rede na sua empresa e o local de rede criado para representar o ITSP.</span><span class="sxs-lookup"><span data-stu-id="86a50-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="86a50-123">A figura a seguir mostra um exemplo de implantação do CAC em um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="86a50-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="86a50-124">**Configuração do CAC em um tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="86a50-124">**CAC configuration on a SIP trunk**</span></span>

![Diagrama do Tronco SIP do Controle de Admissão de Chamadas](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="86a50-126">Para configurar o CAC em um tronco SIP, você terá que executar as seguintes tarefas durante a implantação do CAC:</span><span class="sxs-lookup"><span data-stu-id="86a50-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="86a50-127">Crie um site de rede para representar o ITSP.</span><span class="sxs-lookup"><span data-stu-id="86a50-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="86a50-128">Associe o site de rede a uma região de rede apropriada e aloque a largura de banda de zero para áudio e vídeo para este site de rede.</span><span class="sxs-lookup"><span data-stu-id="86a50-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="86a50-129">Para obter detalhes, consulte [Configurar Sites de rede para CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="86a50-129">For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="86a50-p107">Para o ITSP, essa configuração de site de rede não funciona. Os valores da política de largura de banda são, na verdade, aplicados na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="86a50-p107">For the ITSP, this network site configuration is not functional. Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="86a50-132">Crie um link entre sites para o tronco SIP usando os valores de parâmetro relevantes para o site criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="86a50-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="86a50-133">Por exemplo, use o nome do site de rede na sua empresa como o valor do parâmetro NetworkSiteID1 e o site de rede ITSP como o valor do parâmetro NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="86a50-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="86a50-134">Para obter detalhes, consulte [criar políticas de entre sites de rede no Skype para Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) na documentação de implantação e [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="86a50-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="86a50-135">Obter o endereço IP da Session Border Controller (SCB) ponto de terminação de mídia do seu ITSP.</span><span class="sxs-lookup"><span data-stu-id="86a50-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="86a50-136">Adicione o endereço IP com uma máscara de sub-rede de 32 para o site de rede que representa o ITSP.</span><span class="sxs-lookup"><span data-stu-id="86a50-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="86a50-137">Para obter detalhes, consulte [associar uma sub-rede a um Site de rede](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="86a50-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="86a50-138">Controle de admissão de chamada com um gateway PSTN ou PBX de terceiros</span><span class="sxs-lookup"><span data-stu-id="86a50-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="86a50-139">Este tópico descreve exemplos de como o controle de admissão de chamadas (CAC) pode ser implantado no link entre a interface de gateway do servidor de mediação e um gateway PSTN (rede) telefônica comutada pública de terceiros ou privada Central de comutação telefônica (PBX).</span><span class="sxs-lookup"><span data-stu-id="86a50-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="86a50-140">Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="86a50-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="86a50-141">CAC pode ser implantado em WAN link da interface de gateway do servidor de mediação para um gateway de PBX ou PSTN de terceiros.</span><span class="sxs-lookup"><span data-stu-id="86a50-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="86a50-142">**Caso 1: CAC entre o Servidor de Mediação e um gateway PSTN**</span><span class="sxs-lookup"><span data-stu-id="86a50-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![Caso 1: CAC entre o Gateway PSTN do servidor de mediação](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="86a50-144">Neste exemplo, o CAC é aplicado entre o servidor de mediação e um gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="86a50-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="86a50-145">Se um Skype para o usuário de negócios do cliente no Site de rede 1 faz uma chamada PSTN por meio do gateway PSTN no Site de rede 2, a mídia flui através do link WAN.</span><span class="sxs-lookup"><span data-stu-id="86a50-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="86a50-146">Portanto, duas verificações CAC são executadas para cada sessão PSTN:</span><span class="sxs-lookup"><span data-stu-id="86a50-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="86a50-147">Entre o Skype para o aplicativo cliente de negócios e o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="86a50-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="86a50-148">Entre o servidor de mediação e o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="86a50-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="86a50-149">Isto funciona para as chamadas PSTN de entrada para um cliente no Local de Rede 1 e para chamadas PSTN de saída provenientes de um aplicativo cliente no Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="86a50-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-150">Certifique-se de que a sub-rede do IP ao qual o gateway PSTN pertence está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="86a50-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-151">Certifique-se de que a sub-rede do IP que ambas as interfaces do servidor de mediação pertencem está configurada e associada ao local de rede 1.</span><span class="sxs-lookup"><span data-stu-id="86a50-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-152">Para obter detalhes, consulte [associar uma sub-rede a um Site de rede](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="86a50-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="86a50-153">Caso 2: CAC entre o servidor de mediação e um PBX de terceiros com ponto de terminação de mídia</span><span class="sxs-lookup"><span data-stu-id="86a50-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="86a50-154">Esta configuração é similar ao Caso 1.</span><span class="sxs-lookup"><span data-stu-id="86a50-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="86a50-155">Em ambos os casos, o servidor de mediação sabe qual dispositivo finaliza a mídia no final oposto do link de WAN e o endereço IP do gateway PSTN ou PBX com o ponto de terminação de mídia (MTP) está configurado no servidor de mediação como o próximo salto.</span><span class="sxs-lookup"><span data-stu-id="86a50-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="86a50-156">**Caso 2: CAC entre o Servidor de Mediação e um PBX de terceiros com MTP**</span><span class="sxs-lookup"><span data-stu-id="86a50-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![Caso 2: CAC entre o PBX do servidor de mediação com MTP](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="86a50-158">Neste exemplo, o CAC é aplicado entre o servidor de mediação e o PBX/MTP.</span><span class="sxs-lookup"><span data-stu-id="86a50-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="86a50-159">Se um Skype para o usuário de cliente empresarial no Site de rede 1 faz uma chamada PSTN por meio do PBX/MTP localizado no Site de rede 2, a mídia flui através do link WAN.</span><span class="sxs-lookup"><span data-stu-id="86a50-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="86a50-160">Portanto, para cada sessão PSTN duas verificações CAC são executadas:</span><span class="sxs-lookup"><span data-stu-id="86a50-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="86a50-161">Entre o Skype para o aplicativo cliente de negócios e o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="86a50-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="86a50-162">Entre o servidor de mediação e o PBX/MTP</span><span class="sxs-lookup"><span data-stu-id="86a50-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="86a50-163">Isto funciona para ambas, chamadas PSTN de entrada para um cliente no Local de Rede 1 e chamadas PSTN de saída provenientes de um cliente no Local de Rede 1.</span><span class="sxs-lookup"><span data-stu-id="86a50-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-164">Certifique-se de que a sub-rede do IP à qual o MTP pertence está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="86a50-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-165">Certifique-se de que a sub-rede do IP que ambas as interfaces do servidor de mediação pertencem está configurada e associada ao local de rede 1.</span><span class="sxs-lookup"><span data-stu-id="86a50-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-166">Para obter detalhes, consulte [associar uma sub-rede a um Site de rede](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="86a50-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="86a50-167">Caso 3: CAC entre o servidor de mediação e um PBX de terceiros sem um ponto de terminação de mídia</span><span class="sxs-lookup"><span data-stu-id="86a50-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="86a50-168">O Caso 3 é um ligeiramente diferente dos dois primeiros.</span><span class="sxs-lookup"><span data-stu-id="86a50-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="86a50-169">Se não houver nenhuma MTP ao PBX de terceiros, para uma sessão de saída a solicitação para o PBX de terceiros o servidor de mediação não sabe qual mídia será terminada em que o limite de PBX.</span><span class="sxs-lookup"><span data-stu-id="86a50-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="86a50-170">Nesse caso, a mídia flui diretamente entre o servidor de mediação e o dispositivo de ponto de extremidade de terceiros.</span><span class="sxs-lookup"><span data-stu-id="86a50-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="86a50-171">**Caso 3: CAC entre o Servidor de Mediação e um PBX de terceiros sem MTP**</span><span class="sxs-lookup"><span data-stu-id="86a50-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![Caso 3: CAC entre o PBX do servidor de mediação no MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="86a50-173">Neste exemplo, se um Skype para o usuário de negócios do cliente no Site de rede 1 faz uma chamada para um usuário através do PBX, o servidor de mediação é capaz de realizar as verificações CAC apenas nos trecho proxy entre (Skype para o aplicativo cliente de negócios) e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="86a50-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="86a50-174">Como o servidor de mediação não têm informações sobre o dispositivo de ponto de extremidade enquanto a sessão é solicitada, verificações CAC não podem ser executadas na WAN link (entre o servidor de mediação e o ponto de extremidade de terceiros) antes do estabelecimento da chamada.</span><span class="sxs-lookup"><span data-stu-id="86a50-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="86a50-175">No entanto, depois que a sessão for estabelecida, o servidor de mediação facilita na contabilidade para a largura de banda usada no tronco.</span><span class="sxs-lookup"><span data-stu-id="86a50-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="86a50-176">Para chamadas originadas do ponto de extremidade de terceiros, as informações sobre esse dispositivo de ponto de extremidade estão disponíveis no momento da solicitação de sessão e seleção CAC pode ser executada em ambos os lados do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="86a50-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-177">Certifique-se de que a sub-rede do IP à qual os dispositivos de ponto de extremidade pertencem está configurada e associada ao Local de Rede 2.</span><span class="sxs-lookup"><span data-stu-id="86a50-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-178">Certifique-se de que a sub-rede do IP que ambas as interfaces do servidor de mediação pertencem está configurada e associada ao local de rede 1.</span><span class="sxs-lookup"><span data-stu-id="86a50-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="86a50-179">Para obter detalhes, consulte [associar uma sub-rede a um Site de rede](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span><span class="sxs-lookup"><span data-stu-id="86a50-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


