---
title: 'Lync Server 2013: visão geral do controle de admissão de chamadas'
description: 'Lync Server 2013: visão geral do controle de admissão de chamadas.'
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
ms.openlocfilehash: b0fe2fc75ea9bc887709b7dbe1c2128513fcff6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562907"
---
# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="1f032-103">Visão geral do controle de admissão de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f032-103">Overview of call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f032-104">_**Última modificação do tópico:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="1f032-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="1f032-105">As comunicações em tempo real são sensíveis à perda de latência e pacotes que pode ocorrer em redes congestionadas.</span><span class="sxs-lookup"><span data-stu-id="1f032-105">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="1f032-106">O CAC (serviço de controle de admissão de chamadas) determina, com base na largura de banda da rede disponível, se será permitido estabelecer sessões de comunicação em tempo real, como chamadas de voz ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="1f032-106">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="1f032-107">O design do CAC no Lync Server 2013 oferece quatro atributos principais:</span><span class="sxs-lookup"><span data-stu-id="1f032-107">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="1f032-108">é simples de implantar e gerenciar, sem a necessidade de equipamentos adicionais, como roteadores especialmente configurados.</span><span class="sxs-lookup"><span data-stu-id="1f032-108">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="1f032-p102">Ele aborda casos críticos de uso de comunicações unificadas, como usuários móveis e vários pontos de presença. As políticas CAC são aplicadas de acordo com a localização do ponto de extremidade, não onde o usuário está hospedado.</span><span class="sxs-lookup"><span data-stu-id="1f032-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="1f032-111">Além de chamadas de voz, ele pode ser aplicado a outro tráfego, como chamadas de vídeo e sessões de conferência de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="1f032-111">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="1f032-112">Oferece a flexibilidade para permitir a representação de vários tipos de topologias de rede.</span><span class="sxs-lookup"><span data-stu-id="1f032-112">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="1f032-113">Para obter exemplos, consulte [Components and topologias for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="1f032-113">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="1f032-114">Se uma nova voz ou sessão de vídeo exceder os limites de largura de banda definidos em um link WAN, a sessão é bloqueada ou (somente para chamadas de telefone) redirecionada ao PSTN.</span><span class="sxs-lookup"><span data-stu-id="1f032-114">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="1f032-p104">O CAC controla o tráfego em tempo real somente para voz e vídeo. Ele não controla o tráfego de dados.</span><span class="sxs-lookup"><span data-stu-id="1f032-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="1f032-117">Os administradores definem políticas de CAC, que são impostas pelo serviço de política de largura de banda que é instalado com cada pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1f032-117">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="1f032-118">As configurações de CAC são automaticamente propagadas para todos os servidores front-end do Lync Server em sua rede.</span><span class="sxs-lookup"><span data-stu-id="1f032-118">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="1f032-119">Para chamadas que falham devido a políticas CAC, a ordem de precedência para o redirecionamento de chamada é:</span><span class="sxs-lookup"><span data-stu-id="1f032-119">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="1f032-120">Internet</span><span class="sxs-lookup"><span data-stu-id="1f032-120">Internet</span></span>

2.  <span data-ttu-id="1f032-121">PSTN</span><span class="sxs-lookup"><span data-stu-id="1f032-121">PSTN</span></span>

3.  <span data-ttu-id="1f032-122">Caixa postal</span><span class="sxs-lookup"><span data-stu-id="1f032-122">Voice mail</span></span>

