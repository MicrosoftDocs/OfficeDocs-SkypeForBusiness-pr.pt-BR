---
title: Estudo de caso do Teams voice Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do Teams para corporação multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785938"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="7dc6a-103">Estudo de caso da Contoso: Location-Based Roteamento</span><span class="sxs-lookup"><span data-stu-id="7dc6a-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="7dc6a-104">Location-Based de roteamento (LBR) é um recurso que restringe o bypass de chamada tarifada com base na política e na localização física do usuário no momento de fazer ou receber uma chamada.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="7dc6a-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="7dc6a-105">Overview</span></span>

<span data-ttu-id="7dc6a-106">A Contoso tem dois escritórios em um país onde é ilegal ignorar o provedor de Rede Telefônica Pública Comutado (PSTN) para reduzir os custos de chamadas a longa distância.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="7dc6a-107">O escritório principal tem uma conexão com a Internet que é usada pelo escritório principal e pelo segundo escritório.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="7dc6a-108">Cada escritório tem seu próprio Controlador de Borda de Sessão (SBC) conectado a uma operadora PSTN.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="7dc6a-109">Nesse país, a Contoso tinha a LBR configurada para a implantação do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="7dc6a-110">Para determinar como configurar a LBR para Teams, leia o Plano de Location-Based [roteamento direto.](location-based-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="7dc6a-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="7dc6a-111">A Contoso determinou que o Teams e o Skype for Business seguem os mesmos cenários em que uma chamada pode ser feita, quando ela pode ser recebida, quando uma chamada PSTN pode ser transferida para um usuário do Teams e quando você pode transferir outro usuário do Teams para a chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="7dc6a-112">Para o Skype for Business, a LBR foi configurada com o Tronco SIP do Controlador de Borda de Sessão (SBC) conectando-se à operadora PSTN.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="7dc6a-113">Para esse SBC, a Contoso revisou a lista de [SBCs](direct-routing-border-controllers.md) certificados e determinou que o SBC implantado é certificado para Roteamento Direto, mas não é certificado para Bypass de Mídia.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="7dc6a-114">Para dar suporte à LBR, o Roteamento Direto precisa ser configurado para o SBC no local, deve haver uma saída de Internet local e o SBC precisa ser configurado para Bypass de Mídia.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="7dc6a-115">Com base nessa informação, a Contoso decidiu o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7dc6a-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="7dc6a-116">Para atrasar a habilitação do LBR do Teams até que o SBC existente seja certificado para Bypass de Mídia.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="7dc6a-117">A Contoso decidiu usar o SBC do site principal para a Rota Direta para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="7dc6a-118">O SBC do site principal será o SBC proxy do site remoto.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="7dc6a-119">A Contoso usou um consultor de terceiros com base na Índia para ajudar na certificação da configuração de LBR com a empresa de telefonia no país.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="7dc6a-120">Para dar suporte aos usuários que trabalham de fora do escritório para fazer chamadas PSTN, a empresa emitiu um telefone celular para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="7dc6a-121">Os diagramas a seguir mostram as implantações de antes e depois para um país com regulamentos de telefonia que exigem Location-Based Roteamento:</span><span class="sxs-lookup"><span data-stu-id="7dc6a-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="7dc6a-122">**Implantação original**</span><span class="sxs-lookup"><span data-stu-id="7dc6a-122">**Original deployment**</span></span>

![Diagrama mostrando antes do estado](media/voice-case-study-5.png)

<span data-ttu-id="7dc6a-124">**Implantação com Roteamento Direto**</span><span class="sxs-lookup"><span data-stu-id="7dc6a-124">**Deployment with Direct Routing**</span></span>

![Diagrama mostrando antes do estado](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="7dc6a-126">Configuração:</span><span class="sxs-lookup"><span data-stu-id="7dc6a-126">Configuration:</span></span> 

<span data-ttu-id="7dc6a-127">Para configurar os componentes de rede no Teams, a Contoso seguiu as instruções em Gerenciar sua topologia de rede [para recursos de voz na nuvem.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="7dc6a-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="7dc6a-128">A Contoso concluiu as etapas abaixo para configurar Location-Based Roteamento:</span><span class="sxs-lookup"><span data-stu-id="7dc6a-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="7dc6a-129">Definir regiões de rede - Uma região de rede foi definida.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="7dc6a-130">Definir sites de rede – Dois sites de rede foram definidos.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="7dc6a-131">Um site para cada local de escritório na região.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="7dc6a-132">Definir sub-redes de rede - Cada andar dentro de um local de escritório tem sua própria sub-rede para a rede com fio e sem fio.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="7dc6a-133">Essa configuração resultou em 20 sub-redes para a Contoso.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="7dc6a-134">Definir endereços IP confiáveis – os endereços IP voltados para externos para o SBC foram adicionados ao endereço IP confiável.</span><span class="sxs-lookup"><span data-stu-id="7dc6a-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

