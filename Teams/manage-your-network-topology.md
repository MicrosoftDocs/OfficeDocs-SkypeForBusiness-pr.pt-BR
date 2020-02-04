---
title: Gerenciar a topologia de rede para recursos de voz na nuvem no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como definir configurações de rede para recursos de voz na nuvem no Microsoft Teams.
ms.openlocfilehash: d7ed6780edf578c15580f1f9690fcbf5d9e9658e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708497"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="b9a19-103">Gerenciar a topologia de rede para recursos de voz na nuvem no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9a19-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="b9a19-104">Se a sua organização estiver implantando o [roteamento baseado em localização para roteamento direto](location-based-routing-plan.md) ou [chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md), você deve definir as configurações de rede para usar com esses recursos de voz na nuvem no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9a19-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="b9a19-105">As configurações de rede são usadas para determinar a localização de um cliente de equipes e incluir regiões de rede, sites de rede, sub-redes e endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="b9a19-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="b9a19-106">Dependendo do recurso de voz em nuvem e do recurso que você está implantando, você define algumas ou todas essas configurações.</span><span class="sxs-lookup"><span data-stu-id="b9a19-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="b9a19-107">Para saber mais sobre esses termos, confira [configurações de rede para recursos de voz na nuvem](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b9a19-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="b9a19-108">Você define as configurações de rede na página **topologia de rede** do centro de administração do Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9a19-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b9a19-109">Definir configurações de rede no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9a19-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="b9a19-110">Você define regiões de rede, sites de rede e sub-redes na guia **sites de rede** da página de **topologia de rede** .</span><span class="sxs-lookup"><span data-stu-id="b9a19-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="b9a19-111">Aqui, você pode criar ou modificar um site de rede, associar um site com uma região de rede, associar uma sub-rede ao site, ativar o roteamento baseado em localização e atribuir políticas de emergência ao site.</span><span class="sxs-lookup"><span data-stu-id="b9a19-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="b9a19-112">Você também pode adicionar regiões de rede que podem ser usadas globalmente para todos os sites.</span><span class="sxs-lookup"><span data-stu-id="b9a19-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="b9a19-113">Adicionar e configurar um site de rede</span><span class="sxs-lookup"><span data-stu-id="b9a19-113">Add and configure a network site</span></span>