<span data-ttu-id="1f032-p106">A gravação de detalhes da chamada (CDR) captura as informações sobre chamadas que são reencaminhadas para o PSTN ou o correio de voz. O CDR não captura as informações sobre chamadas reencaminhadas para a Internet, porque a Internet é tratada como um caminho alternativo, em vez de uma opção secundária.</span><span class="sxs-lookup"><span data-stu-id="1f032-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f032-125">Os depósitos de correio de voz não serão negados devido a restrições de largura de banda.</span><span class="sxs-lookup"><span data-stu-id="1f032-125">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="1f032-p107">O Serviço de Política de Largura de Banda gera dois tipos de arquivos de log no formato de valores separados por vírgulas (CSV). O arquivo de log **falhas de verificação** captura as informações quando as solicitações de largura de banda são negadas. O arquivo de log **utilização do link** captura um instantâneo da topologia de rede e a utilização de largura de banda do link de WAN. Ambos arquivos de log podem ajudá-lo a ajustar as políticas CAC com base na utilização.</span><span class="sxs-lookup"><span data-stu-id="1f032-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="1f032-130">Considerações sobre o Controle de Admissão de Chamada</span><span class="sxs-lookup"><span data-stu-id="1f032-130">Call Admission Control Considerations</span></span>

<span data-ttu-id="1f032-131">O administrador seleciona a instalação do Serviço de Política de Largura de Banda no primeiro pool configurado no site central.</span><span class="sxs-lookup"><span data-stu-id="1f032-131">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="1f032-132">Como há apenas um site central por região da rede, há apenas um Serviço de Política de Largura de Banda por região da rede, que gerencia a política de largura de banda para aquela região, os sites associados e os links para esses sites.</span><span class="sxs-lookup"><span data-stu-id="1f032-132">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="1f032-133">O serviço de política de largura de banda é executado como parte dos servidores front-end e, portanto, a alta disponibilidade é interna dentro desse pool.</span><span class="sxs-lookup"><span data-stu-id="1f032-133">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="1f032-134">O serviço de política de largura de banda executado em cada servidor de front-end sincroniza a cada 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="1f032-134">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="1f032-135">Se o pool de front-ends falhar, as políticas do CAC não serão mais impostas para esse site até o pool de front-ends e, conseqüentemente, o serviço de política de largura de banda se tornar operacional novamente.</span><span class="sxs-lookup"><span data-stu-id="1f032-135">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="1f032-136">Isso significa que todas as chamadas serão recebidas enquanto o Serviço de Política de Largura de Banda estiver inoperante.</span><span class="sxs-lookup"><span data-stu-id="1f032-136">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="1f032-137">Portanto, ainda há a possibilidade de excesso de assinatura da largura de banda dos links durante esse período</span><span class="sxs-lookup"><span data-stu-id="1f032-137">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="1f032-138">O serviço de política de largura de banda fornece alta disponibilidade em um pool de front-ends; no entanto, ele não fornece redundância entre pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1f032-138">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="1f032-139">O serviço de política de largura de banda não pode fazer failover de um pool de front-ends para outro.</span><span class="sxs-lookup"><span data-stu-id="1f032-139">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="1f032-140">Após a restauração do serviço para o pool de front-ends, o serviço de política de largura de banda é retomado e pode impor verificações de política de largura de banda novamente.</span><span class="sxs-lookup"><span data-stu-id="1f032-140">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="1f032-141">Considerações de Rede</span><span class="sxs-lookup"><span data-stu-id="1f032-141">Network Considerations</span></span>

