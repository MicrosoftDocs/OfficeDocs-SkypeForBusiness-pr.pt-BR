---
title: Habilitar o Roteamento baseado na localização para o Roteamento direto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Saiba como habilitar o Location-Based roteamento para Roteamento Direto, incluindo habilita-lo para usuários, sites de rede, configurações de gateway e políticas de chamada.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe9600a1ddc530b1dbbcb6c061021c9d4cd9d537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822911"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="cfe57-103">Habilitar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="cfe57-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="cfe57-104">Antes de seguir as etapas deste artigo, [](location-based-routing-plan.md) certifique-se de ler o plano Location-Based roteamento para roteamento direto e concluiu as etapas em Configurar configurações de rede para [Location-Based Roteamento.](location-based-routing-configure-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cfe57-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="cfe57-105">Este artigo descreve como habilitar o Location-Based roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="cfe57-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="cfe57-106">Depois de implantar o Roteamento Direto do Sistema de Telefonia e configurar regiões de rede, sites e sub-redes, você estará pronto para habilitar Location-Based Roteamento.</span><span class="sxs-lookup"><span data-stu-id="cfe57-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="cfe57-107">Para concluir as etapas deste artigo, você precisará de alguma familiaridade com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfe57-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="cfe57-108">Para saber mais, confira a [Visão Geral do PowerShell do Teams.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cfe57-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="cfe57-109">Você precisa habilitar Location-Based roteamento para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cfe57-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="cfe57-110">Usuários</span><span class="sxs-lookup"><span data-stu-id="cfe57-110">Users</span></span>
- <span data-ttu-id="cfe57-111">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="cfe57-111">Network sites</span></span>
- <span data-ttu-id="cfe57-112">Configurações do gateway</span><span class="sxs-lookup"><span data-stu-id="cfe57-112">Gateway configurations</span></span>
- <span data-ttu-id="cfe57-113">Políticas de chamadas</span><span class="sxs-lookup"><span data-stu-id="cfe57-113">Calling policies</span></span>

<span data-ttu-id="cfe57-114">Você pode usar o Centro [de administração da Equipe](#using-the-microsoft-teams-admin-center) da Microsoft ou o [PowerShel](#using-powershell)l para habilitar o Location-Based Roteamento.</span><span class="sxs-lookup"><span data-stu-id="cfe57-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="cfe57-115">Usando o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cfe57-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="cfe57-116">Habilitar Location-Based roteamento para usuários</span><span class="sxs-lookup"><span data-stu-id="cfe57-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="cfe57-117">Crie uma política de roteamento de voz e atribua usos de PSTN à política.</span><span class="sxs-lookup"><span data-stu-id="cfe57-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="cfe57-118">Ao atribuir usos de PSTN a uma política, certifique-se de fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cfe57-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="cfe57-119">Use os usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site.</span><span class="sxs-lookup"><span data-stu-id="cfe57-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="cfe57-120">Use os usos de PSTN associados Location-Based a rotas de voz que usam um gateway PSTN localizado em uma região onde não são necessárias restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cfe57-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="cfe57-121">Atribua a política de roteamento de voz aos usuários que exigem que as restrições de roteamento sejam impostas.</span><span class="sxs-lookup"><span data-stu-id="cfe57-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="cfe57-122">Para saber mais sobre como criar políticas de roteamento de voz e atribuí-las aos usuários, consulte Gerenciar políticas de roteamento [de voz no Microsoft Teams.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cfe57-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="cfe57-123">Habilitar Location-Based roteamento para sites de rede</span><span class="sxs-lookup"><span data-stu-id="cfe57-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="cfe57-124">Habilita Location-Based roteamento para seus sites que precisam impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cfe57-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="cfe57-125">Para fazer isso, na navegação à esquerda do Centro de administração do Microsoft Teams, vá para a topologia de Rede locais, selecione um site de rede, clique em Editar e a ligue o roteamento baseado em  >   **Localização.** </span><span class="sxs-lookup"><span data-stu-id="cfe57-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="cfe57-126">Para saber mais, consulte [Gerenciar sua topologia de rede.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="cfe57-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="cfe57-127">Habilitar Location-Based roteamento para gateways</span><span class="sxs-lookup"><span data-stu-id="cfe57-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="cfe57-128">Habilita Location-Based roteamento para gateways que roteam chamadas para gateways PSTN que encaminham chamadas para o PSTN e associem o site de rede onde o gateway está localizado.</span><span class="sxs-lookup"><span data-stu-id="cfe57-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="cfe57-129">Na navegação à esquerda, vá para **Roteamento Direto** de Voz e  >  clique na **guia SBCs.**</span><span class="sxs-lookup"><span data-stu-id="cfe57-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="cfe57-130">Selecione o SBC e clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="cfe57-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="cfe57-131">Em **Roteamento baseado em localização e otimização de mídia,** ative **Habilitar roteamento baseado em locais.**</span><span class="sxs-lookup"><span data-stu-id="cfe57-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="cfe57-132">Especifique a ID do site do gateway e de definir o modo de bypass.</span><span class="sxs-lookup"><span data-stu-id="cfe57-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="cfe57-133">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cfe57-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="cfe57-134">Habilitar Location-Based roteamento para políticas de chamada</span><span class="sxs-lookup"><span data-stu-id="cfe57-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="cfe57-135">Para impor Location-Based roteamento para usuários específicos, configurar a política de chamada do usuário para impedir o bypass de chamada tarifada PSTN.</span><span class="sxs-lookup"><span data-stu-id="cfe57-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="cfe57-136">Para fazer isso, a turn on the **Prevent toll bypass** setting in the calling policy.</span><span class="sxs-lookup"><span data-stu-id="cfe57-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="cfe57-137">Para saber mais, confira [as políticas de Chamada no Teams.](teams-calling-policy.md)</span><span class="sxs-lookup"><span data-stu-id="cfe57-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="cfe57-138">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfe57-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="cfe57-139">Habilitar Location-Based roteamento para usuários</span><span class="sxs-lookup"><span data-stu-id="cfe57-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="cfe57-140">Use o cmdlet [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para definir os usos de PSTN.</span><span class="sxs-lookup"><span data-stu-id="cfe57-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="cfe57-141">Para vários usos, separe cada uso com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="cfe57-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="cfe57-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cfe57-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="cfe57-143">Use o cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para criar uma política de roteamento de voz para associar o usuário aos usos PSTN apropriados.</span><span class="sxs-lookup"><span data-stu-id="cfe57-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="cfe57-144">Ao atribuir usos de PSTN a uma política de roteamento de voz, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cfe57-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="cfe57-145">Usar usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site</span><span class="sxs-lookup"><span data-stu-id="cfe57-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="cfe57-146">Use os usos de PSTN associados Location-Based a rotas de voz que usam um gateway PSTN localizado em uma região onde não são necessárias restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cfe57-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="cfe57-147">Neste exemplo, criamos duas novas políticas de roteamento de voz e atribuímos usos de PSTN a elas.</span><span class="sxs-lookup"><span data-stu-id="cfe57-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="cfe57-148">A tabela a seguir mostra as políticas de roteamento de voz definidas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="cfe57-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="cfe57-149">Política de roteamento de voz 1</span><span class="sxs-lookup"><span data-stu-id="cfe57-149">Voice routing policy 1</span></span>|<span data-ttu-id="cfe57-150">Política de roteamento de voz 2</span><span class="sxs-lookup"><span data-stu-id="cfe57-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="cfe57-151">ID da política de voz online</span><span class="sxs-lookup"><span data-stu-id="cfe57-151">Online voice policy ID</span></span>   |<span data-ttu-id="cfe57-152">Política de roteamento de voz online de Deli</span><span class="sxs-lookup"><span data-stu-id="cfe57-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="cfe57-153">Política de roteamento de voz online de Badra bad</span><span class="sxs-lookup"><span data-stu-id="cfe57-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="cfe57-154">Usos de PSTN online</span><span class="sxs-lookup"><span data-stu-id="cfe57-154">Online PSTN usages</span></span>  |<span data-ttu-id="cfe57-155">Distância Longa</span><span class="sxs-lookup"><span data-stu-id="cfe57-155">Long Distance</span></span>  |<span data-ttu-id="cfe57-156">Long Distance, Local, Internal</span><span class="sxs-lookup"><span data-stu-id="cfe57-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="cfe57-157">Use o cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para associar políticas de roteamento de voz online aos usuários que exigem restrições de roteamento a serem impostas.</span><span class="sxs-lookup"><span data-stu-id="cfe57-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="cfe57-158">Habilitar Location-Based roteamento para sites de rede</span><span class="sxs-lookup"><span data-stu-id="cfe57-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="cfe57-159">Use o cmdlet [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar Location-Based roteamento de voz e associar políticas de roteamento de voz aos sites de rede que precisam impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cfe57-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="cfe57-160">Neste exemplo, habilitamos Location-Based roteamento para o site de Deli e o site Deli.</span><span class="sxs-lookup"><span data-stu-id="cfe57-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="cfe57-161">A tabela a seguir mostra os sites habilitados para Location-Based roteamento neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="cfe57-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="cfe57-162">Site 1 (Deli)</span><span class="sxs-lookup"><span data-stu-id="cfe57-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="cfe57-163">Site 2 (Ltda bad)</span><span class="sxs-lookup"><span data-stu-id="cfe57-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="cfe57-164">Nome do site</span><span class="sxs-lookup"><span data-stu-id="cfe57-164">Site name</span></span>    |<span data-ttu-id="cfe57-165">Site 1 (Deli)</span><span class="sxs-lookup"><span data-stu-id="cfe57-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="cfe57-166">Site 2 (Ltda bad)</span><span class="sxs-lookup"><span data-stu-id="cfe57-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="cfe57-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="cfe57-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="cfe57-168">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="cfe57-168">True</span></span>    |<span data-ttu-id="cfe57-169">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="cfe57-169">True</span></span>    |
    |<span data-ttu-id="cfe57-170">Sub-redes</span><span class="sxs-lookup"><span data-stu-id="cfe57-170">Subnets</span></span>     |<span data-ttu-id="cfe57-171">Sub-rede 1 (Deli)</span><span class="sxs-lookup"><span data-stu-id="cfe57-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="cfe57-172">Sub-rede 2 (Ltda bad)</span><span class="sxs-lookup"><span data-stu-id="cfe57-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="cfe57-173">Habilitar Location-Based roteamento para gateways</span><span class="sxs-lookup"><span data-stu-id="cfe57-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="cfe57-174">Use o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para criar uma configuração de gateway para cada gateway ou site de rede.</span><span class="sxs-lookup"><span data-stu-id="cfe57-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="cfe57-175">Se vários gateways estão associados a um sistema (por exemplo, Gateway ou PBX), modifique cada gateway para habilitar Location-Based restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cfe57-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="cfe57-176">Neste exemplo, criamos uma configuração de gateway para cada gateway.</span><span class="sxs-lookup"><span data-stu-id="cfe57-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="cfe57-177">Para obter mais informações, consulte [Configurar Roteamento Direto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="cfe57-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="cfe57-178">Use o cmdlet [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar Location-Based roteamento para seus gateways que precisam impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="cfe57-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="cfe57-179">Habilita Location-Based roteamento para gateways que roteam chamadas para gateways PSTN que encaminham chamadas para o PSTN e associem o site de rede onde o gateway está localizado.</span><span class="sxs-lookup"><span data-stu-id="cfe57-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="cfe57-180">Neste exemplo, habilitamos o Location-Based roteamento para cada gateway associado a gateways PSTN nos sites Deli e Deli e Gatewayra bad.</span><span class="sxs-lookup"><span data-stu-id="cfe57-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="cfe57-181">Não habilitar Location-Based roteamento para gateways que não encaminham chamadas para o PSTN.</span><span class="sxs-lookup"><span data-stu-id="cfe57-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="cfe57-182">No entanto, você ainda precisa associar o gateway ao site de rede onde o sistema está localizado.</span><span class="sxs-lookup"><span data-stu-id="cfe57-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="cfe57-183">Isso porque Location-Based restrições de roteamento precisam ser impostas para chamadas PSTN chegando aos pontos de extremidade que estão conectados por meio desse gateway.</span><span class="sxs-lookup"><span data-stu-id="cfe57-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="cfe57-184">Neste exemplo, o Location-Based roteamento não está habilitado para cada gateway associado a sistemas PBX nos sites Deli e Deli e Gatewayra bad.</span><span class="sxs-lookup"><span data-stu-id="cfe57-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="cfe57-185">Habilitar Location-Based roteamento para políticas de chamada</span><span class="sxs-lookup"><span data-stu-id="cfe57-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="cfe57-186">Para impor Location-Based roteamento para usuários específicos, configurar a política de voz dos usuários para impedir o bypass de chamadas tarifadas PTSN.</span><span class="sxs-lookup"><span data-stu-id="cfe57-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="cfe57-187">Use o cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar Location-Based roteamento PSTN impedindo o bypass de chamada tarifada PSTN.</span><span class="sxs-lookup"><span data-stu-id="cfe57-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="cfe57-188">Neste exemplo, evitamos o bypass de chamada PSTN para as políticas de chamada do Usuário1.</span><span class="sxs-lookup"><span data-stu-id="cfe57-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="cfe57-189">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cfe57-189">Related topics</span></span>

- [<span data-ttu-id="cfe57-190">Configurações de rede para recursos de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="cfe57-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
