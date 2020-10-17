---
title: 'Lync Server 2013: Location-Based roteamento e transferências de chamadas consultivas'
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
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513808"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="fdf89-102">Location-Based transferências de chamadas de roteamento e consultoria no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdf89-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdf89-103">_**Última modificação do tópico:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="fdf89-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="fdf89-104">Além de impor Location-Based roteamento às reuniões do Lync, o Location-Based aplicativo de conferência de roteamento impõe Location-Based restrições de roteamento em transferências de chamadas consuldas que entram em pontos de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="fdf89-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="fdf89-105">Uma transferência de chamada consultiva é estabelecida entre duas partes em que uma das partes transfere a chamada para um novo usuário.</span><span class="sxs-lookup"><span data-stu-id="fdf89-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="fdf89-106">Por exemplo, um ponto de extremidade PSTN chama usuário A (Lync chamado).</span><span class="sxs-lookup"><span data-stu-id="fdf89-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="fdf89-107">O usuário A determina que o usuário PSTN deve ser encaminhado para o usuário B (usuário do Lync).</span><span class="sxs-lookup"><span data-stu-id="fdf89-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="fdf89-108">O usuário A coloca a chamada com o usuário PSTN em espera e chama o usuário B. o usuário B concorda em falar com o usuário PSTN.</span><span class="sxs-lookup"><span data-stu-id="fdf89-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="fdf89-109">O usuário A transfere a chamada em espera para o usuário B.</span><span class="sxs-lookup"><span data-stu-id="fdf89-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="fdf89-110">**Fluxo de chamadas de transferência de chamadas consultivas**</span><span class="sxs-lookup"><span data-stu-id="fdf89-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="fdf89-111">![Roteamento baseado em local para o diagrama de conferência](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Roteamento baseado em local para o diagrama de conferência")</span><span class="sxs-lookup"><span data-stu-id="fdf89-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="fdf89-112">Quando um usuário habilitado para roteamento de Location-Based inicia uma transferência de chamada consultiva de um ponto de extremidade PSTN (conforme mostrado na figura anterior), isso cria duas chamadas ativas, uma chamada entre o usuário PSTN e o usuário do Lync A e a outra entre o usuário do Lync e o usuário B. o seguinte comportamento é imposto pelo aplicativo de conferência de roteamento de Location-Based:</span><span class="sxs-lookup"><span data-stu-id="fdf89-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="fdf89-113">Se o roteamento de tronco SIP, a chamada PSTN é autorizada a encaminhar novamente a chamada PSTN para o local de rede onde o usuário B do Lync (ou seja, destino da transferência) está localizado, a transferência de chamada será permitida; caso contrário, a transferência de chamadas consuldas será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="fdf89-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="fdf89-114">Essa autorização é executada com base no local da parte transferida que está no mesmo local de rede que o tronco SIP que está encaminhando a chamada ativa para o ponto de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="fdf89-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="fdf89-115">Se o tronco SIP encaminhar a chamada PSTN de entrada não tiver autorização para rotear chamadas para o local de rede onde a parte transferida (usuário B) está localizada ou a parte transferida está localizada em um site de rede desconhecido, a transferência de chamada consultiva para o ponto de extremidade PSTN (ou seja, destino da transferência de chamada) será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="fdf89-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="fdf89-116">A tabela a seguir descreve como Location-Based restrições de roteamento são aplicadas pelo aplicativo de conferência de roteamento de Location-Based para transferências de chamadas consultivas.</span><span class="sxs-lookup"><span data-stu-id="fdf89-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="fdf89-117">Embora os pontos de extremidade PBX não estejam diretamente associados a um site de rede, o tronco SIP ao qual o PBX está conectado pode ser atribuído a um local de rede.</span><span class="sxs-lookup"><span data-stu-id="fdf89-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="fdf89-118">Portanto, o ponto de extremidade de PBX pode ser indiretamente associado a um site de rede.</span><span class="sxs-lookup"><span data-stu-id="fdf89-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdf89-119">Site de rede da parte transferida por chamada</span><span class="sxs-lookup"><span data-stu-id="fdf89-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="fdf89-120">Local de rede do destino da transferência de chamadas</span><span class="sxs-lookup"><span data-stu-id="fdf89-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="fdf89-121">Comportamento</span><span class="sxs-lookup"><span data-stu-id="fdf89-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf89-122">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="fdf89-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="fdf89-123">Usuário do Lync no mesmo local de rede (por exemplo, site 1)</span><span class="sxs-lookup"><span data-stu-id="fdf89-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="fdf89-124">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf89-125">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="fdf89-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="fdf89-126">Usuário do Lync em diferentes sites de rede (por exemplo, site 2)</span><span class="sxs-lookup"><span data-stu-id="fdf89-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="fdf89-127">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf89-128">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="fdf89-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="fdf89-129">Usuário do Lync em um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="fdf89-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="fdf89-130">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf89-131">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="fdf89-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="fdf89-132">Usuário do Lync federado</span><span class="sxs-lookup"><span data-stu-id="fdf89-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="fdf89-133">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf89-134">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="fdf89-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="fdf89-135">Ponto de extremidade de PBX no mesmo site (ou seja, site 1)</span><span class="sxs-lookup"><span data-stu-id="fdf89-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="fdf89-136">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf89-137">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="fdf89-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="fdf89-138">Ponto de extremidade de PBX em sites diferentes (por exemplo, site 2)</span><span class="sxs-lookup"><span data-stu-id="fdf89-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="fdf89-139">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf89-140">Ponto de extremidade de PBX no mesmo site (ou seja, site 1)</span><span class="sxs-lookup"><span data-stu-id="fdf89-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="fdf89-141">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="fdf89-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="fdf89-142">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf89-143">Ponto de extremidade de PBX em um site diferente (ou seja, site 2)</span><span class="sxs-lookup"><span data-stu-id="fdf89-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="fdf89-144">Ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="fdf89-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="fdf89-145">A transferência consultiva não será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf89-146">Ponto de extremidade de PBX em qualquer site</span><span class="sxs-lookup"><span data-stu-id="fdf89-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="fdf89-147">Usuário do Lync no mesmo local de rede (por exemplo, site 1)</span><span class="sxs-lookup"><span data-stu-id="fdf89-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="fdf89-148">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf89-149">Ponto de extremidade de PBX em qualquer site</span><span class="sxs-lookup"><span data-stu-id="fdf89-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="fdf89-150">Usuário do Lync em diferentes sites de rede (por exemplo, site 2)</span><span class="sxs-lookup"><span data-stu-id="fdf89-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="fdf89-151">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdf89-152">Ponto de extremidade de PBX em qualquer site</span><span class="sxs-lookup"><span data-stu-id="fdf89-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="fdf89-153">Usuário do Lync em um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="fdf89-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="fdf89-154">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdf89-155">Ponto de extremidade de PBX em qualquer site</span><span class="sxs-lookup"><span data-stu-id="fdf89-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="fdf89-156">Usuário do Lync federado</span><span class="sxs-lookup"><span data-stu-id="fdf89-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="fdf89-157">A transferência consultiva será permitida</span><span class="sxs-lookup"><span data-stu-id="fdf89-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

