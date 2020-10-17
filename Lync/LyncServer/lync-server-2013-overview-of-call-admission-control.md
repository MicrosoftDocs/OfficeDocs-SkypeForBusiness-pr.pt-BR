---
title: 'Lync Server 2013: visão geral do controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe2d7622a29a1526430a25341d04bf0b6399e15a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530688"
---
# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="2bf8a-102">Visão geral do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bf8a-102">Overview of call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bf8a-103">_**Última modificação do tópico:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="2bf8a-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="2bf8a-104">As comunicações em tempo real são sensíveis à perda de latência e pacotes que pode ocorrer em redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="2bf8a-105">O CAC (serviço de controle de admissão de chamadas) determina, com base na largura de banda da rede disponível, se será permitido estabelecer sessões de comunicação em tempo real, como chamadas de voz ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="2bf8a-106">O design do CAC no Lync Server 2013 oferece quatro atributos principais:</span><span class="sxs-lookup"><span data-stu-id="2bf8a-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="2bf8a-107">é simples de implantar e gerenciar, sem a necessidade de equipamentos adicionais, como roteadores especialmente configurados.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="2bf8a-p102">Ele aborda casos críticos de uso de comunicações unificadas, como usuários móveis e vários pontos de presença. As políticas CAC são aplicadas de acordo com a localização do ponto de extremidade, não onde o usuário está hospedado.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="2bf8a-110">Além de chamadas de voz, ele pode ser aplicado a outro tráfego, como chamadas de vídeo e sessões de conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="2bf8a-111">Oferece a flexibilidade para permitir a representação de vários tipos de topologias de rede.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="2bf8a-112">Para obter exemplos, consulte [Components and topologias for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="2bf8a-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="2bf8a-113">Se uma nova voz ou sessão de vídeo exceder os limites de largura de banda definidos em um link WAN, a sessão é bloqueada ou (somente para chamadas de telefone) redirecionada ao PSTN.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="2bf8a-p104">O CAC controla o tráfego em tempo real somente para voz e vídeo. Ele não controla o tráfego de dados.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="2bf8a-116">Os administradores definem políticas de CAC, que são impostas pelo serviço de política de largura de banda que é instalado com cada pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="2bf8a-117">As configurações de CAC são automaticamente propagadas para todos os servidores front-end do Lync Server em sua rede.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="2bf8a-118">Para chamadas que falham devido a políticas CAC, a ordem de precedência para o redirecionamento de chamada é:</span><span class="sxs-lookup"><span data-stu-id="2bf8a-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="2bf8a-119">Internet</span><span class="sxs-lookup"><span data-stu-id="2bf8a-119">Internet</span></span>

2.  <span data-ttu-id="2bf8a-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="2bf8a-120">PSTN</span></span>

3.  <span data-ttu-id="2bf8a-121">Caixa postal</span><span class="sxs-lookup"><span data-stu-id="2bf8a-121">Voice mail</span></span>

<span data-ttu-id="2bf8a-p106">A gravação de detalhes da chamada (CDR) captura as informações sobre chamadas que são reencaminhadas para o PSTN ou o correio de voz. O CDR não captura as informações sobre chamadas reencaminhadas para a Internet, porque a Internet é tratada como um caminho alternativo, em vez de uma opção secundária.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2bf8a-124">Os depósitos de correio de voz não serão negados devido a restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="2bf8a-p107">O Serviço de Política de Largura de Banda gera dois tipos de arquivos de log no formato de valores separados por vírgulas (CSV). O arquivo de log **falhas de verificação** captura as informações quando as solicitações de largura de banda são negadas. O arquivo de log **utilização do link** captura um instantâneo da topologia de rede e a utilização de largura de banda do link de WAN. Ambos arquivos de log podem ajudá-lo a ajustar as políticas CAC com base na utilização.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="2bf8a-129">Considerações sobre o Controle de Admissão de Chamada</span><span class="sxs-lookup"><span data-stu-id="2bf8a-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="2bf8a-130">O administrador seleciona a instalação do Serviço de Política de Largura de Banda no primeiro pool configurado no site central.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="2bf8a-131">Como há apenas um site central por região da rede, há apenas um Serviço de Política de Largura de Banda por região da rede, que gerencia a política de largura de banda para aquela região, os sites associados e os links para esses sites.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="2bf8a-132">O serviço de política de largura de banda é executado como parte dos servidores front-end e, portanto, a alta disponibilidade é interna dentro desse pool.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="2bf8a-133">O serviço de política de largura de banda executado em cada servidor de front-end sincroniza a cada 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="2bf8a-134">Se o pool de front-ends falhar, as políticas do CAC não serão mais impostas para esse site até o pool de front-ends e, conseqüentemente, o serviço de política de largura de banda se tornar operacional novamente.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="2bf8a-135">Isso significa que todas as chamadas serão recebidas enquanto o Serviço de Política de Largura de Banda estiver inoperante.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="2bf8a-136">Portanto, ainda há a possibilidade de excesso de assinatura da largura de banda dos links durante esse período</span><span class="sxs-lookup"><span data-stu-id="2bf8a-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="2bf8a-137">O serviço de política de largura de banda fornece alta disponibilidade em um pool de front-ends; no entanto, ele não fornece redundância entre pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="2bf8a-138">O serviço de política de largura de banda não pode fazer failover de um pool de front-ends para outro.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="2bf8a-139">Após a restauração do serviço para o pool de front-ends, o serviço de política de largura de banda é retomado e pode impor verificações de política de largura de banda novamente.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="2bf8a-140">Considerações de Rede</span><span class="sxs-lookup"><span data-stu-id="2bf8a-140">Network Considerations</span></span>

