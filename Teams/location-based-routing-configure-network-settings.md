---
title: Configurar definições de rede para o Roteamento baseado na localização
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como criar e configurar regiões de rede, sites e sub-redes para roteamento baseado em local para roteamento direto.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245101"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="bc03f-103">Configurar definições de rede para o Roteamento baseado na localização</span><span class="sxs-lookup"><span data-stu-id="bc03f-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="bc03f-104">Se ainda não tiver feito isso, leia [roteamento baseado em local de plano para roteamento direto](location-based-routing-plan.md) para revisar outras etapas que você precisará tomar antes de definir as configurações de rede para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="bc03f-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="bc03f-105">Este artigo descreve como definir as configurações de rede para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="bc03f-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="bc03f-106">Depois de implantar o roteamento direto do sistema telefônico em sua organização, as próximas etapas são criar e configurar regiões de rede, sites de rede e sub-redes de rede.</span><span class="sxs-lookup"><span data-stu-id="bc03f-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="bc03f-107">Para concluir as etapas deste artigo, você precisará de familiaridade com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc03f-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="bc03f-108">Para saber mais, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc03f-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="bc03f-109">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="bc03f-109">Define network regions</span></span>
 <span data-ttu-id="bc03f-110">Uma região de rede interconecta várias partes de uma rede em várias áreas geográficas.</span><span class="sxs-lookup"><span data-stu-id="bc03f-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="bc03f-111">Use o cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) para definir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="bc03f-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="bc03f-112">Observe que o parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições e o parâmetro &lt;de ID&gt; de site do CentralSite é opcional.</span><span class="sxs-lookup"><span data-stu-id="bc03f-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="bc03f-113">Neste exemplo, criamos uma região de rede chamada Índia.</span><span class="sxs-lookup"><span data-stu-id="bc03f-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="bc03f-114">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="bc03f-114">Define network sites</span></span>

<span data-ttu-id="bc03f-115">Use o cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="bc03f-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="bc03f-116">Neste exemplo, criamos dois novos sites de rede, Delhi e Hyderabad, na região da Índia.</span><span class="sxs-lookup"><span data-stu-id="bc03f-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="bc03f-117">A tabela a seguir mostra os sites de rede definidos neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="bc03f-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="bc03f-118">Site 1</span><span class="sxs-lookup"><span data-stu-id="bc03f-118">Site 1</span></span> |<span data-ttu-id="bc03f-119">Site 2</span><span class="sxs-lookup"><span data-stu-id="bc03f-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="bc03f-120">ID do site</span><span class="sxs-lookup"><span data-stu-id="bc03f-120">Site ID</span></span>    |    <span data-ttu-id="bc03f-121">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="bc03f-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="bc03f-122">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="bc03f-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="bc03f-123">ID da região</span><span class="sxs-lookup"><span data-stu-id="bc03f-123">Region ID</span></span>  |     <span data-ttu-id="bc03f-124">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="bc03f-124">Region 1 (India)</span></span>    |   <span data-ttu-id="bc03f-125">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="bc03f-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="bc03f-126">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="bc03f-126">Define network subnets</span></span>

<span data-ttu-id="bc03f-127">Use o cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir sub-redes de rede e associá-las a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="bc03f-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="bc03f-128">Cada sub-rede interna só pode ser associada a um site.</span><span class="sxs-lookup"><span data-stu-id="bc03f-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="bc03f-129">Neste exemplo, criamos uma associação entre a sub-rede 192.168.0.0 e o site de rede de Délhi e entre a sub-rede 2001:4898: E8:25:844e: 926f: 85ad: dd8e e o site de rede do Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="bc03f-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="bc03f-130">A tabela a seguir mostra as sub-redes definidas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="bc03f-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="bc03f-131">Site 1</span><span class="sxs-lookup"><span data-stu-id="bc03f-131">Site 1</span></span> |<span data-ttu-id="bc03f-132">Site 2</span><span class="sxs-lookup"><span data-stu-id="bc03f-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="bc03f-133">ID de sub-rede</span><span class="sxs-lookup"><span data-stu-id="bc03f-133">Subnet ID</span></span>   |    <span data-ttu-id="bc03f-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="bc03f-134">192.168.0.0</span></span>     |  <span data-ttu-id="bc03f-135">2001:4898: E8:25:844e: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="bc03f-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="bc03f-136">Remoção</span><span class="sxs-lookup"><span data-stu-id="bc03f-136">Mask</span></span>  |     <span data-ttu-id="bc03f-137">24</span><span class="sxs-lookup"><span data-stu-id="bc03f-137">24</span></span>    |   <span data-ttu-id="bc03f-138">120</span><span class="sxs-lookup"><span data-stu-id="bc03f-138">120</span></span>      |
|<span data-ttu-id="bc03f-139">ID do site</span><span class="sxs-lookup"><span data-stu-id="bc03f-139">Site ID</span></span>  | <span data-ttu-id="bc03f-140">Site (Delhi)</span><span class="sxs-lookup"><span data-stu-id="bc03f-140">Site (Delhi)</span></span> | <span data-ttu-id="bc03f-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="bc03f-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="bc03f-142">Para várias sub-redes, você pode importar um arquivo CSV usando um script como o seguinte.</span><span class="sxs-lookup"><span data-stu-id="bc03f-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="bc03f-143">Neste exemplo, o arquivo CSV tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="bc03f-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="bc03f-144">Definir sub-redes externas</span><span class="sxs-lookup"><span data-stu-id="bc03f-144">Define external subnets</span></span>
<span data-ttu-id="bc03f-145">Use o cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir sub-redes externas e atribuí-las ao locatário.</span><span class="sxs-lookup"><span data-stu-id="bc03f-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="bc03f-146">Você pode definir um número ilimitado de sub-redes para um locatário.</span><span class="sxs-lookup"><span data-stu-id="bc03f-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="bc03f-147">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bc03f-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="bc03f-148">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bc03f-148">Next steps</span></span>
<span data-ttu-id="bc03f-149">Vá para [habilitar o roteamento baseado em local para roteamento direto](location-based-routing-enable.md).</span><span class="sxs-lookup"><span data-stu-id="bc03f-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="bc03f-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bc03f-150">Related topics</span></span>
- [<span data-ttu-id="bc03f-151">Planejar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="bc03f-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="bc03f-152">Terminologia do Roteamento baseado na localização</span><span class="sxs-lookup"><span data-stu-id="bc03f-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
