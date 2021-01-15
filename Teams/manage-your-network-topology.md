---
title: Gerenciar sua topologia de rede para recursos de voz na nuvem no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como definir configurações de rede para recursos de voz na nuvem no Microsoft Teams.
ms.openlocfilehash: 7d8bc7f06934134538fca59a3f19285d97756e2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802571"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="9c5fc-103">Gerenciar sua topologia de rede para recursos de voz na nuvem no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9c5fc-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="9c5fc-104">Se sua organização [](location-based-routing-plan.md) estiver implantando o Roteamento Baseado em Local para Roteamento Direto ou chamadas de emergência [dinâmicas,](configure-dynamic-emergency-calling.md)você deverá definir as configurações de rede para uso com esses recursos de voz na nuvem no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="9c5fc-105">As configurações de rede são usadas para determinar o local de um cliente do Teams e incluem regiões de rede, sites de rede, sub-redes e endereços IP confiáveis.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="9c5fc-106">Dependendo do recurso de voz na nuvem e da funcionalidade que você está implantando, você define algumas ou todas essas configurações.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="9c5fc-107">Para saber mais sobre esses termos, consulte [Configurações de rede para recursos de voz na nuvem.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="9c5fc-108">Você define as configurações de rede na página **de topologia** de rede do centro de administração do Microsoft Teams ou usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="9c5fc-109">Definir configurações de rede no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9c5fc-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="9c5fc-110">Você define regiões de rede, sites de rede e sub-redes na guia **Sites** de rede da **página Topologia de** rede.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="9c5fc-111">Aqui, você pode criar ou modificar um site de rede, associar um site a uma região de rede, associar uma sub-rede ao site, ativar o Roteamento baseado em Local e atribuir políticas de emergência ao site.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="9c5fc-112">Você também pode adicionar regiões de rede que podem ser usadas globalmente para todos os sites.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="9c5fc-113">Adicionar e configurar um site de rede</span><span class="sxs-lookup"><span data-stu-id="9c5fc-113">Add and configure a network site</span></span>

