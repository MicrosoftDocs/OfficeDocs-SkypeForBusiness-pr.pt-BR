---
title: Planejar a conectividade PSTN no Skype for Business Server
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Planeje a conectividade PSTN no Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813561"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="a4827-103">Planejar a conectividade PSTN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a4827-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="a4827-104">Planeje a conectividade PSTN no Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a4827-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="a4827-105">Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para a PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço).</span><span class="sxs-lookup"><span data-stu-id="a4827-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="a4827-106">Os usuários que faz e recebem chamadas não devem estar cientes da tecnologia subjacente: da perspectiva do usuário, uma chamada entre a infraestrutura do Enterprise Voice e a PSTN deve parecer apenas outra chamada telefônica.</span><span class="sxs-lookup"><span data-stu-id="a4827-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="a4827-107">O Skype for Business Server fornece conectividade PSTN confiável e escalonável usando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a4827-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="a4827-108">**Troncos SIP** para um provedor de serviço de telefonia da Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="a4827-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="a4827-109">**Conexões SIP diretas** com um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="a4827-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="a4827-110">**Conexões SIP diretas** com um PBX</span><span class="sxs-lookup"><span data-stu-id="a4827-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="a4827-111">Dependendo de seu tamanho, cobertura geográfica e infraestrutura de voz existente, uma determinada empresa pode usar uma, duas ou até mesmo três opções em vários locais.</span><span class="sxs-lookup"><span data-stu-id="a4827-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="a4827-112">Para obter detalhes sobre essas opções, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="a4827-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="a4827-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a4827-113">In this section</span></span>

- [<span data-ttu-id="a4827-114">Tronco SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a4827-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="a4827-115">Conexões SIP diretas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a4827-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="a4827-116">Tronco M:N no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a4827-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="a4827-117">Regras de conversão no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a4827-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="a4827-118">Planejar o roteamento de voz de saída no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a4827-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

