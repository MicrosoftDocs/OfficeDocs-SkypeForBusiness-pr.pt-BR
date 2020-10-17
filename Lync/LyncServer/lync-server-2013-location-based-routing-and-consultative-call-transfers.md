---
title: 'Lync Server 2013: Location-Based roteamento e transferências de chamadas consultivas'
description: 'Lync Server 2013: Location-Based transferência de chamadas de roteamento e consultoria.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567667"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="1e029-103">Location-Based transferências de chamadas de roteamento e consultoria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e029-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e029-104">_**Última modificação do tópico:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="1e029-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="1e029-105">Além de impor Location-Based roteamento às reuniões do Lync, o Location-Based aplicativo de conferência de roteamento impõe Location-Based restrições de roteamento em transferências de chamadas consuldas que entram em pontos de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="1e029-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="1e029-106">Uma transferência de chamada consultiva é estabelecida entre duas partes em que uma das partes transfere a chamada para um novo usuário.</span><span class="sxs-lookup"><span data-stu-id="1e029-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="1e029-107">Por exemplo, um ponto de extremidade PSTN chama usuário A (Lync chamado).</span><span class="sxs-lookup"><span data-stu-id="1e029-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="1e029-108">O usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (usuário do Lync).</span><span class="sxs-lookup"><span data-stu-id="1e029-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="1e029-109">O usuário A coloca a chamada com o usuário PSTN em espera e chama o usuário B. o usuário B concorda em falar com o usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="1e029-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="1e029-110">O usuário A transfere a chamada em espera para o usuário B.</span><span class="sxs-lookup"><span data-stu-id="1e029-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="1e029-111">**Fluxo de chamadas de transferência de chamadas consultivas**</span><span class="sxs-lookup"><span data-stu-id="1e029-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="1e029-112">![Roteamento baseado em local para o diagrama de conferência](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Roteamento baseado em local para o diagrama de conferência")</span><span class="sxs-lookup"><span data-stu-id="1e029-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="1e029-113">Quando um usuário habilitado para roteamento de Location-Based inicia uma transferência de chamada consultiva de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e o usuário do Lync A e a outra entre o usuário do Lync e o usuário B. o seguinte comportamento é imposto pelo aplicativo de conferência de roteamento de Location-Based:</span><span class="sxs-lookup"><span data-stu-id="1e029-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="1e029-114">Se o roteamento de tronco SIP, a chamada PSTN é autorizada a encaminhar novamente a chamada PSTN para o local de rede onde o usuário B do Lync (ou seja, destino da transferência) está localizado, a transferência de chamada será permitida; caso contrário, a transferência de chamadas consuldas será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="1e029-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="1e029-115">Essa autorização é executada com base no local da parte transferida que está no mesmo local de rede que o tronco SIP que está encaminhando a chamada ativa para o ponto de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="1e029-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="1e029-116">Se o tronco SIP encaminhar a chamada PSTN de entrada não tiver autorização para rotear chamadas para o local de rede onde a parte transferida (usuário B) está localizada ou a parte transferida está localizada em um site de rede desconhecido, a transferência de chamada consultiva para o ponto de extremidade PSTN (ou seja, destino da transferência de chamada) será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="1e029-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="1e029-117">A tabela a seguir descreve como Location-Based restrições de roteamento são aplicadas pelo aplicativo de conferência de roteamento de Location-Based para transferências de chamadas consultivas.</span><span class="sxs-lookup"><span data-stu-id="1e029-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="1e029-118">Embora os pontos de extremidade PBX não estejam diretamente associados a um site de rede, o tronco SIP ao qual o PBX está conectado pode ser atribuído a um local de rede.</span><span class="sxs-lookup"><span data-stu-id="1e029-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="1e029-119">Portanto, o ponto de extremidade de PBX pode ser indiretamente associado a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="1e029-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e029-120">Site de rede da parte transferida por chamada</span><span class="sxs-lookup"><span data-stu-id="1e029-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="1e029-121">Local de rede do destino da transferência de chamadas</span><span class="sxs-lookup"><span data-stu-id="1e029-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="1e029-122">Comportamento</span><span class="sxs-lookup"><span data-stu-id="1e029-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e029-123">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="1e029-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1e029-124">Usuário do Lync no mesmo local de rede (por exemplo, site 1)</span><span class="sxs-lookup"><span data-stu-id="1e029-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="1e029-125">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e029-126">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="1e029-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1e029-127">Usuário do Lync em diferentes sites de rede (por exemplo, site 2)</span><span class="sxs-lookup"><span data-stu-id="1e029-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="1e029-128">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e029-129">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="1e029-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1e029-130">Usuário do Lync em um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="1e029-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="1e029-131">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e029-132">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="1e029-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1e029-133">Usuário do Lync federado</span><span class="sxs-lookup"><span data-stu-id="1e029-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="1e029-134">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e029-135">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="1e029-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1e029-136">Ponto de extremidade de PBX no mesmo site (ou seja, site 1)</span><span class="sxs-lookup"><span data-stu-id="1e029-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="1e029-137">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e029-138">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="1e029-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1e029-139">Ponto de extremidade de PBX em sites diferentes (por exemplo, site 2)</span><span class="sxs-lookup"><span data-stu-id="1e029-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="1e029-140">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e029-141">Ponto de extremidade de PBX no mesmo site (ou seja, site 1)</span><span class="sxs-lookup"><span data-stu-id="1e029-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="1e029-142">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="1e029-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1e029-143">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e029-144">Ponto de extremidade de PBX em um site diferente (ou seja, site 2)</span><span class="sxs-lookup"><span data-stu-id="1e029-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="1e029-145">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="1e029-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1e029-146">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e029-147">Ponto de extremidade de PBX em qualquer site</span><span class="sxs-lookup"><span data-stu-id="1e029-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="1e029-148">Usuário do Lync no mesmo local de rede (por exemplo, site 1)</span><span class="sxs-lookup"><span data-stu-id="1e029-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="1e029-149">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e029-150">Ponto de extremidade de PBX em qualquer site</span><span class="sxs-lookup"><span data-stu-id="1e029-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="1e029-151">Usuário do Lync em diferentes sites de rede (por exemplo, site 2)</span><span class="sxs-lookup"><span data-stu-id="1e029-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="1e029-152">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e029-153">Ponto de extremidade de PBX em qualquer site</span><span class="sxs-lookup"><span data-stu-id="1e029-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="1e029-154">Usuário do Lync em um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="1e029-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="1e029-155">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e029-156">Ponto de extremidade de PBX em qualquer site</span><span class="sxs-lookup"><span data-stu-id="1e029-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="1e029-157">Usuário do Lync federado</span><span class="sxs-lookup"><span data-stu-id="1e029-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="1e029-158">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="1e029-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

