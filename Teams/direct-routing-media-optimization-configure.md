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
ms.openlocfilehash: 518445e10b757adc9a21c426fb885bb04b7a878b
ms.sourcegitcommit: b143611d14765af054a4f84cca52e2003d35af1a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44047850"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="08c07-103">Configurar a otimização de mídia local para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="08c07-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="08c07-104">A configuração da otimização de mídia local é baseada em configurações de rede que são comuns a outros recursos de voz em nuvem, como roteamento baseado em localização e chamadas de emergência dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="08c07-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="08c07-105">Para saber mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte [configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="08c07-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="08c07-106">Antes de configurar a otimização de mídia local, consulte [otimização de mídia local para roteamento direto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="08c07-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="08c07-107">Para configurar a otimização de mídia local, as etapas a seguir são necessárias.</span><span class="sxs-lookup"><span data-stu-id="08c07-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="08c07-108">Você pode usar o centro de administração do teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08c07-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="08c07-109">Para obter detalhes, consulte [gerenciar a topologia de rede](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="08c07-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="08c07-110">Configure o usuário e os sites de SBC (conforme descrito neste artigo).</span><span class="sxs-lookup"><span data-stu-id="08c07-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="08c07-111">Configurar o SBCs para otimização de mídia local (de acordo com a especificação do fornecedor do SBC).</span><span class="sxs-lookup"><span data-stu-id="08c07-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="08c07-112">O diagrama a seguir mostra a configuração de rede usada nos exemplos ao longo deste artigo.</span><span class="sxs-lookup"><span data-stu-id="08c07-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="08c07-113">![Diagrama mostrando a configuração de rede para obter exemplos](media/direct-routing-media-op-9.png "Configuração de rede para obter exemplos")</span><span class="sxs-lookup"><span data-stu-id="08c07-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="08c07-114">Configurar o usuário e os sites de SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="08c07-115">Para configurar o usuário e os sites de SBC, você precisará:</span><span class="sxs-lookup"><span data-stu-id="08c07-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="08c07-116">[Gerenciar endereços IP externos confiáveis](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="08c07-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="08c07-117">[Defina a topologia de rede](#define-the-network-topology) configurando as regiões de rede, sites de rede e sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="08c07-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="08c07-118">[Defina a topologia de rede virtual](#define-the-virtual-network-topology) atribuindo SBC (s) a (s) site (s) a (s) o (s) site (s) com os modos relevantes e valores</span><span class="sxs-lookup"><span data-stu-id="08c07-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="08c07-119">Configurar o SBC (s) para otimização de mídia local de acordo com a especificação do fornecedor do SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="08c07-120">Este artigo descreve a configuração dos componentes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="08c07-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="08c07-121">Para obter informações sobre a configuração do SBC, consulte seu fornecedor de SBC documenation.</span><span class="sxs-lookup"><span data-stu-id="08c07-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="08c07-122">A otimização de mídia local é compatível com os seguintes fornecedores de SBC:</span><span class="sxs-lookup"><span data-stu-id="08c07-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="08c07-123">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="08c07-123">Vendor</span></span> | <span data-ttu-id="08c07-124">Produto</span><span class="sxs-lookup"><span data-stu-id="08c07-124">Product</span></span> |    <span data-ttu-id="08c07-125">Versão do software</span><span class="sxs-lookup"><span data-stu-id="08c07-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="08c07-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="08c07-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="08c07-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="08c07-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="08c07-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="08c07-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="08c07-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="08c07-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="08c07-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="08c07-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="08c07-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="08c07-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="08c07-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="08c07-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="08c07-135">1000B de SBC médio</span><span class="sxs-lookup"><span data-stu-id="08c07-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="08c07-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="08c07-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="08c07-137">Mamédia 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="08c07-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="08c07-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="08c07-139">Representação mediana virtual da edição virtual</span><span class="sxs-lookup"><span data-stu-id="08c07-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="08c07-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="08c07-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="08c07-141">Mamediat Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="08c07-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="08c07-142">7.20A.256</span></span> |
| [<span data-ttu-id="08c07-143">Faixa de opções do SBC Core</span><span class="sxs-lookup"><span data-stu-id="08c07-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="08c07-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="08c07-144">SBC 5110</span></span>         | <span data-ttu-id="08c07-145">8,2</span><span class="sxs-lookup"><span data-stu-id="08c07-145">8.2</span></span>  |
|            |  <span data-ttu-id="08c07-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="08c07-146">SBC 5210</span></span>         | <span data-ttu-id="08c07-147">8,2</span><span class="sxs-lookup"><span data-stu-id="08c07-147">8.2</span></span>  |
|            |  <span data-ttu-id="08c07-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="08c07-148">SBC 5400</span></span>         | <span data-ttu-id="08c07-149">8,2</span><span class="sxs-lookup"><span data-stu-id="08c07-149">8.2</span></span>  |
|            |  <span data-ttu-id="08c07-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="08c07-150">SBC 7000</span></span>         | <span data-ttu-id="08c07-151">8,2</span><span class="sxs-lookup"><span data-stu-id="08c07-151">8.2</span></span>  |
|            |  <span data-ttu-id="08c07-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="08c07-152">SBC SWe</span></span>          | <span data-ttu-id="08c07-153">8,2</span><span class="sxs-lookup"><span data-stu-id="08c07-153">8.2</span></span>  |
| [<span data-ttu-id="08c07-154">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="08c07-154">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="08c07-155">anynode</span><span class="sxs-lookup"><span data-stu-id="08c07-155">anynode</span></span>          | <span data-ttu-id="08c07-156">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="08c07-156">4.0.1+</span></span> |
| [<span data-ttu-id="08c07-157">Oracle</span><span class="sxs-lookup"><span data-stu-id="08c07-157">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="08c07-158">AP 1100</span><span class="sxs-lookup"><span data-stu-id="08c07-158">AP 1100</span></span> | <span data-ttu-id="08c07-159">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="08c07-159">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="08c07-160">AP 3900</span><span class="sxs-lookup"><span data-stu-id="08c07-160">AP 3900</span></span> | <span data-ttu-id="08c07-161">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="08c07-161">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="08c07-162">AP 4600</span><span class="sxs-lookup"><span data-stu-id="08c07-162">AP 4600</span></span> | <span data-ttu-id="08c07-163">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="08c07-163">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="08c07-164">AP 6300</span><span class="sxs-lookup"><span data-stu-id="08c07-164">AP 6300</span></span> | <span data-ttu-id="08c07-165">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="08c07-165">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="08c07-166">AP 6350</span><span class="sxs-lookup"><span data-stu-id="08c07-166">AP 6350</span></span> | <span data-ttu-id="08c07-167">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="08c07-167">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="08c07-168">VME</span><span class="sxs-lookup"><span data-stu-id="08c07-168">VME</span></span>     | <span data-ttu-id="08c07-169">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="08c07-169">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="08c07-170">Gerenciar endereços IP externos confiáveis</span><span class="sxs-lookup"><span data-stu-id="08c07-170">Manage external trusted IP addresses</span></span>

<span data-ttu-id="08c07-171">Os IPs externos confiáveis são os IPs externos da Internet da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="08c07-171">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="08c07-172">Estes IP são os endereços IP usados pelos clientes do Microsoft Teams quando eles se conectam ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08c07-172">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="08c07-173">Você precisa adicionar esses IPs externos para cada site em que você tem usuários usando a otimização de mídia local.</span><span class="sxs-lookup"><span data-stu-id="08c07-173">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="08c07-174">Para adicionar os endereços IP públicos para cada site, use o cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="08c07-174">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="08c07-175">Você pode definir um número ilimitado de endereços IP confiáveis para um locatário.</span><span class="sxs-lookup"><span data-stu-id="08c07-175">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="08c07-176">Se os IPs externos vistos pelo Microsoft 365 forem endereços IPv4 e IPv6, você precisará adicionar os dois tipos de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="08c07-176">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="08c07-177">Para IPv4, use máscara 32.</span><span class="sxs-lookup"><span data-stu-id="08c07-177">For IPv4, use mask 32.</span></span> <span data-ttu-id="08c07-178">Para IPv6, use máscara 128.</span><span class="sxs-lookup"><span data-stu-id="08c07-178">For IPv6, use mask 128.</span></span> <span data-ttu-id="08c07-179">Você pode adicionar endereços IP externos individuais e sub-redes externas de IP especificando diferentes MaskBits no cmdlet.</span><span class="sxs-lookup"><span data-stu-id="08c07-179">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="08c07-180">Exemplo de como adicionar endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="08c07-180">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="08c07-181">Definir a topologia de rede</span><span class="sxs-lookup"><span data-stu-id="08c07-181">Define the network topology</span></span>

<span data-ttu-id="08c07-182">Esta seção descreve como definir as regiões de rede, sites de rede e sub-redes de rede para a sua topologia de rede.</span><span class="sxs-lookup"><span data-stu-id="08c07-182">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="08c07-183">Todos os parâmetros diferenciam maiúsculas de minúsculas, portanto, você precisa garantir que você use o mesmo caso que foi usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="08c07-183">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="08c07-184">(Por exemplo, os valores de GatewaySiteID "Vietnã" e "Vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="08c07-184">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="08c07-185">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="08c07-185">Define network regions</span></span>

<span data-ttu-id="08c07-186">Para definir regiões de rede, use o cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="08c07-186">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="08c07-187">O parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições.</span><span class="sxs-lookup"><span data-stu-id="08c07-187">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="08c07-188">O parâmetro <site ID> CentralSite é opcional.</span><span class="sxs-lookup"><span data-stu-id="08c07-188">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="08c07-189">O exemplo a seguir cria uma região de rede chamada Ásia-Pacífico:</span><span class="sxs-lookup"><span data-stu-id="08c07-189">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="08c07-190">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="08c07-190">Define network sites</span></span>

<span data-ttu-id="08c07-191">Para definir sites de rede, use o cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="08c07-191">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="08c07-192">Cada site de rede deve estar associado a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="08c07-192">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="08c07-193">O exemplo a seguir cria três novos sites de rede, Vietnã, Indonésia e Cingapura na região da Ásia/Pacífico:</span><span class="sxs-lookup"><span data-stu-id="08c07-193">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="08c07-194">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="08c07-194">Define network subnets</span></span>

<span data-ttu-id="08c07-195">Para definir sub-redes de rede e associá-las a sites de rede, use o cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="08c07-195">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="08c07-196">Cada sub-rede de rede só pode ser associada a um site.</span><span class="sxs-lookup"><span data-stu-id="08c07-196">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="08c07-197">O exemplo a seguir define três sub-redes de rede e as associa aos três locais de rede: Vietnã, Indonésia e Cingapura:</span><span class="sxs-lookup"><span data-stu-id="08c07-197">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="08c07-198">Definir a topologia de rede virtual</span><span class="sxs-lookup"><span data-stu-id="08c07-198">Define the virtual network topology</span></span> 

<span data-ttu-id="08c07-199">Primeiro, o administrador do locatário cria uma nova configuração do SBC para cada SBC relevante usando o cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="08c07-199">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="08c07-200">O administrador do locatário define a topologia de rede virtual especificando os sites de rede dos objetos do gateway PSTN usando o cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="08c07-200">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="08c07-201">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08c07-201">Note the following:</span></span> 
   - <span data-ttu-id="08c07-202">Se o cliente tiver um único SBC, o parâmetro-ProxySBC deve ser obrigatório $null ou o valor de FQDN do SBC (SBC central com o cenário de troncos centralizados).</span><span class="sxs-lookup"><span data-stu-id="08c07-202">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="08c07-203">O parâmetro-MediaBypass deve ser definido como $true para dar suporte à otimização de mídia local.</span><span class="sxs-lookup"><span data-stu-id="08c07-203">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="08c07-204">Se o SBC não tiver o parâmetro-Bypassmode definido, os cabeçalhos X-MS não serão enviados.</span><span class="sxs-lookup"><span data-stu-id="08c07-204">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="08c07-205">Todos os parâmetros diferenciam maiúsculas de minúsculas, portanto você precisa garantir que você use o mesmo caso que foi usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="08c07-205">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="08c07-206">(Por exemplo, os valores de GatewaySiteID "Vietnã" e "Vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="08c07-206">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="08c07-207">O exemplo a seguir adiciona três SBCs aos locais de rede Vietnã, Indonésia e Cingapura na região da Ásia com o modo sempre ignorar:</span><span class="sxs-lookup"><span data-stu-id="08c07-207">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="08c07-208">Observação: para garantir operações ininterruptas quando a otimização de mídia local e o roteamento baseado em local (LBR) estiverem configurados ao mesmo tempo, o SBCs downstream deve ser habilitado para LBR definindo o parâmetro GatewaySiteLbrEnabled para $true para cada SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="08c07-208">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="08c07-209">(Essa configuração não é obrigatória para o SBC do proxy.)</span><span class="sxs-lookup"><span data-stu-id="08c07-209">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="08c07-210">Com base nas informações acima, o roteamento direto incluirá três cabeçalhos SIP exclusivos para convites SIP e reconvida, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="08c07-210">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="08c07-211">Cabeçalhos X-MS inseridos no roteamento direto em convites e convites novamente se Bypassmode for definido:</span><span class="sxs-lookup"><span data-stu-id="08c07-211">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="08c07-212">Nome do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="08c07-212">Header name</span></span> | <span data-ttu-id="08c07-213">Valores</span><span class="sxs-lookup"><span data-stu-id="08c07-213">Values</span></span> | <span data-ttu-id="08c07-214">Comentários</span><span class="sxs-lookup"><span data-stu-id="08c07-214">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="08c07-215">X-MS-userlocation</span><span class="sxs-lookup"><span data-stu-id="08c07-215">X-MS-UserLocation</span></span> | <span data-ttu-id="08c07-216">interno/externo</span><span class="sxs-lookup"><span data-stu-id="08c07-216">internal/external</span></span> | <span data-ttu-id="08c07-217">Indica se o usuário é interno ou externo</span><span class="sxs-lookup"><span data-stu-id="08c07-217">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="08c07-218">CONVITE de solicitação-URI SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="08c07-218">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="08c07-219">O FQDN DO SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-219">SBC FQDN</span></span> | <span data-ttu-id="08c07-220">O FQDN que é direcionado para a chamada mesmo se o SBC não estiver diretamente conectado ao roteamento direto</span><span class="sxs-lookup"><span data-stu-id="08c07-220">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="08c07-221">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="08c07-221">X-MS-MediaPath</span></span> | <span data-ttu-id="08c07-222">Exemplo: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-222">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="08c07-223">Ordem do SBCs que deve ser usada para o caminho de mídia entre o usuário e o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="08c07-223">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="08c07-224">O SBC final é sempre último</span><span class="sxs-lookup"><span data-stu-id="08c07-224">The final SBC is always last</span></span> |
| <span data-ttu-id="08c07-225">Site do X-MS-usersite</span><span class="sxs-lookup"><span data-stu-id="08c07-225">X-MS-UserSite</span></span> | <span data-ttu-id="08c07-226">usersiteid</span><span class="sxs-lookup"><span data-stu-id="08c07-226">usersiteID</span></span> | <span data-ttu-id="08c07-227">Cadeia de caracteres definida pelo administrador locatário</span><span class="sxs-lookup"><span data-stu-id="08c07-227">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="08c07-228">Fluxos de chamadas</span><span class="sxs-lookup"><span data-stu-id="08c07-228">Call flows</span></span> 

<span data-ttu-id="08c07-229">Veja a seguir os fluxos de chamadas para dois modos:</span><span class="sxs-lookup"><span data-stu-id="08c07-229">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="08c07-230">Sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="08c07-230">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="08c07-231">Somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="08c07-231">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="08c07-232">Modo sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="08c07-232">Always Bypass mode</span></span>

<span data-ttu-id="08c07-233">Sempre ignorar modo é a opção mais simples de configurar.</span><span class="sxs-lookup"><span data-stu-id="08c07-233">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="08c07-234">O administrador do locatário pode configurar um único site para todos os usuários e o SBCs se todos os SBCs forem acessíveis em qualquer site.</span><span class="sxs-lookup"><span data-stu-id="08c07-234">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="08c07-235">Os exemplos mostram sempre o modo ignorar para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="08c07-235">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="08c07-236">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-236">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="08c07-237">As chamadas recebidas e o usuário estão no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-237">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="08c07-238">Chamadas de saída e o usuário é externo</span><span class="sxs-lookup"><span data-stu-id="08c07-238">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="08c07-239">As chamadas recebidas e o usuário são externos</span><span class="sxs-lookup"><span data-stu-id="08c07-239">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="08c07-240">A tabela a seguir mostra os endereços IP e FQDN usados nos exemplos:</span><span class="sxs-lookup"><span data-stu-id="08c07-240">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="08c07-241">FQDN</span><span class="sxs-lookup"><span data-stu-id="08c07-241">FQDN</span></span> | <span data-ttu-id="08c07-242">Endereço IP externo do SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-242">SBC external IP address</span></span> | <span data-ttu-id="08c07-243">Endereço IP interno do SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-243">SBC internal IP Address</span></span> | <span data-ttu-id="08c07-244">Sub-rede interna</span><span class="sxs-lookup"><span data-stu-id="08c07-244">Internal subnet</span></span> | <span data-ttu-id="08c07-245">Local</span><span class="sxs-lookup"><span data-stu-id="08c07-245">Location</span></span> | <span data-ttu-id="08c07-246">NAT externo (IP confiável)</span><span class="sxs-lookup"><span data-stu-id="08c07-246">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="08c07-247">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-247">VNsbc.contoso.com</span></span> | <span data-ttu-id="08c07-248">Nenhum</span><span class="sxs-lookup"><span data-stu-id="08c07-248">None</span></span> | <span data-ttu-id="08c07-249">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="08c07-249">192.168.1.5</span></span> | <span data-ttu-id="08c07-250">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="08c07-250">192.168.1.0/24</span></span> | <span data-ttu-id="08c07-251">Vietnã</span><span class="sxs-lookup"><span data-stu-id="08c07-251">Vietnam</span></span> | <span data-ttu-id="08c07-252">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="08c07-252">172.16.240.110</span></span> |
| <span data-ttu-id="08c07-253">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-253">IDsbc.contoso.com</span></span> | <span data-ttu-id="08c07-254">Nenhum</span><span class="sxs-lookup"><span data-stu-id="08c07-254">None</span></span> | <span data-ttu-id="08c07-255">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="08c07-255">192.168.2.5</span></span> | <span data-ttu-id="08c07-256">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="08c07-256">192.168.2.0/24</span></span> | <span data-ttu-id="08c07-257">Indonésia</span><span class="sxs-lookup"><span data-stu-id="08c07-257">Indonesia</span></span> | <span data-ttu-id="08c07-258">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="08c07-258">172.16.240.120</span></span> |
| <span data-ttu-id="08c07-259">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-259">proxysbc.contoso.com</span></span> | <span data-ttu-id="08c07-260">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="08c07-260">172.16.240.133</span></span> | <span data-ttu-id="08c07-261">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="08c07-261">192.168.3.5</span></span> | <span data-ttu-id="08c07-262">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="08c07-262">192.168.3.0/24</span></span> | <span data-ttu-id="08c07-263">Singapura</span><span class="sxs-lookup"><span data-stu-id="08c07-263">Singapore</span></span> | <span data-ttu-id="08c07-264">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="08c07-264">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="08c07-265">Chamadas de saída e o usuário está no mesmo local que o SBC com sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="08c07-265">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="08c07-266">Modo</span><span class="sxs-lookup"><span data-stu-id="08c07-266">Mode</span></span> |    <span data-ttu-id="08c07-267">Usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-267">User</span></span> |  <span data-ttu-id="08c07-268">Local</span><span class="sxs-lookup"><span data-stu-id="08c07-268">Location</span></span> |  <span data-ttu-id="08c07-269">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="08c07-269">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="08c07-270">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="08c07-270">AlwaysBypass</span></span> |    <span data-ttu-id="08c07-271">Interno</span><span class="sxs-lookup"><span data-stu-id="08c07-271">Internal</span></span> |  <span data-ttu-id="08c07-272">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-272">The same site as SBC</span></span> |  <span data-ttu-id="08c07-273">Saída</span><span class="sxs-lookup"><span data-stu-id="08c07-273">Outbound</span></span> |

<span data-ttu-id="08c07-274">A tabela a seguir mostra a ação e a configuração do usuário final:</span><span class="sxs-lookup"><span data-stu-id="08c07-274">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="08c07-275">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-275">User physical location</span></span>| <span data-ttu-id="08c07-276">O usuário faz ou recebe uma chamada de/para um número</span><span class="sxs-lookup"><span data-stu-id="08c07-276">User makes or receives a call to/from number</span></span> | <span data-ttu-id="08c07-277">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-277">User phone number</span></span>  | <span data-ttu-id="08c07-278">Política de roteamento de voz online</span><span class="sxs-lookup"><span data-stu-id="08c07-278">Online Voice Routing Policy</span></span> | <span data-ttu-id="08c07-279">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-279">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="08c07-280">Vietnã</span><span class="sxs-lookup"><span data-stu-id="08c07-280">Vietnam</span></span> | <span data-ttu-id="08c07-281">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="08c07-281">+84 4 3926 3000</span></span> | <span data-ttu-id="08c07-282">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="08c07-282">+84 4 5555 5555</span></span>   | <span data-ttu-id="08c07-283">Prioridade 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-283">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="08c07-284">Prioridade 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-284">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="08c07-285">VNsbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="08c07-285">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="08c07-286">proxysbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="08c07-286">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="08c07-287">O diagrama a seguir mostra a escada SIP para uma chamada de saída com o modo sempre ignorado e o usuário no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="08c07-287">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="08c07-288">![Diagrama mostrando chamadas de saída](media/direct-routing-media-op-10.png "Chamadas de saída")</span><span class="sxs-lookup"><span data-stu-id="08c07-288">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="08c07-289">A tabela a seguir mostra os cabeçalhos X-MS enviados pelo roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="08c07-289">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="08c07-290">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="08c07-290">Parameter</span></span> | <span data-ttu-id="08c07-291">Explicação</span><span class="sxs-lookup"><span data-stu-id="08c07-291">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="08c07-292">Convidar + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-292">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="08c07-293">O nome de destino do SBC, conforme definido na política de roteamento de voz online, é enviado no URI de solicitação</span><span class="sxs-lookup"><span data-stu-id="08c07-293">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="08c07-294">X-MS-userlocation: Internal</span><span class="sxs-lookup"><span data-stu-id="08c07-294">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="08c07-295">O campo indicou que o usuário está localizado dentro da rede corporativa</span><span class="sxs-lookup"><span data-stu-id="08c07-295">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="08c07-296">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-296">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="08c07-297">Especifica qual SBC o cliente deve atravessar para o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="08c07-297">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="08c07-298">Nesse caso, como sempre ignoramos, e o cliente é interno o nome de destino enviado como o único nome no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="08c07-298">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="08c07-299">X-MS-usersite: Vietnã</span><span class="sxs-lookup"><span data-stu-id="08c07-299">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="08c07-300">O campo indicado no site em que o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="08c07-300">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="08c07-301">As chamadas recebidas e o usuário estão no mesmo local que o SBC com sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="08c07-301">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="08c07-302">Modo</span><span class="sxs-lookup"><span data-stu-id="08c07-302">Mode</span></span> |    <span data-ttu-id="08c07-303">Usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-303">User</span></span> |  <span data-ttu-id="08c07-304">Local</span><span class="sxs-lookup"><span data-stu-id="08c07-304">Location</span></span> |  <span data-ttu-id="08c07-305">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="08c07-305">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="08c07-306">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="08c07-306">AlwaysBypass</span></span> |    <span data-ttu-id="08c07-307">Interno</span><span class="sxs-lookup"><span data-stu-id="08c07-307">Internal</span></span> | <span data-ttu-id="08c07-308">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-308">The same site as SBC</span></span> | <span data-ttu-id="08c07-309">Entrada</span><span class="sxs-lookup"><span data-stu-id="08c07-309">Inbound</span></span> |


<span data-ttu-id="08c07-310">Em uma chamada de entrada, o local do usuário é desconhecido, e o SBC deve adivinhar onde está o usuário.</span><span class="sxs-lookup"><span data-stu-id="08c07-310">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="08c07-311">Se a estimativa estiver incorreta, será preciso um novo convite.</span><span class="sxs-lookup"><span data-stu-id="08c07-311">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="08c07-312">Esse caso presume que o usuário seja interno, a mídia pode fluir diretamente e não são necessárias mais ações (convidar novamente).</span><span class="sxs-lookup"><span data-stu-id="08c07-312">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="08c07-313">O SBC conectado ao serviço de roteamento direto relata o local do SBC de origem fornecendo campos de rota de registro e de contato.</span><span class="sxs-lookup"><span data-stu-id="08c07-313">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="08c07-314">Com base nesses campos, o caminho de mídia é calculado pelo roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="08c07-314">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="08c07-315">Observação: Considerando que um usuário pode ter vários pontos de extremidade, o suporte do 183 não é possível.</span><span class="sxs-lookup"><span data-stu-id="08c07-315">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="08c07-316">O roteamento direto sempre usará o 180 tocando nesse caso.</span><span class="sxs-lookup"><span data-stu-id="08c07-316">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="08c07-317">O diagrama a seguir mostra a escada em SIP para a chamada de entrada com o modo AlwaysBypass, e o usuário está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="08c07-317">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="08c07-319">Chamadas de saída e o usuário é externo sempre bypass</span><span class="sxs-lookup"><span data-stu-id="08c07-319">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="08c07-320">Modo</span><span class="sxs-lookup"><span data-stu-id="08c07-320">Mode</span></span> |    <span data-ttu-id="08c07-321">Usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-321">User</span></span> |  <span data-ttu-id="08c07-322">Site</span><span class="sxs-lookup"><span data-stu-id="08c07-322">Site</span></span> |  <span data-ttu-id="08c07-323">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="08c07-323">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="08c07-324">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="08c07-324">AlwaysBypass</span></span> |  <span data-ttu-id="08c07-325">Externo</span><span class="sxs-lookup"><span data-stu-id="08c07-325">External</span></span> |  <span data-ttu-id="08c07-326">Não disponível</span><span class="sxs-lookup"><span data-stu-id="08c07-326">N/A</span></span> | <span data-ttu-id="08c07-327">Saída</span><span class="sxs-lookup"><span data-stu-id="08c07-327">Outbound</span></span> |


<span data-ttu-id="08c07-328">O diagrama a seguir mostra a escada SIP para uma chamada de saída com o modo AlwaysBypass e o usuário é externo:</span><span class="sxs-lookup"><span data-stu-id="08c07-328">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="08c07-330">A tabela a seguir mostra os cabeçalhos X-MS enviados pelo serviço de roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="08c07-330">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="08c07-331">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="08c07-331">Parameter</span></span> |   <span data-ttu-id="08c07-332">Explicação</span><span class="sxs-lookup"><span data-stu-id="08c07-332">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="08c07-333">Convidar + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-333">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="08c07-334">O nome de destino do SBC, conforme definido na política de roteamento de voz online, é enviado no URI de solicitação.</span><span class="sxs-lookup"><span data-stu-id="08c07-334">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="08c07-335">X-MS-userlocation: External</span><span class="sxs-lookup"><span data-stu-id="08c07-335">X-MS-UserLocation: external</span></span> | <span data-ttu-id="08c07-336">O campo indicou que o usuário está localizado fora da rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="08c07-336">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="08c07-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-337">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="08c07-338">Especifica qual SBC o cliente deve atravessar para o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="08c07-338">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="08c07-339">Nesse caso, como sempre ignoramos, e o cliente é externo.</span><span class="sxs-lookup"><span data-stu-id="08c07-339">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="08c07-340">As chamadas recebidas e o usuário externo sempre ignoram</span><span class="sxs-lookup"><span data-stu-id="08c07-340">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="08c07-341">Modo</span><span class="sxs-lookup"><span data-stu-id="08c07-341">Mode</span></span> | <span data-ttu-id="08c07-342">Usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-342">User</span></span> | <span data-ttu-id="08c07-343">Site</span><span class="sxs-lookup"><span data-stu-id="08c07-343">Site</span></span> |  <span data-ttu-id="08c07-344">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="08c07-344">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="08c07-345">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="08c07-345">AlwaysBypass</span></span> |  <span data-ttu-id="08c07-346">Externo</span><span class="sxs-lookup"><span data-stu-id="08c07-346">External</span></span> |  <span data-ttu-id="08c07-347">Não disponível</span><span class="sxs-lookup"><span data-stu-id="08c07-347">N/A</span></span> |   <span data-ttu-id="08c07-348">Entrada</span><span class="sxs-lookup"><span data-stu-id="08c07-348">Inbound</span></span> |

<span data-ttu-id="08c07-349">Para uma chamada de entrada, o SBC conectado ao roteamento direto precisa enviar um novo convite (por padrão, os candidatos à mídia local são sempre oferecidos) se a localização do usuário for externa.</span><span class="sxs-lookup"><span data-stu-id="08c07-349">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="08c07-350">O X-MediaPath é calculado com base em rota de registro e o usuário SBC especificado.</span><span class="sxs-lookup"><span data-stu-id="08c07-350">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="08c07-351">O diagrama a seguir mostra a escada SIP para uma chamada de entrada com o modo AlwaysBypass e o usuário é externo.</span><span class="sxs-lookup"><span data-stu-id="08c07-351">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="08c07-353">Somente para o modo usuários locais</span><span class="sxs-lookup"><span data-stu-id="08c07-353">Only for local users mode</span></span>

<span data-ttu-id="08c07-354">Os candidatos à mídia local do SBC de destino serão oferecidos apenas se um usuário estiver no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="08c07-354">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="08c07-355">Em todos os outros casos, a mídia fluirá por um IP interno ou externo do SBC do proxy.</span><span class="sxs-lookup"><span data-stu-id="08c07-355">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="08c07-356">Os seguintes cenários são descritos:</span><span class="sxs-lookup"><span data-stu-id="08c07-356">The following scenarios are described:</span></span>

- [<span data-ttu-id="08c07-357">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-357">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="08c07-358">As chamadas recebidas e o usuário estão no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-358">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="08c07-359">O usuário não está no mesmo local do SBC, mas está na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="08c07-359">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="08c07-360">Chamadas recebidas e o usuário é interno, mas não está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-360">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="08c07-361">A tabela a seguir mostra a ação e a configuração do usuário final:</span><span class="sxs-lookup"><span data-stu-id="08c07-361">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="08c07-362">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-362">User physical location</span></span> |  <span data-ttu-id="08c07-363">O usuário faz ou recebe uma chamada de/para um número</span><span class="sxs-lookup"><span data-stu-id="08c07-363">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="08c07-364">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-364">User phone number</span></span> | <span data-ttu-id="08c07-365">Política de roteamento de voz online</span><span class="sxs-lookup"><span data-stu-id="08c07-365">Online Voice Routing Policy</span></span> |   <span data-ttu-id="08c07-366">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-366">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="08c07-367">Vietnã</span><span class="sxs-lookup"><span data-stu-id="08c07-367">Vietnam</span></span> | <span data-ttu-id="08c07-368">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="08c07-368">+84 4 3926  3000</span></span> |  <span data-ttu-id="08c07-369">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="08c07-369">+84 4 5555 5555</span></span> | <span data-ttu-id="08c07-370">Prioridade 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-370">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="08c07-371">Prioridade 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="08c07-371">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="08c07-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="08c07-372">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="08c07-373">Chamadas de saída e o usuário está no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="08c07-373">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="08c07-374">Modo</span><span class="sxs-lookup"><span data-stu-id="08c07-374">Mode</span></span> | <span data-ttu-id="08c07-375">Usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-375">User</span></span> | <span data-ttu-id="08c07-376">Site</span><span class="sxs-lookup"><span data-stu-id="08c07-376">Site</span></span> | <span data-ttu-id="08c07-377">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="08c07-377">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="08c07-378">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="08c07-378">OnlyForLocalUsers</span></span> |   <span data-ttu-id="08c07-379">Interno</span><span class="sxs-lookup"><span data-stu-id="08c07-379">Internal</span></span> |<span data-ttu-id="08c07-380">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-380">Same as SBC</span></span>   | <span data-ttu-id="08c07-381">Saída</span><span class="sxs-lookup"><span data-stu-id="08c07-381">Outbound</span></span> |

<span data-ttu-id="08c07-382">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers, e o usuário está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="08c07-382">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="08c07-383">Esse é o mesmo fluxo mostrado em [chamadas de saída quando o usuário está no mesmo local do SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="08c07-383">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="08c07-385">As chamadas recebidas e o usuário estão no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="08c07-385">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="08c07-386">Modo</span><span class="sxs-lookup"><span data-stu-id="08c07-386">Mode</span></span> | <span data-ttu-id="08c07-387">Usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-387">User</span></span> | <span data-ttu-id="08c07-388">Site</span><span class="sxs-lookup"><span data-stu-id="08c07-388">Site</span></span> | <span data-ttu-id="08c07-389">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="08c07-389">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="08c07-390">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="08c07-390">OnlyForLocalUsers</span></span> |   <span data-ttu-id="08c07-391">Interno</span><span class="sxs-lookup"><span data-stu-id="08c07-391">Internal</span></span> | <span data-ttu-id="08c07-392">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-392">Same as SBC</span></span> | <span data-ttu-id="08c07-393">Entrada</span><span class="sxs-lookup"><span data-stu-id="08c07-393">Inbound</span></span> |

<span data-ttu-id="08c07-394">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers, e o usuário está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="08c07-394">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="08c07-395">Esse é o mesmo fluxo mostrado em [chamadas de entrada quando o usuário está no mesmo local do SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="08c07-395">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="08c07-397">O usuário não está no mesmo local do SBC, mas está na rede corporativa somente com usuários locais</span><span class="sxs-lookup"><span data-stu-id="08c07-397">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="08c07-398">Modo</span><span class="sxs-lookup"><span data-stu-id="08c07-398">Mode</span></span> | <span data-ttu-id="08c07-399">Usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-399">User</span></span> | <span data-ttu-id="08c07-400">Site</span><span class="sxs-lookup"><span data-stu-id="08c07-400">Site</span></span> |<span data-ttu-id="08c07-401">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="08c07-401">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="08c07-402">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="08c07-402">OnlyForLocalUsers</span></span>  | <span data-ttu-id="08c07-403">Interno</span><span class="sxs-lookup"><span data-stu-id="08c07-403">Internal</span></span> |   <span data-ttu-id="08c07-404">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-404">Different from SBC</span></span> | <span data-ttu-id="08c07-405">Saída</span><span class="sxs-lookup"><span data-stu-id="08c07-405">Outbound</span></span> |

<span data-ttu-id="08c07-406">O roteamento direto calcula o X-MediaPath com base na localização informada do usuário e do modo configurado no SBC.</span><span class="sxs-lookup"><span data-stu-id="08c07-406">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="08c07-407">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="08c07-407">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="08c07-409">A chamada de entrada e o usuário são internas, mas não estão no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="08c07-409">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="08c07-410">Modo</span><span class="sxs-lookup"><span data-stu-id="08c07-410">Mode</span></span> |    <span data-ttu-id="08c07-411">Usuário</span><span class="sxs-lookup"><span data-stu-id="08c07-411">User</span></span> |  <span data-ttu-id="08c07-412">Site</span><span class="sxs-lookup"><span data-stu-id="08c07-412">Site</span></span> |  <span data-ttu-id="08c07-413">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="08c07-413">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="08c07-414">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="08c07-414">OnlyForLocalUsers</span></span> | <span data-ttu-id="08c07-415">Interno</span><span class="sxs-lookup"><span data-stu-id="08c07-415">Internal</span></span> |    <span data-ttu-id="08c07-416">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="08c07-416">Different from SBC</span></span> |    <span data-ttu-id="08c07-417">Entrada</span><span class="sxs-lookup"><span data-stu-id="08c07-417">Inbound</span></span> |

<span data-ttu-id="08c07-418">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="08c07-418">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-17.png)









