---
title: Configurar definições de rede para o Roteamento baseado na localização
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para roteamento baseado no local para roteamento direto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 60af1c90cd1dbd7855da7686950ffd135d1da5dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222359"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="5fbc5-103">Configurar definições de rede para o Roteamento baseado na localização</span><span class="sxs-lookup"><span data-stu-id="5fbc5-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="5fbc5-104">Se você ainda não tiver feito isso, leia [Plan_Location-Based roteamento para roteamento direto](location-based-routing-plan.md) para revisar outras etapas que você precisará levar antes de configurar as definições de rede para roteamento baseado no local.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="5fbc5-105">Este artigo descreve como definir as configurações de rede para roteamento baseado no local.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="5fbc5-106">Depois de implantar roteamento direto de sistema do telefone na sua organização, as próximas etapas são para criar e configurar as regiões de rede, sites de rede e sub-redes da rede.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="5fbc5-107">Para concluir as etapas neste artigo, você precisará de familiaridade com os cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="5fbc5-108">Para saber mais, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="5fbc5-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="5fbc5-109">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="5fbc5-109">Define network regions</span></span>
 <span data-ttu-id="5fbc5-110">Uma região de rede interconexão várias partes de uma rede de várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="5fbc5-111">Use o cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) para definir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="5fbc5-112">Observe que o parâmetro RegionID é um nome lógico que representa a geografia da região tem nenhuma dependência ou restrições e o CentralSite &lt;ID de site&gt; parâmetro é opcional.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="5fbc5-113">Neste exemplo, criamos uma região de rede denominada Índia.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="5fbc5-114">Definir os sites de rede</span><span class="sxs-lookup"><span data-stu-id="5fbc5-114">Define network sites</span></span>

<span data-ttu-id="5fbc5-115">Use o cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir locais de rede.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="5fbc5-116">Neste exemplo, criamos dois novos sites de rede, Délhi e Hyderabad, na região Índia.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="5fbc5-117">A tabela a seguir mostra os sites de rede definidos neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="5fbc5-118">Site 1</span><span class="sxs-lookup"><span data-stu-id="5fbc5-118">Site 1</span></span> |<span data-ttu-id="5fbc5-119">Site 2</span><span class="sxs-lookup"><span data-stu-id="5fbc5-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5fbc5-120">ID do site</span><span class="sxs-lookup"><span data-stu-id="5fbc5-120">Site ID</span></span>    |    <span data-ttu-id="5fbc5-121">1 (Délhi) do site</span><span class="sxs-lookup"><span data-stu-id="5fbc5-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="5fbc5-122">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5fbc5-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="5fbc5-123">ID de região</span><span class="sxs-lookup"><span data-stu-id="5fbc5-123">Region ID</span></span>  |     <span data-ttu-id="5fbc5-124">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="5fbc5-124">Region 1 (India)</span></span>    |   <span data-ttu-id="5fbc5-125">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="5fbc5-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="5fbc5-126">Definir subredes</span><span class="sxs-lookup"><span data-stu-id="5fbc5-126">Define network subnets</span></span>

<span data-ttu-id="5fbc5-127">Use o cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir as sub-redes da rede e associá-los aos sites de rede.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="5fbc5-128">Cada sub-rede interna só pode ser associado um site.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="5fbc5-129">Neste exemplo, criamos uma associação entre a sub-rede 192.168.0.0 e o site de rede Délhi e entre sub-rede 192.168.1.0 e o site de rede de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 192.168.1.0 and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="5fbc5-130">A tabela a seguir mostra as sub-redes definidas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="5fbc5-131">Site 1</span><span class="sxs-lookup"><span data-stu-id="5fbc5-131">Site 1</span></span> |<span data-ttu-id="5fbc5-132">Site 2</span><span class="sxs-lookup"><span data-stu-id="5fbc5-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5fbc5-133">ID de sub-rede</span><span class="sxs-lookup"><span data-stu-id="5fbc5-133">Subnet ID</span></span>   |    <span data-ttu-id="5fbc5-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="5fbc5-134">192.168.0.0</span></span>     |  <span data-ttu-id="5fbc5-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="5fbc5-135">192.168.1.0</span></span>     |
|<span data-ttu-id="5fbc5-136">Máscara</span><span class="sxs-lookup"><span data-stu-id="5fbc5-136">Mask</span></span>  |     <span data-ttu-id="5fbc5-137">24</span><span class="sxs-lookup"><span data-stu-id="5fbc5-137">24</span></span>    |   <span data-ttu-id="5fbc5-138">24</span><span class="sxs-lookup"><span data-stu-id="5fbc5-138">24</span></span>      |
|<span data-ttu-id="5fbc5-139">ID do site</span><span class="sxs-lookup"><span data-stu-id="5fbc5-139">Site ID</span></span>  | <span data-ttu-id="5fbc5-140">Site (Délhi)</span><span class="sxs-lookup"><span data-stu-id="5fbc5-140">Site (Delhi)</span></span> | <span data-ttu-id="5fbc5-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5fbc5-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="5fbc5-142">Para várias sub-redes, você pode importar um arquivo CSV usando um script como o seguinte.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="5fbc5-143">Neste exemplo, o arquivo CSV é parecido com isto:</span><span class="sxs-lookup"><span data-stu-id="5fbc5-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="5fbc5-144">Definir as sub-redes externas</span><span class="sxs-lookup"><span data-stu-id="5fbc5-144">Define external subnets</span></span>
<span data-ttu-id="5fbc5-145">Use o cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir as sub-redes externas e atribuí-las ao inquilino.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="5fbc5-146">Você pode definir um número ilimitado de sub-redes para um inquilino.</span><span class="sxs-lookup"><span data-stu-id="5fbc5-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="5fbc5-147">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5fbc5-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 167.220.2.206 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="5fbc5-148">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5fbc5-148">Next steps</span></span>
<span data-ttu-id="5fbc5-149">Vá para [Habilitar o roteamento baseado no local para roteamento direto](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="5fbc5-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="5fbc5-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5fbc5-150">Related topics</span></span>
- [<span data-ttu-id="5fbc5-151">Planejar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="5fbc5-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="5fbc5-152">Terminologia do Roteamento baseado na localização</span><span class="sxs-lookup"><span data-stu-id="5fbc5-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
