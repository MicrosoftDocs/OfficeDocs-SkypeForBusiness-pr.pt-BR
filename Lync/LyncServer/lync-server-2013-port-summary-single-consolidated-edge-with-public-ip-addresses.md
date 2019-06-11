---
title: Sumário de porta - única borda consolidada com endereços IP públicos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1a61341908bef3a3098e70b06816bbf5ea328b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="6ce9c-102">Sumário de porta - única borda consolidada com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ce9c-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ce9c-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="6ce9c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6ce9c-104">A funcionalidade do servidor de borda do Lync Server 2013 descrita nesta arquitetura de cenário é muito semelhante à implementada no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="6ce9c-105">A adição mais perceptível é a porta **5269 sobre** a entrada TCP para o protocolo de mensagens extensíveis e de presença (XMPP).</span><span class="sxs-lookup"><span data-stu-id="6ce9c-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="6ce9c-106">O Lync Server 2013, opcionalmente, implanta um proxy XMPP no servidor de borda ou no pool de periféricos e o servidor de Gateway XMPP no servidor front-end ou no pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="6ce9c-107">As informações de planejamento para o proxy reverso e a Federação são encontradas em [cenários para inverter proxy no Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [planejamento para SIP, Federação do XMPP e mensagens instantâneas públicas nas seções do Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="6ce9c-108">Além do IPv4, o servidor de borda agora oferece suporte ao IPv6.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="6ce9c-109">Para fins de clareza, somente o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="6ce9c-110">**Rede de perímetro da empresa para uma única aresta consolidada com endereçamento de IP público**</span><span class="sxs-lookup"><span data-stu-id="6ce9c-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="6ce9c-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847] (images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="6ce9c-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="6ce9c-112">Detalhes de protocolo e porta</span><span class="sxs-lookup"><span data-stu-id="6ce9c-112">Port and Protocol Details</span></span>

