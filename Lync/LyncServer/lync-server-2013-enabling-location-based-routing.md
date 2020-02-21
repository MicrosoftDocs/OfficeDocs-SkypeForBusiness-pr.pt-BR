---
title: 'Lync Server 2013: habilitando roteamento baseado em local'
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
ms.openlocfilehash: 5a66ced9530510ade4d91e8d76032a4260870530
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="8e489-102">Habilitando o roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e489-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e489-103">_**Última modificação do tópico:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="8e489-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="8e489-104">Depois que o Enterprise Voice é implantado e as regiões de rede, sites e sub-redes são definidas, você pode habilitar o roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="8e489-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="8e489-105">O roteamento baseado em local deve ser habilitado para os seguintes elementos do Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="8e489-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="8e489-106">Sites de rede</span><span class="sxs-lookup"><span data-stu-id="8e489-106">Network sites</span></span>

  - <span data-ttu-id="8e489-107">Configurações de tronco</span><span class="sxs-lookup"><span data-stu-id="8e489-107">Trunk configurations</span></span>

  - <span data-ttu-id="8e489-108">Políticas de voz</span><span class="sxs-lookup"><span data-stu-id="8e489-108">Voice policies</span></span>

  - <span data-ttu-id="8e489-109">Configuração de roteamento</span><span class="sxs-lookup"><span data-stu-id="8e489-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="8e489-110">Habilitar o roteamento baseado em local para sites de rede</span><span class="sxs-lookup"><span data-stu-id="8e489-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="8e489-111">Depois de implantar o Enterprise Voice e os sites de rede configurados, você está pronto para configurar o roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="8e489-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="8e489-112">Primeiro, você cria uma política de roteamento de voz para associar o site de rede aos usos de PSTN apropriados.</span><span class="sxs-lookup"><span data-stu-id="8e489-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="8e489-113">Ao atribuir usos de PSTN a uma política de roteamento de voz, certifique-se de usar somente os usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site ou um gateway PSTN localizado em uma região onde as restrições de roteamento baseadas em local não são necessárias. Use o comando do Windows PowerShell do Lync Server, o New-CsVoiceRoutingPolicy ou o painel de controle do Lync Server para criar políticas de roteamento de voz.</span><span class="sxs-lookup"><span data-stu-id="8e489-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="8e489-114">Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="8e489-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="8e489-115">Neste exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram duas políticas de roteamento de voz e seus usos de PSTN associados definidos neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8e489-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="8e489-116">Somente as configurações específicas do roteamento baseado em local são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="8e489-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="8e489-117">Política de roteamento de voz 1</span><span class="sxs-lookup"><span data-stu-id="8e489-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="8e489-118">Política de roteamento de voz 2</span><span class="sxs-lookup"><span data-stu-id="8e489-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e489-119">ID da política de voz</span><span class="sxs-lookup"><span data-stu-id="8e489-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="8e489-120">Política de roteamento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="8e489-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="8e489-121">Política de roteamento de voz do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="8e489-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e489-122">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="8e489-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="8e489-123">Uso de Delhi, uso de PBX, uso do PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="8e489-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="8e489-124">Uso do Hyderabad, uso do PBX Hyd, uso do PBX</span><span class="sxs-lookup"><span data-stu-id="8e489-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="8e489-125">Em seguida, configure o roteamento baseado em local para os sites de rede aplicáveis e associe suas políticas de roteamento de voz a eles.</span><span class="sxs-lookup"><span data-stu-id="8e489-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="8e489-126">Use o comando do Windows PowerShell do Lync Server, New-CsNetworkSite, para habilitar o roteamento baseado em local e associar as políticas de roteamento de voz aos sites de rede que devem impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="8e489-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="8e489-127">Neste exemplo, a tabela a seguir ilustra o roteamento baseado em local para dois sites de rede diferentes, Delhi e Hyderabad, definidos neste cenário usando o Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e489-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="8e489-128">Somente as configurações específicas do roteamento baseado em local são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="8e489-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="8e489-129">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8e489-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="8e489-130">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8e489-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e489-131">Nome do Site</span><span class="sxs-lookup"><span data-stu-id="8e489-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="8e489-132">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8e489-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="8e489-133">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8e489-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e489-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="8e489-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="8e489-135">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="8e489-135">True</span></span></p></td>
