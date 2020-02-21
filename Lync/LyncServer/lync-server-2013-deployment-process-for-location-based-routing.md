---
title: 'Lync Server 2013: processo de implantação para roteamento baseado em local'
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
ms.openlocfilehash: 08def9741ad6ba4f91759e88a38fccdea0d44333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="05912-102">Processo de implantação para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05912-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05912-103">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="05912-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="05912-104">Este tópico fornece uma visão geral do processo envolvido na configuração do roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="05912-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="05912-105">Você deve implantar o Lync Server Enterprise Edition ou Standard Edition com o Enterprise Voice antes de configurar o roteamento baseado no local.</span><span class="sxs-lookup"><span data-stu-id="05912-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="05912-106">Os componentes exigidos pelo roteamento baseado em local já estão instalados e habilitados quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="05912-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="05912-107">Processo de implantação de roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05912-108">Fase</span><span class="sxs-lookup"><span data-stu-id="05912-108">Phase</span></span></th>
<th><span data-ttu-id="05912-109">Etapas</span><span class="sxs-lookup"><span data-stu-id="05912-109">Steps</span></span></th>
<th><span data-ttu-id="05912-110">Grupos e funções exigidos</span><span class="sxs-lookup"><span data-stu-id="05912-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="05912-111">Documentação da implantação</span><span class="sxs-lookup"><span data-stu-id="05912-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05912-112">Implantar o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="05912-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="05912-113">Configurar troncos</span><span class="sxs-lookup"><span data-stu-id="05912-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="05912-114">Criar políticas de voz</span><span class="sxs-lookup"><span data-stu-id="05912-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="05912-115">Definir rotas de voz</span><span class="sxs-lookup"><span data-stu-id="05912-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="05912-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="05912-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="05912-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="05912-117">CsAdministrator</span></span><br />
<span data-ttu-id="05912-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="05912-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="05912-119">Implantando o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="05912-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05912-120">Verificar a implantação do Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="05912-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05912-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="05912-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="05912-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="05912-122">CsAdministrator</span></span><br />
<span data-ttu-id="05912-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="05912-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05912-124">Configurar regiões de rede, sites e sub-redes</span><span class="sxs-lookup"><span data-stu-id="05912-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="05912-125">Criar regiões de rede</span><span class="sxs-lookup"><span data-stu-id="05912-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="05912-126">Criar sites de rede</span><span class="sxs-lookup"><span data-stu-id="05912-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="05912-127">Associa sub-redes a sites de rede</span><span class="sxs-lookup"><span data-stu-id="05912-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="05912-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="05912-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="05912-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="05912-129">CsAdministrator</span></span><br />
<span data-ttu-id="05912-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="05912-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="05912-131">Sobre regiões de rede, sites e sub-redes</span><span class="sxs-lookup"><span data-stu-id="05912-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="05912-132">Criar ou modificar uma região de rede</span><span class="sxs-lookup"><span data-stu-id="05912-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="05912-133">Criar ou modificar um local de rede</span><span class="sxs-lookup"><span data-stu-id="05912-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="05912-134">Associar uma subrede a um local de rede</span><span class="sxs-lookup"><span data-stu-id="05912-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05912-135">Configurar roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="05912-136">Criar políticas de roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="05912-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="05912-137">Definir configuração de tronco separada por tronco</span><span class="sxs-lookup"><span data-stu-id="05912-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="05912-138">Modificar políticas de voz</span><span class="sxs-lookup"><span data-stu-id="05912-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="05912-139">Habilitar configuração de roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="05912-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="05912-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="05912-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="05912-141">CsAdministrator</span></span><br />
<span data-ttu-id="05912-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="05912-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="05912-143">Implantação de amostra</span><span class="sxs-lookup"><span data-stu-id="05912-143">Sample Deployment</span></span>

