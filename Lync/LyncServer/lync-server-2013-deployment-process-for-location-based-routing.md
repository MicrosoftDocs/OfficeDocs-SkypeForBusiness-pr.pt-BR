---
title: 'Lync Server 2013: processo de implantação para roteamento Location-Based'
description: 'Lync Server 2013: processo de implantação para roteamento Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c321d9b0eada6e9501b2ded69120feae36be171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551057"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="c5773-103">Processo de implantação para roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5773-103">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5773-104">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="c5773-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="c5773-105">Este tópico fornece uma visão geral do processo envolvido na configuração do roteamento do Location-Based.</span><span class="sxs-lookup"><span data-stu-id="c5773-105">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="c5773-106">Você deve implantar o Lync Server Enterprise Edition ou Standard Edition com o Enterprise Voice antes de configurar o roteamento do Location-Based.</span><span class="sxs-lookup"><span data-stu-id="c5773-106">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="c5773-107">Os componentes exigidos pelo roteamento Location-Based já estão instalados e habilitados quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c5773-107">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="c5773-108">Location-Based processo de implantação de roteamento</span><span class="sxs-lookup"><span data-stu-id="c5773-108">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5773-109">Fase</span><span class="sxs-lookup"><span data-stu-id="c5773-109">Phase</span></span></th>
<th><span data-ttu-id="c5773-110">Etapas</span><span class="sxs-lookup"><span data-stu-id="c5773-110">Steps</span></span></th>
<th><span data-ttu-id="c5773-111">Grupos e funções exigidos</span><span class="sxs-lookup"><span data-stu-id="c5773-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="c5773-112">Documentação da implantação</span><span class="sxs-lookup"><span data-stu-id="c5773-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5773-113">Implantar o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c5773-113">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c5773-114">Configurar troncos</span><span class="sxs-lookup"><span data-stu-id="c5773-114">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="c5773-115">Criar políticas de voz</span><span class="sxs-lookup"><span data-stu-id="c5773-115">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="c5773-116">Definir rotas de voz</span><span class="sxs-lookup"><span data-stu-id="c5773-116">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c5773-117">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="c5773-117">CSVoiceAdmins</span></span><br />
<span data-ttu-id="c5773-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c5773-118">CsAdministrator</span></span><br />
<span data-ttu-id="c5773-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c5773-119">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c5773-120">Implantando o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c5773-120">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5773-121">Verificar a implantação do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c5773-121">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c5773-122">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="c5773-122">CSVoiceAdmins</span></span><br />
<span data-ttu-id="c5773-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c5773-123">CsAdministrator</span></span><br />
<span data-ttu-id="c5773-124">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c5773-124">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c5773-125">Configurar regiões de rede, sites e sub-redes</span><span class="sxs-lookup"><span data-stu-id="c5773-125">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c5773-126">Criar regiões de rede</span><span class="sxs-lookup"><span data-stu-id="c5773-126">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="c5773-127">Criar sites de rede</span><span class="sxs-lookup"><span data-stu-id="c5773-127">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="c5773-128">Associa sub-redes a sites de rede</span><span class="sxs-lookup"><span data-stu-id="c5773-128">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c5773-129">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="c5773-129">CSVoiceAdmins</span></span><br />
<span data-ttu-id="c5773-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c5773-130">CsAdministrator</span></span><br />
<span data-ttu-id="c5773-131">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c5773-131">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="c5773-132">Sobre regiões de rede, sites e sub-redes</span><span class="sxs-lookup"><span data-stu-id="c5773-132">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="c5773-133">Criar ou modificar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="c5773-133">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="c5773-134">Criar ou modificar um local de rede</span><span class="sxs-lookup"><span data-stu-id="c5773-134">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="c5773-135">Associar uma subrede a um local de rede</span><span class="sxs-lookup"><span data-stu-id="c5773-135">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5773-136">Configurar roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="c5773-136">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c5773-137">Criar políticas de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="c5773-137">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="c5773-138">Definir configuração de tronco separada por tronco</span><span class="sxs-lookup"><span data-stu-id="c5773-138">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="c5773-139">Modificar políticas de voz</span><span class="sxs-lookup"><span data-stu-id="c5773-139">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="c5773-140">Habilitar Location-Based configuração de roteamento</span><span class="sxs-lookup"><span data-stu-id="c5773-140">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c5773-141">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="c5773-141">CSVoiceAdmins</span></span><br />
<span data-ttu-id="c5773-142">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c5773-142">CsAdministrator</span></span><br />
<span data-ttu-id="c5773-143">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="c5773-143">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="c5773-144">Implantação de amostra</span><span class="sxs-lookup"><span data-stu-id="c5773-144">Sample Deployment</span></span>

