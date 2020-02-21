---
title: 'Lync Server 2013: requisitos para roteamento baseado em local para conferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 567cebd5fcf1fc2a60fa110754f916525052e57d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="2c380-102">Requisitos para roteamento baseado em local para conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c380-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c380-103">_**Última modificação do tópico:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="2c380-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="2c380-104">Estes são os requisitos necessários para a instalação e configuração do aplicativo de conferência de roteamento baseado em local:</span><span class="sxs-lookup"><span data-stu-id="2c380-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="2c380-105">A atualização cumulativa 2 do Lync Server 2013 deve ser implantada em todos os servidores ou pools da sua topologia.</span><span class="sxs-lookup"><span data-stu-id="2c380-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c380-106">Se um servidor ou pool do Lync em sua topologia não tiver a atualização cumulativa 2 ou superior do Lync Server 2013 instalada, então a imposição do roteamento baseado em local das reuniões do Lync não poderá ser garantida.</span><span class="sxs-lookup"><span data-stu-id="2c380-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="2c380-107">Lync Server 2013 o roteamento baseado em local é um pré-requisito para aplicativo de conferência de roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="2c380-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="2c380-108">Para obter mais informações sobre como configurar o roteamento baseado em local do Lync Server 2013, confira [Configurando o roteamento baseado em local](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="2c380-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="2c380-109">Os requisitos do aplicativo de conferência de roteamento baseado em local são os mesmos que os requisitos para o roteamento baseado em local do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c380-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="2c380-110">Para obter mais informações, consulte [planejando o roteamento baseado em local](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="2c380-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="2c380-111">Servidores com suporte</span><span class="sxs-lookup"><span data-stu-id="2c380-111">Supported Servers</span></span>

<span data-ttu-id="2c380-112">O aplicativo de conferência de roteamento baseado em local exige que a atualização cumulativa 2 do Lync Server 2013 seja implantada em todos os pools de front-end e servidores Standard Edition em sua topologia.</span><span class="sxs-lookup"><span data-stu-id="2c380-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="2c380-113">Se o Lync Server 2013 atualização cumulativa 2 não estiver instalado em alguns servidores do Lync em sua topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas em reuniões do Lync e transferências de chamadas consultivas.</span><span class="sxs-lookup"><span data-stu-id="2c380-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="2c380-114">A tabela a seguir identifica a combinação de funções de servidor e versões que dão suporte ao roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="2c380-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c380-115">Versão do pool de front-end</span><span class="sxs-lookup"><span data-stu-id="2c380-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="2c380-116">Versão do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="2c380-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="2c380-117">Com suporte</span><span class="sxs-lookup"><span data-stu-id="2c380-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c380-118">Atualização cumulativa 2 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c380-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="2c380-119">Atualização cumulativa 2 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c380-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="2c380-120">Sim</span><span class="sxs-lookup"><span data-stu-id="2c380-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c380-121">Atualização cumulativa 2 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c380-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="2c380-122">Atualização cumulativa 1 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c380-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="2c380-123">Não</span><span class="sxs-lookup"><span data-stu-id="2c380-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c380-124">Atualização cumulativa 2 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c380-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="2c380-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2c380-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="2c380-126">Não</span><span class="sxs-lookup"><span data-stu-id="2c380-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c380-127">Atualização cumulativa 2 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c380-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="2c380-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2c380-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="2c380-129">Não</span><span class="sxs-lookup"><span data-stu-id="2c380-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c380-130">Atualização cumulativa 1 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c380-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="2c380-131">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="2c380-131">Any</span></span></p></td>
<td><p><span data-ttu-id="2c380-132">Não</span><span class="sxs-lookup"><span data-stu-id="2c380-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c380-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2c380-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="2c380-134">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="2c380-134">Any</span></span></p></td>
<td><p><span data-ttu-id="2c380-135">Não</span><span class="sxs-lookup"><span data-stu-id="2c380-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c380-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2c380-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="2c380-137">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="2c380-137">Any</span></span></p></td>
<td><p><span data-ttu-id="2c380-138">Não</span><span class="sxs-lookup"><span data-stu-id="2c380-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="2c380-139">Clientes com suporte</span><span class="sxs-lookup"><span data-stu-id="2c380-139">Supported Clients</span></span>

