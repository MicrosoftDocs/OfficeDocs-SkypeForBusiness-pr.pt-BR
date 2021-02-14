---
title: Configurar configurações de rede – roteamento baseado em local
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para Location-Based roteamento direto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822941"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="cb958-103">Configurar definições de rede para o Roteamento baseado na localização</span><span class="sxs-lookup"><span data-stu-id="cb958-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="cb958-104">Se você ainda não fez [](location-based-routing-plan.md) isso, leia Plano Location-Based Roteamento para Roteamento Direto para revisar outras etapas que você precisará seguir antes de definir as configurações de rede para Location-Based Roteamento.</span><span class="sxs-lookup"><span data-stu-id="cb958-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="cb958-105">Este artigo descreve como configurar as configurações de rede para Location-Based Roteamento.</span><span class="sxs-lookup"><span data-stu-id="cb958-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="cb958-106">Depois de implantar o Roteamento Direto do Sistema telefônico em sua organização, as próximas etapas são criar e configurar regiões de rede, sites de rede e sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="cb958-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="cb958-107">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="cb958-107">Define network regions</span></span>

<span data-ttu-id="cb958-108">Uma região de rede contém um conjunto de sites de rede e interconecta várias partes de uma rede em várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="cb958-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="cb958-109">Para ver as etapas sobre como configurar regiões de rede, acesse Gerenciar sua topologia de rede [para recursos de nuvem no Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="cb958-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="cb958-110">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="cb958-110">Define network sites</span></span>

<span data-ttu-id="cb958-111">Um site de rede representa um local onde sua organização tem um local físico, como um escritório, um conjunto de edifícios ou um campus.</span><span class="sxs-lookup"><span data-stu-id="cb958-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="cb958-112">Você deve associar cada site de rede em sua topologia a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="cb958-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="cb958-113">Para ver as etapas sobre como configurar sites de rede, consulte Gerenciar sua topologia de [rede para recursos de nuvem no Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="cb958-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="cb958-114">Uma prática Location-Based roteamento é criar um site separado para cada local que tenha conectividade PSTN exclusiva.</span><span class="sxs-lookup"><span data-stu-id="cb958-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="cb958-115">Você pode criar um site habilitado para Location-Based roteamento ou um site que não está habilitado para Location-Based Roteamento.</span><span class="sxs-lookup"><span data-stu-id="cb958-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="cb958-116">Por exemplo, talvez você queira criar um site que não está habilitado para o roteamento do Location-Based para permitir que os usuários habilitados para o roteamento do Location-Based façam chamadas PSTN quando eles são roteados para esse site.</span><span class="sxs-lookup"><span data-stu-id="cb958-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="cb958-117">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="cb958-117">Define network subnets</span></span>

<span data-ttu-id="cb958-118">Cada sub-rede deve estar associada a um site de rede específico.</span><span class="sxs-lookup"><span data-stu-id="cb958-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="cb958-119">Você pode associar várias sub-redes ao mesmo site de rede, mas não pode associar vários sites à mesma sub-rede.</span><span class="sxs-lookup"><span data-stu-id="cb958-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="cb958-120">Para ver as etapas sobre como configurar sub-redes de rede, vá para Gerenciar sua topologia de rede [para recursos de nuvem no Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="cb958-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="cb958-121">Para Location-Based roteamento, as sub-redes IP no local onde os pontos de extremidade do Teams podem se conectar à rede devem ser definidas e associadas a uma rede definida para impor o bypass de chamadas tarifadas.</span><span class="sxs-lookup"><span data-stu-id="cb958-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="cb958-122">Essa associação de sub-redes permite que Location-Based roteamento localize os pontos de extremidade geograficamente para determinar se uma determinada chamada PSTN deve ser permitida.</span><span class="sxs-lookup"><span data-stu-id="cb958-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="cb958-123">Há suporte para sub-redes IPv6 e IPv4.</span><span class="sxs-lookup"><span data-stu-id="cb958-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="cb958-124">Ao determinar se um ponto de extremidade do Teams está localizado em um site, o Location-Based primeiro verifica se há um endereço IPv6 correspondente.</span><span class="sxs-lookup"><span data-stu-id="cb958-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="cb958-125">Se um endereço IPv6 não estiver presente, o Location-Based roteamento verificará um endereço IPv4.</span><span class="sxs-lookup"><span data-stu-id="cb958-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="cb958-126">Definir endereços IP confiáveis (sub-redes externas)</span><span class="sxs-lookup"><span data-stu-id="cb958-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="cb958-127">Os endereços IP confiáveis são os endereços IP externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="cb958-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="cb958-128">Para ver as etapas sobre como configurar endereços IP confiáveis, acesse Gerenciar sua topologia de rede [para recursos de nuvem no Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="cb958-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="cb958-129">Se o endereço IP externo do usuário corresponde a um endereço IP que está na lista de endereços IP confiável, o Location-Based roteamento verifica para determinar a sub-rede interna onde o ponto de extremidade do usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="cb958-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="cb958-130">Se o endereço IP externo do usuário não corresponder a nenhum endereço IP definido na lista de endereços IP confiável, o ponto de extremidade será classificado como sendo em um local desconhecido e todas as chamadas PSTN de ou de um usuário habilitado para o Location-Based Routing serão bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="cb958-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb958-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="cb958-131">Next steps</span></span>

<span data-ttu-id="cb958-132">Vá para [Habilitar Location-Based roteamento direto.](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="cb958-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cb958-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cb958-133">Related topics</span></span>

- [<span data-ttu-id="cb958-134">Configurações de rede para recursos de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="cb958-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