<span data-ttu-id="05912-144">A implantação a seguir é usada para ilustrar mais os mecanismos habilitados pelo roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="05912-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="05912-145">![e1bd2230-44da-4784-B359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-B359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="05912-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="05912-146">Chamadas PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="05912-146">Incoming PSTN calls</span></span>

<span data-ttu-id="05912-147">Um administrador pode habilitar o tronco definido para rotear chamadas para o "gateway do site 1" para o roteamento baseado em local e associar o "gateway do site 1" ao site 1.</span><span class="sxs-lookup"><span data-stu-id="05912-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="05912-148">Uma vez habilitado, as chamadas que são roteadas através do "gateway do site 1" serão roteadas apenas para os usuários localizados no site 1.</span><span class="sxs-lookup"><span data-stu-id="05912-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="05912-149">Todas as chamadas encaminhadas pelo tronco "gateway do site 1" destinado a usuários em um site diferente, como o site 2, serão bloqueadas para evitar o bypass de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="05912-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="05912-150">Todas as chamadas PSTN de entrada através do "gateway do site 1" só poderão ser roteadas para pontos de extremidade localizados no site 1.</span><span class="sxs-lookup"><span data-stu-id="05912-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="05912-151">Por exemplo, quando "o usuário 1 do Lync" passa para o site 2, todas as chamadas PSTN de entrada através do "gateway do site 1" não serão encaminhadas para os pontos de extremidade "usuário do Lync 1" localizados no site 2.</span><span class="sxs-lookup"><span data-stu-id="05912-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="05912-152">A mesma regra de roteamento se aplica se o "usuário do Lync 1" viajar para um local de rede desconhecido onde o local do usuário não pode ser determinado.</span><span class="sxs-lookup"><span data-stu-id="05912-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="05912-153">A tabela a seguir descreve a experiência do usuário "Lync user 1" neste contexto.</span><span class="sxs-lookup"><span data-stu-id="05912-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="05912-154">Pontos de extremidade do usuário 1 do Lync localizados no local de rede 1</span><span class="sxs-lookup"><span data-stu-id="05912-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="05912-155">Pontos de extremidade do usuário 1 do Lync localizados no local de rede 2</span><span class="sxs-lookup"><span data-stu-id="05912-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="05912-156">Pontos de extremidade de usuário 1 do Lync localizados no site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="05912-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05912-157">Chamadas PSTN de entrada para o usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="05912-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="05912-158">As chamadas são roteadas para pontos de extremidade neste local</span><span class="sxs-lookup"><span data-stu-id="05912-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="05912-159">As chamadas não são encaminhadas para pontos de extremidade neste local</span><span class="sxs-lookup"><span data-stu-id="05912-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="05912-160">As chamadas não são encaminhadas para pontos de extremidade neste local</span><span class="sxs-lookup"><span data-stu-id="05912-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="05912-161">Chamadas PSTN de saída</span><span class="sxs-lookup"><span data-stu-id="05912-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="05912-162">As rotas de voz são referenciadas nas políticas de voz atribuídas diretamente aos usuários e as políticas de roteamento de voz atribuídas a sites de rede.</span><span class="sxs-lookup"><span data-stu-id="05912-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="05912-163">Ambas as políticas contêm referências a rotas, que podem ser usadas para rotear uma chamada de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="05912-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="05912-164">Por exemplo, um administrador pode definir uma política de roteamento de voz para todos os usuários localizados no local de rede 1 para rotear todas as chamadas de saída através do "gateway do site 1" enquanto a política de voz de alguns usuários define uma rota para todas as chamadas de saída através do "gateway do site 2".</span><span class="sxs-lookup"><span data-stu-id="05912-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="05912-165">Enquanto esses usuários estão localizados no local de rede 1, suas chamadas de saída serão roteadas pelo "gateway do site 1".</span><span class="sxs-lookup"><span data-stu-id="05912-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="05912-166">Quando um usuário está localizado em um site de rede configurado para roteamento baseado em local, a rota da política de roteamento de voz do site de rede substitui a rota de política de voz do usuário.</span><span class="sxs-lookup"><span data-stu-id="05912-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="05912-167">Essa regra é particularmente útil para usuários que se movem temporariamente para um site diferente.</span><span class="sxs-lookup"><span data-stu-id="05912-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="05912-168">Neste caso específico, um usuário sempre usará um gateway local para seu local; Se o "usuário do Lync 3" estiver localizado em "site 2", todas as chamadas de saída serão encaminhadas por meio de "gateway do site 2", mas se ele viajar para o site 1, todas as chamadas de saída feitas enquanto ele está no site 1 serão roteadas pelo "gateway do site 1".</span><span class="sxs-lookup"><span data-stu-id="05912-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="05912-169">A tabela a seguir ilustra a experiência do usuário do Lync usuário 1 fazendo uma chamada de saída dos seguintes sites de rede.</span><span class="sxs-lookup"><span data-stu-id="05912-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="05912-170">Local de rede 1</span><span class="sxs-lookup"><span data-stu-id="05912-170">Network site 1</span></span></th>
<th><span data-ttu-id="05912-171">Local de rede 2</span><span class="sxs-lookup"><span data-stu-id="05912-171">Network site 2</span></span></th>
<th><span data-ttu-id="05912-172">Local de rede desconhecido ou não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05912-173">Autorização de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="05912-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="05912-174">Política de voz do usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="05912-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="05912-175">Política de voz do usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="05912-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="05912-176">Política de voz do usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="05912-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05912-177">Roteamento de chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="05912-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="05912-178">Política de roteamento de voz do site 1</span><span class="sxs-lookup"><span data-stu-id="05912-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="05912-179">Política de roteamento de voz do site 2</span><span class="sxs-lookup"><span data-stu-id="05912-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="05912-180">Política de voz do usuário e somente para sistemas não habilitados para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="05912-181">Transferências de chamadas e encaminhamentos</span><span class="sxs-lookup"><span data-stu-id="05912-181">Call transfers and forwards</span></span>

