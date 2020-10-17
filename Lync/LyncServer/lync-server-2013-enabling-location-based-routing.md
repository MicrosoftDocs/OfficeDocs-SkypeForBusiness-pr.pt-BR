---
title: 'Lync Server 2013: habilitando roteamento de Location-Based'
description: 'Lync Server 2013: habilitando roteamento de Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557617"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0eb23-103">Habilitando o roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0eb23-103">Enabling Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eb23-104">_**Última modificação do tópico:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="0eb23-104">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="0eb23-105">Depois que o Enterprise Voice é implantado e as regiões de rede, sites e sub-redes são definidas, você pode habilitar o roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0eb23-105">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="0eb23-106">Location-Based roteamento deve estar habilitado para os seguintes elementos do Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="0eb23-106">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="0eb23-107">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="0eb23-107">Network sites</span></span>

  - <span data-ttu-id="0eb23-108">Configurações de tronco</span><span class="sxs-lookup"><span data-stu-id="0eb23-108">Trunk configurations</span></span>

  - <span data-ttu-id="0eb23-109">Políticas de voz</span><span class="sxs-lookup"><span data-stu-id="0eb23-109">Voice policies</span></span>

  - <span data-ttu-id="0eb23-110">Configuração de roteamento</span><span class="sxs-lookup"><span data-stu-id="0eb23-110">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="0eb23-111">Habilitar o roteamento de Location-Based para sites de rede</span><span class="sxs-lookup"><span data-stu-id="0eb23-111">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="0eb23-112">Depois de implantar o Enterprise Voice e os sites de rede configurados, você está pronto para configurar o roteamento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0eb23-112">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="0eb23-113">Primeiro, você cria uma política de roteamento de voz para associar o site de rede aos usos de PSTN apropriados.</span><span class="sxs-lookup"><span data-stu-id="0eb23-113">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="0eb23-114">Ao atribuir usos de PSTN a uma política de roteamento de voz, certifique-se de usar somente os usos de PSTN que estão associados a rotas de voz que usam um gateway PSTN local para o site ou um gateway PSTN que está localizado em uma região onde Location-Based restrições de roteamento não são necessárias. Use o comando do Windows PowerShell do Lync Server, o New-CsVoiceRoutingPolicy ou o painel de controle do Lync Server para criar políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="0eb23-114">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="0eb23-115">Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="0eb23-115">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="0eb23-116">Neste exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram duas políticas de roteamento de voz e seus usos de PSTN associados definidos neste cenário.</span><span class="sxs-lookup"><span data-stu-id="0eb23-116">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="0eb23-117">Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="0eb23-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0eb23-118">Política de roteamento de voz 1</span><span class="sxs-lookup"><span data-stu-id="0eb23-118">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="0eb23-119">Política de roteamento de voz 2</span><span class="sxs-lookup"><span data-stu-id="0eb23-119">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0eb23-120">ID da política de voz</span><span class="sxs-lookup"><span data-stu-id="0eb23-120">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="0eb23-121">Política de roteamento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="0eb23-121">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0eb23-122">Política de roteamento de voz do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0eb23-122">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0eb23-123">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="0eb23-123">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="0eb23-124">Uso de Delhi, uso de PBX, uso do PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="0eb23-124">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="0eb23-125">Uso do Hyderabad, uso do PBX Hyd, uso do PBX</span><span class="sxs-lookup"><span data-stu-id="0eb23-125">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="0eb23-126">Em seguida, configure Location-Based roteamento para os sites de rede aplicáveis e associe suas políticas de roteamento de voz a eles.</span><span class="sxs-lookup"><span data-stu-id="0eb23-126">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="0eb23-127">Use o comando do Windows PowerShell do Lync Server, New-CsNetworkSite, para habilitar Location-Based roteamento e associar as políticas de roteamento de voz aos sites de rede que devem impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="0eb23-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="0eb23-128">Neste exemplo, a tabela a seguir ilustra Location-Based roteamento para dois locais de rede diferentes, Delhi e Hyderabad, definidos neste cenário usando o Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0eb23-128">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="0eb23-129">Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="0eb23-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0eb23-130">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="0eb23-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="0eb23-131">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0eb23-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0eb23-132">Nome do Site</span><span class="sxs-lookup"><span data-stu-id="0eb23-132">Site Name</span></span></p></td>
