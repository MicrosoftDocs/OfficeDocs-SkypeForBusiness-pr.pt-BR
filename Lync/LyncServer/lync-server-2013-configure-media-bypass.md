---
title: 'Lync Server 2013: configurar bypass de mídia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bf2fb06f25ccf1871393cf4d80ffa3c33a42fc5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="7657c-102">Configurar bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7657c-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7657c-103">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="7657c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="7657c-104">Esta seção pressupõe que você já publicou e configurou pelo menos um ou mais servidores de mediação (conforme descrito em [definir um servidor de mediação no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) e [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md), ou em [definir e configurar um pool de front-ends ou servidor Standard Edition no Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) e [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md), respectivamente, todos na documentação</span><span class="sxs-lookup"><span data-stu-id="7657c-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="7657c-105">Esta seção também pressupõe que você tenha definido pelo menos um ponto de gateway para fornecer conectividade PSTN, conforme descrito em [definir um gateway no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="7657c-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="7657c-106">Se o ponto ao qual você se conecta for o SBC de um provedor de tronco SIP, certifique-se de que o provedor é um provedor qualificado e que o provedor oferece suporte a bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="7657c-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="7657c-107">Por exemplo, vários provedores de tronco SIP permitirão que seu SBC receba tráfego do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="7657c-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="7657c-108">Caso sim, o bypass não deve ser habilitado para o tronco em questão.</span><span class="sxs-lookup"><span data-stu-id="7657c-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="7657c-109">Além disso, não é possível habilitar o bypass de mídia a não ser que sua organização releve seus endereços IP de rede internos para o provedor de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="7657c-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7657c-110">O bypass de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="7657c-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="7657c-111">A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="7657c-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="7657c-112">O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>unificativas – Lync Server em.</span><span class="sxs-lookup"><span data-stu-id="7657c-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="7657c-113">Esta seção descreve como habilitar o bypass de mídia para reduzir o processamento necessário do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="7657c-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="7657c-114">Antes de habilitar o bypass de mídia, certifique-se de que o ambiente atende às condições necessárias para dar suporte ao bypass de mídia, conforme descrito em [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7657c-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="7657c-115">Além disso, certifique-se de ter usado as informações em [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) para decidir se habilitará as configurações globais de bypass de mídia para sempre ignorar o servidor de mediação ou para usar as informações do site e da região ao determinar se deve ignorar o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="7657c-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="7657c-p104">Se você já configurou opcionalmente o controle de admissão de chamada (CAC), outro recurso do Enterprise Voice avançado, observe que a reserva de largura de banda realizada pelo controle de admissão de chamada não é aplicada a qualquer chamada na qual o bypass de mídia é implantado. A verificação se a implantação do bypass de mídia é realizado primeiro e se o bypass de mídia é implantado, o controle de admissão de chamada não é usado para a chamada; apenas se a verificação do bypass de mídia falhar, a verificação é realizada para o controle de admissão de chamada. Os dois recursos são mutuamente exclusivos para qualquer chamada roteada para o PSTN. Esta é a lógica porque o bypass de mídia assume que as restrições de largura de banda não existam entre os pontos de extremidade de mídia em uma chamada; o bypass de mídia não pode ser realizado em links com largura de banda restrita. Como resultado, um dos seguintes serão aplicados em uma chamada PSTN: a) a mídia ignora o Servidor de Mediação e o controle de admissão de chamada não reserva largura de banda para a chamada; ou b) o controle de admissão de chamada aplica a reserva de banda larga para a chamada e a mídia é processada pelo Servidor de Mediação envolvido na chamada.</span><span class="sxs-lookup"><span data-stu-id="7657c-p104">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed. The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control. The two features are thus mutually exclusive for any particular call that is routed to the PSTN. This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth. As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="7657c-121">Próximas etapas: Habilitar o bypass de mídia na conexão de tronco</span><span class="sxs-lookup"><span data-stu-id="7657c-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="7657c-122">Após definir as configurações iniciais para a conectividade PSTN (planos de discagem, políticas de voz, registros de uso de PSTN, rotas de chamadas de saída e regras de conversão), inicie o processo de habilitar o bypass de mídia usando as etapas em [configurar um tronco com bypass de mídia no Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="7657c-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7657c-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="7657c-123">See Also</span></span>


[<span data-ttu-id="7657c-124">Configurar um tronco com bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7657c-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="7657c-125">Configurar o bypass de mídia no Lync Server 2013 para sempre ignorar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="7657c-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="7657c-126">Definir as configurações globais de bypass de mídia no Lync Server 2013 para usar informações do site e da região</span><span class="sxs-lookup"><span data-stu-id="7657c-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="7657c-127">Opções de bypass de mídia global no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7657c-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="7657c-128">Planejamento de bypass de mídia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7657c-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

