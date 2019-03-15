---
title: Servidores proxy para Teams ou Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection: M365-collaboration
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Este artigo fornece informações sobre como usar um servidor proxy com equipes ou Skype para negócios.
ms.openlocfilehash: a09a1bf53fe4d1a38742856c051a80e5928f36ef
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640894"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="cdc07-103">Servidores proxy para Teams ou Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cdc07-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="cdc07-104">Este artigo fornece orientação sobre como usar um servidor proxy com equipes ou Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="cdc07-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="cdc07-105">É recomendável não usar um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="cdc07-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="cdc07-106">Quando se trata de equipes ou Skype para tráfego de negócios sobre proxies, a Microsoft recomenda ignorando proxies.</span><span class="sxs-lookup"><span data-stu-id="cdc07-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="cdc07-107">Proxies não fizer equipes ou Skype para negócios mais seguro porque o tráfego já está criptografado.</span><span class="sxs-lookup"><span data-stu-id="cdc07-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="cdc07-108">E o uso de um proxy pode ocasionar problemas.</span><span class="sxs-lookup"><span data-stu-id="cdc07-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="cdc07-109">Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="cdc07-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="cdc07-110">Problemas como essas resultará em uma experiência negativa em tais equipes ou Skype para cenários de negócios, como áudio e vídeo, onde fluxos em tempo real são essenciais.</span><span class="sxs-lookup"><span data-stu-id="cdc07-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="cdc07-111">Caso seja necessário o uso de um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="cdc07-111">If you need to use a proxy server</span></span>

<span data-ttu-id="cdc07-112">Algumas organizações não têm nenhuma opção para ignorar um proxy para equipes ou Skype para tráfego de negócios.</span><span class="sxs-lookup"><span data-stu-id="cdc07-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="cdc07-113">Nesse caso, os problemas mencionados acima deverão ser levados em consideração.</span><span class="sxs-lookup"><span data-stu-id="cdc07-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="cdc07-114">A Microsoft também recomenda:</span><span class="sxs-lookup"><span data-stu-id="cdc07-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="cdc07-115">O uso de resolução DNS externa</span><span class="sxs-lookup"><span data-stu-id="cdc07-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="cdc07-116">O uso de UDP direto com base em roteamento</span><span class="sxs-lookup"><span data-stu-id="cdc07-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="cdc07-117">Permissão para tráfego UDP</span><span class="sxs-lookup"><span data-stu-id="cdc07-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="cdc07-118">Seguindo as outras recomendações em nossas diretrizes de redes:</span><span class="sxs-lookup"><span data-stu-id="cdc07-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="cdc07-119">Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cdc07-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="cdc07-120">Como otimizar sua rede para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cdc07-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="cdc07-121">A observação desta diretriz minimizará problemas potenciais.</span><span class="sxs-lookup"><span data-stu-id="cdc07-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="cdc07-122">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cdc07-122">Related topics</span></span>

[<span data-ttu-id="cdc07-123">Como otimizar sua rede para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cdc07-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 