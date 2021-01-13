---
title: Componentes de conectividade PSTN no Skype for Business Server
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
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Saiba mais sobre tronco SIP e gateways PSTN para Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813531"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="14e38-103">Componentes de conectividade PSTN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="14e38-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="14e38-104">Saiba mais sobre tronco SIP e gateways PSTN para Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="14e38-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="14e38-p101">Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço). Além disso, os usuários não devem perceber a tecnologia subjacente ao fazer e receber chamadas. Da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve ser igual a qualquer outra sessão SIP.</span><span class="sxs-lookup"><span data-stu-id="14e38-p101">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS). In addition, users should not be aware of the underlying technology when they place and receive calls. From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="14e38-108">Para conexões PSTN, você pode implantar um tronco SIP ou um gateway PSTN (com um PBX, também conhecido como link SIP Direto ou sem um PBX).</span><span class="sxs-lookup"><span data-stu-id="14e38-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="14e38-109">Tronco SIP</span><span class="sxs-lookup"><span data-stu-id="14e38-109">SIP Trunking</span></span>

<span data-ttu-id="14e38-p102">Como alternativa ao uso de gateways PSTN, você pode conectar sua solução Enterprise Voice à PSTN usando o tronco SIP. O tronco SIP permite os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="14e38-p102">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking. SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="14e38-112">Um usuário corporativo dentro ou fora do firewall corporativo pode fazer uma chamada local ou interurbana especificada por um número em conformidade com E.164 que é encerrado no PSTN como um serviço do provedor de serviços correspondente.</span><span class="sxs-lookup"><span data-stu-id="14e38-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="14e38-113">Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário.</span><span class="sxs-lookup"><span data-stu-id="14e38-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="14e38-114">O uso dessa solução de implantação requer um provedor de serviços de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="14e38-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="14e38-115">Gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="14e38-115">PSTN gateways</span></span>

<span data-ttu-id="14e38-116">Os gateways PSTN são dispositivos de terceiros que convertem a sinalização e a mídia entre a infraestrutura do Enterprise Voice e uma PSTN ou um PBX.</span><span class="sxs-lookup"><span data-stu-id="14e38-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="14e38-117">Os gateways PSTN funcionam com o Servidor de Mediação para apresentar uma chamada PSTN ou PBX para um cliente do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="14e38-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="14e38-118">O Servidor de Mediação também apresenta as chamadas dos clientes do Enterprise Voice ao gateway PSTN para roteamento para a PSTN ou o PBX.</span><span class="sxs-lookup"><span data-stu-id="14e38-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="14e38-119">Para uma lista de parceiros que trabalham com a Microsoft para fornecer dispositivos que funcionam com o Skype for Business Server, consulte o site  [do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="14e38-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="14e38-120">Centrais privadas de comutação telefônica</span><span class="sxs-lookup"><span data-stu-id="14e38-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="14e38-121">Se você tiver uma infraestrutura de voz existente que use um PBX (central privada de com central privada), poderá usar seu PBX com o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="14e38-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="14e38-122">Os cenários de integração de PBX com o Enterprise Voice aceitos são:</span><span class="sxs-lookup"><span data-stu-id="14e38-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="14e38-123">IP-PBX que oferece suporte ao desvio de mídia, com um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="14e38-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="14e38-124">IP-PBX que requer um gateway PSTN autônomo.</span><span class="sxs-lookup"><span data-stu-id="14e38-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="14e38-125">Conexão PBX TDM, com um gateway PSTN autônomo.</span><span class="sxs-lookup"><span data-stu-id="14e38-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="14e38-126">O desvio de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="14e38-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="14e38-127">A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com o IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="14e38-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="14e38-128">O bypass de mídia só tem suporte com produtos e versões listados no Programa de Interoperabilidade Aberta de Comunicações [Unificadas - Lync Server.](https://go.microsoft.com/fwlink/p/?linkId=214406)</span><span class="sxs-lookup"><span data-stu-id="14e38-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="14e38-129">Para obter detalhes sobre parceiros que oferecem soluções enterprise voice, consulte o [site do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="14e38-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="14e38-130">Para obter detalhes sobre parceiros que oferecem soluções de hardware do Enterprise Voice, incluindo gateways PSTN, consulte o site [do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="14e38-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

