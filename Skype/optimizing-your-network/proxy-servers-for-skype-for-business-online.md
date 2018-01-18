---
title: Servidores Proxy para Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "Este artigo fornecerá diretrizes para você usar um servidor proxy com o Skype for Business."
ms.openlocfilehash: 325e48c7bfaeffca7c34915e176772f0824903f6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="b19ea-103">Servidores Proxy para Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b19ea-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="b19ea-104">Este artigo fornecerá diretrizes para você usar um servidor proxy com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b19ea-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="b19ea-105">É recomendável não usar um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="b19ea-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="b19ea-p101">Quanto ao tráfego do Skype for Business por meio de proxies, a Microsoft recomenda não usar proxies. Os proxies não tornam o Skype for Business mais seguro, porque seu tráfego já é criptografado.</span><span class="sxs-lookup"><span data-stu-id="b19ea-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="b19ea-p102">E o uso de um proxy pode ocasionar problemas. Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote. Esses problemas resultarão em uma experiência negativa em cenários do Skype for Business como áudio e vídeo, onde streams em tempo real são essenciais.</span><span class="sxs-lookup"><span data-stu-id="b19ea-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="b19ea-111">Caso seja necessário o uso de um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="b19ea-111">If you need to use a proxy server</span></span>

<span data-ttu-id="b19ea-p103">Algumas organizações não têm a opção de não usar um proxy para o tráfego do Skype for Business. Nesse caso, os problemas mencionados acima deverão ser levados em consideração.</span><span class="sxs-lookup"><span data-stu-id="b19ea-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="b19ea-114">A Microsoft também recomenda:</span><span class="sxs-lookup"><span data-stu-id="b19ea-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="b19ea-115">O uso de resolução DNS externa</span><span class="sxs-lookup"><span data-stu-id="b19ea-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="b19ea-116">O uso de UDP direto com base em roteamento</span><span class="sxs-lookup"><span data-stu-id="b19ea-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="b19ea-117">Permissão para tráfego UDP</span><span class="sxs-lookup"><span data-stu-id="b19ea-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="b19ea-118">A seguir são apresentadas outras recomendações que constam em nossas diretrizes de rede:</span><span class="sxs-lookup"><span data-stu-id="b19ea-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="b19ea-119">Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b19ea-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="b19ea-120">Como otimizar sua rede para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b19ea-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="b19ea-121">A observação desta diretriz minimizará problemas potenciais.</span><span class="sxs-lookup"><span data-stu-id="b19ea-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="b19ea-122">Os fornecedores proxy com o Skype for Business embutido oferecem suporte ou opções de configuração</span><span class="sxs-lookup"><span data-stu-id="b19ea-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="b19ea-123">Esta seção apresentará informações sobre fornecedores de proxy que fornecem produtos ou serviços que, comprovadamente, funcionam bem com o tráfego do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b19ea-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="b19ea-124">Para as organizações que usam as **soluções Bluecoat Proxy**, foi lançado um novo firmware que trata de vários problemas relacionados a:</span><span class="sxs-lookup"><span data-stu-id="b19ea-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="b19ea-125">Interceptação SSL</span><span class="sxs-lookup"><span data-stu-id="b19ea-125">SSL interception</span></span>
    
  - <span data-ttu-id="b19ea-126">Verificações de OCSP/SRL</span><span class="sxs-lookup"><span data-stu-id="b19ea-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="b19ea-127">SIP por meio de TLS</span><span class="sxs-lookup"><span data-stu-id="b19ea-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="b19ea-128">Suporte para TURN</span><span class="sxs-lookup"><span data-stu-id="b19ea-128">support for TURN</span></span>
    
<span data-ttu-id="b19ea-p104">O suporte nativo do Bluecoat para Skype for Business pode ser facilmente ativado, permitindo a identificação de tráfego relevante, e gerenciando-o adequadamente. Isso assegura autenticação, sinalização e fluxo de tráfego de mídia otimizados a fim de fornecer uma excelente experiência do usuário sem preocupações com segurança.</span><span class="sxs-lookup"><span data-stu-id="b19ea-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="b19ea-131">Consulte o seguinte link se Bluecoat Proxy é uma parte de sua topologia de rede: https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="b19ea-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="b19ea-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b19ea-132">Related topics</span></span>

[<span data-ttu-id="b19ea-133">Como otimizar sua rede para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b19ea-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)