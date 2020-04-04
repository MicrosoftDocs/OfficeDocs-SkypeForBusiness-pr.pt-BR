---
title: Definir configurações de rede-roteamento baseado em local
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para roteamento baseado em local para roteamento direto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f63ff0191518acf72fd3e4c33abe80b819c3db28
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141274"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="d1cf5-103">Configurar definições de rede para o Roteamento baseado na localização</span><span class="sxs-lookup"><span data-stu-id="d1cf5-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="d1cf5-104">Se ainda não tiver feito isso, leia [roteamento baseado em local de plano para roteamento direto](location-based-routing-plan.md) para revisar outras etapas que você precisará tomar antes de definir as configurações de rede para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="d1cf5-105">Este artigo descreve como definir as configurações de rede para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="d1cf5-106">Depois de implantar o roteamento direto do sistema telefônico em sua organização, as próximas etapas são criar e configurar regiões de rede, sites de rede e sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="d1cf5-107">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="d1cf5-107">Define network regions</span></span>

<span data-ttu-id="d1cf5-108">Uma região de rede contém um conjunto de sites de rede e interconecta várias partes de uma rede em várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d1cf5-109">Para ver as etapas sobre como configurar regiões de rede, vá para [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="d1cf5-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="d1cf5-110">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="d1cf5-110">Define network sites</span></span>

<span data-ttu-id="d1cf5-111">Um site de rede representa um local onde a sua organização tem um local físico, como um escritório, um conjunto de prédios ou um campus.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="d1cf5-112">Você deve associar cada site de rede na sua topologia a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="d1cf5-113">Para ver as etapas sobre como configurar sites de rede, consulte [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="d1cf5-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="d1cf5-114">Uma prática recomendada para o roteamento baseado em localização é criar um site separado para cada local que tenha conectividade PSTN exclusiva.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="d1cf5-115">Você pode criar um site que está habilitado para roteamento baseado em localização ou um site que não está habilitado para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="d1cf5-116">Por exemplo, talvez você queira criar um site que não esteja habilitado para roteamento baseado em local para permitir que os usuários habilitados para roteamento baseado em localização façam chamadas PSTN quando estiverem em roaming para esse site.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="d1cf5-117">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="d1cf5-117">Define network subnets</span></span>

<span data-ttu-id="d1cf5-118">Cada sub-rede deve estar associada a um site de rede específico.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="d1cf5-119">Você pode associar várias sub-redes com o mesmo site de rede, mas não pode associar vários sites com a mesma sub-rede.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="d1cf5-120">Para ver as etapas sobre como configurar sub-redes de rede, vá para [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="d1cf5-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="d1cf5-121">Para roteamento baseado em local, as sub-redes IP no local onde os pontos de extremidade da equipe podem se conectar à rede devem ser definidas e associadas a uma rede definida para aplicar a chamada em tarifas.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="d1cf5-122">Essa associação de sub-redes habilita o roteamento baseado em localização para localizar os pontos de extremidade geograficamente para determinar se uma determinada chamada PSTN deve ser permitida.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="d1cf5-123">As sub-redes IPv6 e IPv4 são aceitas.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="d1cf5-124">Ao determinar se um ponto de extremidade do teams está localizado em um site, o roteamento baseado em local verifica primeiro se há um endereço IPv6 correspondente.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="d1cf5-125">Se um endereço IPv6 não estiver presente, o roteamento baseado em local verificará se há um endereço IPv4.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="d1cf5-126">Definir endereços IP confiáveis (sub-redes externas)</span><span class="sxs-lookup"><span data-stu-id="d1cf5-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="d1cf5-127">Os endereços IP confiáveis são endereços IP externos da Internet da rede corporativa e são usados para determinar se o ponto de extremidade do usuário está dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="d1cf5-128">Para ver as etapas sobre como configurar endereços IP confiáveis, vá para [gerenciar a topologia de rede para recursos de nuvem no Teams](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="d1cf5-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="d1cf5-129">Se o endereço IP externo do usuário corresponder a um endereço IP que está na lista de endereços IP confiáveis, o roteamento baseado em local fará uma verificação para determinar a sub-rede interna na qual o ponto de extremidade do usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="d1cf5-130">Se o endereço IP externo do usuário não corresponder a qualquer endereço IP definido na lista de endereços IP confiáveis, o ponto de extremidade será classificado como sendo de um local desconhecido e as chamadas PSTNs de ou para um usuário habilitado para roteamento baseado em local serão bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="d1cf5-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1cf5-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d1cf5-131">Next steps</span></span>

<span data-ttu-id="d1cf5-132">Vá para [habilitar o roteamento baseado em local para roteamento direto](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="d1cf5-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1cf5-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d1cf5-133">Related topics</span></span>

- [<span data-ttu-id="d1cf5-134">Configurações de rede para recursos de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="d1cf5-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
