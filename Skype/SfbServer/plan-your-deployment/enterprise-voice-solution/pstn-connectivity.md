---
title: Componentes de conectividade de PSTN no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Saiba mais sobre o tronco SIP e gateways PSTN para o Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: 4f346209b483a3d469beba233bd22ee39e45745a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a><span data-ttu-id="3dcb7-103">Componentes de conectividade de PSTN no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3dcb7-103">PSTN connectivity components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3dcb7-104">Saiba mais sobre o tronco SIP e gateways PSTN para o Enterprise Voice no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-104">Learn about SIP trunking and PSTN gateways for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="3dcb7-105">Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço).</span><span class="sxs-lookup"><span data-stu-id="3dcb7-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="3dcb7-106">Além disso, os usuários não devem perceber a tecnologia subjacente ao fazer e receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-106">In addition, users should not be aware of the underlying technology when they place and receive calls.</span></span> <span data-ttu-id="3dcb7-107">Da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve ser semelhante a uma outra sessão SIP.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-107">From the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another SIP session.</span></span>
  
<span data-ttu-id="3dcb7-108">Para conexões PSTN, você pode implantar um tronco SIP ou um gateway PSTN (com um PBX, também conhecido como um link do SIP Direto, ou sem um PBX).</span><span class="sxs-lookup"><span data-stu-id="3dcb7-108">For PSTN connections, you can either deploy a SIP trunk or a PSTN gateway (with a PBX, also known as a Direct SIP link, or without a PBX).</span></span>
  
## <a name="sip-trunking"></a><span data-ttu-id="3dcb7-109">Tronco SIP</span><span class="sxs-lookup"><span data-stu-id="3dcb7-109">SIP Trunking</span></span>

<span data-ttu-id="3dcb7-110">Como alternativa ao uso de gateways PSTN, você pode conectar a solução Enterprise Voice à PSTN usando o tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-110">As an alternative to using PSTN gateways, you can connect your Enterprise Voice solution to the PSTN by using SIP trunking.</span></span> <span data-ttu-id="3dcb7-111">O tronco SIP permite os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="3dcb7-111">SIP trunking enables the following scenarios:</span></span>
  
- <span data-ttu-id="3dcb7-112">Um usuário corporativo dentro ou fora do firewall corporativo pode fazer uma chamada local ou interurbana especificada por um número em conformidade com E.164 que é encerrado no PSTN como um serviço do provedor de serviços correspondente.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-112">An enterprise user inside or outside the corporate firewall can make a local or long-distance call specified by an E.164-compliant number that is terminated on the PSTN as a service of the corresponding service provider.</span></span>
    
- <span data-ttu-id="3dcb7-113">Qualquer assinante do PSTN pode entrar em contato com um usuário corporativo dentro ou fora do firewall corporativo ao discar um número DID (Discagem Direta Interna) associado àquele usuário.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-113">Any PSTN subscriber can contact an enterprise user inside or outside the corporate firewall by dialing a Direct Inward Dialing (DID) number associated with that enterprise user.</span></span>
    
<span data-ttu-id="3dcb7-114">O uso dessa solução de implantação requer um provedor de serviços de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-114">The use of this deployment solution requires a SIP trunking service provider.</span></span> 
  
## <a name="pstn-gateways"></a><span data-ttu-id="3dcb7-115">Gateways PSTN</span><span class="sxs-lookup"><span data-stu-id="3dcb7-115">PSTN gateways</span></span>

<span data-ttu-id="3dcb7-116">Gateways PSTN são dispositivos de terceiros que convertem a sinalização e mídia entre a infraestrutura do Enterprise Voice e uma PSTN ou um PBX.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-116">PSTN gateways are third-party devices that translate signaling and media between the Enterprise Voice infrastructure and a PSTN or a PBX.</span></span> <span data-ttu-id="3dcb7-117">Gateways PSTN funcionam com o servidor de mediação para apresentar uma chamada PSTN ou PBX para um cliente Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-117">PSTN gateways work with the Mediation Server to present a PSTN or PBX call to an Enterprise Voice client.</span></span> <span data-ttu-id="3dcb7-118">O servidor de mediação também apresenta chamadas de clientes do Enterprise Voice para o gateway PSTN para rotear para a PSTN ou PBX.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-118">The Mediation Server also presents calls from Enterprise Voice clients to the PSTN gateway for routing to the PSTN or PBX.</span></span> <span data-ttu-id="3dcb7-119">Para obter uma lista de parceiros que trabalham com a Microsoft para fornecer dispositivos que funcionem com Skype para Business Server, consulte [o site do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="3dcb7-119">For a list of partners who work with Microsoft to provide devices that work with Skype for Business Server, see  [the Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span> 
  
## <a name="private-branch-exchanges"></a><span data-ttu-id="3dcb7-120">Centrais privadas de comutação telefônica</span><span class="sxs-lookup"><span data-stu-id="3dcb7-120">Private Branch Exchanges</span></span>

 <span data-ttu-id="3dcb7-121">Se você tiver uma infraestrutura de voz existente que usa uma troca privada de comutação (PBX), você pode usar sua PBX com o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-121">If you have an existing voice infrastructure that uses a private branch exchange (PBX), you can use your PBX with Enterprise Voice.</span></span>
  
<span data-ttu-id="3dcb7-122">Cenários de integração de PBX Enterprise Voice com suporte são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="3dcb7-122">The supported Enterprise Voice-PBX integration scenarios are as follows:</span></span>
  
- <span data-ttu-id="3dcb7-123">IP-PBX que suporta bypass de mídia com um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-123">IP-PBX that supports media bypass, with a Mediation Server.</span></span>
    
- <span data-ttu-id="3dcb7-124">IP-PBX que requer um gateway PSTN autônomo.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-124">IP-PBX that requires a stand-alone PSTN gateway.</span></span>
    
- <span data-ttu-id="3dcb7-125">Conexão PBX TDM, com um gateway PSTN autônomo.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-125">Time division multiplexing (TDM) PBX, with a stand-alone PSTN gateway.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3dcb7-126">O bypass de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-126">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="3dcb7-127">A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e fez alguns testes com IP-PBXs da Cisco.</span><span class="sxs-lookup"><span data-stu-id="3dcb7-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="3dcb7-128">Bypass de mídia é suportado somente com produtos e versões listadas em [Unified Communications programa de interoperabilidade aberta - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span><span class="sxs-lookup"><span data-stu-id="3dcb7-128">Media bypass is supported only with products and versions listed at [Unified Communications Open Interoperability Program - Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406).</span></span> 
  
<span data-ttu-id="3dcb7-129">Para obter detalhes sobre parceiros que oferecem soluções do Enterprise Voice, consulte o [site do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="3dcb7-129">For details about partners who offer Enterprise Voice solutions, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  
<span data-ttu-id="3dcb7-130">Para obter detalhes sobre parceiros que oferecem soluções de hardware do Enterprise Voice, incluindo os gateways PSTN, consulte o [site do Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).</span><span class="sxs-lookup"><span data-stu-id="3dcb7-130">For details about partners who offer Enterprise Voice hardware solutions, including PSTN gateways, see the [Microsoft Unified Communications Partners website](https://go.microsoft.com/fwlink/p/?linkId=202836).</span></span>
  

