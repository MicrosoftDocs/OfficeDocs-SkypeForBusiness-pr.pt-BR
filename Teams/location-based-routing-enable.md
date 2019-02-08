---
title: Habilitar o roteamento baseado no local para roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Aprenda a habilitar o roteamento baseado no local para roteamento direto.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8437eba299cb42415d224017ca7d0e888fffa684
ms.sourcegitcommit: a80f26cdb91fac904e5c292c700b66af54261c62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "29771004"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="e7eeb-103">Habilitar o roteamento baseado no local para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="e7eeb-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="e7eeb-104">Antes de seguir as etapas neste artigo, verifique se você tiver ler [Plan Location-Based roteamento para roteamento direto](location-based-routing-plan.md) e concluir as etapas em [definir configurações de rede para roteamento baseado em local](location-based-routing-configure-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e7eeb-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="e7eeb-105">Este artigo descreve como habilitar o roteamento baseado no local para roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="e7eeb-106">Depois de implantar o roteamento direto de sistema do telefone e configurar regiões de rede, sites e sub-redes, você está pronto para habilitar o roteamento baseado no local.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="e7eeb-107">Para concluir as etapas neste artigo, você precisará de familiaridade com os cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="e7eeb-108">Para saber mais, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e7eeb-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="e7eeb-109">Você precisa habilitar o roteamento baseado no local para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7eeb-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="e7eeb-110">Usuários</span><span class="sxs-lookup"><span data-stu-id="e7eeb-110">Users</span></span>
- <span data-ttu-id="e7eeb-111">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="e7eeb-111">Network sites</span></span>
- <span data-ttu-id="e7eeb-112">Configurações de gateway</span><span class="sxs-lookup"><span data-stu-id="e7eeb-112">Gateway configurations</span></span>
- <span data-ttu-id="e7eeb-113">Políticas de chamada</span><span class="sxs-lookup"><span data-stu-id="e7eeb-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="e7eeb-114">Habilitar o roteamento baseado no local para usuários</span><span class="sxs-lookup"><span data-stu-id="e7eeb-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="e7eeb-115">Use o ``Set-CsOnlinePstnUsages`` cmdlet para definir os usos da PSTN.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-115">Use the ``Set-CsOnlinePstnUsages`` cmdlet to set PSTN usages.</span></span> <span data-ttu-id="e7eeb-116">Para vários usos, separe cada uso com uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="e7eeb-117">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e7eeb-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="e7eeb-118">Use o ``New-CsOnlineVoiceRoutingPolicy`` cmdlet para criar uma política de roteamento de voz para associar o usuário os usos da PSTN apropriados.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-118">Use the ``New-CsOnlineVoiceRoutingPolicy`` cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="e7eeb-119">Quando você atribui usos da PSTN a uma política de roteamento de voz, não deixe de que fazer um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e7eeb-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="e7eeb-120">Use os usos de PSTN associados às rotas de voz que usam um gateway PSTN local para o site</span><span class="sxs-lookup"><span data-stu-id="e7eeb-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="e7eeb-121">Use os usos de PSTN associados às rotas de voz que usam um gateway PSTN localizado em uma área onde as restrições de roteamento baseado no local não são necessários.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="e7eeb-122">Neste exemplo, criamos duas novas políticas de roteamento de voz e atribuir os usos da PSTN a eles.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="e7eeb-123">A tabela a seguir mostra as políticas de roteamento de voz definidas neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="e7eeb-124">1 política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="e7eeb-124">Voice routing policy 1</span></span>|<span data-ttu-id="e7eeb-125">2 de política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="e7eeb-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="e7eeb-126">ID da política de voz</span><span class="sxs-lookup"><span data-stu-id="e7eeb-126">Voice policy ID</span></span>   |<span data-ttu-id="e7eeb-127">Política de roteamento de voz Délhi</span><span class="sxs-lookup"><span data-stu-id="e7eeb-127">Delhi voice routing policy</span></span>   |<span data-ttu-id="e7eeb-128">Política de roteamento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e7eeb-128">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="e7eeb-129">Usos da PSTN online</span><span class="sxs-lookup"><span data-stu-id="e7eeb-129">Online PSTN usages</span></span>  |<span data-ttu-id="e7eeb-130">Interurbano</span><span class="sxs-lookup"><span data-stu-id="e7eeb-130">Long Distance</span></span>  |<span data-ttu-id="e7eeb-131">Interurbano, Local, interno</span><span class="sxs-lookup"><span data-stu-id="e7eeb-131">Long Distance, Local, Internal</span></span>  |

    <span data-ttu-id="e7eeb-132">Para obter mais informações, consulte [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="e7eeb-132">For more information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>
3. <span data-ttu-id="e7eeb-133">Use o ``Grant-CsOnlineVoiceRoutingPolicy`` políticas de roteamento aos usuários que precisam ser impostas restrições de roteamento de voz de cmdlet para associar online.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-133">Use the ``Grant-CsOnlineVoiceRoutingPolicy`` cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="e7eeb-134">Habilitar o roteamento baseado no local para sites de rede</span><span class="sxs-lookup"><span data-stu-id="e7eeb-134">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="e7eeb-135">Use o ``Set-CsTenantNetworkSite`` cmdlet para habilitar o roteamento baseado no local e associar as políticas de roteamento para os locais de rede que precisam para impor restrições de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-135">Use the ``Set-CsTenantNetworkSite`` cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -OnlineVoiceRoutingPolicy <voice routing policy ID> 
    ```

    <span data-ttu-id="e7eeb-136">Neste exemplo, podemos habilitar roteamento baseado no local para o site de Délhi e local de Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-136">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "DelhiVoiceRoutingPolicy" 
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -OnlineVoiceRoutingPolicy "HyderabadVoiceRoutingPolicy" 
    ```
    <span data-ttu-id="e7eeb-137">A tabela a seguir mostra os sites habilitados para roteamento baseados em local neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-137">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="e7eeb-138">1 (Délhi) do site</span><span class="sxs-lookup"><span data-stu-id="e7eeb-138">Site 1 (Delhi)</span></span>  |<span data-ttu-id="e7eeb-139">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e7eeb-139">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="e7eeb-140">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="e7eeb-140">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="e7eeb-141">True</span><span class="sxs-lookup"><span data-stu-id="e7eeb-141">True</span></span>    |<span data-ttu-id="e7eeb-142">True</span><span class="sxs-lookup"><span data-stu-id="e7eeb-142">True</span></span>    |
    |<span data-ttu-id="e7eeb-143">Política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="e7eeb-143">Voice routing policy</span></span>    | <span data-ttu-id="e7eeb-144">Política de roteamento de voz Délhi</span><span class="sxs-lookup"><span data-stu-id="e7eeb-144">Delhi voice routing policy</span></span>       |<span data-ttu-id="e7eeb-145">Política de roteamento de voz de Hyderabad</span><span class="sxs-lookup"><span data-stu-id="e7eeb-145">Hyderabad voice routing policy</span></span>    |
    |<span data-ttu-id="e7eeb-146">Sub-redes</span><span class="sxs-lookup"><span data-stu-id="e7eeb-146">Subnets</span></span>     |<span data-ttu-id="e7eeb-147">Subrede 1 (Délhi)</span><span class="sxs-lookup"><span data-stu-id="e7eeb-147">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="e7eeb-148">Subrede 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e7eeb-148">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="e7eeb-149">Habilitar o roteamento baseado no local para gateways</span><span class="sxs-lookup"><span data-stu-id="e7eeb-149">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="e7eeb-150">Use o ``New-CsOnlinePstnGateway`` cmdlet para criar uma configuração de gateway para cada site de rede ou gateway.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-150">Use the ``New-CsOnlinePstnGateway`` cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="e7eeb-151">Se vários gateways são associados um sistema (por exemplo, o Gateway ou PBX), modifique cada gateway para habilitar as restrições de roteamento baseados em local.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-151">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="e7eeb-152">Neste exemplo, criamos uma configuração de gateway para cada gateway.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-152">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="e7eeb-153">Para obter mais informações, consulte [Configurar o roteamento direto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="e7eeb-153">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="e7eeb-154">Use o ``Set-CSOnlinePSTNGateway`` cmdlet para habilitar o roteamento baseado no local para seus gateways que precisam para impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-154">Use the ``Set-CSOnlinePSTNGateway`` cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="e7eeb-155">Habilitar o roteamento baseado no local para os gateways que roteiem as chamadas para os gateways PSTN que rotear as chamadas para a PSTN e associe o site de rede onde se encontra o gateway.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-155">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="e7eeb-156">Neste exemplo, podemos habilitar roteamento baseado no local para cada gateway associado aos gateways PSTN nos sites Délhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-156">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="e7eeb-157">Não habilite o roteamento baseado no local para gateways que não encaminhar chamadas para o PSTN.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-157">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="e7eeb-158">No entanto, você ainda precisará associe o gateway para o site de rede em que o sistema está localizado.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-158">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="e7eeb-159">Isso ocorre porque as restrições de roteamento baseados em local precisam ser impostas para chamadas PSTN está atingindo pontos de extremidade que estão conectados por meio deste gateway.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-159">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="e7eeb-160">Neste exemplo, roteamento baseado no local não está habilitado para cada gateway associado aos sistemas de PBX nos sites Délhi e Hyderabad.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-160">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="e7eeb-161">Pontos de extremidade conectados aos sistemas que não encaminhar chamadas para a PSTN (por exemplo, um PBX) terá restrições semelhantes como pontos de extremidade dos usuários de equipes habilitados para roteamento baseado no local.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-161">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="e7eeb-162">Isso significa que esses usuários podem fazer e receber chamadas de e para usuários de equipes, independentemente do local do usuário.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-162">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="e7eeb-163">Eles também podem fazer e receber chamadas de outros sistemas que não rotear as chamadas para a rede PSTN (por exemplo, um ponto de extremidade conectado a um PBX diferente) independentemente do site de rede aos quais o sistema está associado.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-163">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="e7eeb-164">Todas as chamadas de entrada, chamadas de saída, transferências de chamada e o encaminhamento de chamadas que envolvem pontos de extremidade PSTN estará sujeito aplicações de roteamento baseados em local.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-164">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="e7eeb-165">Essas chamadas devem usar somente os gateways PSTN que são definidos como local para tais sistemas.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-165">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="e7eeb-166">A tabela a seguir mostra a configuração do gateway de quatro gateways em dois sites de rede diferente: dois conectados aos gateways PSTN e dois conectados aos sistemas de PBX.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-166">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="e7eeb-167">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="e7eeb-167">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="e7eeb-168">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="e7eeb-168">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="e7eeb-169">DEL PstnGateway:Gateway 1-GW</span><span class="sxs-lookup"><span data-stu-id="e7eeb-169">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="e7eeb-170">True</span><span class="sxs-lookup"><span data-stu-id="e7eeb-170">True</span></span>     |   <span data-ttu-id="e7eeb-171">1 (Délhi) do site</span><span class="sxs-lookup"><span data-stu-id="e7eeb-171">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="e7eeb-172">PstnGateway:Gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="e7eeb-172">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="e7eeb-173">True</span><span class="sxs-lookup"><span data-stu-id="e7eeb-173">True</span></span>      |      <span data-ttu-id="e7eeb-174">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e7eeb-174">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="e7eeb-175">PBX DEL PstnGateway:Gateway 3</span><span class="sxs-lookup"><span data-stu-id="e7eeb-175">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="e7eeb-176">True</span><span class="sxs-lookup"><span data-stu-id="e7eeb-176">True</span></span>     |     <span data-ttu-id="e7eeb-177">1 (Délhi) do site</span><span class="sxs-lookup"><span data-stu-id="e7eeb-177">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="e7eeb-178">PBX HYD PstnGateway:Gateway 4</span><span class="sxs-lookup"><span data-stu-id="e7eeb-178">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="e7eeb-179">True</span><span class="sxs-lookup"><span data-stu-id="e7eeb-179">True</span></span>     |    <span data-ttu-id="e7eeb-180">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="e7eeb-180">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="e7eeb-181">Habilitar o roteamento baseado no local para chamar políticas</span><span class="sxs-lookup"><span data-stu-id="e7eeb-181">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="e7eeb-182">Para impor o roteamento baseado no local para usuários específicos, configurar a política de voz dos usuários para evitar que as tarifas PTSN desvio.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-182">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="e7eeb-183">Use o ``Grant-TeamsCallingPolicy`` o desvio de cmdlet para habilitar o roteamento baseado em local, impedindo a execução de tarifas PSTN.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-183">Use the ``Grant-TeamsCallingPolicy`` cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-TeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="e7eeb-184">Neste exemplo, podemos impedir PSTN Chamada Tarifada desvio do Usuário1 chamar políticas.</span><span class="sxs-lookup"><span data-stu-id="e7eeb-184">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-TeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="e7eeb-185">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e7eeb-185">Related topics</span></span>
- [<span data-ttu-id="e7eeb-186">Planejar o roteamento baseado no local para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="e7eeb-186">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="e7eeb-187">Definir configurações de rede para roteamento baseado no local</span><span class="sxs-lookup"><span data-stu-id="e7eeb-187">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="e7eeb-188">Terminologia de roteamento baseados em local</span><span class="sxs-lookup"><span data-stu-id="e7eeb-188">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