<span data-ttu-id="c5773-145">A implantação a seguir é usada para ilustrar mais os mecanismos habilitados pelo roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="c5773-145">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="c5773-146">![e1bd2230-44da-4784-B359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-B359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="c5773-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="c5773-147">Chamadas PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="c5773-147">Incoming PSTN calls</span></span>

<span data-ttu-id="c5773-148">Um administrador pode habilitar o tronco definido para rotear chamadas para o "gateway do site 1" para Location-Based roteamento e associar o "gateway do site 1" ao site 1.</span><span class="sxs-lookup"><span data-stu-id="c5773-148">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="c5773-149">Uma vez habilitado, as chamadas que são roteadas através do "gateway do site 1" serão roteadas apenas para os usuários localizados no site 1.</span><span class="sxs-lookup"><span data-stu-id="c5773-149">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="c5773-150">Todas as chamadas encaminhadas pelo tronco "gateway do site 1" destinado a usuários em um site diferente, como o site 2, serão bloqueadas para evitar o bypass de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="c5773-150">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="c5773-151">Todas as chamadas PSTN de entrada através do "gateway do site 1" só poderão ser roteadas para pontos de extremidade localizados no site 1.</span><span class="sxs-lookup"><span data-stu-id="c5773-151">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="c5773-152">Por exemplo, quando "o usuário 1 do Lync" passa para o site 2, todas as chamadas PSTN de entrada através do "gateway do site 1" não serão encaminhadas para os pontos de extremidade "usuário do Lync 1" localizados no site 2.</span><span class="sxs-lookup"><span data-stu-id="c5773-152">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="c5773-153">A mesma regra de roteamento se aplica se o "usuário do Lync 1" viajar para um local de rede desconhecido onde o local do usuário não pode ser determinado.</span><span class="sxs-lookup"><span data-stu-id="c5773-153">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="c5773-154">A tabela a seguir descreve a experiência do usuário "Lync user 1" neste contexto.</span><span class="sxs-lookup"><span data-stu-id="c5773-154">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="c5773-155">Pontos de extremidade do usuário 1 do Lync localizados no local de rede 1</span><span class="sxs-lookup"><span data-stu-id="c5773-155">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="c5773-156">Pontos de extremidade do usuário 1 do Lync localizados no local de rede 2</span><span class="sxs-lookup"><span data-stu-id="c5773-156">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="c5773-157">Pontos de extremidade de usuário 1 do Lync localizados no site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="c5773-157">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5773-158">Chamadas PSTN de entrada para o usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="c5773-158">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="c5773-159">As chamadas são roteadas para pontos de extremidade neste local</span><span class="sxs-lookup"><span data-stu-id="c5773-159">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="c5773-160">As chamadas não são encaminhadas para pontos de extremidade neste local</span><span class="sxs-lookup"><span data-stu-id="c5773-160">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="c5773-161">As chamadas não são encaminhadas para pontos de extremidade neste local</span><span class="sxs-lookup"><span data-stu-id="c5773-161">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="c5773-162">Chamadas PSTN de saída</span><span class="sxs-lookup"><span data-stu-id="c5773-162">Outgoing PSTN calls</span></span>

<span data-ttu-id="c5773-163">As rotas de voz são referenciadas nas políticas de voz atribuídas diretamente aos usuários e as políticas de roteamento de voz atribuídas a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="c5773-163">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="c5773-164">Ambas as políticas contêm referências a rotas, que podem ser usadas para rotear uma chamada de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="c5773-164">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="c5773-165">Por exemplo, um administrador pode definir uma política de roteamento de voz para todos os usuários localizados no local de rede 1 para rotear todas as chamadas de saída através do "gateway do site 1" enquanto a política de voz de alguns usuários define uma rota para todas as chamadas de saída através do "gateway do site 2".</span><span class="sxs-lookup"><span data-stu-id="c5773-165">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="c5773-166">Enquanto esses usuários estão localizados no local de rede 1, suas chamadas de saída serão roteadas pelo "gateway do site 1".</span><span class="sxs-lookup"><span data-stu-id="c5773-166">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="c5773-167">Quando um usuário está localizado em um site de rede configurado para roteamento de Location-Based, a rota de política de roteamento de voz do site de rede substitui a rota de política de voz do usuário.</span><span class="sxs-lookup"><span data-stu-id="c5773-167">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="c5773-168">Essa regra é particularmente útil para usuários que se movem temporariamente para um site diferente.</span><span class="sxs-lookup"><span data-stu-id="c5773-168">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="c5773-169">Neste caso específico, um usuário sempre usará um gateway local para seu local; Se o "usuário do Lync 3" estiver localizado em "site 2", todas as chamadas de saída serão encaminhadas por meio de "gateway do site 2", mas se ele viajar para o site 1, todas as chamadas de saída feitas enquanto ele está no site 1 serão roteadas pelo "gateway do site 1".</span><span class="sxs-lookup"><span data-stu-id="c5773-169">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="c5773-170">A tabela a seguir ilustra a experiência do usuário do Lync usuário 1 fazendo uma chamada de saída dos seguintes sites de rede.</span><span class="sxs-lookup"><span data-stu-id="c5773-170">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="c5773-171">Local de rede 1</span><span class="sxs-lookup"><span data-stu-id="c5773-171">Network site 1</span></span></th>
<th><span data-ttu-id="c5773-172">Local de rede 2</span><span class="sxs-lookup"><span data-stu-id="c5773-172">Network site 2</span></span></th>
<th><span data-ttu-id="c5773-173">Local de rede desconhecido ou não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="c5773-173">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5773-174">Autorização de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="c5773-174">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="c5773-175">Política de voz do usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="c5773-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="c5773-176">Política de voz do usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="c5773-176">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="c5773-177">Política de voz do usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="c5773-177">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c5773-178">Roteamento de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="c5773-178">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="c5773-179">Política de roteamento de voz do site 1</span><span class="sxs-lookup"><span data-stu-id="c5773-179">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="c5773-180">Política de roteamento de voz do site 2</span><span class="sxs-lookup"><span data-stu-id="c5773-180">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="c5773-181">Política de voz do usuário e somente para sistemas não habilitados para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="c5773-181">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="c5773-182">Transferências de chamadas e encaminhamentos</span><span class="sxs-lookup"><span data-stu-id="c5773-182">Call transfers and forwards</span></span>

<span data-ttu-id="c5773-183">Quando as chamadas são transferidas ou encaminhadas, o roteamento de chamadas é afetado pelo roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="c5773-183">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="c5773-184">A tabela a seguir mostra a transferência ou o encaminhamento de uma chamada PSTN para outro usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="c5773-184">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5773-185">Usuário Iniciando transferência de chamada ou encaminhamento</span><span class="sxs-lookup"><span data-stu-id="c5773-185">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="c5773-186">Usuário do Lync 2</span><span class="sxs-lookup"><span data-stu-id="c5773-186">Lync user 2</span></span></th>
<th><span data-ttu-id="c5773-187">Usuário do Lync 4</span><span class="sxs-lookup"><span data-stu-id="c5773-187">Lync user 4</span></span></th>
<th><span data-ttu-id="c5773-188">Usuário do Lync no local de rede não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="c5773-188">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5773-189">Usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="c5773-189">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="c5773-190">Encaminhamento ou transferência de chamada permitido</span><span class="sxs-lookup"><span data-stu-id="c5773-190">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="c5773-191">Encaminhamento ou transferência de chamada não permitido</span><span class="sxs-lookup"><span data-stu-id="c5773-191">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="c5773-192">Encaminhamento ou transferência de chamada não permitido</span><span class="sxs-lookup"><span data-stu-id="c5773-192">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="c5773-193">A tabela a seguir ilustra como Location-Based roteamento afeta como a chamada é roteada com base no local do usuário do Lync que está sendo transferido (usuário do Lync 2, usuário do Lync 4 etc.) para um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c5773-193">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5773-194">Ponto de extremidade onde a chamada é transferida ou encaminhada para</span><span class="sxs-lookup"><span data-stu-id="c5773-194">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="c5773-195">Usuário do Lync 2</span><span class="sxs-lookup"><span data-stu-id="c5773-195">Lync user 2</span></span></th>
<th><span data-ttu-id="c5773-196">Usuário do Lync 4</span><span class="sxs-lookup"><span data-stu-id="c5773-196">Lync user 4</span></span></th>
<th><span data-ttu-id="c5773-197">Usuário do Lync no local de rede não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="c5773-197">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5773-198">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c5773-198">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c5773-199">Encaminhamento ou transferência de chamada é roteado através da política de roteamento de voz do site 1 e egresso por meio do gateway do site 1</span><span class="sxs-lookup"><span data-stu-id="c5773-199">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="c5773-200">Encaminhamento ou transferência de chamada é roteado por meio da política de roteamento de voz do site 2 e egresso por meio do gateway do local</span><span class="sxs-lookup"><span data-stu-id="c5773-200">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="c5773-201">Encaminhamento ou transferência de chamada é roteado através da política de voz de usuário do Lync e egresso por meio de um gateway não habilitado para roteamento baseado em local (se disponível)</span><span class="sxs-lookup"><span data-stu-id="c5773-201">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="c5773-202">Toque simultâneo</span><span class="sxs-lookup"><span data-stu-id="c5773-202">Simultaneous ringing</span></span>

<span data-ttu-id="c5773-203">Quando o roteamento baseado em local é configurado na topologia de exemplo, as seguintes interações são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="c5773-203">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="c5773-204">A tabela a seguir ilustra se Location-Based roteamento permite o toque simultâneo para diferentes usuários do Lync (ou seja, usuário do Lync 2, usuário do Lync 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="c5773-204">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5773-205">Destino da chamada PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="c5773-205">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="c5773-206">Usuário do Lync 2</span><span class="sxs-lookup"><span data-stu-id="c5773-206">Lync user 2</span></span></th>
<th><span data-ttu-id="c5773-207">Usuário do Lync 4</span><span class="sxs-lookup"><span data-stu-id="c5773-207">Lync user 4</span></span></th>
<th><span data-ttu-id="c5773-208">Usuário do Lync no local de rede não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="c5773-208">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5773-209">Usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="c5773-209">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="c5773-210">O toque simultâneo é permitido</span><span class="sxs-lookup"><span data-stu-id="c5773-210">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="c5773-211">O toque simultâneo não é permitido</span><span class="sxs-lookup"><span data-stu-id="c5773-211">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="c5773-212">O toque simultâneo não é permitido</span><span class="sxs-lookup"><span data-stu-id="c5773-212">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="c5773-213">A tabela a seguir ilustra se Location-Based roteamento permite o toque simultâneo para um ponto de extremidade PSTN de diferentes usuários do Lync (ou seja, usuário do Lync 2, usuário do Lync 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="c5773-213">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c5773-214">Alvo de anel simultâneo</span><span class="sxs-lookup"><span data-stu-id="c5773-214">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="c5773-215">Usuário do Lync 2</span><span class="sxs-lookup"><span data-stu-id="c5773-215">Lync user 2</span></span></th>
<th><span data-ttu-id="c5773-216">Usuário do Lync 4</span><span class="sxs-lookup"><span data-stu-id="c5773-216">Lync user 4</span></span></th>
<th><span data-ttu-id="c5773-217">Usuário do Lync no local de rede não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="c5773-217">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c5773-218">Celular do Lync user 1 (ponto de extremidade PSTN)</span><span class="sxs-lookup"><span data-stu-id="c5773-218">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="c5773-219">Chamada roteada pela política de roteamento de voz do site 1 de rede e egresso por meio do gateway do site 1</span><span class="sxs-lookup"><span data-stu-id="c5773-219">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="c5773-220">Chamada roteada por meio da política de roteamento de voz do site 2 de rede e saída por meio do gateway do site 2</span><span class="sxs-lookup"><span data-stu-id="c5773-220">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="c5773-221">Chamada roteada através da política de voz do chamador e será egresso por meio de um gateway PSTN não habilitado para roteamento de Location-Based</span><span class="sxs-lookup"><span data-stu-id="c5773-221">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5773-222">Confira também</span><span class="sxs-lookup"><span data-stu-id="c5773-222">See Also</span></span>


[<span data-ttu-id="c5773-223">Planejamento de roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5773-223">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

