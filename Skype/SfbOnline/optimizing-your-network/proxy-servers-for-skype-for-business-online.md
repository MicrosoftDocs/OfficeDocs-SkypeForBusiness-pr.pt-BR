---
title: Servidores Proxy para Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Este artigo fornecerá diretrizes para você usar um servidor proxy com o Skype for Business.
ms.openlocfilehash: fcae4ec366845818d515a4d78c79ea77d038a4a5
ms.sourcegitcommit: abc0f95ef0efe15a8c38cc27a3991abf7480c30e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2018
ms.locfileid: "20211018"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="e2bcc-103">Servidores Proxy para Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2bcc-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="e2bcc-104">Este artigo fornecerá diretrizes para você usar um servidor proxy com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e2bcc-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="e2bcc-105">É recomendável não usar um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="e2bcc-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="e2bcc-p101">Quanto ao tráfego do Skype for Business por meio de proxies, a Microsoft recomenda não usar proxies. Os proxies não tornam o Skype for Business mais seguro, porque seu tráfego já é criptografado.</span><span class="sxs-lookup"><span data-stu-id="e2bcc-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="e2bcc-p102">E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Esses problemas resultarão em uma experiência negativa em cenários do Skype for Business como áudio e vídeo, onde streams em tempo real são essenciais.</span><span class="sxs-lookup"><span data-stu-id="e2bcc-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="e2bcc-111">Caso seja necessário o uso de um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="e2bcc-111">If you need to use a proxy server</span></span>

<span data-ttu-id="e2bcc-p103">Algumas organizações não têm a opção de não usar um proxy para o tráfego do Skype for Business. Nesse caso, os problemas mencionados acima deverão ser levados em consideração.</span><span class="sxs-lookup"><span data-stu-id="e2bcc-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="e2bcc-114">A Microsoft também recomenda:</span><span class="sxs-lookup"><span data-stu-id="e2bcc-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="e2bcc-115">O uso de resolução DNS externa</span><span class="sxs-lookup"><span data-stu-id="e2bcc-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="e2bcc-116">O uso de UDP direto com base em roteamento</span><span class="sxs-lookup"><span data-stu-id="e2bcc-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="e2bcc-117">Permissão para tráfego UDP</span><span class="sxs-lookup"><span data-stu-id="e2bcc-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="e2bcc-118">A seguir são apresentadas outras recomendações que constam em nossas diretrizes de rede:</span><span class="sxs-lookup"><span data-stu-id="e2bcc-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="e2bcc-119">Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2bcc-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="e2bcc-120">Como otimizar sua rede para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2bcc-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="e2bcc-121">A observação desta diretriz minimizará problemas potenciais.</span><span class="sxs-lookup"><span data-stu-id="e2bcc-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2bcc-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e2bcc-122">Related topics</span></span>

[<span data-ttu-id="e2bcc-123">Como otimizar sua rede para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e2bcc-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 