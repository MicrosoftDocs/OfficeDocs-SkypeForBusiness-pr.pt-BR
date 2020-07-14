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
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="3a8b2-103">Configurar a otimização de mídia local para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="3a8b2-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="3a8b2-104">A configuração da otimização de mídia local é baseada em configurações de rede que são comuns a outros recursos de voz em nuvem, como roteamento baseado em localização e chamadas de emergência dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="3a8b2-105">Para saber mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte [configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="3a8b2-106">Antes de configurar a otimização de mídia local, consulte [otimização de mídia local para roteamento direto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="3a8b2-107">Para configurar a otimização de mídia local, as etapas a seguir são necessárias.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="3a8b2-108">Você pode usar o centro de administração do teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="3a8b2-109">Para obter detalhes, consulte [gerenciar a topologia de rede](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="3a8b2-110">Configure o usuário e os sites de SBC (conforme descrito neste artigo).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="3a8b2-111">Configurar o SBCs para otimização de mídia local (de acordo com a especificação do fornecedor do SBC).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="3a8b2-112">O diagrama a seguir mostra a configuração de rede usada nos exemplos ao longo deste artigo.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="3a8b2-113">![Diagrama mostrando a configuração de rede para obter exemplos](media/direct-routing-media-op-9.png "Configuração de rede para obter exemplos")</span><span class="sxs-lookup"><span data-stu-id="3a8b2-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="3a8b2-114">Configurar o usuário e os sites de SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="3a8b2-115">Para configurar o usuário e os sites de SBC, você precisará:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="3a8b2-116">[Gerenciar endereços IP externos confiáveis](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="3a8b2-117">[Defina a topologia de rede](#define-the-network-topology) configurando as regiões de rede, sites de rede e sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="3a8b2-118">[Defina a topologia de rede virtual](#define-the-virtual-network-topology) atribuindo SBC (s) a (s) site (s) a (s) o (s) site (s) com os modos relevantes e valores</span><span class="sxs-lookup"><span data-stu-id="3a8b2-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="3a8b2-119">Configurar o SBC (s) para otimização de mídia local de acordo com a especificação do fornecedor do SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="3a8b2-120">Este artigo descreve a configuração dos componentes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="3a8b2-121">Para obter informações sobre a configuração do SBC, consulte a documentação do seu fornecedor de SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="3a8b2-122">A otimização de mídia local é compatível com os seguintes fornecedores de SBC:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="3a8b2-123">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="3a8b2-123">Vendor</span></span> | <span data-ttu-id="3a8b2-124">Produto</span><span class="sxs-lookup"><span data-stu-id="3a8b2-124">Product</span></span> |    <span data-ttu-id="3a8b2-125">Versão do software</span><span class="sxs-lookup"><span data-stu-id="3a8b2-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="3a8b2-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="3a8b2-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="3a8b2-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="3a8b2-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="3a8b2-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3a8b2-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="3a8b2-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="3a8b2-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3a8b2-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="3a8b2-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="3a8b2-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3a8b2-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="3a8b2-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="3a8b2-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3a8b2-135">1000B de SBC médio</span><span class="sxs-lookup"><span data-stu-id="3a8b2-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="3a8b2-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="3a8b2-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3a8b2-137">Mamédia 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="3a8b2-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="3a8b2-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3a8b2-139">Representação mediana virtual da edição virtual</span><span class="sxs-lookup"><span data-stu-id="3a8b2-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="3a8b2-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="3a8b2-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="3a8b2-141">Mamediat Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="3a8b2-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="3a8b2-142">7.20A.256</span></span> |
| [<span data-ttu-id="3a8b2-143">Faixa de opções do SBC Core</span><span class="sxs-lookup"><span data-stu-id="3a8b2-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="3a8b2-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="3a8b2-144">SBC 5110</span></span>         | <span data-ttu-id="3a8b2-145">8,2</span><span class="sxs-lookup"><span data-stu-id="3a8b2-145">8.2</span></span>  |
|            |  <span data-ttu-id="3a8b2-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="3a8b2-146">SBC 5210</span></span>         | <span data-ttu-id="3a8b2-147">8,2</span><span class="sxs-lookup"><span data-stu-id="3a8b2-147">8.2</span></span>  |
|            |  <span data-ttu-id="3a8b2-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="3a8b2-148">SBC 5400</span></span>         | <span data-ttu-id="3a8b2-149">8,2</span><span class="sxs-lookup"><span data-stu-id="3a8b2-149">8.2</span></span>  |
|            |  <span data-ttu-id="3a8b2-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="3a8b2-150">SBC 7000</span></span>         | <span data-ttu-id="3a8b2-151">8,2</span><span class="sxs-lookup"><span data-stu-id="3a8b2-151">8.2</span></span>  |
|            |  <span data-ttu-id="3a8b2-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="3a8b2-152">SBC SWe</span></span>          | <span data-ttu-id="3a8b2-153">8,2</span><span class="sxs-lookup"><span data-stu-id="3a8b2-153">8.2</span></span>  |
| [<span data-ttu-id="3a8b2-154">Borda SBC da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="3a8b2-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="3a8b2-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="3a8b2-155">SBC SWe Lite</span></span> | <span data-ttu-id="3a8b2-156">8.1.5 (Build 239)</span><span class="sxs-lookup"><span data-stu-id="3a8b2-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="3a8b2-157">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="3a8b2-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="3a8b2-158">anynode</span><span class="sxs-lookup"><span data-stu-id="3a8b2-158">anynode</span></span>          | <span data-ttu-id="3a8b2-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="3a8b2-159">4.0.1+</span></span> |
| [<span data-ttu-id="3a8b2-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="3a8b2-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="3a8b2-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="3a8b2-161">AP 1100</span></span> | <span data-ttu-id="3a8b2-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3a8b2-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="3a8b2-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="3a8b2-163">AP 3900</span></span> | <span data-ttu-id="3a8b2-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3a8b2-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="3a8b2-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="3a8b2-165">AP 4600</span></span> | <span data-ttu-id="3a8b2-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3a8b2-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="3a8b2-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="3a8b2-167">AP 6300</span></span> | <span data-ttu-id="3a8b2-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3a8b2-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="3a8b2-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="3a8b2-169">AP 6350</span></span> | <span data-ttu-id="3a8b2-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3a8b2-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="3a8b2-171">VME</span><span class="sxs-lookup"><span data-stu-id="3a8b2-171">VME</span></span>     | <span data-ttu-id="3a8b2-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="3a8b2-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="3a8b2-173">Gerenciar endereços IP externos confiáveis</span><span class="sxs-lookup"><span data-stu-id="3a8b2-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="3a8b2-174">Os IPs externos confiáveis são os IPs externos da Internet da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="3a8b2-175">Estes IP são os endereços IP usados pelos clientes do Microsoft Teams quando eles se conectam ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="3a8b2-176">Você precisa adicionar esses IPs externos para cada site em que você tem usuários usando a otimização de mídia local.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="3a8b2-177">Para adicionar os endereços IP públicos para cada site, use o cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="3a8b2-178">Você pode definir um número ilimitado de endereços IP confiáveis para um locatário.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="3a8b2-179">Se os IPs externos vistos pelo Microsoft 365 forem endereços IPv4 e IPv6, você precisará adicionar os dois tipos de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="3a8b2-180">Para IPv4, use máscara 32.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="3a8b2-181">Para IPv6, use máscara 128.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="3a8b2-182">Você pode adicionar endereços IP externos individuais e sub-redes externas de IP especificando diferentes MaskBits no cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="3a8b2-183">Exemplo de como adicionar endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="3a8b2-184">Definir a topologia de rede</span><span class="sxs-lookup"><span data-stu-id="3a8b2-184">Define the network topology</span></span>

<span data-ttu-id="3a8b2-185">Esta seção descreve como definir as regiões de rede, sites de rede e sub-redes de rede para a sua topologia de rede.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="3a8b2-186">Todos os parâmetros diferenciam maiúsculas de minúsculas, portanto, você precisa garantir que você use o mesmo caso que foi usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="3a8b2-187">(Por exemplo, os valores de GatewaySiteID "Vietnã" e "Vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="3a8b2-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="3a8b2-188">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="3a8b2-188">Define network regions</span></span>

<span data-ttu-id="3a8b2-189">Para definir regiões de rede, use o cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="3a8b2-190">O parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="3a8b2-191">O <site ID> parâmetro CentralSite é opcional.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="3a8b2-192">O exemplo a seguir cria uma região de rede chamada Ásia-Pacífico:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="3a8b2-193">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="3a8b2-193">Define network sites</span></span>

<span data-ttu-id="3a8b2-194">Para definir sites de rede, use o cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="3a8b2-195">Cada site de rede deve estar associado a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="3a8b2-196">O exemplo a seguir cria três novos sites de rede, Vietnã, Indonésia e Cingapura na região da Ásia/Pacífico:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="3a8b2-197">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="3a8b2-197">Define network subnets</span></span>

<span data-ttu-id="3a8b2-198">Para definir sub-redes de rede e associá-las a sites de rede, use o cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="3a8b2-199">Cada sub-rede de rede só pode ser associada a um site.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="3a8b2-200">O exemplo a seguir define três sub-redes de rede e as associa aos três locais de rede: Vietnã, Indonésia e Cingapura:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="3a8b2-201">Definir a topologia de rede virtual</span><span class="sxs-lookup"><span data-stu-id="3a8b2-201">Define the virtual network topology</span></span> 

<span data-ttu-id="3a8b2-202">Primeiro, o administrador do locatário cria uma nova configuração do SBC para cada SBC relevante usando o cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="3a8b2-203">O administrador do locatário define a topologia de rede virtual especificando os sites de rede dos objetos do gateway PSTN usando o cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="3a8b2-204">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-204">Note the following:</span></span> 
   - <span data-ttu-id="3a8b2-205">Se o cliente tiver um único SBC, o parâmetro-ProxySBC deve ser obrigatório $null ou o valor de FQDN do SBC (SBC central com o cenário de troncos centralizados).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="3a8b2-206">O parâmetro-MediaBypass deve ser definido como $true para dar suporte à otimização de mídia local.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="3a8b2-207">Se o SBC não tiver o parâmetro-Bypassmode definido, os cabeçalhos X-MS não serão enviados.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="3a8b2-208">Todos os parâmetros diferenciam maiúsculas de minúsculas, portanto você precisa garantir que você use o mesmo caso que foi usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="3a8b2-209">(Por exemplo, os valores de GatewaySiteID "Vietnã" e "Vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="3a8b2-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="3a8b2-210">O exemplo a seguir adiciona três SBCs aos locais de rede Vietnã, Indonésia e Cingapura na região da Ásia com o modo sempre ignorar:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="3a8b2-211">Observação: para garantir operações ininterruptas quando a otimização de mídia local e o roteamento baseado em local (LBR) estiverem configurados ao mesmo tempo, o SBCs downstream deve ser habilitado para LBR definindo o parâmetro GatewaySiteLbrEnabled para $true para cada SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="3a8b2-212">(Essa configuração não é obrigatória para o SBC do proxy.)</span><span class="sxs-lookup"><span data-stu-id="3a8b2-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="3a8b2-213">Com base nas informações acima, o roteamento direto incluirá três cabeçalhos SIP exclusivos para convites SIP e reconvida, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="3a8b2-214">Cabeçalhos X-MS inseridos no roteamento direto em convites e convites novamente se Bypassmode for definido:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="3a8b2-215">Nome do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="3a8b2-215">Header name</span></span> | <span data-ttu-id="3a8b2-216">Valores</span><span class="sxs-lookup"><span data-stu-id="3a8b2-216">Values</span></span> | <span data-ttu-id="3a8b2-217">Comentários</span><span class="sxs-lookup"><span data-stu-id="3a8b2-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="3a8b2-218">X-MS-userlocation</span><span class="sxs-lookup"><span data-stu-id="3a8b2-218">X-MS-UserLocation</span></span> | <span data-ttu-id="3a8b2-219">interno/externo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-219">internal/external</span></span> | <span data-ttu-id="3a8b2-220">Indica se o usuário é interno ou externo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="3a8b2-221">CONVITE de solicitação-URI SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="3a8b2-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="3a8b2-222">O FQDN DO SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-222">SBC FQDN</span></span> | <span data-ttu-id="3a8b2-223">O FQDN que é direcionado para a chamada mesmo se o SBC não estiver diretamente conectado ao roteamento direto</span><span class="sxs-lookup"><span data-stu-id="3a8b2-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="3a8b2-224">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="3a8b2-224">X-MS-MediaPath</span></span> | <span data-ttu-id="3a8b2-225">Exemplo: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="3a8b2-226">Ordem do SBCs que deve ser usada para o caminho de mídia entre o usuário e o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="3a8b2-227">O SBC final é sempre último</span><span class="sxs-lookup"><span data-stu-id="3a8b2-227">The final SBC is always last</span></span> |
| <span data-ttu-id="3a8b2-228">Site do X-MS-usersite</span><span class="sxs-lookup"><span data-stu-id="3a8b2-228">X-MS-UserSite</span></span> | <span data-ttu-id="3a8b2-229">usersiteid</span><span class="sxs-lookup"><span data-stu-id="3a8b2-229">usersiteID</span></span> | <span data-ttu-id="3a8b2-230">Cadeia de caracteres definida pelo administrador locatário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="3a8b2-231">Fluxos de chamadas</span><span class="sxs-lookup"><span data-stu-id="3a8b2-231">Call flows</span></span> 

<span data-ttu-id="3a8b2-232">Veja a seguir os fluxos de chamadas para dois modos:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="3a8b2-233">Sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="3a8b2-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="3a8b2-234">Somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3a8b2-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="3a8b2-235">Modo sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="3a8b2-235">Always Bypass mode</span></span>

<span data-ttu-id="3a8b2-236">Sempre ignorar modo é a opção mais simples de configurar.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="3a8b2-237">O administrador do locatário pode configurar um único site para todos os usuários e o SBCs se todos os SBCs forem acessíveis em qualquer site.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="3a8b2-238">Os exemplos mostram sempre o modo ignorar para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="3a8b2-239">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="3a8b2-240">As chamadas recebidas e o usuário estão no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="3a8b2-241">Chamadas de saída e o usuário é externo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="3a8b2-242">As chamadas recebidas e o usuário são externos</span><span class="sxs-lookup"><span data-stu-id="3a8b2-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="3a8b2-243">A tabela a seguir mostra os endereços IP e FQDN usados nos exemplos:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="3a8b2-244">FQDN</span><span class="sxs-lookup"><span data-stu-id="3a8b2-244">FQDN</span></span> | <span data-ttu-id="3a8b2-245">Endereço IP externo do SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-245">SBC external IP address</span></span> | <span data-ttu-id="3a8b2-246">Endereço IP interno do SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-246">SBC internal IP Address</span></span> | <span data-ttu-id="3a8b2-247">Sub-rede interna</span><span class="sxs-lookup"><span data-stu-id="3a8b2-247">Internal subnet</span></span> | <span data-ttu-id="3a8b2-248">Local</span><span class="sxs-lookup"><span data-stu-id="3a8b2-248">Location</span></span> | <span data-ttu-id="3a8b2-249">NAT externo (IP confiável)</span><span class="sxs-lookup"><span data-stu-id="3a8b2-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="3a8b2-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="3a8b2-251">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3a8b2-251">None</span></span> | <span data-ttu-id="3a8b2-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="3a8b2-252">192.168.1.5</span></span> | <span data-ttu-id="3a8b2-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="3a8b2-253">192.168.1.0/24</span></span> | <span data-ttu-id="3a8b2-254">Vietnã</span><span class="sxs-lookup"><span data-stu-id="3a8b2-254">Vietnam</span></span> | <span data-ttu-id="3a8b2-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="3a8b2-255">172.16.240.110</span></span> |
| <span data-ttu-id="3a8b2-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="3a8b2-257">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3a8b2-257">None</span></span> | <span data-ttu-id="3a8b2-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="3a8b2-258">192.168.2.5</span></span> | <span data-ttu-id="3a8b2-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="3a8b2-259">192.168.2.0/24</span></span> | <span data-ttu-id="3a8b2-260">Indonésia</span><span class="sxs-lookup"><span data-stu-id="3a8b2-260">Indonesia</span></span> | <span data-ttu-id="3a8b2-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="3a8b2-261">172.16.240.120</span></span> |
| <span data-ttu-id="3a8b2-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="3a8b2-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="3a8b2-263">172.16.240.133</span></span> | <span data-ttu-id="3a8b2-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="3a8b2-264">192.168.3.5</span></span> | <span data-ttu-id="3a8b2-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="3a8b2-265">192.168.3.0/24</span></span> | <span data-ttu-id="3a8b2-266">Singapura</span><span class="sxs-lookup"><span data-stu-id="3a8b2-266">Singapore</span></span> | <span data-ttu-id="3a8b2-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="3a8b2-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="3a8b2-268">Chamadas de saída e o usuário está no mesmo local que o SBC com sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="3a8b2-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="3a8b2-269">Modo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-269">Mode</span></span> |    <span data-ttu-id="3a8b2-270">Usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-270">User</span></span> |  <span data-ttu-id="3a8b2-271">Local</span><span class="sxs-lookup"><span data-stu-id="3a8b2-271">Location</span></span> |  <span data-ttu-id="3a8b2-272">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="3a8b2-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="3a8b2-273">AlwaysBypass</span></span> |    <span data-ttu-id="3a8b2-274">Interno</span><span class="sxs-lookup"><span data-stu-id="3a8b2-274">Internal</span></span> |  <span data-ttu-id="3a8b2-275">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-275">The same site as SBC</span></span> |  <span data-ttu-id="3a8b2-276">Saída</span><span class="sxs-lookup"><span data-stu-id="3a8b2-276">Outbound</span></span> |

<span data-ttu-id="3a8b2-277">A tabela a seguir mostra a ação e a configuração do usuário final:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="3a8b2-278">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-278">User physical location</span></span>| <span data-ttu-id="3a8b2-279">O usuário faz ou recebe uma chamada de/para um número</span><span class="sxs-lookup"><span data-stu-id="3a8b2-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="3a8b2-280">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-280">User phone number</span></span>  | <span data-ttu-id="3a8b2-281">Política de roteamento de voz online</span><span class="sxs-lookup"><span data-stu-id="3a8b2-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="3a8b2-282">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="3a8b2-283">Vietnã</span><span class="sxs-lookup"><span data-stu-id="3a8b2-283">Vietnam</span></span> | <span data-ttu-id="3a8b2-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="3a8b2-284">+84 4 3926 3000</span></span> | <span data-ttu-id="3a8b2-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="3a8b2-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="3a8b2-286">Prioridade 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="3a8b2-287">Prioridade 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="3a8b2-288">VNsbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="3a8b2-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="3a8b2-289">proxysbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="3a8b2-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="3a8b2-290">O diagrama a seguir mostra a escada SIP para uma chamada de saída com o modo sempre ignorado e o usuário no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="3a8b2-291">![Diagrama mostrando chamadas de saída](media/direct-routing-media-op-10.png "Chamadas de saída")</span><span class="sxs-lookup"><span data-stu-id="3a8b2-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="3a8b2-292">A tabela a seguir mostra os cabeçalhos X-MS enviados pelo roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="3a8b2-293">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="3a8b2-293">Parameter</span></span> | <span data-ttu-id="3a8b2-294">Explicação</span><span class="sxs-lookup"><span data-stu-id="3a8b2-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="3a8b2-295">Convidar + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="3a8b2-296">O FQDN de destino do SBC, conforme definido na política de roteamento de voz online, é enviado no URI de solicitação</span><span class="sxs-lookup"><span data-stu-id="3a8b2-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="3a8b2-297">X-MS-userlocation: Internal</span><span class="sxs-lookup"><span data-stu-id="3a8b2-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="3a8b2-298">O campo indicou que o usuário está localizado dentro da rede corporativa</span><span class="sxs-lookup"><span data-stu-id="3a8b2-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="3a8b2-299">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="3a8b2-300">Especifica qual SBC o cliente deve atravessar para o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="3a8b2-301">Nesse caso, como sempre ignoramos, e o cliente é interno o nome de destino enviado como o único nome no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="3a8b2-302">X-MS-usersite: Vietnã</span><span class="sxs-lookup"><span data-stu-id="3a8b2-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="3a8b2-303">O campo indicado no site em que o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="3a8b2-304">As chamadas recebidas e o usuário estão no mesmo local que o SBC com sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="3a8b2-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="3a8b2-305">Modo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-305">Mode</span></span> |    <span data-ttu-id="3a8b2-306">Usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-306">User</span></span> |  <span data-ttu-id="3a8b2-307">Local</span><span class="sxs-lookup"><span data-stu-id="3a8b2-307">Location</span></span> |  <span data-ttu-id="3a8b2-308">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="3a8b2-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="3a8b2-309">AlwaysBypass</span></span> |    <span data-ttu-id="3a8b2-310">Interno</span><span class="sxs-lookup"><span data-stu-id="3a8b2-310">Internal</span></span> | <span data-ttu-id="3a8b2-311">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-311">The same site as SBC</span></span> | <span data-ttu-id="3a8b2-312">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-312">Inbound</span></span> |


<span data-ttu-id="3a8b2-313">Em uma chamada de entrada, o local do usuário é desconhecido, e o SBC deve adivinhar onde está o usuário.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="3a8b2-314">Se a estimativa estiver incorreta, será preciso um novo convite.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="3a8b2-315">Esse caso presume que o usuário seja interno, a mídia pode fluir diretamente e não são necessárias mais ações (convidar novamente).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="3a8b2-316">O SBC conectado ao serviço de roteamento direto relata o local do SBC de origem fornecendo campos de rota de registro e de contato.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="3a8b2-317">Com base nesses campos, o caminho de mídia é calculado pelo roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="3a8b2-318">Observação: Considerando que um usuário pode ter vários pontos de extremidade, o suporte do 183 não é possível.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="3a8b2-319">O roteamento direto sempre usará o 180 tocando nesse caso.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="3a8b2-320">O diagrama a seguir mostra a escada em SIP para a chamada de entrada com o modo AlwaysBypass, e o usuário está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="3a8b2-322">Chamadas de saída e o usuário é externo sempre bypass</span><span class="sxs-lookup"><span data-stu-id="3a8b2-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="3a8b2-323">Modo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-323">Mode</span></span> |    <span data-ttu-id="3a8b2-324">Usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-324">User</span></span> |  <span data-ttu-id="3a8b2-325">Site</span><span class="sxs-lookup"><span data-stu-id="3a8b2-325">Site</span></span> |  <span data-ttu-id="3a8b2-326">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="3a8b2-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="3a8b2-327">AlwaysBypass</span></span> |  <span data-ttu-id="3a8b2-328">Externo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-328">External</span></span> |  <span data-ttu-id="3a8b2-329">Não disponível</span><span class="sxs-lookup"><span data-stu-id="3a8b2-329">N/A</span></span> | <span data-ttu-id="3a8b2-330">Saída</span><span class="sxs-lookup"><span data-stu-id="3a8b2-330">Outbound</span></span> |


<span data-ttu-id="3a8b2-331">O diagrama a seguir mostra a escada SIP para uma chamada de saída com o modo AlwaysBypass e o usuário é externo:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="3a8b2-333">A tabela a seguir mostra os cabeçalhos X-MS enviados pelo serviço de roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="3a8b2-334">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="3a8b2-334">Parameter</span></span> |   <span data-ttu-id="3a8b2-335">Explicação</span><span class="sxs-lookup"><span data-stu-id="3a8b2-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="3a8b2-336">Convidar + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="3a8b2-337">O FQDN de destino do SBC, conforme definido na política de roteamento de voz online, é enviado no URI de solicitação.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="3a8b2-338">X-MS-userlocation: External</span><span class="sxs-lookup"><span data-stu-id="3a8b2-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="3a8b2-339">O campo indicou que o usuário está localizado fora da rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="3a8b2-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="3a8b2-341">Especifica qual SBC o cliente deve atravessar para o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="3a8b2-342">Nesse caso, como sempre ignoramos, e o cliente é externo.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="3a8b2-343">As chamadas recebidas e o usuário externo sempre ignoram</span><span class="sxs-lookup"><span data-stu-id="3a8b2-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="3a8b2-344">Modo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-344">Mode</span></span> | <span data-ttu-id="3a8b2-345">Usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-345">User</span></span> | <span data-ttu-id="3a8b2-346">Site</span><span class="sxs-lookup"><span data-stu-id="3a8b2-346">Site</span></span> |  <span data-ttu-id="3a8b2-347">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="3a8b2-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="3a8b2-348">AlwaysBypass</span></span> |  <span data-ttu-id="3a8b2-349">Externo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-349">External</span></span> |  <span data-ttu-id="3a8b2-350">Não disponível</span><span class="sxs-lookup"><span data-stu-id="3a8b2-350">N/A</span></span> |   <span data-ttu-id="3a8b2-351">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-351">Inbound</span></span> |

<span data-ttu-id="3a8b2-352">Para uma chamada de entrada, o SBC conectado ao roteamento direto precisa enviar um novo convite (por padrão, os candidatos à mídia local são sempre oferecidos) se a localização do usuário for externa.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="3a8b2-353">O X-MediaPath é calculado com base em rota de registro e o usuário SBC especificado.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="3a8b2-354">O diagrama a seguir mostra a escada SIP para uma chamada de entrada com o modo AlwaysBypass e o usuário é externo.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="3a8b2-356">Somente para o modo usuários locais</span><span class="sxs-lookup"><span data-stu-id="3a8b2-356">Only for local users mode</span></span>

<span data-ttu-id="3a8b2-357">Os candidatos à mídia local do SBC de destino serão oferecidos apenas se um usuário estiver no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="3a8b2-358">Em todos os outros casos, a mídia fluirá por um IP interno ou externo do SBC do proxy.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="3a8b2-359">Os seguintes cenários são descritos:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="3a8b2-360">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="3a8b2-361">As chamadas recebidas e o usuário estão no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="3a8b2-362">O usuário não está no mesmo local do SBC, mas está na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="3a8b2-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="3a8b2-363">Chamadas recebidas e o usuário é interno, mas não está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="3a8b2-364">A tabela a seguir mostra a ação e a configuração do usuário final:</span><span class="sxs-lookup"><span data-stu-id="3a8b2-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="3a8b2-365">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-365">User physical location</span></span> |  <span data-ttu-id="3a8b2-366">O usuário faz ou recebe uma chamada de/para um número</span><span class="sxs-lookup"><span data-stu-id="3a8b2-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="3a8b2-367">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-367">User phone number</span></span> | <span data-ttu-id="3a8b2-368">Política de roteamento de voz online</span><span class="sxs-lookup"><span data-stu-id="3a8b2-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="3a8b2-369">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="3a8b2-370">Vietnã</span><span class="sxs-lookup"><span data-stu-id="3a8b2-370">Vietnam</span></span> | <span data-ttu-id="3a8b2-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="3a8b2-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="3a8b2-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="3a8b2-372">+84 4 5555 5555</span></span> | <span data-ttu-id="3a8b2-373">Prioridade 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="3a8b2-374">Prioridade 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3a8b2-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="3a8b2-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="3a8b2-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="3a8b2-376">Chamadas de saída e o usuário está no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3a8b2-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="3a8b2-377">Modo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-377">Mode</span></span> | <span data-ttu-id="3a8b2-378">Usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-378">User</span></span> | <span data-ttu-id="3a8b2-379">Site</span><span class="sxs-lookup"><span data-stu-id="3a8b2-379">Site</span></span> | <span data-ttu-id="3a8b2-380">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="3a8b2-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="3a8b2-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="3a8b2-382">Interno</span><span class="sxs-lookup"><span data-stu-id="3a8b2-382">Internal</span></span> |<span data-ttu-id="3a8b2-383">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-383">Same as SBC</span></span>   | <span data-ttu-id="3a8b2-384">Saída</span><span class="sxs-lookup"><span data-stu-id="3a8b2-384">Outbound</span></span> |

<span data-ttu-id="3a8b2-385">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers, e o usuário está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="3a8b2-386">Esse é o mesmo fluxo mostrado em [chamadas de saída quando o usuário está no mesmo local do SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="3a8b2-388">As chamadas recebidas e o usuário estão no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3a8b2-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="3a8b2-389">Modo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-389">Mode</span></span> | <span data-ttu-id="3a8b2-390">Usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-390">User</span></span> | <span data-ttu-id="3a8b2-391">Site</span><span class="sxs-lookup"><span data-stu-id="3a8b2-391">Site</span></span> | <span data-ttu-id="3a8b2-392">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="3a8b2-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="3a8b2-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="3a8b2-394">Interno</span><span class="sxs-lookup"><span data-stu-id="3a8b2-394">Internal</span></span> | <span data-ttu-id="3a8b2-395">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-395">Same as SBC</span></span> | <span data-ttu-id="3a8b2-396">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-396">Inbound</span></span> |

<span data-ttu-id="3a8b2-397">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers, e o usuário está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="3a8b2-398">Esse é o mesmo fluxo mostrado em [chamadas de entrada quando o usuário está no mesmo local do SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="3a8b2-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="3a8b2-400">O usuário não está no mesmo local do SBC, mas está na rede corporativa somente com usuários locais</span><span class="sxs-lookup"><span data-stu-id="3a8b2-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="3a8b2-401">Modo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-401">Mode</span></span> | <span data-ttu-id="3a8b2-402">Usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-402">User</span></span> | <span data-ttu-id="3a8b2-403">Site</span><span class="sxs-lookup"><span data-stu-id="3a8b2-403">Site</span></span> |<span data-ttu-id="3a8b2-404">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="3a8b2-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="3a8b2-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="3a8b2-406">Interno</span><span class="sxs-lookup"><span data-stu-id="3a8b2-406">Internal</span></span> |   <span data-ttu-id="3a8b2-407">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-407">Different from SBC</span></span> | <span data-ttu-id="3a8b2-408">Saída</span><span class="sxs-lookup"><span data-stu-id="3a8b2-408">Outbound</span></span> |

<span data-ttu-id="3a8b2-409">O roteamento direto calcula o X-MediaPath com base na localização informada do usuário e do modo configurado no SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="3a8b2-410">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="3a8b2-412">A chamada de entrada e o usuário são internas, mas não estão no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="3a8b2-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="3a8b2-413">Modo</span><span class="sxs-lookup"><span data-stu-id="3a8b2-413">Mode</span></span> |    <span data-ttu-id="3a8b2-414">Usuário</span><span class="sxs-lookup"><span data-stu-id="3a8b2-414">User</span></span> |  <span data-ttu-id="3a8b2-415">Site</span><span class="sxs-lookup"><span data-stu-id="3a8b2-415">Site</span></span> |  <span data-ttu-id="3a8b2-416">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="3a8b2-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="3a8b2-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="3a8b2-418">Interno</span><span class="sxs-lookup"><span data-stu-id="3a8b2-418">Internal</span></span> |    <span data-ttu-id="3a8b2-419">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="3a8b2-419">Different from SBC</span></span> |    <span data-ttu-id="3a8b2-420">Entrada</span><span class="sxs-lookup"><span data-stu-id="3a8b2-420">Inbound</span></span> |

<span data-ttu-id="3a8b2-421">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="3a8b2-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-17.png)









