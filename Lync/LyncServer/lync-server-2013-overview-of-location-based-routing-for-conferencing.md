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
ms.openlocfilehash: 28ca4ea233f783271c91490aa0550bc2344bdaad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="9da88-102">Visão geral do roteamento baseado em local para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9da88-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9da88-103">_**Última modificação do tópico:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="9da88-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="9da88-104">O aplicativo de conferência de roteamento baseado em local oferece ao Lync conferências um mecanismo para a prevenção de desvio de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="9da88-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="9da88-105">O aplicativo monitora conferências ativas e impõe restrições de roteamento com base no local com base no local dos usuários do Lync participando.</span><span class="sxs-lookup"><span data-stu-id="9da88-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="9da88-106">O aplicativo de conferência de roteamento baseado em local determina se o roteamento baseado em local deve ser aplicado em uma reunião do Lync se os seguintes critérios forem atendidos:</span><span class="sxs-lookup"><span data-stu-id="9da88-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="9da88-107">O organizador da reunião está habilitado para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="9da88-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="9da88-108">As restrições de roteamento com base no local serão aplicadas somente a conferências organizadas por usuários habilitados para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="9da88-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="9da88-109">Pelo menos um participante de reunião é um ponto de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="9da88-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="9da88-110">As restrições de roteamento com base no local são aplicáveis apenas para conferências que incluem pontos de extremidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="9da88-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="9da88-111">O local de rede onde o gateway PSTN usado para fazer a ponte da conferência para o PSTN está localizado, bem como os sites de rede onde os organizadores e participantes estão se conectando.</span><span class="sxs-lookup"><span data-stu-id="9da88-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="9da88-112">O aplicativo de conferência de roteamento baseado em local impede a participação de usuários do Lync e pontos de extremidade PSTN de diferentes sites de rede para a mesma conferência.</span><span class="sxs-lookup"><span data-stu-id="9da88-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="9da88-113">Se o organizador de uma reunião estiver habilitado para roteamento baseado em local, o aplicativo de conferência imporá as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="9da88-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="9da88-114">Os pontos de extremidade que podem ingressar em uma reunião do Lync dependem dos pontos de extremidade que já ingressaram na conferência, e essa restrição é ajustada conforme os pontos de extremidade associados deixam e novos pontos de extremidade ingressam na conferência.</span><span class="sxs-lookup"><span data-stu-id="9da88-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="9da88-115">Se os organizadores e participantes estiverem participando de uma reunião do Lync do mesmo local de rede, então um ponto de extremidade PSTN, outro participante do mesmo local de rede, outro participante de um site de rede diferente ou um participante de um site de rede desconhecido tem permissão para ingressar.</span><span class="sxs-lookup"><span data-stu-id="9da88-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="9da88-116">Se os organizadores e participantes estiverem participando da reunião de sites de rede diferentes ou desconhecidos, um ponto de extremidade PSTN não terá permissão para ingressar na reunião se a chamada PSTN ingresses de um tronco SIP habilitado para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="9da88-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="9da88-117">Se os organizadores e participantes estiverem participando da reunião do mesmo local de rede e se houver participantes participando da mesma reunião da PSTN, um ponto de extremidade do Lync de um site de rede diferente não tem permissão para participar da reunião.</span><span class="sxs-lookup"><span data-stu-id="9da88-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="9da88-118">Essas restrições de roteamento com base no local de conferência são resumidas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9da88-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9da88-119">Usuário (s) em uma conferência em um determinado ponto</span><span class="sxs-lookup"><span data-stu-id="9da88-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="9da88-120">Usuário (s) com permissão para ingressar na conferência</span><span class="sxs-lookup"><span data-stu-id="9da88-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="9da88-121">Usuário (s) não autorizados a ingressar na conferência</span><span class="sxs-lookup"><span data-stu-id="9da88-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da88-122">Usuário (s) do cliente VoIP do Lync de um único site de rede</span><span class="sxs-lookup"><span data-stu-id="9da88-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="9da88-123">Usuário de cliente VoIP do Lync do mesmo local de rede</span><span class="sxs-lookup"><span data-stu-id="9da88-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="9da88-124">Usuário de cliente VoIP do Lync de um site de rede diferente</span><span class="sxs-lookup"><span data-stu-id="9da88-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="9da88-125">Usuário de cliente VoIP do Lync de um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="9da88-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="9da88-126">Usuário do cliente do Lync VoIP federado</span><span class="sxs-lookup"><span data-stu-id="9da88-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="9da88-127">Usuário ingressando a partir de um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="9da88-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="9da88-128">Nenhum</span><span class="sxs-lookup"><span data-stu-id="9da88-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da88-129">Usuário (s) do cliente VoIP do Lync de um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="9da88-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="9da88-130">Usuário de cliente VoIP do Lync de qualquer site</span><span class="sxs-lookup"><span data-stu-id="9da88-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="9da88-131">Usuário de cliente VoIP do Lync de um site desconhecido</span><span class="sxs-lookup"><span data-stu-id="9da88-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="9da88-132">Usuário do cliente do Lync VoIP federado</span><span class="sxs-lookup"><span data-stu-id="9da88-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="9da88-133">Ingresso de usuário por meio de um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="9da88-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da88-134">Usuários de cliente do Lync VoIP de diferentes locais de rede</span><span class="sxs-lookup"><span data-stu-id="9da88-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="9da88-135">Usuário de cliente VoIP do Lync de qualquer site de rede</span><span class="sxs-lookup"><span data-stu-id="9da88-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="9da88-136">Usuário de cliente VoIP do Lync de um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="9da88-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="9da88-137">Usuário do cliente do Lync VoIP federado</span><span class="sxs-lookup"><span data-stu-id="9da88-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="9da88-138">Ingresso de usuário por meio de um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="9da88-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da88-139">Usuário (s) do cliente VoIP do Lync de um único site de rede e usuários ingressando de um ponto de extremidade PSTN</span><span class="sxs-lookup"><span data-stu-id="9da88-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="9da88-140">Usuário de cliente VoIP do Lync do mesmo local de rede</span><span class="sxs-lookup"><span data-stu-id="9da88-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="9da88-141">Usuário de cliente VoIP do Lync de um site de rede diferente</span><span class="sxs-lookup"><span data-stu-id="9da88-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="9da88-142">Usuário de cliente VoIP do Lync de um site de rede desconhecido</span><span class="sxs-lookup"><span data-stu-id="9da88-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="9da88-143">Usuário do cliente do Lync VoIP federado</span><span class="sxs-lookup"><span data-stu-id="9da88-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9da88-144">Veja a seguir as características adicionais do aplicativo de conferência de roteamento baseado em local:</span><span class="sxs-lookup"><span data-stu-id="9da88-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="9da88-145">Quando um usuário não tem permissão para ingressar em uma conferência determinada por restrições de roteamento baseado em local, a chamada de usuários para a conferência será rejeitada e seu cliente do Lync relatará que a chamada não foi concluída ou terminou.</span><span class="sxs-lookup"><span data-stu-id="9da88-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="9da88-146">Um ponto de extremidade PSTN ingressando em uma conferência com enforces de roteamento baseado em local não será restrito a ingressar na conferência independentemente de seu estado se o ponto de extremidade ingressar por meio de um tronco que não está habilitado para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="9da88-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="9da88-147">Um sistema PBX conectado a um servidor de mediação por meio de um tronco SIP que não faz chamadas de egresso à PSTN terá as mesmas impostas que os usuários do Lync localizados no mesmo local de rede onde o tronco SIP está definido.</span><span class="sxs-lookup"><span data-stu-id="9da88-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="9da88-148">Por exemplo, um ponto de extremidade PSTN poderá ingressar em uma conferência com um usuário PBX e um usuário do Lync se eles estiverem localizados no mesmo local de rede; caso contrário, o ponto de extremidade PSTN não terá permissão para ingressar na conferência se o usuário do PBX estiver em um local de rede diferente do usuário do Lync.</span><span class="sxs-lookup"><span data-stu-id="9da88-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