1. <span data-ttu-id="b9a19-114">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **locais** > de**topologia de rede**e clique na guia sites de **rede** .</span><span class="sxs-lookup"><span data-stu-id="b9a19-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="b9a19-115">Clique em **novo**e insira um nome e uma descrição para o site.</span><span class="sxs-lookup"><span data-stu-id="b9a19-115">Click **New**, and then enter a name and description for the site.</span></span>

    ![Captura de tela da página Adicionar site de rede](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="b9a19-117">Para associar o site a uma região de rede, clique em **vincular região de rede**, selecione uma região existente ou clique em **Adicionar** para adicionar uma região e, em seguida, clique em **vincular**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-117">To associate the site with a network region, click **Link network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="b9a19-118">Para habilitar o roteamento baseado em local para o site, ative o **roteamento baseado em localização**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="b9a19-119">Para atribuir políticas de serviços de emergência ao site, siga um destes procedimentos ou ambos:</span><span class="sxs-lookup"><span data-stu-id="b9a19-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="b9a19-120">Se a sua organização usar planos de chamadas ou roteamento direto do sistema telefônico implantado, em **política de chamadas de emergência**, selecione a política desejada.</span><span class="sxs-lookup"><span data-stu-id="b9a19-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="b9a19-121">Se sua organização implantou o roteamento direto do sistema telefônico, em **política de roteamento de chamadas de emergência**, selecione a política desejada.</span><span class="sxs-lookup"><span data-stu-id="b9a19-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="b9a19-122">Para associar uma sub-rede ao site, em **sub-redes**, clique em **Adicionar sub-redes**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="b9a19-123">Especifique a versão IP, o endereço IP, o intervalo de rede, adicione uma descrição e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="b9a19-124">Cada sub-rede deve estar associada a um site específico.</span><span class="sxs-lookup"><span data-stu-id="b9a19-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="b9a19-125">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="b9a19-126">Modificar um site de rede</span><span class="sxs-lookup"><span data-stu-id="b9a19-126">Modify a network site</span></span>

1. <span data-ttu-id="b9a19-127">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **locais** > de**topologia de rede**e clique na guia sites de **rede** .</span><span class="sxs-lookup"><span data-stu-id="b9a19-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="b9a19-128">Selecione o site clicando à esquerda do nome do site e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b9a19-129">Faça as alterações desejadas e clique em **salvar.**</span><span class="sxs-lookup"><span data-stu-id="b9a19-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="b9a19-130">Gerenciar endereços IP externos confiáveis</span><span class="sxs-lookup"><span data-stu-id="b9a19-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="b9a19-131">Você gerencia endereços IP externos confiáveis na guia **IPs confiáveis** , na página **topologia de rede** do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9a19-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="b9a19-132">Você pode adicionar um número ilimitado de endereços IP confiáveis externos.</span><span class="sxs-lookup"><span data-stu-id="b9a19-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="b9a19-133">Adicionar um endereço IP confiável</span><span class="sxs-lookup"><span data-stu-id="b9a19-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="b9a19-134">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **locais** > de**topologia de rede**e clique na guia **IPs confiáveis** .</span><span class="sxs-lookup"><span data-stu-id="b9a19-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="b9a19-135">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-135">Click **New**.</span></span>
3. <span data-ttu-id="b9a19-136">No painel **Adicionar endereço IP confiável** , especifique a versão IP, o endereço IP, o intervalo de rede, adicione uma descrição e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Captura de tela do painel Adicionar endereço IP confiável](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="b9a19-138">Editar um endereço IP confiável</span><span class="sxs-lookup"><span data-stu-id="b9a19-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="b9a19-139">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **locais** > de**topologia de rede**e clique na guia **IPs confiáveis** .</span><span class="sxs-lookup"><span data-stu-id="b9a19-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="b9a19-140">Selecione o endereço IP clicando à esquerda dele e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="b9a19-141">No painel **Editar endereço IP confiável** , faça as alterações desejadas e, em seguida, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="b9a19-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="b9a19-142">Definir configurações de rede usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9a19-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="b9a19-143">Para concluir as etapas desta seção, você precisará de familiaridade com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9a19-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b9a19-144">Para saber mais, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b9a19-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="b9a19-145">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="b9a19-145">Define network regions</span></span>

 <span data-ttu-id="b9a19-146">Use o cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) para definir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="b9a19-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="b9a19-147">Observe que o parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições e o parâmetro &lt;de ID&gt; de site do CentralSite é opcional.</span><span class="sxs-lookup"><span data-stu-id="b9a19-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="b9a19-148">Neste exemplo, criamos uma região de rede chamada Índia.</span><span class="sxs-lookup"><span data-stu-id="b9a19-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="b9a19-149">Consulte também [set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span><span class="sxs-lookup"><span data-stu-id="b9a19-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="b9a19-150">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="b9a19-150">Define network sites</span></span>

<span data-ttu-id="b9a19-151">Use o cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="b9a19-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="b9a19-152">Cada site de rede deve estar associado a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="b9a19-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="b9a19-153">Neste exemplo, criamos dois novos sites de rede, Delhi e Hyderabad, na região da Índia.</span><span class="sxs-lookup"><span data-stu-id="b9a19-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>
```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```
<span data-ttu-id="b9a19-154">A tabela a seguir mostra os sites de rede definidos neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="b9a19-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="b9a19-155">Site 1</span><span class="sxs-lookup"><span data-stu-id="b9a19-155">Site 1</span></span> |<span data-ttu-id="b9a19-156">Site 2</span><span class="sxs-lookup"><span data-stu-id="b9a19-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b9a19-157">ID do site</span><span class="sxs-lookup"><span data-stu-id="b9a19-157">Site ID</span></span>    |    <span data-ttu-id="b9a19-158">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b9a19-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="b9a19-159">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b9a19-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="b9a19-160">ID da região</span><span class="sxs-lookup"><span data-stu-id="b9a19-160">Region ID</span></span>  |     <span data-ttu-id="b9a19-161">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="b9a19-161">Region 1 (India)</span></span>    |   <span data-ttu-id="b9a19-162">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="b9a19-162">Region 1 (India)</span></span>      |