<td><p><span data-ttu-id="0eb23-133">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="0eb23-133">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="0eb23-134">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0eb23-134">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0eb23-135">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="0eb23-135">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="0eb23-136">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="0eb23-136">True</span></span></p></td>
<td><p><span data-ttu-id="0eb23-137">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="0eb23-137">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0eb23-138">Política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="0eb23-138">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0eb23-139">Política de roteamento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="0eb23-139">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0eb23-140">Política de roteamento de voz do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0eb23-140">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0eb23-141">Sub-redes</span><span class="sxs-lookup"><span data-stu-id="0eb23-141">Subnets</span></span></p></td>
<td><p><span data-ttu-id="0eb23-142">Sub-rede 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="0eb23-142">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="0eb23-143">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0eb23-143">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="0eb23-144">Habilitar roteamento de Location-Based para troncos</span><span class="sxs-lookup"><span data-stu-id="0eb23-144">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="0eb23-145">Antes que uma configuração de tronco pode ser habilitada para roteamento de Location-Based, você precisa criar uma configuração de tronco para cada tronco ou cada site de rede.</span><span class="sxs-lookup"><span data-stu-id="0eb23-145">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="0eb23-146">Use o comando do Windows PowerShell do Lync Server, New-CsTrunkConfiguration, para criar uma configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="0eb23-146">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="0eb23-147">Se vários troncos estiverem associados a um determinado sistema (ou seja, gateway ou PBX), cada configuração de tronco deverá ser modificada para habilitar restrições de roteamento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0eb23-147">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="0eb23-148">Para obter mais informações, consulte [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0eb23-148">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="0eb23-149">Neste exemplo, os seguintes comandos do Windows PowerShell ilustram a criação de uma configuração de tronco para cada tronco na implantação definida neste cenário.</span><span class="sxs-lookup"><span data-stu-id="0eb23-149">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="0eb23-150">Depois que uma configuração de tronco é configurada por tronco, você pode usar o comando do Lync Server Windows PowerShell, Set-CsTrunkConfiguration, para habilitar Location-Based roteamento para seus troncos que devem impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="0eb23-150">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="0eb23-151">Habilite Location-Based roteamento para troncos que roteiam chamadas para gateways PSTN que roteiam chamadas para a PSTN e associe o local de rede onde o gateway está localizado.</span><span class="sxs-lookup"><span data-stu-id="0eb23-151">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="0eb23-152">Para obter mais informações, consulte [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0eb23-152">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="0eb23-153">Neste exemplo, Location-Based roteamento está habilitado para cada tronco associado aos gateways PSTN em Delhi e Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="0eb23-153">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="0eb23-154">Não habilite o roteamento de Location-Based para troncos que não roteiam chamadas para o PSTN; no entanto, você ainda deve associar o tronco ao site de rede em que o sistema está localizado como Location-Based restrições de roteamento precisam ser impostas para chamadas PSTN que chegam aos pontos de extremidade conectados por meio desse tronco.</span><span class="sxs-lookup"><span data-stu-id="0eb23-154">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="0eb23-155">Para este exemplo, Location-Based roteamento não está habilitado para cada tronco associado a sistemas PBX em Delhi e Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="0eb23-155">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="0eb23-156">Os pontos de extremidade conectados a sistemas que não roteiam chamadas para o PSTN (ou seja, um PBX) terão restrições semelhantes aos pontos de extremidade do Lync dos usuários habilitados para roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0eb23-156">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="0eb23-157">Isso significa que esses usuários poderão fazer e receber chamadas de e para o usuário do Lync independentemente do local do usuário.</span><span class="sxs-lookup"><span data-stu-id="0eb23-157">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="0eb23-158">Eles também poderão fazer chamadas de recebimento para e de outros sistemas que não roteiam chamadas para a rede PSTN (ou seja, um ponto de extremidade conectado a um PBX diferente), independentemente do site de rede ao qual o sistema está associado.</span><span class="sxs-lookup"><span data-stu-id="0eb23-158">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="0eb23-159">Todas as chamadas de entrada, chamadas de saída, transferências de chamadas e encaminhamento de chamadas que envolvem pontos de extremidade PSTN serão sujeitas a Location-Based enforceres de roteamento.</span><span class="sxs-lookup"><span data-stu-id="0eb23-159">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="0eb23-160">Essas chamadas devem usar somente gateways PSTN definidos como locais para esses sistemas.</span><span class="sxs-lookup"><span data-stu-id="0eb23-160">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="0eb23-161">A tabela a seguir ilustra a configuração de tronco de quatro troncos em dois locais de rede diferentes: dois conectados a gateways PSTN e dois conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="0eb23-161">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0eb23-162">Nome</span><span class="sxs-lookup"><span data-stu-id="0eb23-162">Name</span></span></th>
<th><span data-ttu-id="0eb23-163">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="0eb23-163">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="0eb23-164">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="0eb23-164">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0eb23-165">PstnGateway: tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="0eb23-165">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="0eb23-166">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="0eb23-166">True</span></span></p></td>
<td><p><span data-ttu-id="0eb23-167">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="0eb23-167">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0eb23-168">PstnGateway: tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="0eb23-168">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="0eb23-169">Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="0eb23-169">True</span></span></p></td>
<td><p><span data-ttu-id="0eb23-170">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0eb23-170">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0eb23-171">PstnGateway: trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="0eb23-171">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="0eb23-172">Falso</span><span class="sxs-lookup"><span data-stu-id="0eb23-172">False</span></span></p></td>
<td><p><span data-ttu-id="0eb23-173">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="0eb23-173">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0eb23-174">PstnGateway: tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="0eb23-174">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="0eb23-175">Falso</span><span class="sxs-lookup"><span data-stu-id="0eb23-175">False</span></span></p></td>
<td><p><span data-ttu-id="0eb23-176">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0eb23-176">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="0eb23-177">Habilitar o roteamento de Location-Based para políticas de voz</span><span class="sxs-lookup"><span data-stu-id="0eb23-177">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="0eb23-178">Para impor Location-Based roteamento a usuários específicos, configure a política de voz dos usuários para evitar o bypass de chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="0eb23-178">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="0eb23-179">Use o comando do Windows PowerShell do Lync Server, New-CsVoicePolicy, para criar uma nova política de voz ou Set-CsVoicePolicy, se estiver usando uma política existente, para habilitar Location-Based roteamento, impedindo o desvio de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="0eb23-179">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="0eb23-180">Para obter mais informações, consulte [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="0eb23-180">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="0eb23-181">Para este exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram a prevenção de bypass de chamadas PSTN para as políticas de voz de Déli e Hyderabad definidas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="0eb23-181">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="0eb23-182">Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="0eb23-182">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0eb23-183">Política de voz 1</span><span class="sxs-lookup"><span data-stu-id="0eb23-183">Voice policy 1</span></span></th>
<th><span data-ttu-id="0eb23-184">Política de voz 2</span><span class="sxs-lookup"><span data-stu-id="0eb23-184">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0eb23-185">ID da política de voz</span><span class="sxs-lookup"><span data-stu-id="0eb23-185">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="0eb23-186">Política de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="0eb23-186">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="0eb23-187">Política de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="0eb23-187">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0eb23-188">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="0eb23-188">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="0eb23-189">Uso de Delhi, uso de PBX, uso do PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="0eb23-189">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="0eb23-190">Uso do Hyderabad, uso do PBX Hyd, uso do PBX</span><span class="sxs-lookup"><span data-stu-id="0eb23-190">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0eb23-191">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="0eb23-191">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="0eb23-192">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="0eb23-192">True</span></span></p></td>
<td><p><span data-ttu-id="0eb23-193">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="0eb23-193">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="0eb23-194">Habilitar roteamento de Location-Based na configuração de roteamento</span><span class="sxs-lookup"><span data-stu-id="0eb23-194">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="0eb23-195">Por fim, habilite globalmente Location-Based roteamento para sua configuração de roteamento.</span><span class="sxs-lookup"><span data-stu-id="0eb23-195">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="0eb23-196">Use o comando do Windows PowerShell do Lync Server, New-CsRoutingConfiguration, para habilitar o roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="0eb23-196">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="0eb23-197">Para obter mais informações, consulte [set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="0eb23-197">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0eb23-198">enquanto Location-Based roteamento deve ser habilitado por meio de uma configuração global, o conjunto de regras a ser aplicado só será imposto para os sites, os usuários e os troncos para os quais foram configurados conforme especificado nesta documentação.</span><span class="sxs-lookup"><span data-stu-id="0eb23-198">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0eb23-199">Confira também</span><span class="sxs-lookup"><span data-stu-id="0eb23-199">See Also</span></span>


[<span data-ttu-id="0eb23-200">Configurando o roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0eb23-200">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

