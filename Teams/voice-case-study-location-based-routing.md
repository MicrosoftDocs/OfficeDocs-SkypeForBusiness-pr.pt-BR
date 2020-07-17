---
title: Estudo de caso da Contoso Voice Teams
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
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785938"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="370f5-103">Estudo de caso da Contoso: roteamento baseado em localização</span><span class="sxs-lookup"><span data-stu-id="370f5-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="370f5-104">O roteamento baseado em local (LBR) é um recurso que restringe o intervalo de chamadas com base na política e na localização física do usuário no momento da inserção ou recebimento de uma chamada.</span><span class="sxs-lookup"><span data-stu-id="370f5-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="370f5-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="370f5-105">Overview</span></span>

<span data-ttu-id="370f5-106">A contoso tem dois escritórios em um país onde é ilegal ignorar o provedor PSTN (rede telefônica pública comutada) para reduzir os custos de chamadas de longa distância.</span><span class="sxs-lookup"><span data-stu-id="370f5-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="370f5-107">O escritório principal tem uma conexão à Internet que é usada pelo escritório principal e pelo segundo Office.</span><span class="sxs-lookup"><span data-stu-id="370f5-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="370f5-108">Cada escritório tem seu próprio controlador de borda de sessão (SBC) conectado a uma operadora PSTN.</span><span class="sxs-lookup"><span data-stu-id="370f5-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="370f5-109">Neste país, a Contoso tinha LBR configurado para a implantação do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="370f5-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="370f5-110">Para determinar como configurar o LBR para Teams, o [roteamento baseado em local de plano de leitura da Contoso para roteamento direto](location-based-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="370f5-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="370f5-111">A contoso determinou que o Microsoft Teams e o Skype for Business seguem os mesmos cenários em que uma chamada pode ser feita, quando ela pode ser recebida, quando uma chamada PSTN pode ser transferida para um usuário do Teams e quando você pode transferir outro usuário do Team para a chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="370f5-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="370f5-112">Para o Skype for Business, o LBR foi configurado com o tronco SIP do controlador de borda de sessão (SBC) conectado à operadora PSTN.</span><span class="sxs-lookup"><span data-stu-id="370f5-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="370f5-113">Para este SBC, a contoso analisou a [lista de SBCS certificado](direct-routing-border-controllers.md) e determinou que o SBC implantado é certificado para roteamento direto, mas não é certificado para bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="370f5-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="370f5-114">Para dar suporte ao LBR, o roteamento direto precisa ser configurado para o SBC no local, deve ser um egresso de Internet local, e o SBC precisa estar configurado para bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="370f5-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="370f5-115">Com base nessas informações, a Contoso decidiu o seguinte:</span><span class="sxs-lookup"><span data-stu-id="370f5-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="370f5-116">Para atrasar a habilitação de Teams LBR até que o SBC existente seja certificado para bypass de mídia.</span><span class="sxs-lookup"><span data-stu-id="370f5-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="370f5-117">A Contoso decidiu usar o SBC do site principal para a rota direta para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="370f5-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="370f5-118">O SBC do site principal será o SBC do proxy para o site remoto.</span><span class="sxs-lookup"><span data-stu-id="370f5-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="370f5-119">A contoso usou um consultor de terceiros baseado na Índia para auxiliar na certificação da configuração do LBR com a empresa de telefonia do país.</span><span class="sxs-lookup"><span data-stu-id="370f5-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="370f5-120">Para dar suporte a usuários que trabalham fora do escritório para fazer chamadas PSTN, o celular emitido pela empresa foi fornecido para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="370f5-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="370f5-121">Os diagramas a seguir mostram as implantações antes e depois de um país com regulamentos de telefonia que exigem roteamento baseado em localização:</span><span class="sxs-lookup"><span data-stu-id="370f5-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="370f5-122">**Implantação original**</span><span class="sxs-lookup"><span data-stu-id="370f5-122">**Original deployment**</span></span>

![Diagrama mostrando o estado anterior](media/voice-case-study-5.png)

<span data-ttu-id="370f5-124">**Implantação com roteamento direto**</span><span class="sxs-lookup"><span data-stu-id="370f5-124">**Deployment with Direct Routing**</span></span>

![Diagrama mostrando o estado anterior](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="370f5-126">Configuração</span><span class="sxs-lookup"><span data-stu-id="370f5-126">Configuration:</span></span> 

<span data-ttu-id="370f5-127">Para configurar os componentes de rede no Teams, a contoso seguiu as instruções em [gerenciar a topologia de rede para recursos de voz na nuvem](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="370f5-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="370f5-128">A contoso concluiu as etapas abaixo para configurar o roteamento baseado em localização:</span><span class="sxs-lookup"><span data-stu-id="370f5-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="370f5-129">Definir regiões de rede-uma região de rede foi definida.</span><span class="sxs-lookup"><span data-stu-id="370f5-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="370f5-130">Definir sites de rede-dois sites de rede foram definidos.</span><span class="sxs-lookup"><span data-stu-id="370f5-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="370f5-131">Um site para cada local do escritório na região.</span><span class="sxs-lookup"><span data-stu-id="370f5-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="370f5-132">Definir sub-redes de rede: cada andar dentro de um local de escritório tem sua própria sub-rede para a rede com fio e sem fio.</span><span class="sxs-lookup"><span data-stu-id="370f5-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="370f5-133">Essa configuração resultou em 20 sub-redes para contoso.</span><span class="sxs-lookup"><span data-stu-id="370f5-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="370f5-134">Definir endereços IP confiáveis-os endereços IP externos para o SBC foram adicionados ao endereço IP confiável.</span><span class="sxs-lookup"><span data-stu-id="370f5-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

