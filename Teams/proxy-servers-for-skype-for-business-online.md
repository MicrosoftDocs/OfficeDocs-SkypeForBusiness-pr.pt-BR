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
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Este artigo fornece informações sobre como usar um servidor proxy com Microsoft Teams ou Skype for Business.
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117719"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="4dabc-103">Servidores proxy para Teams ou Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4dabc-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="4dabc-104">Este artigo fornece orientações sobre como usar um servidor proxy com Teams ou Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4dabc-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="4dabc-105">É recomendável não usar um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="4dabc-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="4dabc-106">Quando se trata de Teams ou Skype for Business de proxies, a Microsoft recomenda ignorar proxies.</span><span class="sxs-lookup"><span data-stu-id="4dabc-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="4dabc-107">Os proxies não Teams ou Skype for Business mais seguros porque o tráfego já está criptografado.</span><span class="sxs-lookup"><span data-stu-id="4dabc-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="4dabc-108">E o uso de um proxy pode ocasionar problemas.</span><span class="sxs-lookup"><span data-stu-id="4dabc-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="4dabc-109">Problemas relacionados ao desempenho podem ocorrer no ambiente devido à latência e à perda de pacote.</span><span class="sxs-lookup"><span data-stu-id="4dabc-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="4dabc-110">Problemas como esses resultarão em uma experiência negativa em cenários Teams ou Skype for Business como áudio e vídeo, onde fluxos em tempo real são essenciais.</span><span class="sxs-lookup"><span data-stu-id="4dabc-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="4dabc-111">Caso seja necessário o uso de um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="4dabc-111">If you need to use a proxy server</span></span>

<span data-ttu-id="4dabc-112">Algumas organizações não têm opção de ignorar um proxy para Teams ou Skype for Business tráfego.</span><span class="sxs-lookup"><span data-stu-id="4dabc-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="4dabc-113">Nesse caso, os problemas mencionados acima deverão ser levados em consideração.</span><span class="sxs-lookup"><span data-stu-id="4dabc-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="4dabc-114">A Microsoft também recomenda:</span><span class="sxs-lookup"><span data-stu-id="4dabc-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="4dabc-115">O uso de resolução DNS externa</span><span class="sxs-lookup"><span data-stu-id="4dabc-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="4dabc-116">O uso de UDP direto com base em roteamento</span><span class="sxs-lookup"><span data-stu-id="4dabc-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="4dabc-117">Permissão para tráfego UDP</span><span class="sxs-lookup"><span data-stu-id="4dabc-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="4dabc-118">Seguindo as outras recomendações em nossas diretrizes de rede: [Preparar a](prepare-network.md) rede da sua organização para Teams</span><span class="sxs-lookup"><span data-stu-id="4dabc-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="4dabc-119">A observação desta diretriz minimizará problemas potenciais.</span><span class="sxs-lookup"><span data-stu-id="4dabc-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4dabc-120">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4dabc-120">Related topics</span></span>

[<span data-ttu-id="4dabc-121">Princípios de conectividade de rede do Microsoft 365 e do Office 365</span><span class="sxs-lookup"><span data-stu-id="4dabc-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="4dabc-122">Preparo da rede da sua organização para o Teams</span><span class="sxs-lookup"><span data-stu-id="4dabc-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)