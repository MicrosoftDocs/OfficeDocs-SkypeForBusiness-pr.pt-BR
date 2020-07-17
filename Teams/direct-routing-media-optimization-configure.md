---
title: Otimização direta de roteamento de mídia local
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
description: Configurar a otimização de mídia local para roteamento direto
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121601"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="98e5e-103">Configurar a otimização de mídia local para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="98e5e-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="98e5e-104">A configuração da otimização de mídia local é baseada em configurações de rede que são comuns a outros recursos de voz em nuvem, como roteamento baseado em localização e chamadas de emergência dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="98e5e-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="98e5e-105">Para saber mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte [configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="98e5e-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="98e5e-106">Antes de configurar a otimização de mídia local, consulte [otimização de mídia local para roteamento direto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="98e5e-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="98e5e-107">Para configurar a otimização de mídia local, as etapas a seguir são necessárias.</span><span class="sxs-lookup"><span data-stu-id="98e5e-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="98e5e-108">Você pode usar o centro de administração do teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98e5e-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="98e5e-109">Para obter detalhes, consulte [gerenciar a topologia de rede](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="98e5e-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="98e5e-110">Configure o usuário e os sites de SBC (conforme descrito neste artigo).</span><span class="sxs-lookup"><span data-stu-id="98e5e-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="98e5e-111">Configurar o SBCs para otimização de mídia local (de acordo com a especificação do fornecedor do SBC).</span><span class="sxs-lookup"><span data-stu-id="98e5e-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="98e5e-112">O diagrama a seguir mostra a configuração de rede usada nos exemplos ao longo deste artigo.</span><span class="sxs-lookup"><span data-stu-id="98e5e-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="98e5e-113">![Diagrama mostrando a configuração de rede para obter exemplos](media/direct-routing-media-op-9.png "Configuração de rede para obter exemplos")</span><span class="sxs-lookup"><span data-stu-id="98e5e-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="98e5e-114">Configurar o usuário e os sites de SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="98e5e-115">Para configurar o usuário e os sites de SBC, você precisará:</span><span class="sxs-lookup"><span data-stu-id="98e5e-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="98e5e-116">[Gerenciar endereços IP externos confiáveis](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="98e5e-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="98e5e-117">[Defina a topologia de rede](#define-the-network-topology) configurando as regiões de rede, sites de rede e sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="98e5e-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="98e5e-118">[Defina a topologia de rede virtual](#define-the-virtual-network-topology) atribuindo SBC (s) a (s) site (s) a (s) o (s) site (s) com os modos relevantes e valores</span><span class="sxs-lookup"><span data-stu-id="98e5e-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="98e5e-119">Configurar o SBC (s) para otimização de mídia local de acordo com a especificação do fornecedor do SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="98e5e-120">Este artigo descreve a configuração dos componentes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98e5e-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="98e5e-121">Para obter informações sobre a configuração do SBC, consulte a documentação do seu fornecedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="98e5e-122">A otimização de mídia local é compatível com os seguintes fornecedores de SBC:</span><span class="sxs-lookup"><span data-stu-id="98e5e-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="98e5e-123">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="98e5e-123">Vendor</span></span> | <span data-ttu-id="98e5e-124">Produto</span><span class="sxs-lookup"><span data-stu-id="98e5e-124">Product</span></span> |    <span data-ttu-id="98e5e-125">Versão do software</span><span class="sxs-lookup"><span data-stu-id="98e5e-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="98e5e-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="98e5e-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="98e5e-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="98e5e-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="98e5e-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="98e5e-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="98e5e-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="98e5e-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="98e5e-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="98e5e-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="98e5e-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="98e5e-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="98e5e-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="98e5e-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="98e5e-135">1000B de SBC médio</span><span class="sxs-lookup"><span data-stu-id="98e5e-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="98e5e-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="98e5e-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="98e5e-137">Mamédia 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="98e5e-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="98e5e-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="98e5e-139">Representação mediana virtual da edição virtual</span><span class="sxs-lookup"><span data-stu-id="98e5e-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="98e5e-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="98e5e-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="98e5e-141">Mamediat Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="98e5e-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="98e5e-142">7.20A.256</span></span> |
| [<span data-ttu-id="98e5e-143">Faixa de opções do SBC Core</span><span class="sxs-lookup"><span data-stu-id="98e5e-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="98e5e-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="98e5e-144">SBC 5110</span></span>         | <span data-ttu-id="98e5e-145">8,2</span><span class="sxs-lookup"><span data-stu-id="98e5e-145">8.2</span></span>  |
|            |  <span data-ttu-id="98e5e-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="98e5e-146">SBC 5210</span></span>         | <span data-ttu-id="98e5e-147">8,2</span><span class="sxs-lookup"><span data-stu-id="98e5e-147">8.2</span></span>  |
|            |  <span data-ttu-id="98e5e-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="98e5e-148">SBC 5400</span></span>         | <span data-ttu-id="98e5e-149">8,2</span><span class="sxs-lookup"><span data-stu-id="98e5e-149">8.2</span></span>  |
|            |  <span data-ttu-id="98e5e-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="98e5e-150">SBC 7000</span></span>         | <span data-ttu-id="98e5e-151">8,2</span><span class="sxs-lookup"><span data-stu-id="98e5e-151">8.2</span></span>  |
|            |  <span data-ttu-id="98e5e-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="98e5e-152">SBC SWe</span></span>          | <span data-ttu-id="98e5e-153">8,2</span><span class="sxs-lookup"><span data-stu-id="98e5e-153">8.2</span></span>  |
| [<span data-ttu-id="98e5e-154">Borda SBC da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="98e5e-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="98e5e-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="98e5e-155">SBC SWe Lite</span></span> | <span data-ttu-id="98e5e-156">8.1.5 (Build 239)</span><span class="sxs-lookup"><span data-stu-id="98e5e-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="98e5e-157">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="98e5e-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="98e5e-158">anynode</span><span class="sxs-lookup"><span data-stu-id="98e5e-158">anynode</span></span>          | <span data-ttu-id="98e5e-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="98e5e-159">4.0.1+</span></span> |
| [<span data-ttu-id="98e5e-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="98e5e-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="98e5e-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="98e5e-161">AP 1100</span></span> | <span data-ttu-id="98e5e-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="98e5e-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="98e5e-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="98e5e-163">AP 3900</span></span> | <span data-ttu-id="98e5e-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="98e5e-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="98e5e-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="98e5e-165">AP 4600</span></span> | <span data-ttu-id="98e5e-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="98e5e-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="98e5e-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="98e5e-167">AP 6300</span></span> | <span data-ttu-id="98e5e-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="98e5e-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="98e5e-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="98e5e-169">AP 6350</span></span> | <span data-ttu-id="98e5e-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="98e5e-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="98e5e-171">VME</span><span class="sxs-lookup"><span data-stu-id="98e5e-171">VME</span></span>     | <span data-ttu-id="98e5e-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="98e5e-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="98e5e-173">Gerenciar endereços IP externos confiáveis</span><span class="sxs-lookup"><span data-stu-id="98e5e-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="98e5e-174">Os IPs externos confiáveis são os IPs externos da Internet da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="98e5e-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="98e5e-175">Estes IP são os endereços IP usados pelos clientes do Microsoft Teams quando eles se conectam ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98e5e-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="98e5e-176">Você precisa adicionar esses IPs externos para cada site em que você tem usuários usando a otimização de mídia local.</span><span class="sxs-lookup"><span data-stu-id="98e5e-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="98e5e-177">Para adicionar os endereços IP públicos para cada site, use o cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="98e5e-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="98e5e-178">Você pode definir um número ilimitado de endereços IP confiáveis para um locatário.</span><span class="sxs-lookup"><span data-stu-id="98e5e-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="98e5e-179">Se os IPs externos vistos pelo Microsoft 365 forem endereços IPv4 e IPv6, você precisará adicionar os dois tipos de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="98e5e-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="98e5e-180">Para IPv4, use máscara 32.</span><span class="sxs-lookup"><span data-stu-id="98e5e-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="98e5e-181">Para IPv6, use máscara 128.</span><span class="sxs-lookup"><span data-stu-id="98e5e-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="98e5e-182">Você pode adicionar endereços IP externos individuais e sub-redes externas de IP especificando diferentes MaskBits no cmdlet.</span><span class="sxs-lookup"><span data-stu-id="98e5e-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="98e5e-183">Exemplo de como adicionar endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="98e5e-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="98e5e-184">Definir a topologia de rede</span><span class="sxs-lookup"><span data-stu-id="98e5e-184">Define the network topology</span></span>

<span data-ttu-id="98e5e-185">Esta seção descreve como definir as regiões de rede, sites de rede e sub-redes de rede para a sua topologia de rede.</span><span class="sxs-lookup"><span data-stu-id="98e5e-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="98e5e-186">Todos os parâmetros diferenciam maiúsculas de minúsculas, portanto, você precisa garantir que você use o mesmo caso que foi usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="98e5e-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="98e5e-187">(Por exemplo, os valores de GatewaySiteID "Vietnã" e "Vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="98e5e-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="98e5e-188">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="98e5e-188">Define network regions</span></span>

<span data-ttu-id="98e5e-189">Para definir regiões de rede, use o cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="98e5e-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="98e5e-190">O parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições.</span><span class="sxs-lookup"><span data-stu-id="98e5e-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="98e5e-191">O <site ID> parâmetro CentralSite é opcional.</span><span class="sxs-lookup"><span data-stu-id="98e5e-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="98e5e-192">O exemplo a seguir cria uma região de rede chamada Ásia-Pacífico:</span><span class="sxs-lookup"><span data-stu-id="98e5e-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="98e5e-193">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="98e5e-193">Define network sites</span></span>

<span data-ttu-id="98e5e-194">Para definir sites de rede, use o cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="98e5e-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="98e5e-195">Cada site de rede deve estar associado a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="98e5e-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="98e5e-196">O exemplo a seguir cria três novos sites de rede, Vietnã, Indonésia e Cingapura na região da Ásia/Pacífico:</span><span class="sxs-lookup"><span data-stu-id="98e5e-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="98e5e-197">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="98e5e-197">Define network subnets</span></span>

<span data-ttu-id="98e5e-198">Para definir sub-redes de rede e associá-las a sites de rede, use o cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="98e5e-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="98e5e-199">Cada sub-rede de rede só pode ser associada a um site.</span><span class="sxs-lookup"><span data-stu-id="98e5e-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="98e5e-200">O exemplo a seguir define três sub-redes de rede e as associa aos três locais de rede: Vietnã, Indonésia e Cingapura:</span><span class="sxs-lookup"><span data-stu-id="98e5e-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="98e5e-201">Definir a topologia de rede virtual</span><span class="sxs-lookup"><span data-stu-id="98e5e-201">Define the virtual network topology</span></span> 

<span data-ttu-id="98e5e-202">Primeiro, o administrador do locatário cria uma nova configuração do SBC para cada SBC relevante usando o cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="98e5e-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="98e5e-203">O administrador do locatário define a topologia de rede virtual especificando os sites de rede dos objetos do gateway PSTN usando o cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="98e5e-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="98e5e-204">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="98e5e-204">Note the following:</span></span> 
   - <span data-ttu-id="98e5e-205">Se o cliente tiver um único SBC, o parâmetro-ProxySBC deve ser obrigatório $null ou o valor de FQDN do SBC (SBC central com o cenário de troncos centralizados).</span><span class="sxs-lookup"><span data-stu-id="98e5e-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="98e5e-206">O parâmetro-MediaBypass deve ser definido como $true para dar suporte à otimização de mídia local.</span><span class="sxs-lookup"><span data-stu-id="98e5e-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="98e5e-207">Se o SBC não tiver o parâmetro-Bypassmode definido, os cabeçalhos X-MS não serão enviados.</span><span class="sxs-lookup"><span data-stu-id="98e5e-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="98e5e-208">Todos os parâmetros diferenciam maiúsculas de minúsculas, portanto você precisa garantir que você use o mesmo caso que foi usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="98e5e-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="98e5e-209">(Por exemplo, os valores de GatewaySiteID "Vietnã" e "Vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="98e5e-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="98e5e-210">O exemplo a seguir adiciona três SBCs aos locais de rede Vietnã, Indonésia e Cingapura na região da Ásia com o modo sempre ignorar:</span><span class="sxs-lookup"><span data-stu-id="98e5e-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="98e5e-211">Observação: para garantir operações ininterruptas quando a otimização de mídia local e o roteamento baseado em local (LBR) estiverem configurados ao mesmo tempo, o SBCs downstream deve ser habilitado para LBR definindo o parâmetro GatewaySiteLbrEnabled para $true para cada SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="98e5e-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="98e5e-212">(Essa configuração não é obrigatória para o SBC do proxy.)</span><span class="sxs-lookup"><span data-stu-id="98e5e-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="98e5e-213">Com base nas informações acima, o roteamento direto incluirá três cabeçalhos SIP exclusivos para convites SIP e reconvida, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="98e5e-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="98e5e-214">Cabeçalhos X-MS inseridos no roteamento direto em convites e convites novamente se Bypassmode for definido:</span><span class="sxs-lookup"><span data-stu-id="98e5e-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="98e5e-215">Nome do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="98e5e-215">Header name</span></span> | <span data-ttu-id="98e5e-216">Valores</span><span class="sxs-lookup"><span data-stu-id="98e5e-216">Values</span></span> | <span data-ttu-id="98e5e-217">Comentários</span><span class="sxs-lookup"><span data-stu-id="98e5e-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="98e5e-218">X-MS-userlocation</span><span class="sxs-lookup"><span data-stu-id="98e5e-218">X-MS-UserLocation</span></span> | <span data-ttu-id="98e5e-219">interno/externo</span><span class="sxs-lookup"><span data-stu-id="98e5e-219">internal/external</span></span> | <span data-ttu-id="98e5e-220">Indica se o usuário é interno ou externo</span><span class="sxs-lookup"><span data-stu-id="98e5e-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="98e5e-221">CONVITE de solicitação-URI SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="98e5e-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="98e5e-222">O FQDN DO SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-222">SBC FQDN</span></span> | <span data-ttu-id="98e5e-223">O FQDN que é direcionado para a chamada mesmo se o SBC não estiver diretamente conectado ao roteamento direto</span><span class="sxs-lookup"><span data-stu-id="98e5e-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="98e5e-224">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="98e5e-224">X-MS-MediaPath</span></span> | <span data-ttu-id="98e5e-225">Exemplo: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="98e5e-226">Ordem do SBCs que deve ser usada para o caminho de mídia entre o usuário e o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="98e5e-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="98e5e-227">O SBC final é sempre último</span><span class="sxs-lookup"><span data-stu-id="98e5e-227">The final SBC is always last</span></span> |
| <span data-ttu-id="98e5e-228">Site do X-MS-usersite</span><span class="sxs-lookup"><span data-stu-id="98e5e-228">X-MS-UserSite</span></span> | <span data-ttu-id="98e5e-229">usersiteid</span><span class="sxs-lookup"><span data-stu-id="98e5e-229">usersiteID</span></span> | <span data-ttu-id="98e5e-230">Cadeia de caracteres definida pelo administrador locatário</span><span class="sxs-lookup"><span data-stu-id="98e5e-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="98e5e-231">Fluxos de chamadas</span><span class="sxs-lookup"><span data-stu-id="98e5e-231">Call flows</span></span> 

<span data-ttu-id="98e5e-232">Veja a seguir os fluxos de chamadas para dois modos:</span><span class="sxs-lookup"><span data-stu-id="98e5e-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="98e5e-233">Sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="98e5e-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="98e5e-234">Somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="98e5e-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="98e5e-235">Modo sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="98e5e-235">Always Bypass mode</span></span>

<span data-ttu-id="98e5e-236">Sempre ignorar modo é a opção mais simples de configurar.</span><span class="sxs-lookup"><span data-stu-id="98e5e-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="98e5e-237">O administrador do locatário pode configurar um único site para todos os usuários e o SBCs se todos os SBCs forem acessíveis em qualquer site.</span><span class="sxs-lookup"><span data-stu-id="98e5e-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="98e5e-238">Os exemplos mostram sempre o modo ignorar para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="98e5e-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="98e5e-239">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="98e5e-240">As chamadas recebidas e o usuário estão no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="98e5e-241">Chamadas de saída e o usuário é externo</span><span class="sxs-lookup"><span data-stu-id="98e5e-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="98e5e-242">As chamadas recebidas e o usuário são externos</span><span class="sxs-lookup"><span data-stu-id="98e5e-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="98e5e-243">A tabela a seguir mostra os endereços IP e FQDN usados nos exemplos:</span><span class="sxs-lookup"><span data-stu-id="98e5e-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="98e5e-244">FQDN</span><span class="sxs-lookup"><span data-stu-id="98e5e-244">FQDN</span></span> | <span data-ttu-id="98e5e-245">Endereço IP externo do SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-245">SBC external IP address</span></span> | <span data-ttu-id="98e5e-246">Endereço IP interno do SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-246">SBC internal IP Address</span></span> | <span data-ttu-id="98e5e-247">Sub-rede interna</span><span class="sxs-lookup"><span data-stu-id="98e5e-247">Internal subnet</span></span> | <span data-ttu-id="98e5e-248">Local</span><span class="sxs-lookup"><span data-stu-id="98e5e-248">Location</span></span> | <span data-ttu-id="98e5e-249">NAT externo (IP confiável)</span><span class="sxs-lookup"><span data-stu-id="98e5e-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="98e5e-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="98e5e-251">Nenhum</span><span class="sxs-lookup"><span data-stu-id="98e5e-251">None</span></span> | <span data-ttu-id="98e5e-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="98e5e-252">192.168.1.5</span></span> | <span data-ttu-id="98e5e-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="98e5e-253">192.168.1.0/24</span></span> | <span data-ttu-id="98e5e-254">Vietnã</span><span class="sxs-lookup"><span data-stu-id="98e5e-254">Vietnam</span></span> | <span data-ttu-id="98e5e-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="98e5e-255">172.16.240.110</span></span> |
| <span data-ttu-id="98e5e-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="98e5e-257">Nenhum</span><span class="sxs-lookup"><span data-stu-id="98e5e-257">None</span></span> | <span data-ttu-id="98e5e-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="98e5e-258">192.168.2.5</span></span> | <span data-ttu-id="98e5e-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="98e5e-259">192.168.2.0/24</span></span> | <span data-ttu-id="98e5e-260">Indonésia</span><span class="sxs-lookup"><span data-stu-id="98e5e-260">Indonesia</span></span> | <span data-ttu-id="98e5e-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="98e5e-261">172.16.240.120</span></span> |
| <span data-ttu-id="98e5e-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="98e5e-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="98e5e-263">172.16.240.133</span></span> | <span data-ttu-id="98e5e-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="98e5e-264">192.168.3.5</span></span> | <span data-ttu-id="98e5e-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="98e5e-265">192.168.3.0/24</span></span> | <span data-ttu-id="98e5e-266">Singapura</span><span class="sxs-lookup"><span data-stu-id="98e5e-266">Singapore</span></span> | <span data-ttu-id="98e5e-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="98e5e-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="98e5e-268">Chamadas de saída e o usuário está no mesmo local que o SBC com sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="98e5e-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="98e5e-269">Modo</span><span class="sxs-lookup"><span data-stu-id="98e5e-269">Mode</span></span> |    <span data-ttu-id="98e5e-270">Usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-270">User</span></span> |  <span data-ttu-id="98e5e-271">Local</span><span class="sxs-lookup"><span data-stu-id="98e5e-271">Location</span></span> |  <span data-ttu-id="98e5e-272">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="98e5e-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="98e5e-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="98e5e-273">AlwaysBypass</span></span> |    <span data-ttu-id="98e5e-274">Interno</span><span class="sxs-lookup"><span data-stu-id="98e5e-274">Internal</span></span> |  <span data-ttu-id="98e5e-275">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-275">The same site as SBC</span></span> |  <span data-ttu-id="98e5e-276">Saída</span><span class="sxs-lookup"><span data-stu-id="98e5e-276">Outbound</span></span> |

<span data-ttu-id="98e5e-277">A tabela a seguir mostra a ação e a configuração do usuário final:</span><span class="sxs-lookup"><span data-stu-id="98e5e-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="98e5e-278">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-278">User physical location</span></span>| <span data-ttu-id="98e5e-279">O usuário faz ou recebe uma chamada de/para um número</span><span class="sxs-lookup"><span data-stu-id="98e5e-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="98e5e-280">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-280">User phone number</span></span>  | <span data-ttu-id="98e5e-281">Política de roteamento de voz online</span><span class="sxs-lookup"><span data-stu-id="98e5e-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="98e5e-282">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="98e5e-283">Vietnã</span><span class="sxs-lookup"><span data-stu-id="98e5e-283">Vietnam</span></span> | <span data-ttu-id="98e5e-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="98e5e-284">+84 4 3926 3000</span></span> | <span data-ttu-id="98e5e-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="98e5e-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="98e5e-286">Prioridade 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="98e5e-287">Prioridade 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="98e5e-288">VNsbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="98e5e-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="98e5e-289">proxysbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="98e5e-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="98e5e-290">O diagrama a seguir mostra a escada SIP para uma chamada de saída com o modo sempre ignorado e o usuário no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="98e5e-291">![Diagrama mostrando chamadas de saída](media/direct-routing-media-op-10.png "Chamadas de saída")</span><span class="sxs-lookup"><span data-stu-id="98e5e-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="98e5e-292">A tabela a seguir mostra os cabeçalhos X-MS enviados pelo roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="98e5e-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="98e5e-293">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="98e5e-293">Parameter</span></span> | <span data-ttu-id="98e5e-294">Explicação</span><span class="sxs-lookup"><span data-stu-id="98e5e-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="98e5e-295">Convidar + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="98e5e-296">O FQDN de destino do SBC, conforme definido na política de roteamento de voz online, é enviado no URI de solicitação</span><span class="sxs-lookup"><span data-stu-id="98e5e-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="98e5e-297">X-MS-userlocation: Internal</span><span class="sxs-lookup"><span data-stu-id="98e5e-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="98e5e-298">O campo indicou que o usuário está localizado dentro da rede corporativa</span><span class="sxs-lookup"><span data-stu-id="98e5e-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="98e5e-299">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="98e5e-300">Especifica qual SBC o cliente deve atravessar para o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="98e5e-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="98e5e-301">Nesse caso, como sempre ignoramos, e o cliente é interno o nome de destino enviado como o único nome no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="98e5e-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="98e5e-302">X-MS-usersite: Vietnã</span><span class="sxs-lookup"><span data-stu-id="98e5e-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="98e5e-303">O campo indicado no site em que o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="98e5e-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="98e5e-304">As chamadas recebidas e o usuário estão no mesmo local que o SBC com sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="98e5e-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="98e5e-305">Modo</span><span class="sxs-lookup"><span data-stu-id="98e5e-305">Mode</span></span> |    <span data-ttu-id="98e5e-306">Usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-306">User</span></span> |  <span data-ttu-id="98e5e-307">Local</span><span class="sxs-lookup"><span data-stu-id="98e5e-307">Location</span></span> |  <span data-ttu-id="98e5e-308">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="98e5e-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="98e5e-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="98e5e-309">AlwaysBypass</span></span> |    <span data-ttu-id="98e5e-310">Interno</span><span class="sxs-lookup"><span data-stu-id="98e5e-310">Internal</span></span> | <span data-ttu-id="98e5e-311">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-311">The same site as SBC</span></span> | <span data-ttu-id="98e5e-312">Entrada</span><span class="sxs-lookup"><span data-stu-id="98e5e-312">Inbound</span></span> |


<span data-ttu-id="98e5e-313">Em uma chamada de entrada, o local do usuário é desconhecido, e o SBC deve adivinhar onde está o usuário.</span><span class="sxs-lookup"><span data-stu-id="98e5e-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="98e5e-314">Se a estimativa estiver incorreta, será preciso um novo convite.</span><span class="sxs-lookup"><span data-stu-id="98e5e-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="98e5e-315">Esse caso presume que o usuário seja interno, a mídia pode fluir diretamente e não são necessárias mais ações (convidar novamente).</span><span class="sxs-lookup"><span data-stu-id="98e5e-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="98e5e-316">O SBC conectado ao serviço de roteamento direto relata o local do SBC de origem fornecendo campos de rota de registro e de contato.</span><span class="sxs-lookup"><span data-stu-id="98e5e-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="98e5e-317">Com base nesses campos, o caminho de mídia é calculado pelo roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="98e5e-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="98e5e-318">Observação: Considerando que um usuário pode ter vários pontos de extremidade, o suporte do 183 não é possível.</span><span class="sxs-lookup"><span data-stu-id="98e5e-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="98e5e-319">O roteamento direto sempre usará o 180 tocando nesse caso.</span><span class="sxs-lookup"><span data-stu-id="98e5e-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="98e5e-320">O diagrama a seguir mostra a escada em SIP para a chamada de entrada com o modo AlwaysBypass, e o usuário está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="98e5e-322">Chamadas de saída e o usuário é externo sempre bypass</span><span class="sxs-lookup"><span data-stu-id="98e5e-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="98e5e-323">Modo</span><span class="sxs-lookup"><span data-stu-id="98e5e-323">Mode</span></span> |    <span data-ttu-id="98e5e-324">Usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-324">User</span></span> |  <span data-ttu-id="98e5e-325">Site</span><span class="sxs-lookup"><span data-stu-id="98e5e-325">Site</span></span> |  <span data-ttu-id="98e5e-326">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="98e5e-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="98e5e-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="98e5e-327">AlwaysBypass</span></span> |  <span data-ttu-id="98e5e-328">Externo</span><span class="sxs-lookup"><span data-stu-id="98e5e-328">External</span></span> |  <span data-ttu-id="98e5e-329">Não disponível</span><span class="sxs-lookup"><span data-stu-id="98e5e-329">N/A</span></span> | <span data-ttu-id="98e5e-330">Saída</span><span class="sxs-lookup"><span data-stu-id="98e5e-330">Outbound</span></span> |


<span data-ttu-id="98e5e-331">O diagrama a seguir mostra a escada SIP para uma chamada de saída com o modo AlwaysBypass e o usuário é externo:</span><span class="sxs-lookup"><span data-stu-id="98e5e-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="98e5e-333">A tabela a seguir mostra os cabeçalhos X-MS enviados pelo serviço de roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="98e5e-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="98e5e-334">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="98e5e-334">Parameter</span></span> |   <span data-ttu-id="98e5e-335">Explicação</span><span class="sxs-lookup"><span data-stu-id="98e5e-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="98e5e-336">Convidar + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="98e5e-337">O FQDN de destino do SBC, conforme definido na política de roteamento de voz online, é enviado no URI de solicitação.</span><span class="sxs-lookup"><span data-stu-id="98e5e-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="98e5e-338">X-MS-userlocation: External</span><span class="sxs-lookup"><span data-stu-id="98e5e-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="98e5e-339">O campo indicou que o usuário está localizado fora da rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="98e5e-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="98e5e-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="98e5e-341">Especifica qual SBC o cliente deve atravessar para o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="98e5e-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="98e5e-342">Nesse caso, como sempre ignoramos, e o cliente é externo.</span><span class="sxs-lookup"><span data-stu-id="98e5e-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="98e5e-343">As chamadas recebidas e o usuário externo sempre ignoram</span><span class="sxs-lookup"><span data-stu-id="98e5e-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="98e5e-344">Modo</span><span class="sxs-lookup"><span data-stu-id="98e5e-344">Mode</span></span> | <span data-ttu-id="98e5e-345">Usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-345">User</span></span> | <span data-ttu-id="98e5e-346">Site</span><span class="sxs-lookup"><span data-stu-id="98e5e-346">Site</span></span> |  <span data-ttu-id="98e5e-347">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="98e5e-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="98e5e-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="98e5e-348">AlwaysBypass</span></span> |  <span data-ttu-id="98e5e-349">Externo</span><span class="sxs-lookup"><span data-stu-id="98e5e-349">External</span></span> |  <span data-ttu-id="98e5e-350">Não disponível</span><span class="sxs-lookup"><span data-stu-id="98e5e-350">N/A</span></span> |   <span data-ttu-id="98e5e-351">Entrada</span><span class="sxs-lookup"><span data-stu-id="98e5e-351">Inbound</span></span> |

<span data-ttu-id="98e5e-352">Para uma chamada de entrada, o SBC conectado ao roteamento direto precisa enviar um novo convite (por padrão, os candidatos à mídia local são sempre oferecidos) se a localização do usuário for externa.</span><span class="sxs-lookup"><span data-stu-id="98e5e-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="98e5e-353">O X-MediaPath é calculado com base em rota de registro e o usuário SBC especificado.</span><span class="sxs-lookup"><span data-stu-id="98e5e-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="98e5e-354">O diagrama a seguir mostra a escada SIP para uma chamada de entrada com o modo AlwaysBypass e o usuário é externo.</span><span class="sxs-lookup"><span data-stu-id="98e5e-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="98e5e-356">Somente para o modo usuários locais</span><span class="sxs-lookup"><span data-stu-id="98e5e-356">Only for local users mode</span></span>

<span data-ttu-id="98e5e-357">Os candidatos à mídia local do SBC de destino serão oferecidos apenas se um usuário estiver no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="98e5e-358">Em todos os outros casos, a mídia fluirá por um IP interno ou externo do SBC do proxy.</span><span class="sxs-lookup"><span data-stu-id="98e5e-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="98e5e-359">Os seguintes cenários são descritos:</span><span class="sxs-lookup"><span data-stu-id="98e5e-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="98e5e-360">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="98e5e-361">As chamadas recebidas e o usuário estão no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="98e5e-362">O usuário não está no mesmo local do SBC, mas está na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="98e5e-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="98e5e-363">Chamadas recebidas e o usuário é interno, mas não está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="98e5e-364">A tabela a seguir mostra a ação e a configuração do usuário final:</span><span class="sxs-lookup"><span data-stu-id="98e5e-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="98e5e-365">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-365">User physical location</span></span> |  <span data-ttu-id="98e5e-366">O usuário faz ou recebe uma chamada de/para um número</span><span class="sxs-lookup"><span data-stu-id="98e5e-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="98e5e-367">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-367">User phone number</span></span> | <span data-ttu-id="98e5e-368">Política de roteamento de voz online</span><span class="sxs-lookup"><span data-stu-id="98e5e-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="98e5e-369">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="98e5e-370">Vietnã</span><span class="sxs-lookup"><span data-stu-id="98e5e-370">Vietnam</span></span> | <span data-ttu-id="98e5e-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="98e5e-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="98e5e-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="98e5e-372">+84 4 5555 5555</span></span> | <span data-ttu-id="98e5e-373">Prioridade 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="98e5e-374">Prioridade 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="98e5e-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="98e5e-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="98e5e-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="98e5e-376">Chamadas de saída e o usuário está no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="98e5e-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="98e5e-377">Modo</span><span class="sxs-lookup"><span data-stu-id="98e5e-377">Mode</span></span> | <span data-ttu-id="98e5e-378">Usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-378">User</span></span> | <span data-ttu-id="98e5e-379">Site</span><span class="sxs-lookup"><span data-stu-id="98e5e-379">Site</span></span> | <span data-ttu-id="98e5e-380">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="98e5e-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="98e5e-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="98e5e-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="98e5e-382">Interno</span><span class="sxs-lookup"><span data-stu-id="98e5e-382">Internal</span></span> |<span data-ttu-id="98e5e-383">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-383">Same as SBC</span></span>   | <span data-ttu-id="98e5e-384">Saída</span><span class="sxs-lookup"><span data-stu-id="98e5e-384">Outbound</span></span> |

<span data-ttu-id="98e5e-385">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers, e o usuário está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="98e5e-386">Esse é o mesmo fluxo mostrado em [chamadas de saída quando o usuário está no mesmo local do SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="98e5e-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="98e5e-388">As chamadas recebidas e o usuário estão no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="98e5e-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="98e5e-389">Modo</span><span class="sxs-lookup"><span data-stu-id="98e5e-389">Mode</span></span> | <span data-ttu-id="98e5e-390">Usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-390">User</span></span> | <span data-ttu-id="98e5e-391">Site</span><span class="sxs-lookup"><span data-stu-id="98e5e-391">Site</span></span> | <span data-ttu-id="98e5e-392">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="98e5e-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="98e5e-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="98e5e-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="98e5e-394">Interno</span><span class="sxs-lookup"><span data-stu-id="98e5e-394">Internal</span></span> | <span data-ttu-id="98e5e-395">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-395">Same as SBC</span></span> | <span data-ttu-id="98e5e-396">Entrada</span><span class="sxs-lookup"><span data-stu-id="98e5e-396">Inbound</span></span> |

<span data-ttu-id="98e5e-397">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers, e o usuário está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="98e5e-398">Esse é o mesmo fluxo mostrado em [chamadas de entrada quando o usuário está no mesmo local do SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="98e5e-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="98e5e-400">O usuário não está no mesmo local do SBC, mas está na rede corporativa somente com usuários locais</span><span class="sxs-lookup"><span data-stu-id="98e5e-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="98e5e-401">Modo</span><span class="sxs-lookup"><span data-stu-id="98e5e-401">Mode</span></span> | <span data-ttu-id="98e5e-402">Usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-402">User</span></span> | <span data-ttu-id="98e5e-403">Site</span><span class="sxs-lookup"><span data-stu-id="98e5e-403">Site</span></span> |<span data-ttu-id="98e5e-404">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="98e5e-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="98e5e-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="98e5e-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="98e5e-406">Interno</span><span class="sxs-lookup"><span data-stu-id="98e5e-406">Internal</span></span> |   <span data-ttu-id="98e5e-407">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-407">Different from SBC</span></span> | <span data-ttu-id="98e5e-408">Saída</span><span class="sxs-lookup"><span data-stu-id="98e5e-408">Outbound</span></span> |

<span data-ttu-id="98e5e-409">O roteamento direto calcula o X-MediaPath com base na localização informada do usuário e do modo configurado no SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="98e5e-410">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="98e5e-412">A chamada de entrada e o usuário são internas, mas não estão no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="98e5e-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="98e5e-413">Modo</span><span class="sxs-lookup"><span data-stu-id="98e5e-413">Mode</span></span> |    <span data-ttu-id="98e5e-414">Usuário</span><span class="sxs-lookup"><span data-stu-id="98e5e-414">User</span></span> |  <span data-ttu-id="98e5e-415">Site</span><span class="sxs-lookup"><span data-stu-id="98e5e-415">Site</span></span> |  <span data-ttu-id="98e5e-416">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="98e5e-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="98e5e-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="98e5e-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="98e5e-418">Interno</span><span class="sxs-lookup"><span data-stu-id="98e5e-418">Internal</span></span> |    <span data-ttu-id="98e5e-419">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="98e5e-419">Different from SBC</span></span> |    <span data-ttu-id="98e5e-420">Entrada</span><span class="sxs-lookup"><span data-stu-id="98e5e-420">Inbound</span></span> |

<span data-ttu-id="98e5e-421">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="98e5e-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-17.png)