<span data-ttu-id="2c380-140">Os clientes do Lync que dão suporte ao roteamento baseado em local de reuniões do Lync são os mesmos clientes que dão suporte ao roteamento baseado em local do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c380-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="2c380-141">Para obter mais informações, consulte [suporte de cliente e servidor para roteamento baseado em local](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="2c380-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="2c380-142">Requisitos do servidor de mediação para transferências de chamadas consultivas</span><span class="sxs-lookup"><span data-stu-id="2c380-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="2c380-143">O aplicativo de conferência de roteamento baseado em local requer a implantação de servidores de mediação autônomos para impor restrições de roteamento com base no local em transferências de chamadas consultivas.</span><span class="sxs-lookup"><span data-stu-id="2c380-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="2c380-144">Para impor o roteamento baseado em local das transferências de chamadas consultivas, o servidor de mediação deve estar associado a apenas um ponto de servidor de mediação (ou seja, PBX, gateway SIP, etc.) em regiões de rede onde o roteamento baseado em local é necessário.</span><span class="sxs-lookup"><span data-stu-id="2c380-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="2c380-145">Se outros servidores de mediação estiverem implantados na mesma região de rede, o par do servidor de mediação deverá estar associado a um servidor de mediação diferente.</span><span class="sxs-lookup"><span data-stu-id="2c380-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="2c380-146">Este requisito é detalhado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2c380-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="2c380-147">Servidor de mediação único por vários pontos de servidor de mediação quando uma transferência de chamada consultiva é roteada para um ponto de servidor de mediação por meio de um servidor de mediação configurado com vários troncos SIP para vários pares (ou seja, PBXs e gateways), o consultion a transferência de chamada é bloqueada para evitar o bypass de chamadas PSTN se a transferência de chamada consultiva é permitida por meio de alguns troncos SIP, mas não é permitida através de outros troncos SIP.</span><span class="sxs-lookup"><span data-stu-id="2c380-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="2c380-148">Por exemplo, no caso de um único servidor de mediação servindo um ponto de servidor de mediação de gateway PSTN e um ponto de servidor de mediação PBX, o seguinte comportamento será observado:</span><span class="sxs-lookup"><span data-stu-id="2c380-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="2c380-149">Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PSTN para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada para evitar o bypass de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="2c380-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="2c380-150">Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PBX no mesmo site (site 1) para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada mesmo que não se incorra em possíveis Tol PSTN l ignorando.</span><span class="sxs-lookup"><span data-stu-id="2c380-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="2c380-151">Servidores de mediação separados por ponto de servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="2c380-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="2c380-152">Quando uma transferência consultiva é direcionada para um ponto de servidor de mediação, a transferência consultiva será avaliada em relação ao ponto único do servidor de mediação atendido pelo servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="2c380-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="2c380-153">A chamada será desativada ou permitida com base em seu potencial de incorrer em desvio de interchamada PSTN, independentemente de todos os outros pares de servidores de mediação no site, conforme eles são atendidos por servidores de mediação separados.</span><span class="sxs-lookup"><span data-stu-id="2c380-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="2c380-154">Por exemplo, no caso de um servidor de mediação separado servindo um ponto de servidor de mediação de gateway PSTN e um ponto de servidor de mediação PBX, o seguinte comportamento será observado:</span><span class="sxs-lookup"><span data-stu-id="2c380-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="2c380-155">Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PSTN para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será desautorizada para evitar o bypass de chamada PSTN.</span><span class="sxs-lookup"><span data-stu-id="2c380-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="2c380-156">Quando um usuário do Lync de um determinado site (ou seja, site 1) tenta transferir uma chamada com um ponto de extremidade PBX no mesmo site (site 1) para um usuário do Lync de um site diferente (ou seja, site 2) via transferência consultiva, a chamada será permitida, pois ela não incorrerá em um possível desvio de PSTN em potencial tendo.</span><span class="sxs-lookup"><span data-stu-id="2c380-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="2c380-157">Recursos não suportados pelo aplicativo de conferência de roteamento baseado em local</span><span class="sxs-lookup"><span data-stu-id="2c380-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="2c380-158">Os seguintes recursos não são suportados pelo aplicativo de conferência de roteamento baseado em local:</span><span class="sxs-lookup"><span data-stu-id="2c380-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="2c380-159">Conferência discada.</span><span class="sxs-lookup"><span data-stu-id="2c380-159">Dial-in conferencing.</span></span> <span data-ttu-id="2c380-160">O roteamento baseado em local não pode ser imposto para conferência discada.</span><span class="sxs-lookup"><span data-stu-id="2c380-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="2c380-161">Qualquer solicitação de discagem para uma determinada conferência não será restringida pelo roteamento baseado em local, mesmo se o organizador da conferência for um usuário do Lync habilitado para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="2c380-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="2c380-162">É recomendável não provisionar os números de acesso de conferência nas regiões onde as restrições de roteamento baseadas em local precisam ser impostas.</span><span class="sxs-lookup"><span data-stu-id="2c380-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