<span data-ttu-id="2bf8a-141">Embora a restrição de largura de banda para áudio e vídeo seja imposta pelo serviço de política de largura de banda no Lync Server 2013, essa restrição não é imposta no roteador de rede (camada 2 e 3).</span><span class="sxs-lookup"><span data-stu-id="2bf8a-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="2bf8a-142">Lync Server 2010 CAC não é possível impedir que um aplicativo de dados, por exemplo, consuma toda a largura de banda da rede em um link de WAN, incluindo a largura de banda reservada para áudio e vídeo pela sua política de CAC.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="2bf8a-143">Para proteger a largura de banda necessária em sua rede, você pode implantar um protocolo de QoS (qualidade de serviço), como os serviços diferenciados (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="2bf8a-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="2bf8a-144">Portanto, uma prática recomendada é coordenar as políticas de largura de banda do CAC que você define com qualquer configuração de QoS que você possa implantar.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="2bf8a-145">Mídia e Sinalização de Caminhos através de VPN</span><span class="sxs-lookup"><span data-stu-id="2bf8a-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="2bf8a-p111">Se a sua empresa oferece suporte à mídia através de VPN, verifique se tanto o fluxo de mídia e o fluxo de sinalização vão através de VPN ou ambos são roteados pela internet. Por padrão, a mídia e os fluxos de sinalização passam pelo encapsulamento VPN.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="2bf8a-148">Controle de Admissão de Chamada de Usuários Externos</span><span class="sxs-lookup"><span data-stu-id="2bf8a-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="2bf8a-149">O controle de admissão de chamada não será aplicado aos usuários remotos onde o tráfego de rede flui através da Internet.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="2bf8a-150">Como o tráfego de mídia está atravessando a Internet, o que não é gerenciado pelo Lync Server, o CAC não pode ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="2bf8a-151">Serão realizadas verificações de CAC, no entanto, na parte da chamada que flui através da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="2bf8a-152">Controle de Admissão de Chamada das Conexões PSTN</span><span class="sxs-lookup"><span data-stu-id="2bf8a-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="2bf8a-153">O controle de admissão de chamadas é aplicável no servidor de mediação independentemente de estar conectado a um IP/PBX, um gateway PSTN ou um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="2bf8a-154">Como o servidor de mediação é um agente de usuário back-to-back (B2BUA), ele termina a mídia.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="2bf8a-155">Ele tem dois lados de conexão: um lado conectado ao Lync Server e um lado do gateway, que está conectado a gateways PSTN, IP/PBXs ou troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="2bf8a-156">Para obter detalhes sobre conexões PSTN, consulte [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="2bf8a-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="2bf8a-157">O CAC pode ser aplicado em ambos os lados do servidor de mediação, a menos que o bypass de mídia esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="2bf8a-158">Se o bypass de mídia estiver habilitado, o tráfego de mídia não percorrerá o servidor de mediação, mas, em vez disso, fluirá diretamente entre o cliente Lync e o gateway.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="2bf8a-159">Nesse caso, o CAC não é necessário.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="2bf8a-160">Para obter detalhes, consulte [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="2bf8a-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="2bf8a-161">A figura a seguir ilustra como o CAC é aplicado em conexões PSTN, com e sem o bypass de mídia habilitado.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="2bf8a-162">**Aplicação de controle de admissão de chamada em conexões para o PSTN**</span><span class="sxs-lookup"><span data-stu-id="2bf8a-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="2bf8a-163">![Imposição de conexão de mídia do CAC de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Imposição de conexão de mídia do CAC de voz")</span><span class="sxs-lookup"><span data-stu-id="2bf8a-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="2bf8a-164">Compatibilidade de Controle de Admissão de Chamada com Versões Anteriores do Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="2bf8a-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="2bf8a-165">O controle de admissão de chamadas pode ser habilitado somente em pontos de extremidade habilitados para o Lync Server 2010 e posterior.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="2bf8a-166">O controle de admissão de chamadas não pode ser habilitado em pontos de extremidade que executam o Office Communicator 2007 R2 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="2bf8a-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="2bf8a-167">**Aplicativo do CAC em diferentes versões do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="2bf8a-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="2bf8a-168">![Diagrama de comparação de versão do CAC de voz](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagrama de comparação de versão do CAC de voz")</span><span class="sxs-lookup"><span data-stu-id="2bf8a-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