<td><p><span data-ttu-id="8e489-136">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="8e489-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e489-137">Política de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="8e489-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="8e489-138">Política de roteamento de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="8e489-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="8e489-139">Política de roteamento de voz do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="8e489-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e489-140">Sub-redes</span><span class="sxs-lookup"><span data-stu-id="8e489-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="8e489-141">Sub-rede 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8e489-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="8e489-142">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8e489-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="8e489-143">Habilitar roteamento baseado em local para troncos</span><span class="sxs-lookup"><span data-stu-id="8e489-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="8e489-144">Antes que uma configuração de tronco possa ser habilitada para roteamento baseado em local, você precisará criar uma configuração de tronco para cada tronco ou cada site de rede.</span><span class="sxs-lookup"><span data-stu-id="8e489-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="8e489-145">Use o comando do Windows PowerShell do Lync Server, New-CsTrunkConfiguration, para criar uma configuração de tronco.</span><span class="sxs-lookup"><span data-stu-id="8e489-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="8e489-146">Se vários troncos estiverem associados a um determinado sistema (ou seja, gateway ou PBX), cada configuração de tronco deverá ser modificada para habilitar as restrições de roteamento com base no local.</span><span class="sxs-lookup"><span data-stu-id="8e489-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="8e489-147">Para obter mais informações, consulte [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8e489-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="8e489-148">Neste exemplo, os seguintes comandos do Windows PowerShell ilustram a criação de uma configuração de tronco para cada tronco na implantação definida neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8e489-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="8e489-149">Depois que uma configuração de tronco é configurada por tronco, você pode usar o comando do Lync Server Windows PowerShell, Set-CsTrunkConfiguration, para habilitar o roteamento baseado em local para seus troncos que devem impor restrições de roteamento.</span><span class="sxs-lookup"><span data-stu-id="8e489-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="8e489-150">Habilitar o roteamento baseado em local para troncos que roteiam chamadas para gateways PSTN que roteiam chamadas para o PSTN e associam o site de rede onde o gateway está localizado.</span><span class="sxs-lookup"><span data-stu-id="8e489-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="8e489-151">Para obter mais informações, consulte [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8e489-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="8e489-152">Neste exemplo, o roteamento baseado em local está habilitado para cada tronco associado aos gateways PSTN em Delhi e Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="8e489-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="8e489-153">Não habilite o roteamento baseado em local para troncos que não roteiam chamadas para o PSTN; no entanto, você ainda deve associar o tronco ao site de rede em que o sistema está localizado como as restrições de roteamento baseadas em local precisam ser impostas para chamadas PSTN que chegam aos pontos de extremidade conectados por esse tronco.</span><span class="sxs-lookup"><span data-stu-id="8e489-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="8e489-154">Neste exemplo, o roteamento baseado em local não está habilitado para cada tronco associado aos sistemas PBX em Delhi e Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="8e489-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="8e489-155">Os pontos de extremidade conectados aos sistemas que não roteiam chamadas para o PSTN (ou seja, um PBX) terão restrições semelhantes aos pontos de extremidade do Lync dos usuários habilitados para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="8e489-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="8e489-156">Isso significa que esses usuários poderão fazer e receber chamadas de e para o usuário do Lync independentemente do local do usuário.</span><span class="sxs-lookup"><span data-stu-id="8e489-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="8e489-157">Eles também poderão fazer chamadas de recebimento para e de outros sistemas que não roteiam chamadas para a rede PSTN (ou seja, um ponto de extremidade conectado a um PBX diferente), independentemente do site de rede ao qual o sistema está associado.</span><span class="sxs-lookup"><span data-stu-id="8e489-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="8e489-158">Todas as chamadas de entrada, chamadas de saída, transferências de chamadas e encaminhamento de chamadas que envolvem pontos de extremidade PSTN serão sujeitas a enforces de roteamento com base no local.</span><span class="sxs-lookup"><span data-stu-id="8e489-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="8e489-159">Essas chamadas devem usar somente gateways PSTN definidos como locais para esses sistemas.</span><span class="sxs-lookup"><span data-stu-id="8e489-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="8e489-160">A tabela a seguir ilustra a configuração de tronco de quatro troncos em dois locais de rede diferentes: dois conectados a gateways PSTN e dois conectados a sistemas PBX.</span><span class="sxs-lookup"><span data-stu-id="8e489-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8e489-161">Nome</span><span class="sxs-lookup"><span data-stu-id="8e489-161">Name</span></span></th>
<th><span data-ttu-id="8e489-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="8e489-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="8e489-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="8e489-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e489-164">PstnGateway: tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="8e489-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="8e489-165">True</span><span class="sxs-lookup"><span data-stu-id="8e489-165">True</span></span></p></td>
<td><p><span data-ttu-id="8e489-166">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8e489-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e489-167">PstnGateway: tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="8e489-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="8e489-168">True</span><span class="sxs-lookup"><span data-stu-id="8e489-168">True</span></span></p></td>
<td><p><span data-ttu-id="8e489-169">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8e489-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e489-170">PstnGateway: trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="8e489-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="8e489-171">Falso</span><span class="sxs-lookup"><span data-stu-id="8e489-171">False</span></span></p></td>
<td><p><span data-ttu-id="8e489-172">Site 1 (Déli)</span><span class="sxs-lookup"><span data-stu-id="8e489-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e489-173">PstnGateway: tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="8e489-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="8e489-174">Falso</span><span class="sxs-lookup"><span data-stu-id="8e489-174">False</span></span></p></td>
<td><p><span data-ttu-id="8e489-175">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8e489-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="8e489-176">Habilitar roteamento baseado em local para políticas de voz</span><span class="sxs-lookup"><span data-stu-id="8e489-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="8e489-177">Para impor o roteamento baseado em local a usuários específicos, configure a política de voz dos usuários para evitar o bypass de chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="8e489-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="8e489-178">Use o comando do Windows PowerShell do Lync Server, New-CsVoicePolicy, para criar uma nova política de voz ou Set-CsVoicePolicy, se estiver usando uma política existente, para habilitar o roteamento baseado em local, impedindo o desvio de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="8e489-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="8e489-179">Para obter mais informações, consulte [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="8e489-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="8e489-180">Para este exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram a prevenção de bypass de chamadas PSTN para as políticas de voz de Déli e Hyderabad definidas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="8e489-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="8e489-181">Somente as configurações específicas do roteamento baseado em local são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="8e489-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="8e489-182">Política de voz 1</span><span class="sxs-lookup"><span data-stu-id="8e489-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="8e489-183">Política de voz 2</span><span class="sxs-lookup"><span data-stu-id="8e489-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e489-184">ID da política de voz</span><span class="sxs-lookup"><span data-stu-id="8e489-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="8e489-185">Política de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="8e489-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="8e489-186">Política de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="8e489-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e489-187">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="8e489-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="8e489-188">Uso de Delhi, uso de PBX, uso do PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="8e489-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="8e489-189">Uso do Hyderabad, uso do PBX Hyd, uso do PBX</span><span class="sxs-lookup"><span data-stu-id="8e489-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e489-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="8e489-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="8e489-191">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="8e489-191">True</span></span></p></td>
<td><p><span data-ttu-id="8e489-192">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="8e489-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="8e489-193">Habilitar o roteamento baseado em local na configuração de roteamento</span><span class="sxs-lookup"><span data-stu-id="8e489-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="8e489-194">Por fim, habilite globalmente o roteamento baseado em local para sua configuração de roteamento.</span><span class="sxs-lookup"><span data-stu-id="8e489-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="8e489-195">Use o comando do Windows PowerShell do Lync Server, New-CsRoutingConfiguration, para habilitar o roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="8e489-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="8e489-196">Para obter mais informações, consulte [set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8e489-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e489-197">Embora o roteamento baseado em local deva ser habilitado por meio de uma configuração global, o conjunto de regras a ser aplicado só será imposto para os sites, os usuários e os troncos para os quais foram configurados conforme especificado nesta documentação.</span><span class="sxs-lookup"><span data-stu-id="8e489-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e489-198">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e489-198">See Also</span></span>


[<span data-ttu-id="8e489-199">Configurando o roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e489-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

