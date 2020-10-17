---
title: 'Lync Server 2013: componentes de conectividade PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa82336ed96c61315da4c25a0152ba75d15d7b6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531738"
---
# <a name="pstn-connectivity-components-in-lync-server-2013"></a><span data-ttu-id="535cc-102">Componentes de conectividade PSTN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="535cc-102">PSTN connectivity components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="535cc-103">_**Última modificação do tópico:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="535cc-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="535cc-p101">Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço). Além disso, os usuários não devem perceber a tecnologia subjacente ao fazer e receber chamadas. Da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve ser igual a qualquer outra sessão SIP.</span><span class="sxs-lookup"><span data-stu-id="535cc-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>

<span data-ttu-id="535cc-107">Para conexões PSTN, você pode implantar um tronco SIP ou um gateway PSTN (com um PBX, também conhecido como um link SIP direto, ou sem um PBX).</span><span class="sxs-lookup"><span data-stu-id="535cc-107">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>

<div>

## <a name="sip-trunking"></a><span data-ttu-id="535cc-108">Tronco SIP</span><span class="sxs-lookup"><span data-stu-id="535cc-108">SIP Trunking</span></span>

<span data-ttu-id="535cc-p102">Como alternativa ao uso de gateways PSTN, você pode conectar sua solução Enterprise Voice à PSTN usando o tronco SIP. O tronco SIP permite os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="535cc-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>

  - <span data-ttu-id="535cc-111">Um usuário corporativo dentro ou fora do firewall corporativo pode fazer uma chamada local ou interurbana especificada por um número em conformidade com E.164 que é encerrado no PSTN como um serviço do provedor de serviços correspondente.</span><span class="sxs-lookup"><span data-stu-id="535cc-111">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>

  - <span data-ttu-id="535cc-112">Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário.</span><span class="sxs-lookup"><span data-stu-id="535cc-112">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>

<span data-ttu-id="535cc-113">O uso dessa solução de implantação requer um provedor de serviços de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="535cc-113">The use of this deployment solution requires a SIP trunking service provider.</span></span>

</div>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="535cc-114">Gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="535cc-114">PSTN gateways</span></span>

<span data-ttu-id="535cc-115">Os gateways PSTN são dispositivos de terceiros que convertem a sinalização e a mídia entre a infraestrutura do Enterprise Voice e uma PSTN ou um PBX.</span><span class="sxs-lookup"><span data-stu-id="535cc-115">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="535cc-116">Os gateways PSTN funcionam com o Servidor de Mediação para apresentar uma chamada PSTN ou PBX para um cliente do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="535cc-116">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="535cc-117">O Servidor de Mediação também apresenta as chamadas dos clientes do Enterprise Voice ao gateway PSTN para roteamento para a PSTN ou o PBX.</span><span class="sxs-lookup"><span data-stu-id="535cc-117">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="535cc-118">Para obter uma lista de parceiros que trabalham com a Microsoft para fornecer dispositivos que funcionam com o Lync Server, consulte o site do Microsoft Unified Communications Partners em [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="535cc-118">For a list of partners who work with Microsoft to provide devices that work with Lync Server, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

<div>

## <a name="private-branch-exchanges"></a><span data-ttu-id="535cc-119">Centrais privadas de comutação telefônica</span><span class="sxs-lookup"><span data-stu-id="535cc-119">Private Branch Exchanges</span></span>

<span data-ttu-id="535cc-120">Se você tiver uma infraestrutura de voz existente que usa um PBX (Private Branch Exchange), você pode usar seu PBX com o Lync Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="535cc-120">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Lync Server Enterprise Voice.</span></span>

<span data-ttu-id="535cc-121">Os cenários de integração de PBX com o Enterprise Voice aceitos são:</span><span class="sxs-lookup"><span data-stu-id="535cc-121">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>

  - <span data-ttu-id="535cc-122">IP-PBX que oferece suporte ao desvio de mídia, com um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="535cc-122">IP-PBX that supports media bypass, with a Mediation Server.</span></span>

  - <span data-ttu-id="535cc-123">IP-PBX que requer um gateway PSTN autônomo.</span><span class="sxs-lookup"><span data-stu-id="535cc-123">IP-PBX that requires a stand-alone PSTN gateway.</span></span>

  - <span data-ttu-id="535cc-124">Conexão PBX TDM, com um gateway PSTN autônomo.</span><span class="sxs-lookup"><span data-stu-id="535cc-124">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="535cc-125">O desvio de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="535cc-125">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="535cc-126">A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="535cc-126">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="535cc-127">O bypass de mídia é suportado apenas com produtos e versões listados no programa de interoperabilidade aberta de comunicações unificativas – Lync Server em <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="535cc-127">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="535cc-128">Para obter detalhes sobre parceiros que oferecem soluções do Enterprise Voice, consulte o site do Microsoft Unified Communications Partners em [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="535cc-128">For details about partners who offer Enterprise Voice solutions, see the Microsoft Unified Communications Partners website at [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

<span data-ttu-id="535cc-129">Para obter detalhes sobre parceiros que oferecem soluções de hardware do Enterprise Voice, incluindo gateways PSTN, consulte o site de parceiros de comunicações unificadas da Microsoft [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .</span><span class="sxs-lookup"><span data-stu-id="535cc-129">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the Microsoft Unified Communications Partners website [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

