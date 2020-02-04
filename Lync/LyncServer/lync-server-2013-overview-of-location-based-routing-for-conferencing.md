---
title: 'Lync Server 2013: visão geral do roteamento baseado em local para conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adb103d1f2314e033d9ef0958dd05a7648012bde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="9c510-102">Visão geral do roteamento baseado em local para conferências no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c510-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c510-103">_**Tópico da última modificação:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="9c510-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="9c510-104">O aplicativo de conferência de roteamento baseado em localização fornece às conferências do Lync um mecanismo para impedir que o bypass seja interurbana de PSTN.</span><span class="sxs-lookup"><span data-stu-id="9c510-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="9c510-105">O aplicativo monitora conferências ativas e impõe restrições de roteamento com base na localização com base no local dos usuários do Lync participantes.</span><span class="sxs-lookup"><span data-stu-id="9c510-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="9c510-106">O aplicativo de conferência de roteamento baseado em local determina se o roteamento baseado em localização deve ser imposto em uma reunião do Lync se os seguintes critérios forem atendidos:</span><span class="sxs-lookup"><span data-stu-id="9c510-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="9c510-107">O organizador da reunião está habilitado para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="9c510-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="9c510-108">As restrições de roteamento baseadas em local serão aplicadas somente a conferências organizadas por usuários que estão habilitados para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="9c510-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="9c510-109">Pelo menos um participante da reunião é um ponto de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="9c510-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="9c510-110">As restrições de roteamento baseadas em local são aplicáveis somente para conferências que incluem pontos de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="9c510-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="9c510-111">O local da rede onde o gateway PSTN usado para fazer a ligação da conferência com o PSTN está localizado, bem como os locais de rede, de onde os organizadores e os participantes estão se conectando.</span><span class="sxs-lookup"><span data-stu-id="9c510-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="9c510-112">O aplicativo de conferência de roteamento baseado em localização impede a participação de usuários do Lync e pontos de extremidade PSTN de diferentes sites de rede para a mesma conferência.</span><span class="sxs-lookup"><span data-stu-id="9c510-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="9c510-113">Se o organizador de uma reunião estiver habilitado para roteamento baseado em localização, o aplicativo de conferência forçará as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="9c510-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="9c510-114">Os pontos de extremidade que podem ingressar em uma reunião do Lync dependem dos pontos de extremidade que já ingressaram na conferência, e essa restrição é ajustada quando os pontos de extremidade associados deixam e os novos pontos de extremidade entram na conferência.</span><span class="sxs-lookup"><span data-stu-id="9c510-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="9c510-115">Se os organizadores e os participantes ingressarem em uma reunião do Lync a partir do mesmo local de rede, um ponto de extremidade PSTN, outro participante do mesmo local de rede, outro participante de um site de rede diferente ou um participante de um site de rede desconhecido tem permissão para ingressar em.</span><span class="sxs-lookup"><span data-stu-id="9c510-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="9c510-116">Se os organizadores e os participantes estiverem ingressando na reunião de locais de rede diferentes ou desconhecidos, um ponto de extremidade PSTN não terá autorização para participar da reunião se a chamada PSTN ingressar de um tronco SIP habilitado para Roteamento Baseado na Localização.</span><span class="sxs-lookup"><span data-stu-id="9c510-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="9c510-117">Se os organizadores e participantes estiverem ingressando na reunião no mesmo local de rede e houver participantes ingressando na mesma reunião a partir da PSTN, um ponto de extremidade do Lync de um site de rede diferente não poderá ingressar na reunião.</span><span class="sxs-lookup"><span data-stu-id="9c510-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="9c510-118">Essas restrições de roteamento baseado em localização de conferências são resumidas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9c510-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c510-119">Usuário(s) em uma conferência em um determinado ponto</span><span class="sxs-lookup"><span data-stu-id="9c510-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="9c510-120">Usuário(s) autorizados a ingressar na conferência</span><span class="sxs-lookup"><span data-stu-id="9c510-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="9c510-121">Usuário(s) não autorizados a ingressar na conferência</span><span class="sxs-lookup"><span data-stu-id="9c510-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c510-122">Usuário (s) do cliente VoIP do Lync de um único site de rede</span><span class="sxs-lookup"><span data-stu-id="9c510-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="9c510-123">Usuário do cliente VoIP do Lync do mesmo local de rede</span><span class="sxs-lookup"><span data-stu-id="9c510-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="9c510-124">Usuário do cliente VoIP do Lync de um site de rede diferente</span><span class="sxs-lookup"><span data-stu-id="9c510-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="9c510-125">Usuário do cliente VoIP do Lync de um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="9c510-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="9c510-126">Usuário do cliente VoIP do Lync federado</span><span class="sxs-lookup"><span data-stu-id="9c510-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="9c510-127">Usuário ingressando a partir de um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="9c510-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="9c510-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9c510-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c510-129">Usuário (s) do cliente VoIP do Lync de um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="9c510-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="9c510-130">Usuário do cliente VoIP do Lync de qualquer site</span><span class="sxs-lookup"><span data-stu-id="9c510-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="9c510-131">Usuário do cliente VoIP do Lync de um site desconhecido</span><span class="sxs-lookup"><span data-stu-id="9c510-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="9c510-132">Usuário do cliente VoIP do Lync federado</span><span class="sxs-lookup"><span data-stu-id="9c510-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="9c510-133">Usuário ingressando por meio de um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="9c510-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c510-134">Usuários do cliente VoIP do Lync de diferentes sites de rede</span><span class="sxs-lookup"><span data-stu-id="9c510-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="9c510-135">Usuário do cliente VoIP do Lync de qualquer site de rede</span><span class="sxs-lookup"><span data-stu-id="9c510-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="9c510-136">Usuário do cliente VoIP do Lync de um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="9c510-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="9c510-137">Usuário do cliente VoIP do Lync federado</span><span class="sxs-lookup"><span data-stu-id="9c510-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="9c510-138">Usuário ingressando por meio de um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="9c510-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c510-139">Usuários do cliente VoIP do Lync de um único site de rede e usuários que ingressam em um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="9c510-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="9c510-140">Usuário do cliente VoIP do Lync do mesmo local de rede</span><span class="sxs-lookup"><span data-stu-id="9c510-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="9c510-141">Usuário do cliente VoIP do Lync de um site de rede diferente</span><span class="sxs-lookup"><span data-stu-id="9c510-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="9c510-142">Usuário do cliente VoIP do Lync de um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="9c510-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="9c510-143">Usuário do cliente VoIP do Lync federado</span><span class="sxs-lookup"><span data-stu-id="9c510-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9c510-144">Veja a seguir as características adicionais do aplicativo de conferência de roteamento baseado em localização:</span><span class="sxs-lookup"><span data-stu-id="9c510-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="9c510-145">Quando um usuário não tem permissão para ingressar em determinadas restrições de roteamento baseado em localização, os usuários chamam para a conferência serão recusados e o cliente do Lync reportará que a chamada não foi concluída ou encerrada.</span><span class="sxs-lookup"><span data-stu-id="9c510-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="9c510-146">Um ponto de extremidade PSTN ingressando em uma conferência com enforces de roteamento baseado em local não será restrito a ingressar na conferência independentemente de seu estado se o ponto de extremidade se associar por meio de um tronco que não está habilitado para roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="9c510-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="9c510-147">Um sistema PBX conectado a um servidor de mediação por meio de um tronco SIP que não faz chamadas para a PSTN terá os mesmos enforces como usuários do Lync localizados no mesmo local de rede onde o tronco SIP está definido.</span><span class="sxs-lookup"><span data-stu-id="9c510-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="9c510-148">Por exemplo, um ponto de extremidade PSTN poderá ingressar em uma conferência com um usuário do PBX e um usuário do Lync se eles estiverem localizados no mesmo site de rede; caso contrário, o ponto de extremidade PSTN não terá permissão para ingressar na conferência se o usuário do PBX estiver em um site de rede diferente do que o usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="9c510-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

