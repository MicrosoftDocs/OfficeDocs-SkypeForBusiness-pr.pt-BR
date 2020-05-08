---
title: Habilitar o Roteamento baseado na localização para o Roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como habilitar o roteamento baseado em local para roteamento direto, incluindo a habilitação para usuários, sites de rede, configurações de gateway e políticas de chamadas.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69f2ee37e63f83d6fc1d19ea733ff44ad23e7011
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158988"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="b4227-103">Habilitar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="b4227-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="b4227-104">Antes de seguir as etapas deste artigo, verifique se você leu o [roteamento baseado em local de plano para roteamento direto](location-based-routing-plan.md) e concluiu as etapas em [definir configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b4227-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="b4227-105">Este artigo descreve como habilitar o roteamento baseado em localização para roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="b4227-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="b4227-106">Depois de implantar o roteamento direto do sistema telefônico e configurar regiões de rede, sites e sub-redes, você estará pronto para habilitar o roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="b4227-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="b4227-107">Para concluir as etapas deste artigo, você precisará de familiaridade com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4227-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b4227-108">Para saber mais, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b4227-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="b4227-109">Você precisa ativar o roteamento baseado em local para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4227-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="b4227-110">Usuários</span><span class="sxs-lookup"><span data-stu-id="b4227-110">Users</span></span>
- <span data-ttu-id="b4227-111">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="b4227-111">Network sites</span></span>
- <span data-ttu-id="b4227-112">Configurações de gateway</span><span class="sxs-lookup"><span data-stu-id="b4227-112">Gateway configurations</span></span>
- <span data-ttu-id="b4227-113">Políticas de chamada</span><span class="sxs-lookup"><span data-stu-id="b4227-113">Calling policies</span></span>

<span data-ttu-id="b4227-114">Você pode usar o [centro de administração do Microsoft Team](#using-the-microsoft-teams-admin-center) ou o [PowerShel](#using-powershell)l para habilitar o roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="b4227-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b4227-115">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4227-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="b4227-116">Habilitar roteamento baseado em local para usuários</span><span class="sxs-lookup"><span data-stu-id="b4227-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="b4227-117">Criar uma política de roteamento de voz e atribuir usos de PSTN à política.</span><span class="sxs-lookup"><span data-stu-id="b4227-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="b4227-118">Ao atribuir usos de PSTN a uma política, certifique-se de executar uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="b4227-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="b4227-119">Use usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site.</span><span class="sxs-lookup"><span data-stu-id="b4227-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="b4227-120">Use usos de PSTN associados a rotas de voz que usam um gateway PSTN localizado em uma região onde restrições de roteamento baseadas em localização não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="b4227-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="b4227-121">Atribua a política de roteamento de voz aos usuários que exigem restrições de roteamento a serem impostas.</span><span class="sxs-lookup"><span data-stu-id="b4227-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="b4227-122">Para saber mais sobre como criar políticas de roteamento de voz e atribuí-las aos usuários, consulte [gerenciar políticas de roteamento de voz no Microsoft Teams](manage-voice-routing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b4227-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="b4227-123">Habilitar o roteamento baseado em local para sites de rede</span><span class="sxs-lookup"><span data-stu-id="b4227-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="b4227-124">Habilite o roteamento baseado em local para seus sites que precisam impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="b4227-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="b4227-125">Para fazer isso, no painel de navegação esquerdo do centro de administração do Microsoft Teams, vá para **locais** > **topologia de rede**, selecione um site de rede, clique em **Editar**e ative o **roteamento baseado em localização**.</span><span class="sxs-lookup"><span data-stu-id="b4227-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="b4227-126">Para saber mais, consulte [gerenciar a topologia de rede](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="b4227-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="b4227-127">Habilitar roteamento baseado em local para gateways</span><span class="sxs-lookup"><span data-stu-id="b4227-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="b4227-128">Habilite o roteamento baseado em local para gateways que roteiam chamadas para gateways PSTN que roteiam chamadas para a PSTN e associe o site de rede onde o gateway está localizado.</span><span class="sxs-lookup"><span data-stu-id="b4227-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="b4227-129">No painel de navegação esquerdo, vá para**Roteamento direto**de **voz** > e clique na guia **SBCS** .</span><span class="sxs-lookup"><span data-stu-id="b4227-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="b4227-130">Selecione o SBC e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b4227-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="b4227-131">Em **roteamento baseado em localização e otimização de mídia**, ative **habilitar roteamento baseado em local**.</span><span class="sxs-lookup"><span data-stu-id="b4227-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="b4227-132">Especifique a ID do site do gateway e, em seguida, defina o modo ignorar.</span><span class="sxs-lookup"><span data-stu-id="b4227-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="b4227-133">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b4227-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="b4227-134">Habilitar roteamento baseado em local para políticas de chamadas</span><span class="sxs-lookup"><span data-stu-id="b4227-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="b4227-135">Para impor o roteamento baseado em localização para usuários específicos, configure a política de chamada do usuário para impedir o bypass de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="b4227-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="b4227-136">Para fazer isso, ative a configuração **impedir o bypass de chamada** na política de chamada.</span><span class="sxs-lookup"><span data-stu-id="b4227-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="b4227-137">Para saber mais, consulte [chamando políticas no Teams](teams-calling-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b4227-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="b4227-138">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4227-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="b4227-139">Habilitar roteamento baseado em local para usuários</span><span class="sxs-lookup"><span data-stu-id="b4227-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="b4227-140">Use o cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para definir usos de PSTN.</span><span class="sxs-lookup"><span data-stu-id="b4227-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="b4227-141">Para vários usos, separe cada uso com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="b4227-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="b4227-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b4227-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="b4227-143">Use o cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para criar uma política de roteamento de voz para associar o usuário aos usos de PSTN apropriados.</span><span class="sxs-lookup"><span data-stu-id="b4227-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="b4227-144">Ao atribuir usos de PSTN a uma política de roteamento de voz, certifique-se de seguir um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b4227-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="b4227-145">Usar usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site</span><span class="sxs-lookup"><span data-stu-id="b4227-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="b4227-146">Use usos de PSTN associados a rotas de voz que usam um gateway PSTN localizado em uma região onde restrições de roteamento baseadas em localização não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="b4227-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="b4227-147">Neste exemplo, criamos duas novas políticas de roteamento de voz e atribuem usos de PSTN a elas.</span><span class="sxs-lookup"><span data-stu-id="b4227-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="b4227-148">A tabela a seguir mostra as políticas de roteamento de voz definidas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="b4227-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="b4227-149">Política de roteamento de voz 1</span><span class="sxs-lookup"><span data-stu-id="b4227-149">Voice routing policy 1</span></span>|<span data-ttu-id="b4227-150">Política de roteamento de voz 2</span><span class="sxs-lookup"><span data-stu-id="b4227-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="b4227-151">ID da política de voz online</span><span class="sxs-lookup"><span data-stu-id="b4227-151">Online voice policy ID</span></span>   |<span data-ttu-id="b4227-152">Política de roteamento de voz online da Délhi</span><span class="sxs-lookup"><span data-stu-id="b4227-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="b4227-153">Política de roteamento de voz do Hyderabad online</span><span class="sxs-lookup"><span data-stu-id="b4227-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="b4227-154">Usos de PSTN online</span><span class="sxs-lookup"><span data-stu-id="b4227-154">Online PSTN usages</span></span>  |<span data-ttu-id="b4227-155">Longa distância</span><span class="sxs-lookup"><span data-stu-id="b4227-155">Long Distance</span></span>  |<span data-ttu-id="b4227-156">Longa distância, local, interna</span><span class="sxs-lookup"><span data-stu-id="b4227-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="b4227-157">Use o cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para associar políticas de roteamento de voz online aos usuários que precisam de restrições de roteamento para serem impostas.</span><span class="sxs-lookup"><span data-stu-id="b4227-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="b4227-158">Habilitar o roteamento baseado em local para sites de rede</span><span class="sxs-lookup"><span data-stu-id="b4227-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="b4227-159">Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar o roteamento baseado em localização e associar políticas de roteamento de voz a seus sites de rede que precisam impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="b4227-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="b4227-160">Neste exemplo, habilitamos o roteamento baseado em local para o site de Delhi e o site do Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="b4227-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="b4227-161">A tabela a seguir mostra os sites habilitados para roteamento baseado em local neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="b4227-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="b4227-162">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b4227-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="b4227-163">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b4227-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="b4227-164">Nome do site</span><span class="sxs-lookup"><span data-stu-id="b4227-164">Site name</span></span>    |<span data-ttu-id="b4227-165">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b4227-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="b4227-166">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b4227-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="b4227-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="b4227-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="b4227-168">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b4227-168">True</span></span>    |<span data-ttu-id="b4227-169">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b4227-169">True</span></span>    |
    |<span data-ttu-id="b4227-170">Sub-redes</span><span class="sxs-lookup"><span data-stu-id="b4227-170">Subnets</span></span>     |<span data-ttu-id="b4227-171">Sub-rede 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b4227-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="b4227-172">Sub-rede 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b4227-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="b4227-173">Habilitar roteamento baseado em local para gateways</span><span class="sxs-lookup"><span data-stu-id="b4227-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="b4227-174">Use o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para criar uma configuração de gateway para cada site de gateway ou de rede.</span><span class="sxs-lookup"><span data-stu-id="b4227-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="b4227-175">Se vários gateways estiverem associados a um sistema (por exemplo, gateway ou PBX), modifique cada gateway para habilitar as restrições de roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="b4227-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="b4227-176">Neste exemplo, criamos uma configuração de gateway para cada gateway.</span><span class="sxs-lookup"><span data-stu-id="b4227-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="b4227-177">Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b4227-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="b4227-178">Use o cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar o roteamento baseado em localização para seus gateways que precisam impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="b4227-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="b4227-179">Habilite o roteamento baseado em local para gateways que roteiam chamadas para gateways PSTN que roteiam chamadas para a PSTN e associe o site de rede onde o gateway está localizado.</span><span class="sxs-lookup"><span data-stu-id="b4227-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="b4227-180">Neste exemplo, habilitamos o roteamento baseado em local para cada gateway associado a gateways PSTN nos sites Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="b4227-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="b4227-181">Não habilite o roteamento baseado em localização para gateways que não roteiam chamadas para a PSTN.</span><span class="sxs-lookup"><span data-stu-id="b4227-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="b4227-182">No entanto, você ainda precisa associar o gateway ao site de rede onde o sistema está localizado.</span><span class="sxs-lookup"><span data-stu-id="b4227-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="b4227-183">Isso ocorre porque restrições de roteamento baseadas em local precisam ser impostas para que chamadas PSTN atinjam pontos de extremidade conectados por meio desse gateway.</span><span class="sxs-lookup"><span data-stu-id="b4227-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="b4227-184">Neste exemplo, o roteamento baseado em localização não está habilitado para cada gateway associado a sistemas PBX nos sites Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="b4227-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="b4227-185">Os pontos de extremidade conectados a sistemas que não roteiam chamadas para a PSTN (por exemplo, um PBX) terão restrições semelhantes aos pontos de extremidade de usuários do teams habilitados para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="b4227-185">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="b4227-186">Isso significa que esses usuários podem fazer e receber chamadas para e de usuários do teams independentemente da localização do usuário.</span><span class="sxs-lookup"><span data-stu-id="b4227-186">This means that these users can place and receive calls to and from Teams users regardless of the user's location.</span></span> <span data-ttu-id="b4227-187">Eles também podem fazer e receber chamadas de e para outros sistemas que não roteiam chamadas para a rede PSTN (por exemplo, um ponto de extremidade conectado a um PBX diferente), independentemente do site de rede ao qual o sistema está associado.</span><span class="sxs-lookup"><span data-stu-id="b4227-187">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="b4227-188">Todas as chamadas recebidas, chamadas de saída, transferências de chamadas e encaminhamento de chamadas que envolvem pontos de extremidade PSTN estarão sujeitas a imposição de roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="b4227-188">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="b4227-189">Essas chamadas devem usar somente gateways PSTN definidos como locais para tais sistemas.</span><span class="sxs-lookup"><span data-stu-id="b4227-189">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="b4227-190">A tabela a seguir mostra a configuração de gateway de quatro gateways em dois locais de rede diferentes: dois conectados a gateways PSTN e dois conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="b4227-190">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="b4227-191">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="b4227-191">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="b4227-192">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="b4227-192">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="b4227-193">PstnGateway: gateway 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="b4227-193">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="b4227-194">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b4227-194">True</span></span>     |   <span data-ttu-id="b4227-195">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b4227-195">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="b4227-196">PstnGateway: gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="b4227-196">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="b4227-197">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b4227-197">True</span></span>      |      <span data-ttu-id="b4227-198">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b4227-198">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="b4227-199">PstnGateway: gateway 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="b4227-199">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="b4227-200">Falso</span><span class="sxs-lookup"><span data-stu-id="b4227-200">False</span></span>     |     <span data-ttu-id="b4227-201">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b4227-201">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="b4227-202">PstnGateway: gateway 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="b4227-202">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="b4227-203">Falso</span><span class="sxs-lookup"><span data-stu-id="b4227-203">False</span></span>     |    <span data-ttu-id="b4227-204">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b4227-204">Site 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="b4227-205">Habilitar roteamento baseado em local para políticas de chamadas</span><span class="sxs-lookup"><span data-stu-id="b4227-205">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="b4227-206">Para impor o roteamento baseado em localização para usuários específicos, configure a política de voz dos usuários para impedir o PTSN de chamada tarifada.</span><span class="sxs-lookup"><span data-stu-id="b4227-206">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="b4227-207">Use o cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar o roteamento baseado em localização impedindo o bypass de chamada PSTN PSTN.</span><span class="sxs-lookup"><span data-stu-id="b4227-207">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="b4227-208">Neste exemplo, impedimos que a chamada em PSTN seja ignorada para políticas de chamada User1's.</span><span class="sxs-lookup"><span data-stu-id="b4227-208">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="b4227-209">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b4227-209">Related topics</span></span>

- [<span data-ttu-id="b4227-210">Configurações de rede para recursos de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="b4227-210">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
