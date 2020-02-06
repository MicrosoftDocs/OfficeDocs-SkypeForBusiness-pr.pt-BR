---
title: Componentes de conectividade PSTN no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Saiba mais sobre o entroncamento SIP e os gateways PSTN para Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 443f5425beeed5b032968837ac56ce3a26468cdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802531"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a><span data-ttu-id="2a584-103">Componentes de conectividade PSTN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2a584-103">PSTN connectivity components in Skype for Business Server</span></span>
 
<span data-ttu-id="2a584-104">Saiba mais sobre o entroncamento SIP e os gateways PSTN para Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2a584-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="2a584-105">Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço).</span><span class="sxs-lookup"><span data-stu-id="2a584-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="2a584-106">Além disso, os usuários não devem perceber a tecnologia subjacente ao fazer e receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="2a584-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="2a584-107">Da perspectiva do usuário, uma chamada entre a infraestrutura Enterprise Voice e a PSTN deve parecer apenas com outra sessão SIP.</span><span class="sxs-lookup"><span data-stu-id="2a584-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="2a584-108">Para conexões PSTN, você pode implantar um tronco SIP ou um gateway PSTN (com um PBX, também conhecido como um link do SIP Direto, ou sem um PBX).</span><span class="sxs-lookup"><span data-stu-id="2a584-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="2a584-109">Tronco SIP</span><span class="sxs-lookup"><span data-stu-id="2a584-109">SIP Trunking</span></span>

<span data-ttu-id="2a584-110">Como uma alternativa para o uso de gateways PSTN, você pode conectar sua solução Enterprise Voice à PSTN usando o entroncamento SIP.</span><span class="sxs-lookup"><span data-stu-id="2a584-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="2a584-111">O tronco SIP permite os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="2a584-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="2a584-112">Um usuário corporativo dentro ou fora do firewall corporativo pode fazer uma chamada local ou interurbana especificada por um número em conformidade com E.164 que é encerrado no PSTN como um serviço do provedor de serviços correspondente.</span><span class="sxs-lookup"><span data-stu-id="2a584-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="2a584-113">Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário.</span><span class="sxs-lookup"><span data-stu-id="2a584-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="2a584-114">O uso dessa solução de implantação requer um provedor de serviços de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="2a584-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="2a584-115">Gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="2a584-115">PSTN gateways</span></span>

<span data-ttu-id="2a584-116">Os gateways PSTN são dispositivos de terceiros que traduzem sinais e mídias entre a infraestrutura do Enterprise Voice e uma PSTN ou PBX.</span><span class="sxs-lookup"><span data-stu-id="2a584-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="2a584-117">Os gateways PSTN funcionam com o servidor de mediação para apresentar uma PSTN ou uma chamada PBX para um cliente Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2a584-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="2a584-118">O servidor de mediação também apresenta chamadas de clientes do Enterprise Voice para o gateway PSTN para roteamento para a PSTN ou PBX.</span><span class="sxs-lookup"><span data-stu-id="2a584-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="2a584-119">Para obter uma lista dos parceiros que trabalham com a Microsoft para fornecer dispositivos que funcionam com o Skype for Business Server, consulte [o website Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="2a584-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="2a584-120">Centrais privadas de comutação telefônica</span><span class="sxs-lookup"><span data-stu-id="2a584-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="2a584-121">Se você tiver uma infraestrutura de voz existente que usa um PBX (Private Branch Exchange), você pode usar seu PBX com o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2a584-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="2a584-122">Os cenários de integração de Enterprise Voice-PBX compatíveis são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="2a584-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="2a584-123">PBX IP que dá suporte ao bypass de mídia, com um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="2a584-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="2a584-124">IP-PBX que requer um gateway PSTN autônomo.</span><span class="sxs-lookup"><span data-stu-id="2a584-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="2a584-125">Conexão PBX TDM, com um gateway PSTN autônomo.</span><span class="sxs-lookup"><span data-stu-id="2a584-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2a584-126">O bypass de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="2a584-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="2a584-127">A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="2a584-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="2a584-128">O bypass de mídia só tem suporte com produtos e versões listados no [programa de interoperabilidade aberta da comunicação unificada-Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="2a584-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="2a584-129">Para obter detalhes sobre os parceiros que oferecem soluções Enterprise Voice, consulte o [website Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="2a584-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="2a584-130">Para obter detalhes sobre os parceiros que oferecem soluções de hardware de Voice Enterprise, incluindo gateways PSTN, consulte o [website Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="2a584-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

