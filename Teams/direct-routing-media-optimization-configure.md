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
ms.openlocfilehash: 3097f97a856dc4e947281847c65669c23c73a408
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157928"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="23827-103">Configurar a otimização de mídia local para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="23827-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="23827-104">A configuração da otimização de mídia local é baseada em configurações de rede que são comuns a outros recursos de voz em nuvem, como roteamento baseado em localização e chamadas de emergência dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="23827-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="23827-105">Para saber mais sobre regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte [configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="23827-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="23827-106">Antes de configurar a otimização de mídia local, consulte [otimização de mídia local para roteamento direto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="23827-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="23827-107">Para configurar a otimização de mídia local, as etapas a seguir são necessárias.</span><span class="sxs-lookup"><span data-stu-id="23827-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="23827-108">Você pode usar o centro de administração do teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23827-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="23827-109">Para obter detalhes, consulte [gerenciar a topologia de rede](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="23827-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="23827-110">Configure o usuário e os sites de SBC (conforme descrito neste artigo).</span><span class="sxs-lookup"><span data-stu-id="23827-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="23827-111">Configurar o SBCs para otimização de mídia local (de acordo com a especificação do fornecedor do SBC).</span><span class="sxs-lookup"><span data-stu-id="23827-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="23827-112">O diagrama a seguir mostra a configuração de rede usada nos exemplos ao longo deste artigo.</span><span class="sxs-lookup"><span data-stu-id="23827-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="23827-113">![Diagrama mostrando a configuração de rede para obter exemplos](media/direct-routing-media-op-9.png "Configuração de rede para obter exemplos")</span><span class="sxs-lookup"><span data-stu-id="23827-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="23827-114">Configurar o usuário e os sites de SBC</span><span class="sxs-lookup"><span data-stu-id="23827-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="23827-115">Para configurar o usuário e os sites de SBC, você precisará:</span><span class="sxs-lookup"><span data-stu-id="23827-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="23827-116">[Gerenciar endereços IP externos confiáveis](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="23827-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="23827-117">[Defina a topologia de rede](#define-the-network-topology) configurando as regiões de rede, sites de rede e sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="23827-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="23827-118">[Defina a topologia de rede virtual](#define-the-virtual-network-topology) atribuindo SBC (s) a (s) site (s) a (s) o (s) site (s) com os modos relevantes e valores</span><span class="sxs-lookup"><span data-stu-id="23827-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="23827-119">Configurar o SBC (s) para otimização de mídia local de acordo com a especificação do fornecedor do SBC</span><span class="sxs-lookup"><span data-stu-id="23827-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="23827-120">Este artigo descreve a configuração dos componentes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="23827-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="23827-121">Para obter informações sobre a configuração do SBC, consulte seu fornecedor de SBC documenation.</span><span class="sxs-lookup"><span data-stu-id="23827-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="23827-122">A otimização de mídia local é compatível com os seguintes fornecedores de SBC:</span><span class="sxs-lookup"><span data-stu-id="23827-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="23827-123">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="23827-123">Vendor</span></span> | <span data-ttu-id="23827-124">Produto</span><span class="sxs-lookup"><span data-stu-id="23827-124">Product</span></span> |    <span data-ttu-id="23827-125">Versão do software</span><span class="sxs-lookup"><span data-stu-id="23827-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="23827-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="23827-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="23827-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="23827-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="23827-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="23827-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="23827-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="23827-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="23827-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="23827-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="23827-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="23827-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="23827-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="23827-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="23827-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="23827-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="23827-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="23827-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="23827-135">1000B de SBC médio</span><span class="sxs-lookup"><span data-stu-id="23827-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="23827-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="23827-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="23827-137">Mamédia 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="23827-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="23827-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="23827-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="23827-139">Representação mediana virtual da edição virtual</span><span class="sxs-lookup"><span data-stu-id="23827-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="23827-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="23827-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="23827-141">Mamediat Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="23827-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="23827-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="23827-142">7.20A.256</span></span> |
| [<span data-ttu-id="23827-143">Faixa de opções do SBC Core</span><span class="sxs-lookup"><span data-stu-id="23827-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="23827-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="23827-144">SBC 5110</span></span>         | <span data-ttu-id="23827-145">8,2</span><span class="sxs-lookup"><span data-stu-id="23827-145">8.2</span></span>  |
|            |  <span data-ttu-id="23827-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="23827-146">SBC 5210</span></span>         | <span data-ttu-id="23827-147">8,2</span><span class="sxs-lookup"><span data-stu-id="23827-147">8.2</span></span>  |
|            |  <span data-ttu-id="23827-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="23827-148">SBC 5400</span></span>         | <span data-ttu-id="23827-149">8,2</span><span class="sxs-lookup"><span data-stu-id="23827-149">8.2</span></span>  |
|            |  <span data-ttu-id="23827-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="23827-150">SBC 7000</span></span>         | <span data-ttu-id="23827-151">8,2</span><span class="sxs-lookup"><span data-stu-id="23827-151">8.2</span></span>  |
|            |  <span data-ttu-id="23827-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="23827-152">SBC SWe</span></span>          | <span data-ttu-id="23827-153">8,2</span><span class="sxs-lookup"><span data-stu-id="23827-153">8.2</span></span>  |
| [<span data-ttu-id="23827-154">Borda SBC da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="23827-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="23827-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="23827-155">SBC 1000</span></span>         | <span data-ttu-id="23827-156">8.1.1, Build 527</span><span class="sxs-lookup"><span data-stu-id="23827-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="23827-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="23827-157">SBC 2000</span></span>         | <span data-ttu-id="23827-158">8.1.1, Build 527</span><span class="sxs-lookup"><span data-stu-id="23827-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="23827-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="23827-159">SBC SWe Lite</span></span>     | <span data-ttu-id="23827-160">8.1.0, Build 222</span><span class="sxs-lookup"><span data-stu-id="23827-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="23827-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="23827-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="23827-162">anynode</span><span class="sxs-lookup"><span data-stu-id="23827-162">anynode</span></span>          | <span data-ttu-id="23827-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="23827-163">4.0.1+</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="23827-164">Gerenciar endereços IP externos confiáveis</span><span class="sxs-lookup"><span data-stu-id="23827-164">Manage external trusted IP addresses</span></span>

<span data-ttu-id="23827-165">Os IPs externos confiáveis são os IPs externos da Internet da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="23827-165">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="23827-166">Estes IP são os endereços IP usados pelos clientes do Microsoft Teams quando eles se conectam ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23827-166">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="23827-167">Você precisa adicionar esses IPs externos para cada site em que você tem usuários usando a otimização de mídia local.</span><span class="sxs-lookup"><span data-stu-id="23827-167">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="23827-168">Para adicionar os endereços IP públicos para cada site, use o cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="23827-168">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="23827-169">Você pode definir um número ilimitado de endereços IP confiáveis para um locatário.</span><span class="sxs-lookup"><span data-stu-id="23827-169">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="23827-170">Se os IPs externos vistos pelo Microsoft 365 forem endereços IPv4 e IPv6, você precisará adicionar os dois tipos de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="23827-170">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="23827-171">Para IPv4, use máscara 32.</span><span class="sxs-lookup"><span data-stu-id="23827-171">For IPv4, use mask 32.</span></span> <span data-ttu-id="23827-172">Para IPv6, use máscara 128.</span><span class="sxs-lookup"><span data-stu-id="23827-172">For IPv6, use mask 128.</span></span> <span data-ttu-id="23827-173">Você pode adicionar endereços IP externos individuais e sub-redes externas de IP especificando diferentes MaskBits no cmdlet.</span><span class="sxs-lookup"><span data-stu-id="23827-173">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="23827-174">Exemplo de como adicionar endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="23827-174">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="23827-175">Definir a topologia de rede</span><span class="sxs-lookup"><span data-stu-id="23827-175">Define the network topology</span></span>

<span data-ttu-id="23827-176">Esta seção descreve como definir as regiões de rede, sites de rede e sub-redes de rede para a sua topologia de rede.</span><span class="sxs-lookup"><span data-stu-id="23827-176">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="23827-177">Todos os parâmetros diferenciam maiúsculas de minúsculas, portanto, você precisa garantir que você use o mesmo caso que foi usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="23827-177">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="23827-178">(Por exemplo, os valores de GatewaySiteID "Vietnã" e "Vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="23827-178">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="23827-179">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="23827-179">Define network regions</span></span>

<span data-ttu-id="23827-180">Para definir regiões de rede, use o cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="23827-180">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="23827-181">O parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições.</span><span class="sxs-lookup"><span data-stu-id="23827-181">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="23827-182">O parâmetro <site ID> CentralSite é opcional.</span><span class="sxs-lookup"><span data-stu-id="23827-182">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="23827-183">O exemplo a seguir cria uma região de rede chamada Ásia-Pacífico:</span><span class="sxs-lookup"><span data-stu-id="23827-183">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="23827-184">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="23827-184">Define network sites</span></span>

<span data-ttu-id="23827-185">Para definir sites de rede, use o cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="23827-185">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="23827-186">Cada site de rede deve estar associado a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="23827-186">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="23827-187">O exemplo a seguir cria três novos sites de rede, Vietnã, Indonésia e Cingapura na região da Ásia/Pacífico:</span><span class="sxs-lookup"><span data-stu-id="23827-187">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="23827-188">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="23827-188">Define network subnets</span></span>

<span data-ttu-id="23827-189">Para definir sub-redes de rede e associá-las a sites de rede, use o cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="23827-189">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="23827-190">Cada sub-rede de rede só pode ser associada a um site.</span><span class="sxs-lookup"><span data-stu-id="23827-190">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="23827-191">O exemplo a seguir define três sub-redes de rede e as associa aos três locais de rede: Vietnã, Indonésia e Cingapura:</span><span class="sxs-lookup"><span data-stu-id="23827-191">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="23827-192">Definir a topologia de rede virtual</span><span class="sxs-lookup"><span data-stu-id="23827-192">Define the virtual network topology</span></span> 

<span data-ttu-id="23827-193">Primeiro, o administrador do locatário cria uma nova configuração do SBC para cada SBC relevante usando o cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="23827-193">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="23827-194">O administrador do locatário define a topologia de rede virtual especificando os sites de rede dos objetos do gateway PSTN usando o cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="23827-194">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="23827-195">Observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="23827-195">Note the following:</span></span> 
   - <span data-ttu-id="23827-196">Se o cliente tiver um único SBC, o parâmetro-ProxySBC deve ser obrigatório $null ou o valor de FQDN do SBC (SBC central com o cenário de troncos centralizados).</span><span class="sxs-lookup"><span data-stu-id="23827-196">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="23827-197">O parâmetro-MediaBypass deve ser definido como $true para dar suporte à otimização de mídia local.</span><span class="sxs-lookup"><span data-stu-id="23827-197">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="23827-198">Se o SBC não tiver o parâmetro-Bypassmode definido, os cabeçalhos X-MS não serão enviados.</span><span class="sxs-lookup"><span data-stu-id="23827-198">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="23827-199">Todos os parâmetros diferenciam maiúsculas de minúsculas, portanto você precisa garantir que você use o mesmo caso que foi usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="23827-199">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="23827-200">(Por exemplo, os valores de GatewaySiteID "Vietnã" e "Vietnã" serão tratados como sites diferentes.)</span><span class="sxs-lookup"><span data-stu-id="23827-200">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="23827-201">O exemplo a seguir adiciona três SBCs aos locais de rede Vietnã, Indonésia e Cingapura na região da Ásia com o modo sempre ignorar:</span><span class="sxs-lookup"><span data-stu-id="23827-201">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="23827-202">Observação: para garantir operações ininterruptas quando a otimização de mídia local e o roteamento baseado em local (LBR) estiverem configurados ao mesmo tempo, o SBCs downstream deve ser habilitado para LBR definindo o parâmetro GatewaySiteLbrEnabled para $true para cada SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="23827-202">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="23827-203">(Essa configuração não é obrigatória para o SBC do proxy.)</span><span class="sxs-lookup"><span data-stu-id="23827-203">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="23827-204">Com base nas informações acima, o roteamento direto incluirá três cabeçalhos SIP exclusivos para convites SIP e reconvida, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="23827-204">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="23827-205">Cabeçalhos X-MS inseridos no roteamento direto em convites e convites novamente se Bypassmode for definido:</span><span class="sxs-lookup"><span data-stu-id="23827-205">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="23827-206">Nome do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="23827-206">Header name</span></span> | <span data-ttu-id="23827-207">Valores</span><span class="sxs-lookup"><span data-stu-id="23827-207">Values</span></span> | <span data-ttu-id="23827-208">Comentários</span><span class="sxs-lookup"><span data-stu-id="23827-208">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="23827-209">X-MS-userlocation</span><span class="sxs-lookup"><span data-stu-id="23827-209">X-MS-UserLocation</span></span> | <span data-ttu-id="23827-210">interno/externo</span><span class="sxs-lookup"><span data-stu-id="23827-210">internal/external</span></span> | <span data-ttu-id="23827-211">Indica se o usuário é interno ou externo</span><span class="sxs-lookup"><span data-stu-id="23827-211">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="23827-212">CONVITE de solicitação-URI SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="23827-212">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="23827-213">O FQDN DO SBC</span><span class="sxs-lookup"><span data-stu-id="23827-213">SBC FQDN</span></span> | <span data-ttu-id="23827-214">O FQDN que é direcionado para a chamada mesmo se o SBC não estiver diretamente conectado ao roteamento direto</span><span class="sxs-lookup"><span data-stu-id="23827-214">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="23827-215">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="23827-215">X-MS-MediaPath</span></span> | <span data-ttu-id="23827-216">Exemplo: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-216">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="23827-217">Ordem do SBCs que deve ser usada para o caminho de mídia entre o usuário e o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="23827-217">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="23827-218">O SBC final é sempre último</span><span class="sxs-lookup"><span data-stu-id="23827-218">The final SBC is always last</span></span> |
| <span data-ttu-id="23827-219">Site do X-MS-usersite</span><span class="sxs-lookup"><span data-stu-id="23827-219">X-MS-UserSite</span></span> | <span data-ttu-id="23827-220">usersiteid</span><span class="sxs-lookup"><span data-stu-id="23827-220">usersiteID</span></span> | <span data-ttu-id="23827-221">Cadeia de caracteres definida pelo administrador locatário</span><span class="sxs-lookup"><span data-stu-id="23827-221">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="23827-222">Fluxos de chamadas</span><span class="sxs-lookup"><span data-stu-id="23827-222">Call flows</span></span> 

<span data-ttu-id="23827-223">Veja a seguir os fluxos de chamadas para dois modos:</span><span class="sxs-lookup"><span data-stu-id="23827-223">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="23827-224">Sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="23827-224">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="23827-225">Somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="23827-225">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="23827-226">Modo sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="23827-226">Always Bypass mode</span></span>

<span data-ttu-id="23827-227">Sempre ignorar modo é a opção mais simples de configurar.</span><span class="sxs-lookup"><span data-stu-id="23827-227">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="23827-228">O administrador do locatário pode configurar um único site para todos os usuários e o SBCs se todos os SBCs forem acessíveis em qualquer site.</span><span class="sxs-lookup"><span data-stu-id="23827-228">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="23827-229">Os exemplos mostram sempre o modo ignorar para os seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="23827-229">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="23827-230">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="23827-230">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="23827-231">As chamadas recebidas e o usuário estão no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="23827-231">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="23827-232">Chamadas de saída e o usuário é externo</span><span class="sxs-lookup"><span data-stu-id="23827-232">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="23827-233">As chamadas recebidas e o usuário são externos</span><span class="sxs-lookup"><span data-stu-id="23827-233">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="23827-234">A tabela a seguir mostra os endereços IP e FQDN usados nos exemplos:</span><span class="sxs-lookup"><span data-stu-id="23827-234">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="23827-235">FQDN</span><span class="sxs-lookup"><span data-stu-id="23827-235">FQDN</span></span> | <span data-ttu-id="23827-236">Endereço IP externo do SBC</span><span class="sxs-lookup"><span data-stu-id="23827-236">SBC external IP address</span></span> | <span data-ttu-id="23827-237">Endereço IP interno do SBC</span><span class="sxs-lookup"><span data-stu-id="23827-237">SBC internal IP Address</span></span> | <span data-ttu-id="23827-238">Sub-rede interna</span><span class="sxs-lookup"><span data-stu-id="23827-238">Internal subnet</span></span> | <span data-ttu-id="23827-239">Local</span><span class="sxs-lookup"><span data-stu-id="23827-239">Location</span></span> | <span data-ttu-id="23827-240">NAT externo (IP confiável)</span><span class="sxs-lookup"><span data-stu-id="23827-240">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="23827-241">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-241">VNsbc.contoso.com</span></span> | <span data-ttu-id="23827-242">Nenhum</span><span class="sxs-lookup"><span data-stu-id="23827-242">None</span></span> | <span data-ttu-id="23827-243">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="23827-243">192.168.1.5</span></span> | <span data-ttu-id="23827-244">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="23827-244">192.168.1.0/24</span></span> | <span data-ttu-id="23827-245">Vietnã</span><span class="sxs-lookup"><span data-stu-id="23827-245">Vietnam</span></span> | <span data-ttu-id="23827-246">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="23827-246">172.16.240.110</span></span> |
| <span data-ttu-id="23827-247">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-247">IDsbc.contoso.com</span></span> | <span data-ttu-id="23827-248">Nenhum</span><span class="sxs-lookup"><span data-stu-id="23827-248">None</span></span> | <span data-ttu-id="23827-249">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="23827-249">192.168.2.5</span></span> | <span data-ttu-id="23827-250">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="23827-250">192.168.2.0/24</span></span> | <span data-ttu-id="23827-251">Indonésia</span><span class="sxs-lookup"><span data-stu-id="23827-251">Indonesia</span></span> | <span data-ttu-id="23827-252">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="23827-252">172.16.240.120</span></span> |
| <span data-ttu-id="23827-253">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-253">proxysbc.contoso.com</span></span> | <span data-ttu-id="23827-254">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="23827-254">172.16.240.133</span></span> | <span data-ttu-id="23827-255">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="23827-255">192.168.3.5</span></span> | <span data-ttu-id="23827-256">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="23827-256">192.168.3.0/24</span></span> | <span data-ttu-id="23827-257">Singapura</span><span class="sxs-lookup"><span data-stu-id="23827-257">Singapore</span></span> | <span data-ttu-id="23827-258">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="23827-258">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="23827-259">Chamadas de saída e o usuário está no mesmo local que o SBC com sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="23827-259">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="23827-260">Modo</span><span class="sxs-lookup"><span data-stu-id="23827-260">Mode</span></span> |    <span data-ttu-id="23827-261">Usuário</span><span class="sxs-lookup"><span data-stu-id="23827-261">User</span></span> |  <span data-ttu-id="23827-262">Local</span><span class="sxs-lookup"><span data-stu-id="23827-262">Location</span></span> |  <span data-ttu-id="23827-263">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="23827-263">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="23827-264">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="23827-264">AlwaysBypass</span></span> |    <span data-ttu-id="23827-265">Interno</span><span class="sxs-lookup"><span data-stu-id="23827-265">Internal</span></span> |  <span data-ttu-id="23827-266">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="23827-266">The same site as SBC</span></span> |  <span data-ttu-id="23827-267">Saída</span><span class="sxs-lookup"><span data-stu-id="23827-267">Outbound</span></span> |

<span data-ttu-id="23827-268">A tabela a seguir mostra a ação e a configuração do usuário final:</span><span class="sxs-lookup"><span data-stu-id="23827-268">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="23827-269">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="23827-269">User physical location</span></span>| <span data-ttu-id="23827-270">O usuário faz ou recebe uma chamada de/para um número</span><span class="sxs-lookup"><span data-stu-id="23827-270">User makes or receives a call to/from number</span></span> | <span data-ttu-id="23827-271">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="23827-271">User phone number</span></span>  | <span data-ttu-id="23827-272">Política de roteamento de voz online</span><span class="sxs-lookup"><span data-stu-id="23827-272">Online Voice Routing Policy</span></span> | <span data-ttu-id="23827-273">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="23827-273">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="23827-274">Vietnã</span><span class="sxs-lookup"><span data-stu-id="23827-274">Vietnam</span></span> | <span data-ttu-id="23827-275">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="23827-275">+84 4 3926 3000</span></span> | <span data-ttu-id="23827-276">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="23827-276">+84 4 5555 5555</span></span>   | <span data-ttu-id="23827-277">Prioridade 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-277">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="23827-278">Prioridade 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-278">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="23827-279">VNsbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="23827-279">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="23827-280">proxysbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="23827-280">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="23827-281">O diagrama a seguir mostra a escada SIP para uma chamada de saída com o modo sempre ignorado e o usuário no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="23827-281">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="23827-282">![Diagrama mostrando chamadas de saída](media/direct-routing-media-op-10.png "Chamadas de saída")</span><span class="sxs-lookup"><span data-stu-id="23827-282">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="23827-283">A tabela a seguir mostra os cabeçalhos X-MS enviados pelo roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="23827-283">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="23827-284">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="23827-284">Parameter</span></span> | <span data-ttu-id="23827-285">Explicação</span><span class="sxs-lookup"><span data-stu-id="23827-285">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="23827-286">Convidar + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-286">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="23827-287">O nome de destino do SBC, conforme definido na política de roteamento de voz online, é enviado no URI de solicitação</span><span class="sxs-lookup"><span data-stu-id="23827-287">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="23827-288">X-MS-userlocation: Internal</span><span class="sxs-lookup"><span data-stu-id="23827-288">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="23827-289">O campo indicou que o usuário está localizado dentro da rede corporativa</span><span class="sxs-lookup"><span data-stu-id="23827-289">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="23827-290">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-290">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="23827-291">Especifica qual SBC o cliente deve atravessar para o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="23827-291">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="23827-292">Nesse caso, como sempre ignoramos, e o cliente é interno o nome de destino enviado como o único nome no cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="23827-292">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="23827-293">X-MS-usersite: Vietnã</span><span class="sxs-lookup"><span data-stu-id="23827-293">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="23827-294">O campo indicado no site em que o usuário está localizado.</span><span class="sxs-lookup"><span data-stu-id="23827-294">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="23827-295">As chamadas recebidas e o usuário estão no mesmo local que o SBC com sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="23827-295">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="23827-296">Modo</span><span class="sxs-lookup"><span data-stu-id="23827-296">Mode</span></span> |    <span data-ttu-id="23827-297">Usuário</span><span class="sxs-lookup"><span data-stu-id="23827-297">User</span></span> |  <span data-ttu-id="23827-298">Local</span><span class="sxs-lookup"><span data-stu-id="23827-298">Location</span></span> |  <span data-ttu-id="23827-299">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="23827-299">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="23827-300">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="23827-300">AlwaysBypass</span></span> |    <span data-ttu-id="23827-301">Interno</span><span class="sxs-lookup"><span data-stu-id="23827-301">Internal</span></span> | <span data-ttu-id="23827-302">O mesmo site que o SBC</span><span class="sxs-lookup"><span data-stu-id="23827-302">The same site as SBC</span></span> | <span data-ttu-id="23827-303">Entrada</span><span class="sxs-lookup"><span data-stu-id="23827-303">Inbound</span></span> |


<span data-ttu-id="23827-304">Em uma chamada de entrada, o local do usuário é desconhecido, e o SBC deve adivinhar onde está o usuário.</span><span class="sxs-lookup"><span data-stu-id="23827-304">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="23827-305">Se a estimativa estiver incorreta, será preciso um novo convite.</span><span class="sxs-lookup"><span data-stu-id="23827-305">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="23827-306">Esse caso presume que o usuário seja interno, a mídia pode fluir diretamente e não são necessárias mais ações (convidar novamente).</span><span class="sxs-lookup"><span data-stu-id="23827-306">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="23827-307">O SBC conectado ao serviço de roteamento direto relata o local do SBC de origem fornecendo campos de rota de registro e de contato.</span><span class="sxs-lookup"><span data-stu-id="23827-307">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="23827-308">Com base nesses campos, o caminho de mídia é calculado pelo roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="23827-308">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="23827-309">Observação: Considerando que um usuário pode ter vários pontos de extremidade, o suporte do 183 não é possível.</span><span class="sxs-lookup"><span data-stu-id="23827-309">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="23827-310">O roteamento direto sempre usará o 180 tocando nesse caso.</span><span class="sxs-lookup"><span data-stu-id="23827-310">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="23827-311">O diagrama a seguir mostra a escada em SIP para a chamada de entrada com o modo AlwaysBypass, e o usuário está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="23827-311">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="23827-313">Chamadas de saída e o usuário é externo sempre bypass</span><span class="sxs-lookup"><span data-stu-id="23827-313">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="23827-314">Modo</span><span class="sxs-lookup"><span data-stu-id="23827-314">Mode</span></span> |    <span data-ttu-id="23827-315">Usuário</span><span class="sxs-lookup"><span data-stu-id="23827-315">User</span></span> |  <span data-ttu-id="23827-316">Site</span><span class="sxs-lookup"><span data-stu-id="23827-316">Site</span></span> |  <span data-ttu-id="23827-317">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="23827-317">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="23827-318">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="23827-318">AlwaysBypass</span></span> |  <span data-ttu-id="23827-319">Externo</span><span class="sxs-lookup"><span data-stu-id="23827-319">External</span></span> |  <span data-ttu-id="23827-320">Não disponível</span><span class="sxs-lookup"><span data-stu-id="23827-320">N/A</span></span> | <span data-ttu-id="23827-321">Saída</span><span class="sxs-lookup"><span data-stu-id="23827-321">Outbound</span></span> |


<span data-ttu-id="23827-322">O diagrama a seguir mostra a escada SIP para uma chamada de saída com o modo AlwaysBypass e o usuário é externo:</span><span class="sxs-lookup"><span data-stu-id="23827-322">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="23827-324">A tabela a seguir mostra os cabeçalhos X-MS enviados pelo serviço de roteamento direto:</span><span class="sxs-lookup"><span data-stu-id="23827-324">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="23827-325">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="23827-325">Parameter</span></span> |   <span data-ttu-id="23827-326">Explicação</span><span class="sxs-lookup"><span data-stu-id="23827-326">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="23827-327">Convidar + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-327">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="23827-328">O nome de destino do SBC, conforme definido na política de roteamento de voz online, é enviado no URI de solicitação.</span><span class="sxs-lookup"><span data-stu-id="23827-328">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="23827-329">X-MS-userlocation: External</span><span class="sxs-lookup"><span data-stu-id="23827-329">X-MS-UserLocation: external</span></span> | <span data-ttu-id="23827-330">O campo indicou que o usuário está localizado fora da rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="23827-330">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="23827-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="23827-332">Especifica qual SBC o cliente deve atravessar para o SBC de destino.</span><span class="sxs-lookup"><span data-stu-id="23827-332">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="23827-333">Nesse caso, como sempre ignoramos, e o cliente é externo.</span><span class="sxs-lookup"><span data-stu-id="23827-333">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="23827-334">As chamadas recebidas e o usuário externo sempre ignoram</span><span class="sxs-lookup"><span data-stu-id="23827-334">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="23827-335">Modo</span><span class="sxs-lookup"><span data-stu-id="23827-335">Mode</span></span> | <span data-ttu-id="23827-336">Usuário</span><span class="sxs-lookup"><span data-stu-id="23827-336">User</span></span> | <span data-ttu-id="23827-337">Site</span><span class="sxs-lookup"><span data-stu-id="23827-337">Site</span></span> |  <span data-ttu-id="23827-338">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="23827-338">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="23827-339">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="23827-339">AlwaysBypass</span></span> |  <span data-ttu-id="23827-340">Externo</span><span class="sxs-lookup"><span data-stu-id="23827-340">External</span></span> |  <span data-ttu-id="23827-341">Não disponível</span><span class="sxs-lookup"><span data-stu-id="23827-341">N/A</span></span> |   <span data-ttu-id="23827-342">Entrada</span><span class="sxs-lookup"><span data-stu-id="23827-342">Inbound</span></span> |

<span data-ttu-id="23827-343">Para uma chamada de entrada, o SBC conectado ao roteamento direto precisa enviar um novo convite (por padrão, os candidatos à mídia local são sempre oferecidos) se a localização do usuário for externa.</span><span class="sxs-lookup"><span data-stu-id="23827-343">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="23827-344">O X-MediaPath é calculado com base em rota de registro e o usuário SBC especificado.</span><span class="sxs-lookup"><span data-stu-id="23827-344">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="23827-345">O diagrama a seguir mostra a escada SIP para uma chamada de entrada com o modo AlwaysBypass e o usuário é externo.</span><span class="sxs-lookup"><span data-stu-id="23827-345">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="23827-347">Somente para o modo usuários locais</span><span class="sxs-lookup"><span data-stu-id="23827-347">Only for local users mode</span></span>

<span data-ttu-id="23827-348">Os candidatos à mídia local do SBC de destino serão oferecidos apenas se um usuário estiver no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="23827-348">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="23827-349">Em todos os outros casos, a mídia fluirá por um IP interno ou externo do SBC do proxy.</span><span class="sxs-lookup"><span data-stu-id="23827-349">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="23827-350">Os seguintes cenários são descritos:</span><span class="sxs-lookup"><span data-stu-id="23827-350">The following scenarios are described:</span></span>

- [<span data-ttu-id="23827-351">Chamadas de saída e o usuário está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="23827-351">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="23827-352">As chamadas recebidas e o usuário estão no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="23827-352">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="23827-353">O usuário não está no mesmo local do SBC, mas está na rede corporativa</span><span class="sxs-lookup"><span data-stu-id="23827-353">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="23827-354">Chamadas recebidas e o usuário é interno, mas não está no mesmo local que o SBC</span><span class="sxs-lookup"><span data-stu-id="23827-354">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="23827-355">A tabela a seguir mostra a ação e a configuração do usuário final:</span><span class="sxs-lookup"><span data-stu-id="23827-355">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="23827-356">Localização física do usuário</span><span class="sxs-lookup"><span data-stu-id="23827-356">User physical location</span></span> |  <span data-ttu-id="23827-357">O usuário faz ou recebe uma chamada de/para um número</span><span class="sxs-lookup"><span data-stu-id="23827-357">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="23827-358">Número de telefone do usuário</span><span class="sxs-lookup"><span data-stu-id="23827-358">User phone number</span></span> | <span data-ttu-id="23827-359">Política de roteamento de voz online</span><span class="sxs-lookup"><span data-stu-id="23827-359">Online Voice Routing Policy</span></span> |   <span data-ttu-id="23827-360">Modo configurado para SBC</span><span class="sxs-lookup"><span data-stu-id="23827-360">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="23827-361">Vietnã</span><span class="sxs-lookup"><span data-stu-id="23827-361">Vietnam</span></span> | <span data-ttu-id="23827-362">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="23827-362">+84 4 3926  3000</span></span> |  <span data-ttu-id="23827-363">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="23827-363">+84 4 5555 5555</span></span> | <span data-ttu-id="23827-364">Prioridade 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-364">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="23827-365">Prioridade 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23827-365">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="23827-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – sempre ignorar</span><span class="sxs-lookup"><span data-stu-id="23827-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="23827-367">Chamadas de saída e o usuário está no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="23827-367">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="23827-368">Modo</span><span class="sxs-lookup"><span data-stu-id="23827-368">Mode</span></span> | <span data-ttu-id="23827-369">Usuário</span><span class="sxs-lookup"><span data-stu-id="23827-369">User</span></span> | <span data-ttu-id="23827-370">Site</span><span class="sxs-lookup"><span data-stu-id="23827-370">Site</span></span> | <span data-ttu-id="23827-371">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="23827-371">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="23827-372">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="23827-372">OnlyForLocalUsers</span></span> |   <span data-ttu-id="23827-373">Interno</span><span class="sxs-lookup"><span data-stu-id="23827-373">Internal</span></span> |<span data-ttu-id="23827-374">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="23827-374">Same as SBC</span></span>   | <span data-ttu-id="23827-375">Saída</span><span class="sxs-lookup"><span data-stu-id="23827-375">Outbound</span></span> |

<span data-ttu-id="23827-376">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers, e o usuário está no mesmo local que o SBC.</span><span class="sxs-lookup"><span data-stu-id="23827-376">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="23827-377">Esse é o mesmo fluxo mostrado em [chamadas de saída quando o usuário está no mesmo local do SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="23827-377">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="23827-379">As chamadas recebidas e o usuário estão no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="23827-379">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="23827-380">Modo</span><span class="sxs-lookup"><span data-stu-id="23827-380">Mode</span></span> | <span data-ttu-id="23827-381">Usuário</span><span class="sxs-lookup"><span data-stu-id="23827-381">User</span></span> | <span data-ttu-id="23827-382">Site</span><span class="sxs-lookup"><span data-stu-id="23827-382">Site</span></span> | <span data-ttu-id="23827-383">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="23827-383">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="23827-384">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="23827-384">OnlyForLocalUsers</span></span> |   <span data-ttu-id="23827-385">Interno</span><span class="sxs-lookup"><span data-stu-id="23827-385">Internal</span></span> | <span data-ttu-id="23827-386">Mesmo que SBC</span><span class="sxs-lookup"><span data-stu-id="23827-386">Same as SBC</span></span> | <span data-ttu-id="23827-387">Entrada</span><span class="sxs-lookup"><span data-stu-id="23827-387">Inbound</span></span> |

<span data-ttu-id="23827-388">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers, e o usuário está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="23827-388">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="23827-389">Esse é o mesmo fluxo mostrado em [chamadas de entrada quando o usuário está no mesmo local do SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="23827-389">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="23827-391">O usuário não está no mesmo local do SBC, mas está na rede corporativa somente com usuários locais</span><span class="sxs-lookup"><span data-stu-id="23827-391">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="23827-392">Modo</span><span class="sxs-lookup"><span data-stu-id="23827-392">Mode</span></span> | <span data-ttu-id="23827-393">Usuário</span><span class="sxs-lookup"><span data-stu-id="23827-393">User</span></span> | <span data-ttu-id="23827-394">Site</span><span class="sxs-lookup"><span data-stu-id="23827-394">Site</span></span> |<span data-ttu-id="23827-395">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="23827-395">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="23827-396">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="23827-396">OnlyForLocalUsers</span></span>  | <span data-ttu-id="23827-397">Interno</span><span class="sxs-lookup"><span data-stu-id="23827-397">Internal</span></span> |   <span data-ttu-id="23827-398">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="23827-398">Different from SBC</span></span> | <span data-ttu-id="23827-399">Saída</span><span class="sxs-lookup"><span data-stu-id="23827-399">Outbound</span></span> |

<span data-ttu-id="23827-400">O roteamento direto calcula o X-MediaPath com base na localização informada do usuário e do modo configurado no SBC.</span><span class="sxs-lookup"><span data-stu-id="23827-400">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="23827-401">O diagrama a seguir mostra uma chamada de saída com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="23827-401">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="23827-403">A chamada de entrada e o usuário são internas, mas não estão no mesmo local que o SBC somente para usuários locais</span><span class="sxs-lookup"><span data-stu-id="23827-403">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="23827-404">Modo</span><span class="sxs-lookup"><span data-stu-id="23827-404">Mode</span></span> |    <span data-ttu-id="23827-405">Usuário</span><span class="sxs-lookup"><span data-stu-id="23827-405">User</span></span> |  <span data-ttu-id="23827-406">Site</span><span class="sxs-lookup"><span data-stu-id="23827-406">Site</span></span> |  <span data-ttu-id="23827-407">Direção da chamada</span><span class="sxs-lookup"><span data-stu-id="23827-407">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="23827-408">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="23827-408">OnlyForLocalUsers</span></span> | <span data-ttu-id="23827-409">Interno</span><span class="sxs-lookup"><span data-stu-id="23827-409">Internal</span></span> |    <span data-ttu-id="23827-410">Diferente do SBC</span><span class="sxs-lookup"><span data-stu-id="23827-410">Different from SBC</span></span> |    <span data-ttu-id="23827-411">Entrada</span><span class="sxs-lookup"><span data-stu-id="23827-411">Inbound</span></span> |

<span data-ttu-id="23827-412">O diagrama a seguir mostra uma chamada de entrada com o modo OnlyForLocalUsers e um usuário interno que não está no mesmo local do SBC.</span><span class="sxs-lookup"><span data-stu-id="23827-412">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagrama mostrando a escada SIP](media/direct-routing-media-op-17.png)









