---
title: 'Lync Server 2013: roteamento baseado em localização e transferências de chamadas consultivas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7c7b73efb670c5569b8c4600c1759e981cda211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="c731b-102">Roteamento baseado em localização e transferências de chamadas consultivas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c731b-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c731b-103">_**Tópico da última modificação:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="c731b-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="c731b-104">Além de aplicar o roteamento baseado em localização a reuniões do Lync, o aplicativo de conferência de roteamento baseado em localização impõe restrições de roteamento baseado em localização em transferências de chamadas consuldas que entram em pontos de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="c731b-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="c731b-105">Uma transferência de chamada consultiva é estabelecida entre duas partes em que uma delas transfere a chamada para um novo usuário.</span><span class="sxs-lookup"><span data-stu-id="c731b-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="c731b-106">Por exemplo, um ponto de extremidade PSTN chama o usuário A (chamado do Lync).</span><span class="sxs-lookup"><span data-stu-id="c731b-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="c731b-107">O usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (usuário do Lync).</span><span class="sxs-lookup"><span data-stu-id="c731b-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="c731b-108">O usuário A coloca a chamada com o usuário PSTN em espera e liga para o usuário B. O usuário B concorda em falar com o usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="c731b-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="c731b-109">O usuário A transfere a chamada espera para o usuário B.</span><span class="sxs-lookup"><span data-stu-id="c731b-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="c731b-110">**Fluxo da Transferência de Chamada Consultiva**</span><span class="sxs-lookup"><span data-stu-id="c731b-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="c731b-111">![Roteamento baseado em local para o diagrama de conferência] (images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Roteamento baseado em local para o diagrama de conferência")</span><span class="sxs-lookup"><span data-stu-id="c731b-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="c731b-112">Quando um usuário habilitado para roteamento baseado em local inicia uma transferência de chamadas consultivas de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e o usuário do Lync A e a outra entre o usuário do Lync A e o usuário do Lync B. o comportamento a seguir é imposto pelo aplicativo de conferência de roteamento baseado em localização:</span><span class="sxs-lookup"><span data-stu-id="c731b-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="c731b-113">Se o encaminhamento de tronco SIP a chamada PSTN estiver autorizada a redirecionar a chamada PSTN para o site de rede onde o usuário do Lync B (ou seja, destino da transferência) estiver localizado, a transferência de chamada será permitida; caso contrário, a transferência de chamadas consultivas será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="c731b-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="c731b-114">Essa autorização é realizada caso o local da parte transferida seja no mesmo local de rede do tronco SIP que está encaminhando a chamada ativa para o ponto de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="c731b-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="c731b-115">Se o tronco SIP que faz a chamada PSTN não estiver autorizado a encaminhar chamadas para o site de rede onde a parte transferida (usuário B do Lync) estiver localizada ou a parte transferidas estiver localizada em um site de rede desconhecido, a transferência de chamadas Consul para a PSTN o ponto de extremidade (ou seja, destino de transferência de chamada) será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="c731b-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="c731b-116">A tabela a seguir descreve como as restrições de roteamento baseadas em localização são aplicadas pelo aplicativo de videoconferência baseado em localização para transferências de chamadas consultivas.</span><span class="sxs-lookup"><span data-stu-id="c731b-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="c731b-117">Embora os pontos de extremidade PBX não estejam associados diretamente a um local de rede, o tronco SIP ao qual o PBX está conectado pode ser atribuído a um local de rede.</span><span class="sxs-lookup"><span data-stu-id="c731b-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="c731b-118">Portanto, o ponto de extremidade PBX pode ser indiretamente associado a um local de rede.</span><span class="sxs-lookup"><span data-stu-id="c731b-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c731b-119">Local de rede da parte transferida da chamada</span><span class="sxs-lookup"><span data-stu-id="c731b-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="c731b-120">Local de rede de destino da transferência de chamada</span><span class="sxs-lookup"><span data-stu-id="c731b-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="c731b-121">Comportamento</span><span class="sxs-lookup"><span data-stu-id="c731b-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c731b-122">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c731b-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c731b-123">Usuário do Lync no mesmo local de rede (por exemplo, site 1)</span><span class="sxs-lookup"><span data-stu-id="c731b-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c731b-124">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c731b-125">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c731b-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c731b-126">Usuário do Lync em sites de rede diferentes (por exemplo, site 2)</span><span class="sxs-lookup"><span data-stu-id="c731b-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c731b-127">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c731b-128">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c731b-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c731b-129">Usuário do Lync em um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="c731b-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="c731b-130">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c731b-131">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c731b-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c731b-132">Usuário do Lync federado</span><span class="sxs-lookup"><span data-stu-id="c731b-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="c731b-133">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c731b-134">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c731b-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c731b-135">Ponto de extremidade do PBX no mesmo local (isto é, local 1)</span><span class="sxs-lookup"><span data-stu-id="c731b-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c731b-136">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c731b-137">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c731b-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c731b-138">Ponto de extremidade PBX em locais diferentes (isto é, local 2)</span><span class="sxs-lookup"><span data-stu-id="c731b-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c731b-139">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c731b-140">Ponto de extremidade do PBX no mesmo local (isto é, local 1)</span><span class="sxs-lookup"><span data-stu-id="c731b-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c731b-141">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c731b-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c731b-142">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c731b-143">Ponto de extremidade do PBX em locais diferentes (i.e. local 2)</span><span class="sxs-lookup"><span data-stu-id="c731b-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c731b-144">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="c731b-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="c731b-145">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c731b-146">Ponto de extremidade PBX em qualquer local</span><span class="sxs-lookup"><span data-stu-id="c731b-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c731b-147">Usuário do Lync no mesmo local de rede (por exemplo, site 1)</span><span class="sxs-lookup"><span data-stu-id="c731b-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="c731b-148">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c731b-149">Ponto de extremidade PBX em qualquer local</span><span class="sxs-lookup"><span data-stu-id="c731b-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c731b-150">Usuário do Lync em sites de rede diferentes (por exemplo, site 2)</span><span class="sxs-lookup"><span data-stu-id="c731b-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="c731b-151">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c731b-152">Ponto de extremidade PBX em qualquer local</span><span class="sxs-lookup"><span data-stu-id="c731b-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c731b-153">Usuário do Lync em um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="c731b-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="c731b-154">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c731b-155">Ponto de extremidade PBX em qualquer local</span><span class="sxs-lookup"><span data-stu-id="c731b-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="c731b-156">Usuário do Lync federado</span><span class="sxs-lookup"><span data-stu-id="c731b-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="c731b-157">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="c731b-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

