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
description: Saiba como habilitar o roteamento baseado em local para roteamento direto.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 615848be1f91f80b0afd06c1eaa44a4f9d7b4f63
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615791"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="b7bfb-103">Habilitar o Roteamento baseado na localização para o Roteamento direto</span><span class="sxs-lookup"><span data-stu-id="b7bfb-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="b7bfb-104">Antes de seguir as etapas deste artigo, verifique se você leu o [roteamento baseado em local de plano para roteamento direto](location-based-routing-plan.md) e concluiu as etapas em [definir configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b7bfb-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="b7bfb-105">Este artigo descreve como habilitar o roteamento baseado em localização para roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="b7bfb-106">Depois de implantar o roteamento direto do sistema telefônico e configurar regiões de rede, sites e sub-redes, você estará pronto para habilitar o roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="b7bfb-107">Para concluir as etapas deste artigo, você precisará de familiaridade com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b7bfb-108">Para saber mais, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b7bfb-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="b7bfb-109">Você precisa ativar o roteamento baseado em local para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b7bfb-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="b7bfb-110">Usuários</span><span class="sxs-lookup"><span data-stu-id="b7bfb-110">Users</span></span>
- <span data-ttu-id="b7bfb-111">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="b7bfb-111">Network sites</span></span>
- <span data-ttu-id="b7bfb-112">Configurações de gateway</span><span class="sxs-lookup"><span data-stu-id="b7bfb-112">Gateway configurations</span></span>
- <span data-ttu-id="b7bfb-113">Políticas de chamada</span><span class="sxs-lookup"><span data-stu-id="b7bfb-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="b7bfb-114">Habilitar roteamento baseado em local para usuários</span><span class="sxs-lookup"><span data-stu-id="b7bfb-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="b7bfb-115">Use o cmdlet [set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) para definir usos de PSTN.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="b7bfb-116">Para vários usos, separe cada uso com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="b7bfb-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b7bfb-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="b7bfb-118">Use o cmdlet [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) para criar uma política de roteamento de voz para associar o usuário aos usos de PSTN apropriados.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="b7bfb-119">Ao atribuir usos de PSTN a uma política de roteamento de voz, certifique-se de seguir um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="b7bfb-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="b7bfb-120">Usar usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site</span><span class="sxs-lookup"><span data-stu-id="b7bfb-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="b7bfb-121">Use usos de PSTN associados a rotas de voz que usam um gateway PSTN localizado em uma região onde restrições de roteamento baseadas em localização não são necessárias.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="b7bfb-122">Neste exemplo, criamos duas novas políticas de roteamento de voz e atribuem usos de PSTN a elas.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="b7bfb-123">A tabela a seguir mostra as políticas de roteamento de voz definidas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="b7bfb-124">Política de roteamento de voz 1</span><span class="sxs-lookup"><span data-stu-id="b7bfb-124">Voice routing policy 1</span></span>|<span data-ttu-id="b7bfb-125">Política de roteamento de voz 2</span><span class="sxs-lookup"><span data-stu-id="b7bfb-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="b7bfb-126">ID da política de voz online</span><span class="sxs-lookup"><span data-stu-id="b7bfb-126">Online voice policy ID</span></span>   |<span data-ttu-id="b7bfb-127">Política de roteamento de voz online da Délhi</span><span class="sxs-lookup"><span data-stu-id="b7bfb-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="b7bfb-128">Política de roteamento de voz do Hyderabad online</span><span class="sxs-lookup"><span data-stu-id="b7bfb-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="b7bfb-129">Usos de PSTN online</span><span class="sxs-lookup"><span data-stu-id="b7bfb-129">Online PSTN usages</span></span>  |<span data-ttu-id="b7bfb-130">Longa distância</span><span class="sxs-lookup"><span data-stu-id="b7bfb-130">Long Distance</span></span>  |<span data-ttu-id="b7bfb-131">Longa distância, local, interna</span><span class="sxs-lookup"><span data-stu-id="b7bfb-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="b7bfb-132">Use o cmdlet [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) para associar políticas de roteamento de voz online aos usuários que precisam de restrições de roteamento para serem impostas.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="b7bfb-133">Habilitar o roteamento baseado em local para sites de rede</span><span class="sxs-lookup"><span data-stu-id="b7bfb-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="b7bfb-134">Use o cmdlet [set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) para habilitar o roteamento baseado em localização e associar políticas de roteamento de voz a seus sites de rede que precisam impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="b7bfb-135">Neste exemplo, habilitamos o roteamento baseado em local para o site de Delhi e o site do Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="b7bfb-136">A tabela a seguir mostra os sites habilitados para roteamento baseado em local neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="b7bfb-137">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="b7bfb-138">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="b7bfb-139">Nome do site</span><span class="sxs-lookup"><span data-stu-id="b7bfb-139">Site name</span></span>    |<span data-ttu-id="b7bfb-140">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="b7bfb-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="b7bfb-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="b7bfb-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="b7bfb-143">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b7bfb-143">True</span></span>    |<span data-ttu-id="b7bfb-144">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b7bfb-144">True</span></span>    |
    |<span data-ttu-id="b7bfb-145">Sub-redes</span><span class="sxs-lookup"><span data-stu-id="b7bfb-145">Subnets</span></span>     |<span data-ttu-id="b7bfb-146">Sub-rede 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="b7bfb-147">Sub-rede 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="b7bfb-148">Habilitar roteamento baseado em local para gateways</span><span class="sxs-lookup"><span data-stu-id="b7bfb-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="b7bfb-149">Use o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) para criar uma configuração de gateway para cada site de gateway ou de rede.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="b7bfb-150">Se vários gateways estiverem associados a um sistema (por exemplo, gateway ou PBX), modifique cada gateway para habilitar as restrições de roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="b7bfb-151">Neste exemplo, criamos uma configuração de gateway para cada gateway.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="b7bfb-152">Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b7bfb-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="b7bfb-153">Use o cmdlet [set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) para habilitar o roteamento baseado em localização para seus gateways que precisam impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="b7bfb-154">Habilite o roteamento baseado em local para gateways que roteiam chamadas para gateways PSTN que roteiam chamadas para a PSTN e associe o site de rede onde o gateway está localizado.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="b7bfb-155">Neste exemplo, habilitamos o roteamento baseado em local para cada gateway associado a gateways PSTN nos sites Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="b7bfb-156">Não habilite o roteamento baseado em localização para gateways que não roteiam chamadas para a PSTN.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="b7bfb-157">No entanto, você ainda precisa associar o gateway ao site de rede onde o sistema está localizado.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="b7bfb-158">Isso ocorre porque restrições de roteamento baseadas em local precisam ser impostas para que chamadas PSTN atinjam pontos de extremidade conectados por meio desse gateway.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="b7bfb-159">Neste exemplo, o roteamento baseado em localização não está habilitado para cada gateway associado a sistemas PBX nos sites Delhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="b7bfb-160">Os pontos de extremidade conectados a sistemas que não roteiam chamadas para a PSTN (por exemplo, um PBX) terão restrições semelhantes aos pontos de extremidade de usuários do teams habilitados para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="b7bfb-161">Isso significa que esses usuários podem fazer e receber chamadas para e de usuários do teams independentemente da localização do usuário.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="b7bfb-162">Eles também podem fazer e receber chamadas de e para outros sistemas que não roteiam chamadas para a rede PSTN (por exemplo, um ponto de extremidade conectado a um PBX diferente), independentemente do site de rede ao qual o sistema está associado.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="b7bfb-163">Todas as chamadas recebidas, chamadas de saída, transferências de chamadas e encaminhamento de chamadas que envolvem pontos de extremidade PSTN estarão sujeitas a imposição de roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="b7bfb-164">Essas chamadas devem usar somente gateways PSTN definidos como locais para tais sistemas.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="b7bfb-165">A tabela a seguir mostra a configuração de gateway de quatro gateways em dois locais de rede diferentes: dois conectados a gateways PSTN e dois conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="b7bfb-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="b7bfb-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="b7bfb-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="b7bfb-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="b7bfb-168">PstnGateway: gateway 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="b7bfb-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="b7bfb-169">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b7bfb-169">True</span></span>     |   <span data-ttu-id="b7bfb-170">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="b7bfb-171">PstnGateway: gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="b7bfb-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="b7bfb-172">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b7bfb-172">True</span></span>      |      <span data-ttu-id="b7bfb-173">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="b7bfb-174">PstnGateway: gateway 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="b7bfb-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="b7bfb-175">False</span><span class="sxs-lookup"><span data-stu-id="b7bfb-175">False</span></span>     |     <span data-ttu-id="b7bfb-176">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="b7bfb-177">PstnGateway: gateway 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="b7bfb-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="b7bfb-178">False</span><span class="sxs-lookup"><span data-stu-id="b7bfb-178">False</span></span>     |    <span data-ttu-id="b7bfb-179">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b7bfb-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="b7bfb-180">Habilitar roteamento baseado em local para políticas de chamadas</span><span class="sxs-lookup"><span data-stu-id="b7bfb-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="b7bfb-181">Para impor o roteamento baseado em localização para usuários específicos, configure a política de voz dos usuários para impedir o PTSN de chamada tarifada.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="b7bfb-182">Use o cmdlet [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) para habilitar o roteamento baseado em localização impedindo o bypass de chamada PSTN PSTN.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="b7bfb-183">Neste exemplo, impedimos que a chamada em PSTN seja ignorada para políticas de chamada User1's.</span><span class="sxs-lookup"><span data-stu-id="b7bfb-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a><span data-ttu-id="b7bfb-184">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b7bfb-184">Related topics</span></span>

- [<span data-ttu-id="b7bfb-185">Configurações de rede para recursos de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="b7bfb-185">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