1. <span data-ttu-id="9c5fc-114">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para topologia de Rede de Locais e clique na guia  >   **Sites de** rede.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="9c5fc-115">Clique **em** Adicionar e insira um nome e uma descrição para o site.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![Captura de tela da página Adicionar site de rede](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="9c5fc-117">Para associar o site a uma região de rede, clique em Adicionar região de **rede,** selecione uma região existente ou clique em **Adicionar** para adicionar uma região e clique em **Link.**</span><span class="sxs-lookup"><span data-stu-id="9c5fc-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="9c5fc-118">Para habilitar Location-Based roteamento para o site, ative o **roteamento baseado em local.**</span><span class="sxs-lookup"><span data-stu-id="9c5fc-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="9c5fc-119">Para atribuir políticas de serviços de emergência ao site, faça uma ou ambas as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="9c5fc-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="9c5fc-120">Se sua organização usa Planos de Chamadas ou Roteamento Direto do Sistema de Telefonia implantado, em Política de Chamada de **Emergência,** selecione a política que você deseja.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="9c5fc-121">Se sua organização implantou o Roteamento Direto do Sistema de Telefonia, em **Política** de Roteamento de Chamadas de Emergência, selecione a política que você deseja.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="9c5fc-122">Para associar uma sub-rede ao site, em **Sub-redes,** clique em **Adicionar sub-redes.**</span><span class="sxs-lookup"><span data-stu-id="9c5fc-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="9c5fc-123">Especifique a versão IP, o endereço IP, o intervalo de rede, adicione uma descrição e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="9c5fc-124">Cada sub-rede deve ser associada a um site específico.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="9c5fc-125">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="9c5fc-126">Modificar um site de rede</span><span class="sxs-lookup"><span data-stu-id="9c5fc-126">Modify a network site</span></span>

1. <span data-ttu-id="9c5fc-127">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para topologia de Rede de Locais e clique na guia  >   **Sites de** rede.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="9c5fc-128">Selecione o site clicando à esquerda do nome do site e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="9c5fc-129">Faça as alterações que você deseja e clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="9c5fc-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="9c5fc-130">Gerenciar endereços IP confiáveis externos</span><span class="sxs-lookup"><span data-stu-id="9c5fc-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="9c5fc-131">Você gerencia endereços IP confiáveis externos na guia **IPs Confiáveis** na **página Topologia** de rede do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="9c5fc-132">Você pode adicionar um número ilimitado de endereços IP confiáveis externos.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="9c5fc-133">Adicionar um endereço IP confiável</span><span class="sxs-lookup"><span data-stu-id="9c5fc-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="9c5fc-134">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a topologia de Rede de Locais e clique na guia  >   **IPs Confiáveis.**</span><span class="sxs-lookup"><span data-stu-id="9c5fc-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="9c5fc-135">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-135">Click **New**.</span></span>
3. <span data-ttu-id="9c5fc-136">No painel **Adicionar endereço IP** confiável, especifique a versão IP, o endereço IP, o intervalo de rede, adicione uma descrição e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![Captura de tela do painel Adicionar endereço IP confiável](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="9c5fc-138">Editar um endereço IP confiável</span><span class="sxs-lookup"><span data-stu-id="9c5fc-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="9c5fc-139">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para a topologia de Rede de Locais e clique na guia  >   **IPs Confiáveis.**</span><span class="sxs-lookup"><span data-stu-id="9c5fc-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="9c5fc-140">Selecione o endereço IP clicando à esquerda dele e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="9c5fc-141">No painel **Editar endereço IP** confiável, faça as alterações que deseja e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="9c5fc-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="9c5fc-142">Definir configurações de rede usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9c5fc-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="9c5fc-143">Para concluir as etapas desta seção, você precisará de alguma familiaridade com os cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="9c5fc-144">Para saber mais, consulte [Visão geral do PowerShell do Teams.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="9c5fc-145">Definir regiões de rede</span><span class="sxs-lookup"><span data-stu-id="9c5fc-145">Define network regions</span></span>

 <span data-ttu-id="9c5fc-146">Use o cmdlet [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) para definir regiões de rede.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="9c5fc-147">Observe que o parâmetro RegionID é um nome lógico que representa a geografia da região e não tem dependências ou restrições, e o parâmetro ID do site centralSite &lt; &gt; é opcional.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="9c5fc-148">Neste exemplo, criamos uma região de rede chamada Índia.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-148">In this example, we create a network region named India.</span></span>
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="9c5fc-149">Consulte também [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span><span class="sxs-lookup"><span data-stu-id="9c5fc-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="9c5fc-150">Definir sites de rede</span><span class="sxs-lookup"><span data-stu-id="9c5fc-150">Define network sites</span></span>

<span data-ttu-id="9c5fc-151">Use o cmdlet [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) para definir sites de rede.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="9c5fc-152">Cada site de rede deve ser associado a uma região de rede.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="9c5fc-153">Neste exemplo, criamos dois novos sites de rede, Deli e Loungerabad, na região da Índia.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="9c5fc-154">A tabela a seguir mostra os sites de rede definidos neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="9c5fc-155">Site 1</span><span class="sxs-lookup"><span data-stu-id="9c5fc-155">Site 1</span></span> |<span data-ttu-id="9c5fc-156">Site 2</span><span class="sxs-lookup"><span data-stu-id="9c5fc-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="9c5fc-157">Site ID</span><span class="sxs-lookup"><span data-stu-id="9c5fc-157">Site ID</span></span>    |    <span data-ttu-id="9c5fc-158">Site 1 (Deli)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="9c5fc-159">Site 2 (Loungerabad)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="9c5fc-160">ID da região</span><span class="sxs-lookup"><span data-stu-id="9c5fc-160">Region ID</span></span>  |     <span data-ttu-id="9c5fc-161">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-161">Region 1 (India)</span></span>    |   <span data-ttu-id="9c5fc-162">Região 1 (Índia)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-162">Region 1 (India)</span></span>      |

<span data-ttu-id="9c5fc-163">Consulte também [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span><span class="sxs-lookup"><span data-stu-id="9c5fc-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="9c5fc-164">Definir sub-redes de rede</span><span class="sxs-lookup"><span data-stu-id="9c5fc-164">Define network subnets</span></span>

<span data-ttu-id="9c5fc-165">Use o cmdlet [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) para definir sub-redes de rede e associá-las a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="9c5fc-166">Cada sub-rede de rede só pode ser associada a um site.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="9c5fc-167">Neste exemplo, criamos uma associação entre a sub-rede 192.168.0.0 e o site de rede Deli e entre a sub-rede 2001:4898:e8:25:844e:926f:85ad:dd8e e o site de rede Deli.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="9c5fc-168">A tabela a seguir mostra as sub-redes definidas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="9c5fc-169">Site 1</span><span class="sxs-lookup"><span data-stu-id="9c5fc-169">Site 1</span></span> |<span data-ttu-id="9c5fc-170">Site 2</span><span class="sxs-lookup"><span data-stu-id="9c5fc-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="9c5fc-171">ID da sub-rede</span><span class="sxs-lookup"><span data-stu-id="9c5fc-171">Subnet ID</span></span>   |    <span data-ttu-id="9c5fc-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="9c5fc-172">192.168.0.0</span></span>     |  <span data-ttu-id="9c5fc-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span><span class="sxs-lookup"><span data-stu-id="9c5fc-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="9c5fc-174">Máscara</span><span class="sxs-lookup"><span data-stu-id="9c5fc-174">Mask</span></span>  |     <span data-ttu-id="9c5fc-175">24</span><span class="sxs-lookup"><span data-stu-id="9c5fc-175">24</span></span>    |   <span data-ttu-id="9c5fc-176">120</span><span class="sxs-lookup"><span data-stu-id="9c5fc-176">120</span></span>      |
|<span data-ttu-id="9c5fc-177">Site ID</span><span class="sxs-lookup"><span data-stu-id="9c5fc-177">Site ID</span></span>  | <span data-ttu-id="9c5fc-178">Site (Deli)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-178">Site (Delhi)</span></span> | <span data-ttu-id="9c5fc-179">Site 2 (Loungerabad)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="9c5fc-180">Para várias sub-redes, você pode importar um arquivo CSV usando um script como o seguinte.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="9c5fc-181">Neste exemplo, o arquivo CSV tem a aparência a seguir:</span><span class="sxs-lookup"><span data-stu-id="9c5fc-181">In this example, the CSV file looks something like this:</span></span> 

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="9c5fc-182">Consulte também [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span><span class="sxs-lookup"><span data-stu-id="9c5fc-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="9c5fc-183">Definir sub-redes externas (endereços IP confiáveis externos)</span><span class="sxs-lookup"><span data-stu-id="9c5fc-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="9c5fc-184">Use o cmdlet [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) para definir sub-redes externas e atribuí-las ao locatário.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="9c5fc-185">Você pode definir um número ilimitado de sub-redes externas para um locatário.</span><span class="sxs-lookup"><span data-stu-id="9c5fc-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="9c5fc-186">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9c5fc-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="9c5fc-187">Consulte também [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span><span class="sxs-lookup"><span data-stu-id="9c5fc-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9c5fc-188">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9c5fc-188">Related topics</span></span>

- [<span data-ttu-id="9c5fc-189">Configurações de rede para recursos de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="9c5fc-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