<span data-ttu-id="6ce9c-113">Recomendamos que você abra apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="6ce9c-114">Para que o acesso remoto funcione para qualquer serviço de borda, é obrigatório que o tráfego SIP tenha permissão de fluxo bidirecionalmente, como mostrado na figura de tráfego de borda de entrada/saída.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="6ce9c-115">Declarado de outra maneira, o recurso de mensagens SIP para e do serviço de borda de acesso está envolvido em mensagens instantâneas (IM), presença, Web conferência, áudio/vídeo (A/V) e Federação.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="6ce9c-116">Resumo de firewall para uma única aresta consolidada com endereços IP públicos: interface externa</span><span class="sxs-lookup"><span data-stu-id="6ce9c-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ce9c-117">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="6ce9c-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6ce9c-118">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="6ce9c-118">Source IP address</span></span></th>
<th><span data-ttu-id="6ce9c-119">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="6ce9c-119">Destination IP address</span></span></th>
<th><span data-ttu-id="6ce9c-120">Notas</span><span class="sxs-lookup"><span data-stu-id="6ce9c-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6ce9c-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-122">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-122">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-123">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-124">O serviço de proxy XMPP aceita o tráfego de contatos do XMPP em agrupamentos XMPP definidos</span><span class="sxs-lookup"><span data-stu-id="6ce9c-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="6ce9c-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-126">Endereço IP público do serviço de borda do acesso ao servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-127">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-127">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-128">Revogação e verificação de revogação/revogação de certificados e recuperação</span><span class="sxs-lookup"><span data-stu-id="6ce9c-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="6ce9c-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-130">Endereço IP público do serviço de borda do acesso ao servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-131">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-131">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-132">Consulta DNS via TCP</span><span class="sxs-lookup"><span data-stu-id="6ce9c-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="6ce9c-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-134">Endereço IP público do serviço de borda do acesso ao servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-135">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-135">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-136">Consulta DNS via UDP</span><span class="sxs-lookup"><span data-stu-id="6ce9c-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-137">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-138">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-138">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-139">Endereço IP público do serviço de borda do acesso ao servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-140">Tráfego SIP de cliente para servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="6ce9c-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-141">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-142">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-142">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-143">Endereço IP público do serviço de borda do acesso ao servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-144">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="6ce9c-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-145">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-146">Endereço IP público do serviço de borda do acesso ao servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-147">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-147">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-148">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="6ce9c-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-149">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6ce9c-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-150">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-150">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-151">Endereço IP público do serviço de borda de Webconferência do Edge Server Web</span><span class="sxs-lookup"><span data-stu-id="6ce9c-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-152">Mídia de Webconferência</span><span class="sxs-lookup"><span data-stu-id="6ce9c-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-153">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="6ce9c-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-154">Endereço IP público do serviço de borda do acesso ao servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-155">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-155">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-156">Obrigatório para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="6ce9c-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-158">Endereço IP público do serviço de borda do servidor de borda A/V</span><span class="sxs-lookup"><span data-stu-id="6ce9c-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-159">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-159">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-160">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="6ce9c-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-161">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="6ce9c-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-162">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-162">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-163">Endereço IP público do serviço de borda do servidor de borda A/V</span><span class="sxs-lookup"><span data-stu-id="6ce9c-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-164">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="6ce9c-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-166">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-166">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-167">Endereço IP público do serviço de borda do servidor de borda A/V</span><span class="sxs-lookup"><span data-stu-id="6ce9c-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-168">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6ce9c-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-170">Endereço IP público do serviço de borda do servidor de borda A/V</span><span class="sxs-lookup"><span data-stu-id="6ce9c-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-171">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-171">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-172">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor edge edge-to-edge.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="6ce9c-173">Obrigatório para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2 e também se vários pools de bordas forem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6ce9c-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-175">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-175">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-176">Endereço IP público do serviço de borda do servidor de borda A/V</span><span class="sxs-lookup"><span data-stu-id="6ce9c-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-177">STUN/desliga a negociação de candidatos via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6ce9c-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6ce9c-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-179">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-179">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-180">Endereço IP público do serviço de borda do servidor de borda A/V</span><span class="sxs-lookup"><span data-stu-id="6ce9c-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-181">STUN/TRANSFORMe a negociação de candidatos via TCP/443</span><span class="sxs-lookup"><span data-stu-id="6ce9c-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6ce9c-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-183">Endereço IP público do serviço de borda do servidor de borda A/V</span><span class="sxs-lookup"><span data-stu-id="6ce9c-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-184">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-184">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-185">STUN/TRANSFORMe a negociação de candidatos via TCP/443</span><span class="sxs-lookup"><span data-stu-id="6ce9c-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="6ce9c-186">Resumo de firewall para uma única aresta consolidada com endereços IP públicos: interface interna</span><span class="sxs-lookup"><span data-stu-id="6ce9c-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ce9c-187">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="6ce9c-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6ce9c-188">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="6ce9c-188">Source IP address</span></span></th>
<th><span data-ttu-id="6ce9c-189">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="6ce9c-189">Destination IP address</span></span></th>
<th><span data-ttu-id="6ce9c-190">Comentários</span><span class="sxs-lookup"><span data-stu-id="6ce9c-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="6ce9c-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-192">Any (pode ser definido como padrão de servidor Standard Edition, endereço IP do servidor Standard Edition ou endereço IP do pool executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-193">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-194">Tráfego de XMPP de saída do serviço de gateway do XMPP em execução em servidor front-end ou pool de front-end</span><span class="sxs-lookup"><span data-stu-id="6ce9c-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6ce9c-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-196">Any (pode ser definido como director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-197">IP do servidor de borda ou pool que mantém a interface interna</span><span class="sxs-lookup"><span data-stu-id="6ce9c-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-198">Tráfego SIP de saída (do director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6ce9c-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-200">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-201">Any (pode ser definido como director, endereço IP do pool do diretor, servidor front-end ou endereço do pool de front-end)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-202">Tráfego SIP de entrada (para o director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="6ce9c-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-204">Any (pode ser definido como o endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool Front-end)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-205">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-206">Tráfego de Webconferência do servidor front-end ou de cada servidor front-end se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="6ce9c-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-208">Any (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-209">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-210">Autenticação de usuários de A/V (serviço de autenticação A/V) do servidor front-end ou do endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6ce9c-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-212">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-212">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-213">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-214">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="6ce9c-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6ce9c-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-216">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-216">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-217">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-218">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes se não for possível estabelecer comunicação UDP, o TCP será usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="6ce9c-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="6ce9c-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-220">Any (pode ser definido como o endereço IP do servidor front-end ou o pool que mantém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-221">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-222">Replicação de alterações do repositório de gerenciamento central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="6ce9c-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-224">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-224">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-225">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-226">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="6ce9c-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="6ce9c-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-228">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-228">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-229">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-230">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="6ce9c-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="6ce9c-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-232">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-232">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-233">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-234">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="6ce9c-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="6ce9c-235">Resumo do firewall para Federação</span><span class="sxs-lookup"><span data-stu-id="6ce9c-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ce9c-236">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="6ce9c-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6ce9c-237">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="6ce9c-237">Source IP address</span></span></th>
<th><span data-ttu-id="6ce9c-238">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="6ce9c-238">Destination IP address</span></span></th>
<th><span data-ttu-id="6ce9c-239">Notas</span><span class="sxs-lookup"><span data-stu-id="6ce9c-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-240">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-241">Endereço IP público do serviço de borda do Access</span><span class="sxs-lookup"><span data-stu-id="6ce9c-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-242">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-242">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-243">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="6ce9c-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="6ce9c-244">Resumo do Firewall – Conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="6ce9c-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ce9c-245">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="6ce9c-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6ce9c-246">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="6ce9c-246">Source IP address</span></span></th>
<th><span data-ttu-id="6ce9c-247">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="6ce9c-247">Destination IP address</span></span></th>
<th><span data-ttu-id="6ce9c-248">Notas</span><span class="sxs-lookup"><span data-stu-id="6ce9c-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-249">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-250">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="6ce9c-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-251">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-252">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="6ce9c-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-253">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-254">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-255">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="6ce9c-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-256">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="6ce9c-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-257">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-258">Clientes</span><span class="sxs-lookup"><span data-stu-id="6ce9c-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-259">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-260">Tráfego SIP de cliente para servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="6ce9c-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-261">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="6ce9c-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-262">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="6ce9c-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-263">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6ce9c-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-264">Usado para sessões de A/V com o Windows Live Messenger se a conectividade de mensagem de chat pública estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6ce9c-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-266">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="6ce9c-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-267">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6ce9c-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-268">Necessário para conectividade de IM pública com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6ce9c-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6ce9c-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-270">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6ce9c-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-271">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="6ce9c-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-272">Necessário para conectividade de IM pública com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="6ce9c-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="6ce9c-273">Resumo de firewall para mensagens extensíveis e protocolo de presença</span><span class="sxs-lookup"><span data-stu-id="6ce9c-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ce9c-274">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="6ce9c-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6ce9c-275">Fonte (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="6ce9c-276">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="6ce9c-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="6ce9c-277">Comentários</span><span class="sxs-lookup"><span data-stu-id="6ce9c-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6ce9c-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-279">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-279">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-280">Endereço IP da interface do serviço de borda do acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-281">Porta de comunicação de servidor para servidor padrão para XMPP.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6ce9c-282">Permite a comunicação com o servidor de borda XMPP o proxy de parceiros de XMPP federado</span><span class="sxs-lookup"><span data-stu-id="6ce9c-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ce9c-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6ce9c-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-284">Endereço IP da interface do serviço de borda do acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="6ce9c-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-285">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-285">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-286">Porta de comunicação de servidor para servidor padrão para XMPP.</span><span class="sxs-lookup"><span data-stu-id="6ce9c-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6ce9c-287">Permite a comunicação do proxy do servidor de borda XMPP com parceiros do XMPP federado</span><span class="sxs-lookup"><span data-stu-id="6ce9c-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ce9c-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="6ce9c-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-289">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="6ce9c-289">Any</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-290">Cada IP de interface do servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="6ce9c-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="6ce9c-291">Tráfego de XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-end para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="6ce9c-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