<span data-ttu-id="05912-182">Quando as chamadas são transferidas ou encaminhadas, o roteamento de chamadas é afetado pelo roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="05912-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="05912-183">A tabela a seguir mostra a transferência ou o encaminhamento de uma chamada PSTN para outro usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="05912-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05912-184">Usuário Iniciando transferência de chamada ou encaminhamento</span><span class="sxs-lookup"><span data-stu-id="05912-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="05912-185">Usuário do Lync 2</span><span class="sxs-lookup"><span data-stu-id="05912-185">Lync user 2</span></span></th>
<th><span data-ttu-id="05912-186">Usuário do Lync 4</span><span class="sxs-lookup"><span data-stu-id="05912-186">Lync user 4</span></span></th>
<th><span data-ttu-id="05912-187">Usuário do Lync no local de rede não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05912-188">Usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="05912-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="05912-189">Encaminhamento ou transferência de chamada permitido</span><span class="sxs-lookup"><span data-stu-id="05912-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="05912-190">Encaminhamento ou transferência de chamada não permitido</span><span class="sxs-lookup"><span data-stu-id="05912-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="05912-191">Encaminhamento ou transferência de chamada não permitido</span><span class="sxs-lookup"><span data-stu-id="05912-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="05912-192">A tabela a seguir ilustra como o roteamento baseado em local afeta como a chamada é roteada com base no local do usuário do Lync que está sendo transferido (usuário do Lync 2, usuário do Lync 4 etc.) para um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="05912-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05912-193">Ponto de extremidade onde a chamada é transferida ou encaminhada para</span><span class="sxs-lookup"><span data-stu-id="05912-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="05912-194">Usuário do Lync 2</span><span class="sxs-lookup"><span data-stu-id="05912-194">Lync user 2</span></span></th>
<th><span data-ttu-id="05912-195">Usuário do Lync 4</span><span class="sxs-lookup"><span data-stu-id="05912-195">Lync user 4</span></span></th>
<th><span data-ttu-id="05912-196">Usuário do Lync no local de rede não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05912-197">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="05912-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="05912-198">Encaminhamento ou transferência de chamada é roteado através da política de roteamento de voz do site 1 e egresso por meio do gateway do site 1</span><span class="sxs-lookup"><span data-stu-id="05912-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="05912-199">Encaminhamento ou transferência de chamada é roteado por meio da política de roteamento de voz do site 2 e egresso por meio do gateway do local</span><span class="sxs-lookup"><span data-stu-id="05912-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="05912-200">Encaminhamento ou transferência de chamada é roteado através da política de voz de usuário do Lync e egresso por meio de um gateway não habilitado para roteamento baseado em local (se disponível)</span><span class="sxs-lookup"><span data-stu-id="05912-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="05912-201">Toque simultâneo</span><span class="sxs-lookup"><span data-stu-id="05912-201">Simultaneous ringing</span></span>

