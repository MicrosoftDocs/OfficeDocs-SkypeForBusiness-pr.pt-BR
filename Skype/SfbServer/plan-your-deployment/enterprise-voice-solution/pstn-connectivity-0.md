---
title: Planejar a conectividade PSTN no Skype for Business Server
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Plano para conectividade PSTN no Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: 12c18ba0be3f01651fb72ff325d7e51566da86ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802541"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="f526b-103">Planejar a conectividade PSTN no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f526b-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="f526b-104">Plano para conectividade PSTN no Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f526b-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="f526b-105">Uma solução de VoIP em nível empresarial deve fornecer chamadas de e para PSTN (rede telefônica pública comutada), sem redução de QoS (Qualidade de Serviço).</span><span class="sxs-lookup"><span data-stu-id="f526b-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="f526b-106">Os usuários que fizerem e receberem chamadas não devem estar cientes da tecnologia subjacente: da perspectiva do usuário, uma chamada entre a infraestrutura Enterprise Voice e a PSTN deve parecer com apenas outra chamada telefônica.</span><span class="sxs-lookup"><span data-stu-id="f526b-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="f526b-107">O Skype for Business Server fornece conectividade PSTN confiável e escalonável usando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f526b-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="f526b-108">**Troncos SIP** para um provedor de serviços de telefonia da Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="f526b-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="f526b-109">**Conexões SIP diretas** com um gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="f526b-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="f526b-110">**Conexões SIP diretas** com um PBX</span><span class="sxs-lookup"><span data-stu-id="f526b-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="f526b-p102">Dependendo de seu tamanho, cobertura geográfica e infraestrutura de voz existente, uma determinada empresa pode usar uma, duas ou até mesmo três opções em vários locais. Para obter detalhes sobre essas opções, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="f526b-p102">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations. For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f526b-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f526b-113">In this section</span></span>

- [<span data-ttu-id="f526b-114">Entroncamento SIP no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f526b-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="f526b-115">Conexões SIP diretas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f526b-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="f526b-116">Tronco M:N no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f526b-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="f526b-117">Regras de tradução no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f526b-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="f526b-118">Plano para roteamento de voz de saída no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f526b-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

