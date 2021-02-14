---
title: Otimização de Mídia Local de Roteamento Direto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurar Otimização de Mídia Local para Roteamento Direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576983"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="3cec2-103">Configurar Otimização de Mídia Local para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="3cec2-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="3cec2-104">A configuração de Otimização de Mídia Local baseia-se nas configurações de rede que são comuns a outros recursos de voz na nuvem, como o roteamento Location-Based e chamadas de emergência dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="3cec2-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="3cec2-105">Para saber mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte Configurações de rede para recursos [de voz na nuvem.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3cec2-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="3cec2-106">Antes de configurar a Otimização de Mídia Local, consulte [Otimização de mídia local para Roteamento Direto.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="3cec2-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="3cec2-107">Para configurar a Otimização de Mídia Local, as etapas a seguir são necessárias.</span><span class="sxs-lookup"><span data-stu-id="3cec2-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="3cec2-108">Você pode usar o Centro de Administração do Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3cec2-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="3cec2-109">Para obter detalhes, consulte [Gerenciar sua topologia de rede.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="3cec2-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="3cec2-110">Configure o usuário e os sites SBC (conforme descrito neste artigo).</span><span class="sxs-lookup"><span data-stu-id="3cec2-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="3cec2-111">Configure os SBCs para Otimização de Mídia Local (de acordo com a especificação do fornecedor SBC).</span><span class="sxs-lookup"><span data-stu-id="3cec2-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="3cec2-112">O diagrama a seguir mostra a configuração de rede usada nos exemplos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="3cec2-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="3cec2-113">![Diagrama mostrando a configuração de rede para exemplos](media/direct-routing-media-op-9.png "Configuração de rede para exemplos")</span><span class="sxs-lookup"><span data-stu-id="3cec2-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="3cec2-114">Configurar o usuário e os sites SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="3cec2-115">Para configurar o usuário e os sites SBC, você precisará:</span><span class="sxs-lookup"><span data-stu-id="3cec2-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="3cec2-116">[Gerenciar endereços IP confiáveis externos.](#manage-external-trusted-ip-addresses)</span><span class="sxs-lookup"><span data-stu-id="3cec2-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="3cec2-117">[Defina a topologia de rede](#define-the-network-topology) configurando as regiões de rede, os sites de rede e as sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="3cec2-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="3cec2-118">[Defina a topologia de](#define-the-virtual-network-topology) rede virtual atribuindo SBC(s) a sites(s) com modos relevantes e valores SBC de proxy.</span><span class="sxs-lookup"><span data-stu-id="3cec2-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="3cec2-119">Configurar SBC(s) para Otimização de Mídia Local de acordo com a especificação do fornecedor SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="3cec2-120">Este artigo descreve a configuração dos componentes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3cec2-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="3cec2-121">Para obter informações sobre configuração SBC, consulte a documentação do fornecedor SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="3cec2-122">A Otimização de Mídia Local tem suporte dos seguintes fornecedores SBC:</span><span class="sxs-lookup"><span data-stu-id="3cec2-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="3cec2-123">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="3cec2-123">Vendor</span></span> | <span data-ttu-id="3cec2-124">Produto</span><span class="sxs-lookup"><span data-stu-id="3cec2-124">Product</span></span> |    <span data-ttu-id="3cec2-125">Versão do software</span><span class="sxs-lookup"><span data-stu-id="3cec2-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="3cec2-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="3cec2-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="3cec2-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="3cec2-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="3cec2-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3cec2-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="3cec2-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="3cec2-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3cec2-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="3cec2-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="3cec2-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3cec2-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="3cec2-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="3cec2-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3cec2-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="3cec2-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="3cec2-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3cec2-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="3cec2-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="3cec2-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3cec2-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="3cec2-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="3cec2-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3cec2-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="3cec2-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="3cec2-142">7.20A.256</span></span> |
| [<span data-ttu-id="3cec2-143">Núcleo SBC da Faixa de Opções</span><span class="sxs-lookup"><span data-stu-id="3cec2-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="3cec2-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="3cec2-144">SBC 5110</span></span>         | <span data-ttu-id="3cec2-145">8.2</span><span class="sxs-lookup"><span data-stu-id="3cec2-145">8.2</span></span>  |
|            |  <span data-ttu-id="3cec2-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="3cec2-146">SBC 5210</span></span>         | <span data-ttu-id="3cec2-147">8.2</span><span class="sxs-lookup"><span data-stu-id="3cec2-147">8.2</span></span>  |
|            |  <span data-ttu-id="3cec2-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="3cec2-148">SBC 5400</span></span>         | <span data-ttu-id="3cec2-149">8.2</span><span class="sxs-lookup"><span data-stu-id="3cec2-149">8.2</span></span>  |
|            |  <span data-ttu-id="3cec2-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="3cec2-150">SBC 7000</span></span>         | <span data-ttu-id="3cec2-151">8.2</span><span class="sxs-lookup"><span data-stu-id="3cec2-151">8.2</span></span>  |
|            |  <span data-ttu-id="3cec2-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="3cec2-152">SBC SWe</span></span>          | <span data-ttu-id="3cec2-153">8.2</span><span class="sxs-lookup"><span data-stu-id="3cec2-153">8.2</span></span>  |
| [<span data-ttu-id="3cec2-154">Borda SBC da Faixa de Opções</span><span class="sxs-lookup"><span data-stu-id="3cec2-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="3cec2-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="3cec2-155">SBC SWe Lite</span></span> | <span data-ttu-id="3cec2-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="3cec2-156">8.1.5</span></span> |
|               | <span data-ttu-id="3cec2-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="3cec2-157">SBC 1000</span></span> | <span data-ttu-id="3cec2-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="3cec2-158">8.1.5</span></span>  |
|               | <span data-ttu-id="3cec2-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="3cec2-159">SBC 2000</span></span> | <span data-ttu-id="3cec2-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="3cec2-160">8.1.5</span></span>  |
| [<span data-ttu-id="3cec2-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="3cec2-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="3cec2-162">anynode</span><span class="sxs-lookup"><span data-stu-id="3cec2-162">anynode</span></span>          | <span data-ttu-id="3cec2-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="3cec2-163">4.0.1+</span></span> |
| [<span data-ttu-id="3cec2-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="3cec2-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="3cec2-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="3cec2-165">AP 1100</span></span> | <span data-ttu-id="3cec2-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3cec2-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="3cec2-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="3cec2-167">AP 3900</span></span> | <span data-ttu-id="3cec2-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3cec2-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="3cec2-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="3cec2-169">AP 4600</span></span> | <span data-ttu-id="3cec2-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3cec2-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="3cec2-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="3cec2-171">AP 6300</span></span> | <span data-ttu-id="3cec2-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3cec2-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="3cec2-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="3cec2-173">AP 6350</span></span> | <span data-ttu-id="3cec2-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3cec2-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="3cec2-175">VME</span><span class="sxs-lookup"><span data-stu-id="3cec2-175">VME</span></span>     | <span data-ttu-id="3cec2-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3cec2-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="3cec2-177">Gerenciar endereços IP confiáveis externos</span><span class="sxs-lookup"><span data-stu-id="3cec2-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="3cec2-178">IPs confiáveis externos são os IPs externos da Internet da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="3cec2-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="3cec2-179">Esses IP são os endereços IP usados pelos clientes do Microsoft Teams quando eles se conectam ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cec2-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="3cec2-180">Você precisa adicionar esses IPs externos para cada site onde você tem usuários usando Otimização de Mídia Local.</span><span class="sxs-lookup"><span data-stu-id="3cec2-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="3cec2-181">Para adicionar os endereços IP públicos de cada site, use New-CsTenantTrustedIPAddress cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3cec2-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="3cec2-182">Você pode definir um número ilimitado de endereços IP confiáveis para um locatário.</span><span class="sxs-lookup"><span data-stu-id="3cec2-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="3cec2-183">Se os IPs externos vistos pelo Microsoft 365 são endereços IPv4 e IPv6, você precisa adicionar os dois tipos de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="3cec2-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="3cec2-184">Para IPv4, use a máscara 32.</span><span class="sxs-lookup"><span data-stu-id="3cec2-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="3cec2-185">Para IPv6, use a máscara 128.</span><span class="sxs-lookup"><span data-stu-id="3cec2-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="3cec2-186">Você pode adicionar endereços IP externos individuais e sub-redes IP externas especificando diferentes MaskBits no cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3cec2-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="3cec2-187">Exemplo de adição de endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="3cec2-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="3cec2-188">Definir a topologia de rede</span><span class="sxs-lookup"><span data-stu-id="3cec2-188">Define the network topology</span></span>

<span data-ttu-id="3cec2-189">Esta seção descreve como definir as regiões de rede, os sites de rede e as sub-redes de rede para sua topologia de rede.</span><span class="sxs-lookup"><span data-stu-id="3cec2-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="3cec2-190">Todos os parâmetros são sensíveis a minúsculas, portanto, você precisa garantir que use o mesmo caso usado durante a configuração.</span><span class="sxs-lookup"><span data-stu-id="3cec2-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="3cec2-191">(Por exemplo, os valores GatewaySiteID "Vietnã" e "vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="3cec2-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="3cec2-192">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="3cec2-192">Define network regions</span></span>

<span data-ttu-id="3cec2-193">Para definir regiões de rede, use New-CsTenantNetworkRegion cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3cec2-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="3cec2-194">O parâmetro ID Região é um nome lógico que representa a geografia da região e não tem dependências ou restrições.</span><span class="sxs-lookup"><span data-stu-id="3cec2-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="3cec2-195">O parâmetro CentralSite <site ID> é opcional.</span><span class="sxs-lookup"><span data-stu-id="3cec2-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="3cec2-196">O exemplo a seguir cria uma região de rede chamada APAC:</span><span class="sxs-lookup"><span data-stu-id="3cec2-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="3cec2-197">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="3cec2-197">Define network sites</span></span>

<span data-ttu-id="3cec2-198">Para definir sites de rede, use o cmdlet New-CsTenantNetworkSite de rede.</span><span class="sxs-lookup"><span data-stu-id="3cec2-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="3cec2-199">Cada site de rede deve estar associado a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="3cec2-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="3cec2-200">O exemplo a seguir cria três novos sites de rede, Vietnã, Indonésia e Cingapura na região APAC:</span><span class="sxs-lookup"><span data-stu-id="3cec2-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="3cec2-201">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="3cec2-201">Define network subnets</span></span>

<span data-ttu-id="3cec2-202">Para definir sub-redes de rede e associá-las a sites de rede, use o cmdlet New-CsTenantNetworkSubnet rede.</span><span class="sxs-lookup"><span data-stu-id="3cec2-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="3cec2-203">Cada sub-rede de rede só pode ser associada a um site.</span><span class="sxs-lookup"><span data-stu-id="3cec2-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="3cec2-204">O exemplo a seguir define três sub-redes de rede e as associa aos três sites de rede: Vietnã, Indonésia e Cingapura:</span><span class="sxs-lookup"><span data-stu-id="3cec2-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="3cec2-205">Definir a topologia de rede virtual</span><span class="sxs-lookup"><span data-stu-id="3cec2-205">Define the virtual network topology</span></span> 

<span data-ttu-id="3cec2-206">Primeiro, o administrador do locatário cria uma nova configuração SBC para cada SBC relevante usando o cmdlet New-CsOnlinePSTNGateway usuário.</span><span class="sxs-lookup"><span data-stu-id="3cec2-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="3cec2-207">O administrador do locatário define a topologia de rede virtual especificando os sites de rede para os objetos de gateway PSTN usando o cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="3cec2-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="3cec2-208">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3cec2-208">Note the following:</span></span> 
   - <span data-ttu-id="3cec2-209">Se o cliente tiver um único SBC, o parâmetro -ProxySBC deve ser obrigatório $null ou FQDN SBC (SBC Central com cenário centralizado de troncos).</span><span class="sxs-lookup"><span data-stu-id="3cec2-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="3cec2-210">O parâmetro -MediaBypass deve ser definido como $true para dar suporte à Otimização de Mídia Local.</span><span class="sxs-lookup"><span data-stu-id="3cec2-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="3cec2-211">Se o SBC não tiver o parâmetro -BypassMode definido, os headers X-MS não serão enviados.</span><span class="sxs-lookup"><span data-stu-id="3cec2-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="3cec2-212">Todos os parâmetros são sensíveis a minúsculas, portanto, você precisa garantir que use o mesmo caso usado durante a configuração.</span><span class="sxs-lookup"><span data-stu-id="3cec2-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="3cec2-213">(Por exemplo, os valores GatewaySiteID "Vietnã" e "vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="3cec2-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="3cec2-214">O exemplo a seguir adiciona três SBCs aos sites de rede Vietnã, Indonésia e Cingapura na região APAC com o modo Sempre ignorar:</span><span class="sxs-lookup"><span data-stu-id="3cec2-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="3cec2-215">Observação: para garantir operações ininterruptas quando a Otimização de Mídia Local e o roteamento de Location-Based (LBR) estão configurados ao mesmo tempo, os SBCs downstream devem ser habilitados para a LBR, definindo o parâmetro GatewaySiteLbrEnabled para $true para cada SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="3cec2-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="3cec2-216">(Essa configuração não é obrigatória para o SBC proxy.)</span><span class="sxs-lookup"><span data-stu-id="3cec2-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="3cec2-217">Com base nas informações acima, o Roteamento Direto incluirá três Headers SIP proprietários para Convites SIP e Re-convidar, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3cec2-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="3cec2-218">Os Headers X-MS introduzidos no Roteamento Direto em Convites e Re-Invites se BypassMode estiver definido:</span><span class="sxs-lookup"><span data-stu-id="3cec2-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="3cec2-219">Nome do header</span><span class="sxs-lookup"><span data-stu-id="3cec2-219">Header name</span></span> | <span data-ttu-id="3cec2-220">Valores</span><span class="sxs-lookup"><span data-stu-id="3cec2-220">Values</span></span> | <span data-ttu-id="3cec2-221">Comentários</span><span class="sxs-lookup"><span data-stu-id="3cec2-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="3cec2-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="3cec2-222">X-MS-UserLocation</span></span> | <span data-ttu-id="3cec2-223">interno/externo</span><span class="sxs-lookup"><span data-stu-id="3cec2-223">internal/external</span></span> | <span data-ttu-id="3cec2-224">Indica se o usuário é interno ou externo</span><span class="sxs-lookup"><span data-stu-id="3cec2-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="3cec2-225">Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="3cec2-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="3cec2-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="3cec2-226">SBC FQDN</span></span> | <span data-ttu-id="3cec2-227">O FQDN que é direcionado para a chamada mesmo que o SBC não esteja conectado diretamente ao Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="3cec2-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="3cec2-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="3cec2-228">X-MS-MediaPath</span></span> | <span data-ttu-id="3cec2-229">Exemplo: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="3cec2-230">Ordem de SBCs que devem ser usados para o caminho de mídia entre o usuário e o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="3cec2-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="3cec2-231">O SBC final é sempre o último</span><span class="sxs-lookup"><span data-stu-id="3cec2-231">The final SBC is always last</span></span> |
| <span data-ttu-id="3cec2-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="3cec2-232">X-MS-UserSite</span></span> | <span data-ttu-id="3cec2-233">iDdosu usuários</span><span class="sxs-lookup"><span data-stu-id="3cec2-233">usersiteID</span></span> | <span data-ttu-id="3cec2-234">Cadeia de caracteres definida pelo administrador do locatário</span><span class="sxs-lookup"><span data-stu-id="3cec2-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="3cec2-235">Fluxos de chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-235">Call flows</span></span> 

<span data-ttu-id="3cec2-236">O seguinte mostra os fluxos de chamada para dois modos:</span><span class="sxs-lookup"><span data-stu-id="3cec2-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="3cec2-237">Sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="3cec2-238">Somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3cec2-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="3cec2-239">Modo Sempre Ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-239">Always Bypass mode</span></span>

<span data-ttu-id="3cec2-240">O modo Sempre Ignorar é a opção mais simples de configurar.</span><span class="sxs-lookup"><span data-stu-id="3cec2-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="3cec2-241">O administrador do locatário pode configurar um único site para todos os usuários e SBCs se todos os SBCs puderem ser acessíveis de qualquer site.</span><span class="sxs-lookup"><span data-stu-id="3cec2-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="3cec2-242">Os exemplos mostram o modo Sempre ignorado para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="3cec2-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="3cec2-243">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="3cec2-244">Chamadas de entrada e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="3cec2-245">Chamadas de saída e o usuário é externo</span><span class="sxs-lookup"><span data-stu-id="3cec2-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="3cec2-246">Chamadas de entrada e o usuário é externo</span><span class="sxs-lookup"><span data-stu-id="3cec2-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="3cec2-247">A tabela a seguir mostra os endereços IP e FQDN usados nos exemplos:</span><span class="sxs-lookup"><span data-stu-id="3cec2-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="3cec2-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="3cec2-248">FQDN</span></span> | <span data-ttu-id="3cec2-249">Endereço IP externo SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-249">SBC external IP address</span></span> | <span data-ttu-id="3cec2-250">Endereço IP interno SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-250">SBC internal IP Address</span></span> | <span data-ttu-id="3cec2-251">Sub-rede interna</span><span class="sxs-lookup"><span data-stu-id="3cec2-251">Internal subnet</span></span> | <span data-ttu-id="3cec2-252">Local</span><span class="sxs-lookup"><span data-stu-id="3cec2-252">Location</span></span> | <span data-ttu-id="3cec2-253">NAT externo (IP confiável)</span><span class="sxs-lookup"><span data-stu-id="3cec2-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="3cec2-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="3cec2-255">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3cec2-255">None</span></span> | <span data-ttu-id="3cec2-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="3cec2-256">192.168.1.5</span></span> | <span data-ttu-id="3cec2-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="3cec2-257">192.168.1.0/24</span></span> | <span data-ttu-id="3cec2-258">Vietnã</span><span class="sxs-lookup"><span data-stu-id="3cec2-258">Vietnam</span></span> | <span data-ttu-id="3cec2-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="3cec2-259">172.16.240.110</span></span> |
| <span data-ttu-id="3cec2-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="3cec2-261">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3cec2-261">None</span></span> | <span data-ttu-id="3cec2-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="3cec2-262">192.168.2.5</span></span> | <span data-ttu-id="3cec2-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="3cec2-263">192.168.2.0/24</span></span> | <span data-ttu-id="3cec2-264">Indonésia</span><span class="sxs-lookup"><span data-stu-id="3cec2-264">Indonesia</span></span> | <span data-ttu-id="3cec2-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="3cec2-265">172.16.240.120</span></span> |
| <span data-ttu-id="3cec2-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="3cec2-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="3cec2-267">172.16.240.133</span></span> | <span data-ttu-id="3cec2-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="3cec2-268">192.168.3.5</span></span> | <span data-ttu-id="3cec2-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="3cec2-269">192.168.3.0/24</span></span> | <span data-ttu-id="3cec2-270">Singapura</span><span class="sxs-lookup"><span data-stu-id="3cec2-270">Singapore</span></span> | <span data-ttu-id="3cec2-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="3cec2-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="3cec2-272">Chamadas de saída e o usuário está no mesmo local que o SBC com Sempre Ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="3cec2-273">Modo</span><span class="sxs-lookup"><span data-stu-id="3cec2-273">Mode</span></span> |    <span data-ttu-id="3cec2-274">Usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-274">User</span></span> |  <span data-ttu-id="3cec2-275">Local</span><span class="sxs-lookup"><span data-stu-id="3cec2-275">Location</span></span> |  <span data-ttu-id="3cec2-276">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="3cec2-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="3cec2-277">AlwaysBypass</span></span> |    <span data-ttu-id="3cec2-278">Interno</span><span class="sxs-lookup"><span data-stu-id="3cec2-278">Internal</span></span> |  <span data-ttu-id="3cec2-279">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-279">The same site as SBC</span></span> |  <span data-ttu-id="3cec2-280">Saída</span><span class="sxs-lookup"><span data-stu-id="3cec2-280">Outbound</span></span> |

<span data-ttu-id="3cec2-281">A tabela a seguir mostra a configuração e a ação do usuário final:</span><span class="sxs-lookup"><span data-stu-id="3cec2-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="3cec2-282">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-282">User physical location</span></span>| <span data-ttu-id="3cec2-283">O usuário faz ou recebe uma chamada para/de número</span><span class="sxs-lookup"><span data-stu-id="3cec2-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="3cec2-284">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-284">User phone number</span></span>  | <span data-ttu-id="3cec2-285">Política de Roteamento de Voz Online</span><span class="sxs-lookup"><span data-stu-id="3cec2-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="3cec2-286">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="3cec2-287">Vietnã</span><span class="sxs-lookup"><span data-stu-id="3cec2-287">Vietnam</span></span> | <span data-ttu-id="3cec2-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="3cec2-288">+84 4 3926 3000</span></span> | <span data-ttu-id="3cec2-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="3cec2-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="3cec2-290">Prioridade 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="3cec2-291">Prioridade 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="3cec2-292">VNsbc.contoso.com – Sempre Ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="3cec2-293">proxysbc.contoso.com – Sempre Ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="3cec2-294">O diagrama a seguir mostra a classificação SIP para uma chamada de saída com o modo Sempre ignorar e o usuário no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="3cec2-295">![Diagrama mostrando chamadas de saída](media/direct-routing-media-op-10.png "Chamadas de saída")</span><span class="sxs-lookup"><span data-stu-id="3cec2-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="3cec2-296">A tabela a seguir mostra os headers X-MS enviados pelo Roteamento Direto:</span><span class="sxs-lookup"><span data-stu-id="3cec2-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="3cec2-297">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="3cec2-297">Parameter</span></span> | <span data-ttu-id="3cec2-298">Explicação</span><span class="sxs-lookup"><span data-stu-id="3cec2-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="3cec2-299">Convidar +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="3cec2-300">O FQDN de destino do SBC conforme definido na Política de Roteamento de Voz Online é enviado no URI de Solicitação</span><span class="sxs-lookup"><span data-stu-id="3cec2-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="3cec2-301">X-MS-UserLocation: interno</span><span class="sxs-lookup"><span data-stu-id="3cec2-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="3cec2-302">O campo indica que o usuário está localizado dentro da rede corporativa</span><span class="sxs-lookup"><span data-stu-id="3cec2-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="3cec2-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="3cec2-304">Especifica qual SBC o cliente deve percorrer até o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="3cec2-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="3cec2-305">Nesse caso, como sempre ignoramos, e o cliente é interno o nome de destino enviado como o único nome no header.</span><span class="sxs-lookup"><span data-stu-id="3cec2-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="3cec2-306">X-MS-UserSite: Vietnã</span><span class="sxs-lookup"><span data-stu-id="3cec2-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="3cec2-307">O campo indicado no site em que o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="3cec2-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="3cec2-308">Chamadas de entrada e o usuário está no mesmo local que o SBC com Sempre Ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="3cec2-309">Modo</span><span class="sxs-lookup"><span data-stu-id="3cec2-309">Mode</span></span> |    <span data-ttu-id="3cec2-310">Usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-310">User</span></span> |  <span data-ttu-id="3cec2-311">Local</span><span class="sxs-lookup"><span data-stu-id="3cec2-311">Location</span></span> |  <span data-ttu-id="3cec2-312">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="3cec2-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="3cec2-313">AlwaysBypass</span></span> |    <span data-ttu-id="3cec2-314">Interno</span><span class="sxs-lookup"><span data-stu-id="3cec2-314">Internal</span></span> | <span data-ttu-id="3cec2-315">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-315">The same site as SBC</span></span> | <span data-ttu-id="3cec2-316">Entrada</span><span class="sxs-lookup"><span data-stu-id="3cec2-316">Inbound</span></span> |


<span data-ttu-id="3cec2-317">Em uma chamada de entrada, a localização do usuário é desconhecida e o SBC deve adivinhar onde o usuário está.</span><span class="sxs-lookup"><span data-stu-id="3cec2-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="3cec2-318">Se a suposição não estiver correta, será necessário um novo convite.</span><span class="sxs-lookup"><span data-stu-id="3cec2-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="3cec2-319">Esse caso pressu que o usuário é interno, que a mídia pode fluir diretamente e nenhuma ação é necessária (convidar de novo).</span><span class="sxs-lookup"><span data-stu-id="3cec2-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="3cec2-320">O SBC conectado ao serviço roteamento direto informa o local SBC de origem, fornecendo campos Record-Route e Contato.</span><span class="sxs-lookup"><span data-stu-id="3cec2-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="3cec2-321">Com base nesses campos, o caminho da mídia é calculado pelo Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="3cec2-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="3cec2-322">Observação: como um usuário pode ter vários pontos de extremidade, não é possível ter suporte para 183.</span><span class="sxs-lookup"><span data-stu-id="3cec2-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="3cec2-323">O Roteamento Direto sempre usará o Toque 180 nesse caso.</span><span class="sxs-lookup"><span data-stu-id="3cec2-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="3cec2-324">O diagrama a seguir mostra a classificação SIP para chamada de entrada com o modo AlwaysBypass e o usuário está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagrama mostrando sip](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="3cec2-326">Chamadas de saída e o usuário é externo com Sempre Ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="3cec2-327">Modo</span><span class="sxs-lookup"><span data-stu-id="3cec2-327">Mode</span></span> |    <span data-ttu-id="3cec2-328">Usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-328">User</span></span> |  <span data-ttu-id="3cec2-329">Site</span><span class="sxs-lookup"><span data-stu-id="3cec2-329">Site</span></span> |  <span data-ttu-id="3cec2-330">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="3cec2-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="3cec2-331">AlwaysBypass</span></span> |  <span data-ttu-id="3cec2-332">Externo</span><span class="sxs-lookup"><span data-stu-id="3cec2-332">External</span></span> |  <span data-ttu-id="3cec2-333">Não disponível</span><span class="sxs-lookup"><span data-stu-id="3cec2-333">N/A</span></span> | <span data-ttu-id="3cec2-334">Saída</span><span class="sxs-lookup"><span data-stu-id="3cec2-334">Outbound</span></span> |


<span data-ttu-id="3cec2-335">O diagrama a seguir mostra a classificação SIP para uma chamada de saída com o modo AlwaysBypass e o usuário é externo:</span><span class="sxs-lookup"><span data-stu-id="3cec2-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagrama mostrando sip](media/direct-routing-media-op-12.png)

<span data-ttu-id="3cec2-337">A tabela a seguir mostra os headers X-MS enviados pelo serviço roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="3cec2-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="3cec2-338">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="3cec2-338">Parameter</span></span> |   <span data-ttu-id="3cec2-339">Explicação</span><span class="sxs-lookup"><span data-stu-id="3cec2-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="3cec2-340">Convidar +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="3cec2-341">O FQDN de destino do SBC conforme definido na Política de Roteamento de Voz Online é enviado no URI de Solicitação.</span><span class="sxs-lookup"><span data-stu-id="3cec2-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="3cec2-342">X-MS-UserLocation: externo</span><span class="sxs-lookup"><span data-stu-id="3cec2-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="3cec2-343">O campo indicou que o usuário está localizado fora da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="3cec2-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="3cec2-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="3cec2-345">Especifica qual SBC o cliente deve percorrer até o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="3cec2-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="3cec2-346">Nesse caso, como sempre ignoramos, e o cliente é externo.</span><span class="sxs-lookup"><span data-stu-id="3cec2-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="3cec2-347">Chamadas de entrada e o usuário é externo com Sempre Ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="3cec2-348">Modo</span><span class="sxs-lookup"><span data-stu-id="3cec2-348">Mode</span></span> | <span data-ttu-id="3cec2-349">Usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-349">User</span></span> | <span data-ttu-id="3cec2-350">Site</span><span class="sxs-lookup"><span data-stu-id="3cec2-350">Site</span></span> |  <span data-ttu-id="3cec2-351">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="3cec2-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="3cec2-352">AlwaysBypass</span></span> |  <span data-ttu-id="3cec2-353">Externo</span><span class="sxs-lookup"><span data-stu-id="3cec2-353">External</span></span> |  <span data-ttu-id="3cec2-354">Não disponível</span><span class="sxs-lookup"><span data-stu-id="3cec2-354">N/A</span></span> |   <span data-ttu-id="3cec2-355">Entrada</span><span class="sxs-lookup"><span data-stu-id="3cec2-355">Inbound</span></span> |

<span data-ttu-id="3cec2-356">Para uma chamada de entrada, o SBC conectado ao Roteamento Direto precisa enviar um novo convite (por padrão, os candidatos à mídia local sempre são oferecidos) se o local do usuário for externo.</span><span class="sxs-lookup"><span data-stu-id="3cec2-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="3cec2-357">O X-MediaPath é calculado com base Record-Route e o usuário SBC especificado.</span><span class="sxs-lookup"><span data-stu-id="3cec2-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="3cec2-358">O diagrama a seguir mostra a classificação SIP para uma chamada de entrada com o modo AlwaysBypass e o usuário é externo.</span><span class="sxs-lookup"><span data-stu-id="3cec2-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagrama mostrando sip](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="3cec2-360">Somente para o modo de usuários locais</span><span class="sxs-lookup"><span data-stu-id="3cec2-360">Only for local users mode</span></span>

<span data-ttu-id="3cec2-361">Os candidatos à mídia local do SBC de destino serão oferecidos somente se um usuário estiver no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="3cec2-362">Em todos os outros casos, a mídia fluirá por um IP interno ou externo do SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="3cec2-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="3cec2-363">Os seguintes cenários são descritos:</span><span class="sxs-lookup"><span data-stu-id="3cec2-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="3cec2-364">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="3cec2-365">Chamadas de entrada e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="3cec2-366">O usuário não está no mesmo local que o SBC, mas está na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="3cec2-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="3cec2-367">Chamadas de entrada e o usuário é interno, mas não está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="3cec2-368">A tabela a seguir mostra a configuração e a ação do usuário final:</span><span class="sxs-lookup"><span data-stu-id="3cec2-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="3cec2-369">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-369">User physical location</span></span> |  <span data-ttu-id="3cec2-370">O usuário faz ou recebe uma chamada para/de número</span><span class="sxs-lookup"><span data-stu-id="3cec2-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="3cec2-371">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-371">User phone number</span></span> | <span data-ttu-id="3cec2-372">Política de Roteamento de Voz Online</span><span class="sxs-lookup"><span data-stu-id="3cec2-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="3cec2-373">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="3cec2-374">Vietnã</span><span class="sxs-lookup"><span data-stu-id="3cec2-374">Vietnam</span></span> | <span data-ttu-id="3cec2-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="3cec2-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="3cec2-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="3cec2-376">+84 4 5555 5555</span></span> | <span data-ttu-id="3cec2-377">Prioridade 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="3cec2-378">Prioridade 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3cec2-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="3cec2-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Sempre Ignorar</span><span class="sxs-lookup"><span data-stu-id="3cec2-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="3cec2-380">Chamadas de saída e o usuário está no mesmo local que o SBC com Somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3cec2-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="3cec2-381">Modo</span><span class="sxs-lookup"><span data-stu-id="3cec2-381">Mode</span></span> | <span data-ttu-id="3cec2-382">Usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-382">User</span></span> | <span data-ttu-id="3cec2-383">Site</span><span class="sxs-lookup"><span data-stu-id="3cec2-383">Site</span></span> | <span data-ttu-id="3cec2-384">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="3cec2-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="3cec2-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="3cec2-386">Interno</span><span class="sxs-lookup"><span data-stu-id="3cec2-386">Internal</span></span> |<span data-ttu-id="3cec2-387">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-387">Same as SBC</span></span>   | <span data-ttu-id="3cec2-388">Saída</span><span class="sxs-lookup"><span data-stu-id="3cec2-388">Outbound</span></span> |

<span data-ttu-id="3cec2-389">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers e o usuário está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="3cec2-390">Esse é o mesmo fluxo mostrado em chamadas de saída quando o usuário está [no mesmo local que o SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="3cec2-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando sip](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="3cec2-392">Chamadas de entrada e o usuário está no mesmo local que o SBC com Somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3cec2-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="3cec2-393">Modo</span><span class="sxs-lookup"><span data-stu-id="3cec2-393">Mode</span></span> | <span data-ttu-id="3cec2-394">Usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-394">User</span></span> | <span data-ttu-id="3cec2-395">Site</span><span class="sxs-lookup"><span data-stu-id="3cec2-395">Site</span></span> | <span data-ttu-id="3cec2-396">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="3cec2-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="3cec2-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="3cec2-398">Interno</span><span class="sxs-lookup"><span data-stu-id="3cec2-398">Internal</span></span> | <span data-ttu-id="3cec2-399">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-399">Same as SBC</span></span> | <span data-ttu-id="3cec2-400">Entrada</span><span class="sxs-lookup"><span data-stu-id="3cec2-400">Inbound</span></span> |

<span data-ttu-id="3cec2-401">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers e o usuário está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="3cec2-402">Esse é o mesmo fluxo mostrado em chamadas de entrada quando o usuário está [no mesmo local que o SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="3cec2-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando sip](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="3cec2-404">O usuário não está no mesmo local que o SBC, mas está na rede corporativa apenas para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3cec2-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="3cec2-405">Modo</span><span class="sxs-lookup"><span data-stu-id="3cec2-405">Mode</span></span> | <span data-ttu-id="3cec2-406">Usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-406">User</span></span> | <span data-ttu-id="3cec2-407">Site</span><span class="sxs-lookup"><span data-stu-id="3cec2-407">Site</span></span> |<span data-ttu-id="3cec2-408">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="3cec2-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="3cec2-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="3cec2-410">Interno</span><span class="sxs-lookup"><span data-stu-id="3cec2-410">Internal</span></span> |   <span data-ttu-id="3cec2-411">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-411">Different from SBC</span></span> | <span data-ttu-id="3cec2-412">Saída</span><span class="sxs-lookup"><span data-stu-id="3cec2-412">Outbound</span></span> |

<span data-ttu-id="3cec2-413">O roteamento direto calcula o X-MediaPath com base no local relatado do usuário e no modo configurado no SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="3cec2-414">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando sip](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="3cec2-416">Chamada de entrada e o usuário é interno, mas não está no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3cec2-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="3cec2-417">Modo</span><span class="sxs-lookup"><span data-stu-id="3cec2-417">Mode</span></span> |    <span data-ttu-id="3cec2-418">Usuário</span><span class="sxs-lookup"><span data-stu-id="3cec2-418">User</span></span> |  <span data-ttu-id="3cec2-419">Site</span><span class="sxs-lookup"><span data-stu-id="3cec2-419">Site</span></span> |  <span data-ttu-id="3cec2-420">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3cec2-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="3cec2-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="3cec2-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="3cec2-422">Interno</span><span class="sxs-lookup"><span data-stu-id="3cec2-422">Internal</span></span> |    <span data-ttu-id="3cec2-423">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="3cec2-423">Different from SBC</span></span> |    <span data-ttu-id="3cec2-424">Entrada</span><span class="sxs-lookup"><span data-stu-id="3cec2-424">Inbound</span></span> |

<span data-ttu-id="3cec2-425">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="3cec2-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando sip](media/direct-routing-media-op-17.png)