<span data-ttu-id="05912-202">Quando o roteamento baseado em local é configurado na topologia de exemplo, as seguintes interações são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="05912-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="05912-203">A tabela a seguir ilustra se o roteamento baseado em local permite o toque simultâneo para diferentes usuários do Lync (ou seja, usuário do Lync 2, usuário do Lync 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="05912-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05912-204">Destino da chamada PSTN de entrada</span><span class="sxs-lookup"><span data-stu-id="05912-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="05912-205">Usuário do Lync 2</span><span class="sxs-lookup"><span data-stu-id="05912-205">Lync user 2</span></span></th>
<th><span data-ttu-id="05912-206">Usuário do Lync 4</span><span class="sxs-lookup"><span data-stu-id="05912-206">Lync user 4</span></span></th>
<th><span data-ttu-id="05912-207">Usuário do Lync no local de rede não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05912-208">Usuário 1 do Lync</span><span class="sxs-lookup"><span data-stu-id="05912-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="05912-209">O toque simultâneo é permitido</span><span class="sxs-lookup"><span data-stu-id="05912-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="05912-210">O toque simultâneo não é permitido</span><span class="sxs-lookup"><span data-stu-id="05912-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="05912-211">O toque simultâneo não é permitido</span><span class="sxs-lookup"><span data-stu-id="05912-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="05912-212">A tabela a seguir ilustra se o roteamento baseado em local permite o toque simultâneo para um ponto de extremidade PSTN de diferentes usuários do Lync (ou seja, usuário do Lync 2, usuário do Lync 4, etc.).</span><span class="sxs-lookup"><span data-stu-id="05912-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05912-213">Alvo de anel simultâneo</span><span class="sxs-lookup"><span data-stu-id="05912-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="05912-214">Usuário do Lync 2</span><span class="sxs-lookup"><span data-stu-id="05912-214">Lync user 2</span></span></th>
<th><span data-ttu-id="05912-215">Usuário do Lync 4</span><span class="sxs-lookup"><span data-stu-id="05912-215">Lync user 4</span></span></th>
<th><span data-ttu-id="05912-216">Usuário do Lync no local de rede não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05912-217">Celular do Lync user 1 (ponto de extremidade PSTN)</span><span class="sxs-lookup"><span data-stu-id="05912-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="05912-218">Chamada roteada pela política de roteamento de voz do site 1 de rede e egresso por meio do gateway do site 1</span><span class="sxs-lookup"><span data-stu-id="05912-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="05912-219">Chamada roteada por meio da política de roteamento de voz do site 2 de rede e saída por meio do gateway do site 2</span><span class="sxs-lookup"><span data-stu-id="05912-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="05912-220">Chamada roteada através da política de voz do chamador e será egresso por meio de um gateway PSTN não habilitado para roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="05912-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="05912-221">Confira também</span><span class="sxs-lookup"><span data-stu-id="05912-221">See Also</span></span>


[<span data-ttu-id="05912-222">Planejamento de roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05912-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

