---
title: Monitorar e melhorar a qualidade das chamadas para o Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use as configurações de qualidade do serviço (QoS) e, em seguida, faça a análise de chamada e painel de qualidade da chamada no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085928"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="89688-103">Monitorar e melhorar a qualidade das chamadas para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="89688-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="89688-104">Este artigo apresenta três ferramentas importantes que você pode usar para monitorar, solucionar problemas, gerenciar e melhorar a qualidade das chamadas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="89688-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="89688-105">**Painel de qualidade de chamada (CQD)**: para analisar tendências ou problemas de toda a organização, melhorar o desempenho</span><span class="sxs-lookup"><span data-stu-id="89688-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="89688-106">**Análise de chamadas**: para analisar a qualidade da chamada e da reunião para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="89688-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="89688-107">**QoS (qualidade de serviço)**: priorizar o tráfego de rede importante</span><span class="sxs-lookup"><span data-stu-id="89688-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="89688-108">Monitorar e solucionar problemas com a qualidade das chamadas</span><span class="sxs-lookup"><span data-stu-id="89688-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="89688-109">Você usará a análise de **chamadas** por usuário e o **painel de qualidade da chamada** para encontrar e solucionar problemas de qualidade de chamada que surgem durante a operação contínua.</span><span class="sxs-lookup"><span data-stu-id="89688-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="89688-110">Isso permite que você conduza melhorias de desempenho em toda a sua rede.</span><span class="sxs-lookup"><span data-stu-id="89688-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="89688-111">Ambas as ferramentas estão no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="89688-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="89688-112">A **análise de chamadas** mostra informações detalhadas sobre os dispositivos, redes e conectividade relacionados a ***chamadas e reuniões específicas*** para cada usuário no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="89688-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in Teams.</span></span> <span data-ttu-id="89688-113">Os agentes de administração do Teams e da assistência técnica usarão essas informações para solucionar problemas de qualidade de chamada e conexão em uma chamada específica.</span><span class="sxs-lookup"><span data-stu-id="89688-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="89688-114">Para saber mais, leia [Configurar análise de chamadas](set-up-call-analytics.md) e [use a análise de chamadas para solucionar problemas de qualidade de chamadas ruins](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="89688-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="89688-115">O **painel de qualidade de chamada (CQD)** oferece uma ***visão geral*** da qualidade das chamadas em toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="89688-115">**Call Quality Dashboard (CQD)** gives you a ***network-wide view*** of call quality across your organization.</span></span> <span data-ttu-id="89688-116">Use as informações do CQD para ajudá-lo a identificar e corrigir problemas.</span><span class="sxs-lookup"><span data-stu-id="89688-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="89688-117">Primeiro, [Configure o CQD](turning-on-and-using-call-quality-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="89688-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="89688-118">Em seguida, leia [gerenciar a qualidade da chamada e da reunião no Teams](quality-of-experience-review-guide.md).</span><span class="sxs-lookup"><span data-stu-id="89688-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="89688-119">A análise de chamadas e o CQD são executados em paralelo e podem ser usados de forma independente ou em conjunto.</span><span class="sxs-lookup"><span data-stu-id="89688-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="89688-120">Por exemplo, se um especialista em suporte a comunicações determinar que precisa de mais ajuda para solucionar o problema de chamada de um usuário, ele escalonará a chamada para um engenheiro de suporte a comunicações, que terá acesso a informações adicionais sobre a chamada.</span><span class="sxs-lookup"><span data-stu-id="89688-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="89688-121">Por sua vez, o engenheiro de suporte à comunicação alerta um engenheiro de rede para um possível problema relacionado a sites que observou na análise de chamadas.</span><span class="sxs-lookup"><span data-stu-id="89688-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="89688-122">O engenheiro de rede verifica CQD para ver se um problema geral relacionado ao site pode ser um motivo contribuinte do problema com a chamada do usuário.</span><span class="sxs-lookup"><span data-stu-id="89688-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="89688-123">Priorize o tráfego de rede importante usando QoS</span><span class="sxs-lookup"><span data-stu-id="89688-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="89688-124">À medida que seus usuários começarem a usar o Microsoft Teams para chamadas e reuniões, eles poderão enfrentar a voz de um autor ou recortar ou recortar uma chamada ou reunião.</span><span class="sxs-lookup"><span data-stu-id="89688-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="89688-125">O vídeo compartilhado pode congelar ou ser pixel ou falhar completamente.</span><span class="sxs-lookup"><span data-stu-id="89688-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="89688-126">Isso ocorre devido aos pacotes de IP que representam o tráfego de voz e vídeo que está encontrando o congestionamento da rede e que chega fora de sequência.</span><span class="sxs-lookup"><span data-stu-id="89688-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="89688-127">Se isso acontecer (ou para impedir que isso aconteça em primeiro lugar), use a **QoS (qualidade de serviço)**.</span><span class="sxs-lookup"><span data-stu-id="89688-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="89688-128">Com a QoS, você prioriza o tráfego de rede sensível à demora (por exemplo, fluxos de voz ou vídeo), permitindo que ele seja "recortado em linha" na frente do tráfego que seja menos confidencial (como baixar um novo aplicativo, onde um segundo adicional para baixar não é um negócio).</span><span class="sxs-lookup"><span data-stu-id="89688-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="89688-129">A QoS identifica e marca todos os pacotes em fluxos em tempo real usando objetos de política de grupo do Windows e um recurso de roteamento chamado de listas de controle de acesso baseado em porta, o que instrui sua rede a fornecer voz, vídeo e tela que compartilhem sua própria largura de banda de rede dedicada.</span><span class="sxs-lookup"><span data-stu-id="89688-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="89688-130">O ideal é que você implemente a QoS na sua rede interna enquanto estiver pronto para implantar o Microsoft Teams, mas você pode fazer isso a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="89688-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="89688-131">Se você for suficientemente pequeno, talvez não precise de QoS.</span><span class="sxs-lookup"><span data-stu-id="89688-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="89688-132">Quando estiver pronto, leia [implementar qualidade de serviço (QoS) no Microsoft Teams](QoS-in-Teams.md).</span><span class="sxs-lookup"><span data-stu-id="89688-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="89688-133">Para usar a QoS para gerenciar o tráfego de reunião, confira [definir como deseja manipular o tráfego de mídia em tempo real para reuniões de equipe](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span><span class="sxs-lookup"><span data-stu-id="89688-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="89688-134">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="89688-134">Related Topics</span></span>

[<span data-ttu-id="89688-135">Configurar a análise de chamadas</span><span class="sxs-lookup"><span data-stu-id="89688-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="89688-136">Usar a Análise de Chamada para solucionar problemas de baixa qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="89688-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="89688-137">Configurar o CQD</span><span class="sxs-lookup"><span data-stu-id="89688-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="89688-138">Gerenciar a qualidade da chamada e da reunião no Teams</span><span class="sxs-lookup"><span data-stu-id="89688-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="89688-139">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="89688-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