<span data-ttu-id="1f032-142">Embora a restrição de largura de banda para áudio e vídeo seja imposta pelo serviço de política de largura de banda no Lync Server 2013, essa restrição não é imposta no roteador de rede (camada 2 e 3).</span><span class="sxs-lookup"><span data-stu-id="1f032-142">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="1f032-143">Lync Server 2010 CAC não é possível impedir que um aplicativo de dados, por exemplo, consuma toda a largura de banda da rede em um link de WAN, incluindo a largura de banda reservada para áudio e vídeo pela sua política de CAC.</span><span class="sxs-lookup"><span data-stu-id="1f032-143">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="1f032-144">Para proteger a largura de banda necessária em sua rede, você pode implantar um protocolo de QoS (qualidade de serviço), como os serviços diferenciados (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="1f032-144">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="1f032-145">Portanto, uma prática recomendada é coordenar as políticas de largura de banda do CAC que você define com qualquer configuração de QoS que você possa implantar.</span><span class="sxs-lookup"><span data-stu-id="1f032-145">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="1f032-146">Mídia e Sinalização de Caminhos através de VPN</span><span class="sxs-lookup"><span data-stu-id="1f032-146">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="1f032-p111">Se a sua empresa oferece suporte à mídia através de VPN, verifique se tanto o fluxo de mídia e o fluxo de sinalização vão através de VPN ou ambos são roteados pela internet. Por padrão, a mídia e os fluxos de sinalização passam pelo encapsulamento VPN.</span><span class="sxs-lookup"><span data-stu-id="1f032-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="1f032-149">Controle de Admissão de Chamada de Usuários Externos</span><span class="sxs-lookup"><span data-stu-id="1f032-149">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="1f032-150">O controle de admissão de chamada não será aplicado aos usuários remotos onde o tráfego de rede flui através da Internet.</span><span class="sxs-lookup"><span data-stu-id="1f032-150">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="1f032-151">Como o tráfego de mídia está atravessando a Internet, o que não é gerenciado pelo Lync Server, o CAC não pode ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="1f032-151">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="1f032-152">Serão realizadas verificações de CAC, no entanto, na parte da chamada que flui através da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="1f032-152">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="1f032-153">Controle de Admissão de Chamada das Conexões PSTN</span><span class="sxs-lookup"><span data-stu-id="1f032-153">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="1f032-154">O controle de admissão de chamadas é aplicável no servidor de mediação independentemente de estar conectado a um IP/PBX, um gateway PSTN ou um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="1f032-154">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="1f032-155">Como o servidor de mediação é um agente de usuário back-to-back (B2BUA), ele termina a mídia.</span><span class="sxs-lookup"><span data-stu-id="1f032-155">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="1f032-156">Ele tem dois lados de conexão: um lado conectado ao Lync Server e um lado do gateway, que está conectado a gateways PSTN, IP/PBXs ou troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="1f032-156">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="1f032-157">Para obter detalhes sobre conexões PSTN, consulte [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="1f032-157">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="1f032-158">O CAC pode ser aplicado em ambos os lados do servidor de mediação, a menos que o bypass de mídia esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="1f032-158">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="1f032-159">Se o bypass de mídia estiver habilitado, o tráfego de mídia não percorrerá o servidor de mediação, mas, em vez disso, fluirá diretamente entre o cliente Lync e o gateway.</span><span class="sxs-lookup"><span data-stu-id="1f032-159">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="1f032-160">Nesse caso, o CAC não é necessário.</span><span class="sxs-lookup"><span data-stu-id="1f032-160">In this case, CAC is not needed.</span></span> <span data-ttu-id="1f032-161">Para obter detalhes, consulte [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="1f032-161">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="1f032-162">A figura a seguir ilustra como o CAC é aplicado em conexões PSTN, com e sem o bypass de mídia habilitado.</span><span class="sxs-lookup"><span data-stu-id="1f032-162">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="1f032-163">**Aplicação de controle de admissão de chamada em conexões para o PSTN**</span><span class="sxs-lookup"><span data-stu-id="1f032-163">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="1f032-164">![Imposição de conexão de mídia do CAC de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Imposição de conexão de mídia do CAC de voz")</span><span class="sxs-lookup"><span data-stu-id="1f032-164">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="1f032-165">Compatibilidade de Controle de Admissão de Chamada com Versões Anteriores do Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="1f032-165">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="1f032-166">O controle de admissão de chamadas pode ser habilitado somente em pontos de extremidade habilitados para o Lync Server 2010 e posterior.</span><span class="sxs-lookup"><span data-stu-id="1f032-166">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="1f032-167">O controle de admissão de chamadas não pode ser habilitado em pontos de extremidade que executam o Office Communicator 2007 R2 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="1f032-167">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="1f032-168">**Aplicativo do CAC em diferentes versões do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="1f032-168">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="1f032-169">![Diagrama de comparação de versão do CAC de voz](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagrama de comparação de versão do CAC de voz")</span><span class="sxs-lookup"><span data-stu-id="1f032-169">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

