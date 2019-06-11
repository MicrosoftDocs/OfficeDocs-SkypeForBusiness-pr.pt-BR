---
title: Resumo de porta - única borda consolidada com endereços IP privados usando NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b7c908d52577375f9caaab974f059ffda17fb35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="ba654-102">Resumo de porta - única borda consolidada com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba654-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba654-103">_**Tópico da última modificação:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="ba654-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="ba654-104">A funcionalidade do servidor de borda do Lync Server 2013 descrita nesta arquitetura de cenário é muito semelhante à implementada no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ba654-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="ba654-105">A adição mais perceptível é a porta **5269 sobre** a entrada TCP para o protocolo de mensagens extensíveis e de presença (XMPP).</span><span class="sxs-lookup"><span data-stu-id="ba654-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="ba654-106">O Lync Server 2013, opcionalmente, implanta um proxy XMPP no servidor de borda ou no pool de periféricos e o servidor de Gateway XMPP no servidor front-end ou no pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="ba654-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="ba654-107">Além do IPv4, o servidor de borda agora oferece suporte ao IPv6.</span><span class="sxs-lookup"><span data-stu-id="ba654-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="ba654-108">Para fins de clareza, somente o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="ba654-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="ba654-109">**Perímetro de rede para um único servidor de borda consolidado com endereçamento IP privado usando NAT**</span><span class="sxs-lookup"><span data-stu-id="ba654-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="ba654-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847] (images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="ba654-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ba654-111">Detalhes de protocolo e porta</span><span class="sxs-lookup"><span data-stu-id="ba654-111">Port and Protocol Details</span></span>

<span data-ttu-id="ba654-112">Recomendamos que você abra apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="ba654-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="ba654-113">Para que o acesso remoto funcione para qualquer serviço de borda, é obrigatório que o tráfego SIP tenha permissão de fluxo bidirecional, conforme mostrado na figura de tráfego de borda de entrada/saída.</span><span class="sxs-lookup"><span data-stu-id="ba654-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="ba654-114">Declarado de outra maneira, o recurso de mensagens SIP para e do serviço de borda de acesso está envolvido em mensagens instantâneas (IM), presença, conferência via Web, áudio/vídeo (A/V) e Federação.</span><span class="sxs-lookup"><span data-stu-id="ba654-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="ba654-115">Resumo de firewall para uma única aresta consolidada com endereços IP privados usando NAT: interface externa</span><span class="sxs-lookup"><span data-stu-id="ba654-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba654-116">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba654-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba654-117">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="ba654-117">Source IP address</span></span></th>
<th><span data-ttu-id="ba654-118">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="ba654-118">Destination IP address</span></span></th>
<th><span data-ttu-id="ba654-119">Notas</span><span class="sxs-lookup"><span data-stu-id="ba654-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba654-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ba654-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ba654-121">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-121">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-122">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="ba654-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ba654-123">O serviço de proxy XMPP aceita o tráfego de contatos do XMPP em agrupamentos XMPP definidos</span><span class="sxs-lookup"><span data-stu-id="ba654-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ba654-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ba654-125">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-126">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-126">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-127">Revogação e verificação de revogação/revogação de certificados e recuperação</span><span class="sxs-lookup"><span data-stu-id="ba654-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="ba654-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="ba654-129">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-130">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-130">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-131">Consulta DNS via TCP</span><span class="sxs-lookup"><span data-stu-id="ba654-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="ba654-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="ba654-133">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-134">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-135">Consulta DNS via UDP</span><span class="sxs-lookup"><span data-stu-id="ba654-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-136">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba654-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba654-137">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-137">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-138">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-139">Tráfego SIP de cliente para servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="ba654-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-140">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba654-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba654-141">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-141">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-142">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-143">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="ba654-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-144">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba654-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba654-145">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-146">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-146">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-147">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="ba654-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-148">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba654-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba654-149">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-149">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-150">Serviço de borda de Webconferência Web Edge Server</span><span class="sxs-lookup"><span data-stu-id="ba654-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-151">Mídia de Webconferência</span><span class="sxs-lookup"><span data-stu-id="ba654-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-152">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="ba654-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba654-153">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-154">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-154">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-155">Obrigatório para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba654-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba654-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba654-157">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-158">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-158">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-159">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="ba654-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-160">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="ba654-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba654-161">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-161">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-162">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-163">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="ba654-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ba654-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba654-165">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-165">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-166">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-167">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="ba654-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba654-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba654-169">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-170">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-170">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-171">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor edge edge-to-edge.</span><span class="sxs-lookup"><span data-stu-id="ba654-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="ba654-172">Obrigatório para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2 e também se vários pools de bordas forem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="ba654-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba654-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba654-174">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-174">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-175">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-176">STUN/desliga a negociação de candidatos via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba654-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba654-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba654-178">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-178">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-179">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-180">STUN/TRANSFORMe a negociação de candidatos via TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba654-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba654-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba654-182">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-183">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-183">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-184">STUN/TRANSFORMe a negociação de candidatos via TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba654-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="ba654-185">Resumo de firewall para uma única aresta consolidada com endereços IP privados usando NAT: interface interna</span><span class="sxs-lookup"><span data-stu-id="ba654-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba654-186">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba654-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba654-187">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="ba654-187">Source IP address</span></span></th>
<th><span data-ttu-id="ba654-188">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="ba654-188">Destination IP address</span></span></th>
<th><span data-ttu-id="ba654-189">Comentários</span><span class="sxs-lookup"><span data-stu-id="ba654-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba654-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ba654-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ba654-191">Any (pode ser definido como padrão de servidor Standard Edition, endereço IP do servidor Standard Edition ou endereço IP do pool executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="ba654-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="ba654-192">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-193">Tráfego de XMPP de saída do serviço de gateway do XMPP em execução em servidor front-end ou pool de front-end</span><span class="sxs-lookup"><span data-stu-id="ba654-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba654-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba654-195">Any (pode ser definido como director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end)</span><span class="sxs-lookup"><span data-stu-id="ba654-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ba654-196">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-197">Tráfego SIP de saída (do director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ba654-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba654-199">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-200">Any (pode ser definido como director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end)</span><span class="sxs-lookup"><span data-stu-id="ba654-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ba654-201">Tráfego SIP de entrada (para o director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="ba654-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="ba654-203">Any (pode ser definido como o endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool Front-end)</span><span class="sxs-lookup"><span data-stu-id="ba654-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="ba654-204">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-205">Tráfego de Webconferência do servidor front-end ou de cada servidor front-end se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="ba654-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="ba654-207">Any (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="ba654-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="ba654-208">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-209">Autenticação de usuários de A/V (serviço de autenticação A/V) do servidor front-end ou do endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba654-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba654-211">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-211">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-212">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-213">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="ba654-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ba654-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba654-215">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-215">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-216">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-217">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes se não for possível estabelecer comunicação UDP, o TCP será usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="ba654-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ba654-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ba654-219">Any (pode ser definido como o endereço IP do servidor front-end ou o pool que mantém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="ba654-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="ba654-220">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-221">Replicação de alterações do repositório de gerenciamento central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ba654-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ba654-223">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-223">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-224">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-225">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="ba654-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ba654-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ba654-227">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-227">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-228">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-229">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="ba654-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ba654-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ba654-231">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-231">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-232">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ba654-233">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="ba654-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="ba654-234">Resumo do firewall para Federação</span><span class="sxs-lookup"><span data-stu-id="ba654-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba654-235">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba654-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba654-236">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="ba654-236">Source IP address</span></span></th>
<th><span data-ttu-id="ba654-237">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="ba654-237">Destination IP address</span></span></th>
<th><span data-ttu-id="ba654-238">Notas</span><span class="sxs-lookup"><span data-stu-id="ba654-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba654-239">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba654-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba654-240">Endereço IP público do serviço de borda do Access</span><span class="sxs-lookup"><span data-stu-id="ba654-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ba654-241">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-241">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-242">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="ba654-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ba654-243">Resumo do Firewall – Conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="ba654-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba654-244">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba654-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba654-245">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="ba654-245">Source IP address</span></span></th>
<th><span data-ttu-id="ba654-246">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="ba654-246">Destination IP address</span></span></th>
<th><span data-ttu-id="ba654-247">Notas</span><span class="sxs-lookup"><span data-stu-id="ba654-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba654-248">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba654-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba654-249">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="ba654-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ba654-250">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-251">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="ba654-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-252">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ba654-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ba654-253">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-254">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="ba654-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ba654-255">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="ba654-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-256">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ba654-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ba654-257">Clientes</span><span class="sxs-lookup"><span data-stu-id="ba654-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="ba654-258">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-259">Tráfego SIP de cliente para servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="ba654-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-260">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="ba654-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ba654-261">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-262">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ba654-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ba654-263">Usado para sessões de A/V com o Windows Live Messenger se a conectividade de mensagem de chat pública estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="ba654-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba654-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba654-265">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-266">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ba654-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ba654-267">Necessário para conectividade de IM pública com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ba654-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ba654-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ba654-269">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ba654-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ba654-270">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="ba654-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ba654-271">Necessário para conectividade de IM pública com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ba654-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="ba654-272">Resumo de firewall para mensagens extensíveis e protocolo de presença</span><span class="sxs-lookup"><span data-stu-id="ba654-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba654-273">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="ba654-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ba654-274">Fonte (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="ba654-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="ba654-275">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="ba654-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="ba654-276">Comentários</span><span class="sxs-lookup"><span data-stu-id="ba654-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba654-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ba654-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ba654-278">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-278">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-279">Endereço IP da interface do serviço de borda do acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ba654-280">Porta de comunicação de servidor para servidor padrão para XMPP.</span><span class="sxs-lookup"><span data-stu-id="ba654-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ba654-281">Permite a comunicação com o servidor de borda XMPP o proxy de parceiros de XMPP federado</span><span class="sxs-lookup"><span data-stu-id="ba654-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba654-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ba654-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ba654-283">Endereço IP da interface do serviço de borda do acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ba654-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ba654-284">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-284">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-285">Porta de comunicação de servidor para servidor padrão para XMPP.</span><span class="sxs-lookup"><span data-stu-id="ba654-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ba654-286">Permite a comunicação do proxy do servidor de borda XMPP com parceiros do XMPP federado</span><span class="sxs-lookup"><span data-stu-id="ba654-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba654-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ba654-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ba654-288">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="ba654-288">Any</span></span></p></td>
<td><p><span data-ttu-id="ba654-289">Cada IP de interface do servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="ba654-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="ba654-290">Tráfego de XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-end para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="ba654-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