<span data-ttu-id="b9a19-163">Consulte também [set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span><span class="sxs-lookup"><span data-stu-id="b9a19-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="b9a19-164">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="b9a19-164">Define network subnets</span></span>

<span data-ttu-id="b9a19-165">Use o cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir sub-redes de rede e associá-las a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="b9a19-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="b9a19-166">Cada sub-rede de rede só pode ser associada a um site.</span><span class="sxs-lookup"><span data-stu-id="b9a19-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="b9a19-167">Neste exemplo, criamos uma associação entre a sub-rede 192.168.0.0 e o site de rede de Délhi e entre a sub-rede 2001:4898: E8:25:844e: 926f: 85ad: dd8e e o site de rede do Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="b9a19-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"

```
<span data-ttu-id="b9a19-168">A tabela a seguir mostra as sub-redes definidas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="b9a19-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="b9a19-169">Site 1</span><span class="sxs-lookup"><span data-stu-id="b9a19-169">Site 1</span></span> |<span data-ttu-id="b9a19-170">Site 2</span><span class="sxs-lookup"><span data-stu-id="b9a19-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b9a19-171">ID de sub-rede</span><span class="sxs-lookup"><span data-stu-id="b9a19-171">Subnet ID</span></span>   |    <span data-ttu-id="b9a19-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="b9a19-172">192.168.0.0</span></span>     |  <span data-ttu-id="b9a19-173">2001:4898: E8:25:844e: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="b9a19-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="b9a19-174">Remoção</span><span class="sxs-lookup"><span data-stu-id="b9a19-174">Mask</span></span>  |     <span data-ttu-id="b9a19-175">24</span><span class="sxs-lookup"><span data-stu-id="b9a19-175">24</span></span>    |   <span data-ttu-id="b9a19-176">120</span><span class="sxs-lookup"><span data-stu-id="b9a19-176">120</span></span>      |
|<span data-ttu-id="b9a19-177">ID do site</span><span class="sxs-lookup"><span data-stu-id="b9a19-177">Site ID</span></span>  | <span data-ttu-id="b9a19-178">Site (Delhi)</span><span class="sxs-lookup"><span data-stu-id="b9a19-178">Site (Delhi)</span></span> | <span data-ttu-id="b9a19-179">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b9a19-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="b9a19-180">Para várias sub-redes, você pode importar um arquivo CSV usando um script como o seguinte.</span><span class="sxs-lookup"><span data-stu-id="b9a19-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="b9a19-181">Neste exemplo, o arquivo CSV tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="b9a19-181">In this example, the CSV file looks something like this:</span></span>
```output
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="b9a19-182">Consulte também [set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span><span class="sxs-lookup"><span data-stu-id="b9a19-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="b9a19-183">Definir sub-redes externas (endereços IP externos confiáveis)</span><span class="sxs-lookup"><span data-stu-id="b9a19-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="b9a19-184">Use o cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir sub-redes externas e atribuí-las ao locatário.</span><span class="sxs-lookup"><span data-stu-id="b9a19-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="b9a19-185">Você pode definir um número ilimitado de sub-redes externas para um locatário.</span><span class="sxs-lookup"><span data-stu-id="b9a19-185">You can define an unlimited number of external subnets for a tenant.</span></span>
```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="b9a19-186">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b9a19-186">For example:</span></span>
```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="b9a19-187">Consulte também [set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span><span class="sxs-lookup"><span data-stu-id="b9a19-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9a19-188">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b9a19-188">Related topics</span></span>

- [<span data-ttu-id="b9a19-189">Configurações de rede para recursos de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="b9a19-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
