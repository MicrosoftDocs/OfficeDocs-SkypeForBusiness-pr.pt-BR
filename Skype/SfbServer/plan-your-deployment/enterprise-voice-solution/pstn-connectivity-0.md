---
title: Planejamento de conectividade PSTN no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planejar a conectividade PSTN no Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: 785dd39d4a809283ae53f7eedbe398a6271b7c5b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server-2015"></a><span data-ttu-id="57f2f-103">Planejamento de conectividade PSTN no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="57f2f-103">Plan for PSTN connectivity in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="57f2f-104">Planejar a conectividade PSTN no Enterprise Voice no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="57f2f-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="57f2f-105">Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço).</span><span class="sxs-lookup"><span data-stu-id="57f2f-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="57f2f-106">Os usuários que façam e recebam chamadas não devem estar cientes da tecnologia subjacente: da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve ser semelhante a qualquer outra telefonema.</span><span class="sxs-lookup"><span data-stu-id="57f2f-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="57f2f-107">Skype para Business Server fornece uma conectividade PSTN confiável e escalável usando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="57f2f-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="57f2f-108">**Troncos SIP** para um provedor de serviços de telefonia da Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="57f2f-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="57f2f-109">**Conexões SIP diretas** com um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="57f2f-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="57f2f-110">**Conexões SIP diretas** com um PBX</span><span class="sxs-lookup"><span data-stu-id="57f2f-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="57f2f-p102">Dependendo de seu tamanho, cobertura geográfica e infraestrutura de voz existente, uma determinada empresa pode usar uma, duas ou até mesmo três opções em vários locais. Para obter detalhes sobre essas opções, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="57f2f-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="57f2f-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="57f2f-113">In this section</span></span>

- [<span data-ttu-id="57f2f-114">Tronco SIP no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="57f2f-114">SIP trunking in Skype for Business Server 2015</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="57f2f-115">Conexões SIP diretas no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="57f2f-115">Direct SIP connections in Skype for Business Server 2015</span></span>](direct-sip.md)
    
- [<span data-ttu-id="57f2f-116">Tronco M:N no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="57f2f-116">M:N trunk in Skype for Business Server 2015</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="57f2f-117">Regras de conversão no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="57f2f-117">Translation rules in Skype for Business Server 2015</span></span>](translation-rules.md)
    
- [<span data-ttu-id="57f2f-118">Planejar o roteamento de voz de saída em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="57f2f-118">Plan for outbound voice routing in Skype for Business Server 2015</span></span>](outbound-voice-routing.md)
    

