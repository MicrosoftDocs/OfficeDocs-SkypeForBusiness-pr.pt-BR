---
title: 'Lync Server 2013: Resumo de porta - borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20071cba55551a42ea6406723bb1f9ed55853afa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="a0bc9-102">Resumo de porta - borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0bc9-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0bc9-103">_**Tópico da última modificação:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="a0bc9-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="a0bc9-104">A funcionalidade do servidor de borda do Lync Server 2013 descrita nesta arquitetura de cenário é muito semelhante à implementada no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="a0bc9-105">A adição mais perceptível é a porta **5269 sobre** a entrada TCP para o protocolo de mensagens extensíveis e de presença (XMPP).</span><span class="sxs-lookup"><span data-stu-id="a0bc9-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="a0bc9-106">O Lync Server 2013, opcionalmente, implanta um proxy XMPP no servidor de borda ou no pool de periféricos e o servidor de Gateway XMPP no servidor front-end ou no pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="a0bc9-107">Além do IPv4, o servidor de borda agora oferece suporte ao IPv6.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="a0bc9-108">Para fins de clareza, somente o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="a0bc9-109">**Rede de perímetro da empresa para borda consolidada dimensionada com endereços IP privados usando NAT**</span><span class="sxs-lookup"><span data-stu-id="a0bc9-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="a0bc9-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="a0bc9-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a0bc9-111">Detalhes de protocolo e porta</span><span class="sxs-lookup"><span data-stu-id="a0bc9-111">Port and Protocol Details</span></span>

<span data-ttu-id="a0bc9-112">É recomendável que você abra apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="a0bc9-113">Para que o acesso remoto funcione para qualquer serviço de borda, é obrigatório que o tráfego SIP tenha permissão de fluxo bidirecional, conforme mostrado na figura de tráfego de borda de entrada/saída.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="a0bc9-114">Declarado de outra maneira, o recurso de mensagens SIP para e do serviço de borda de acesso está envolvido em mensagens instantâneas (IM), presença, Web conferência, áudio/vídeo (A/V) e Federação.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="a0bc9-115">Resumo de firewall para borda consolidada dimensionada, balanceamento de carga de DNS com endereços IP privados usando NAT: interface externa – nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0bc9-116">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a0bc9-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a0bc9-117">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="a0bc9-117">Source IP address</span></span></th>
<th><span data-ttu-id="a0bc9-118">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="a0bc9-118">Destination IP address</span></span></th>
<th><span data-ttu-id="a0bc9-119">Notas</span><span class="sxs-lookup"><span data-stu-id="a0bc9-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a0bc9-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-121">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-121">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-122">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-123">O serviço de proxy XMPP aceita o tráfego de contatos do XMPP em agrupamentos XMPP definidos</span><span class="sxs-lookup"><span data-stu-id="a0bc9-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a0bc9-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-125">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-126">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-126">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-127">O serviço de proxy XMPP envia o tráfego para os contatos do XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="a0bc9-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a0bc9-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-129">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-130">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-130">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-131">Revogação e verificação de revogação/revogação de certificados e recuperação</span><span class="sxs-lookup"><span data-stu-id="a0bc9-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="a0bc9-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-133">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-134">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-135">Consulta DNS via TCP</span><span class="sxs-lookup"><span data-stu-id="a0bc9-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="a0bc9-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-137">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-138">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-139">Consulta DNS via UDP</span><span class="sxs-lookup"><span data-stu-id="a0bc9-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-140">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-141">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-142">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-143">Tráfego SIP de cliente para servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="a0bc9-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-144">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-145">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-145">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-146">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-147">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="a0bc9-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-148">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-149">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-150">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-150">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-151">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="a0bc9-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-152">Web Conferencing/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a0bc9-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-153">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-153">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-154">Serviço de borda de Webconferência Web Edge Server</span><span class="sxs-lookup"><span data-stu-id="a0bc9-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-155">Mídia de Webconferência</span><span class="sxs-lookup"><span data-stu-id="a0bc9-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-156">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="a0bc9-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-157">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-158">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-158">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-159">Obrigatório para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-160">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a0bc9-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-161">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-162">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-162">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-163">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-164">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="a0bc9-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-165">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-165">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-166">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-167">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a0bc9-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-168">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a0bc9-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-169">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-169">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-170">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-171">Obrigatório somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a0bc9-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a0bc9-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-173">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-174">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-174">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-175">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor edge edge-to-edge.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="a0bc9-176">Obrigatório para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2 e também se vários pools de bordas forem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a0bc9-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-178">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-178">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-179">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-180">STUN/desliga a negociação de candidatos via UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a0bc9-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a0bc9-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-182">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-182">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-183">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-184">STUN/TRANSFORMe a negociação de candidatos via TCP/443</span><span class="sxs-lookup"><span data-stu-id="a0bc9-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a0bc9-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-186">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-187">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-187">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-188">STUN/TRANSFORMe a negociação de candidatos via TCP/443</span><span class="sxs-lookup"><span data-stu-id="a0bc9-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="a0bc9-189">Resumo de firewall para borda consolidada dimensionada, balanceamento de carga de DNS com endereços IP privados usando NAT: interface interna – nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0bc9-190">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a0bc9-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a0bc9-191">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="a0bc9-191">Source IP address</span></span></th>
<th><span data-ttu-id="a0bc9-192">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="a0bc9-192">Destination IP address</span></span></th>
<th><span data-ttu-id="a0bc9-193">Comentários</span><span class="sxs-lookup"><span data-stu-id="a0bc9-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a0bc9-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-195">Any (pode ser definido como endereço do servidor front-end ou endereço IP do pool de front-end executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-196">Endereço IP da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-197">Tráfego de XMPP de saída do serviço de gateway do XMPP em execução em servidor front-end ou pool de front-end</span><span class="sxs-lookup"><span data-stu-id="a0bc9-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a0bc9-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-199">Any (pode ser definido como director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-200">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-201">Tráfego SIP de saída (do director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a0bc9-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-203">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-204">Any (pode ser definido como director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-205">Tráfego SIP de entrada (para o director, endereço IP do pool do diretor, servidor front-end ou endereço IP do pool de front-end) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="a0bc9-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-207">Any (pode ser definido como o endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool Front-end)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-208">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-209">Tráfego de Webconferência do servidor front-end ou de cada servidor front-end se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="a0bc9-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-211">Any (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-212">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-213">Autenticação de usuários de A/V (serviço de autenticação A/V) do servidor front-end ou do endereço IP do pool de front-end ou qualquer aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes que use este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a0bc9-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-215">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-215">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-216">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-217">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="a0bc9-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a0bc9-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-219">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-219">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-220">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-221">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de ramificação sobreviventes ou servidor de ramificação sobreviventes se não for possível estabelecer comunicação UDP, o TCP será usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="a0bc9-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a0bc9-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-223">Any (pode ser definido como o endereço IP do servidor front-end ou o pool que mantém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-224">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-225">Replicação de alterações do repositório de gerenciamento central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a0bc9-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-227">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-227">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-228">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-229">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="a0bc9-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a0bc9-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-231">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-231">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-232">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-233">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="a0bc9-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a0bc9-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-235">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-235">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-236">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-237">Controlador de serviço de log centralizado usando cmdlets do Shell de gerenciamento do Lync Server e do serviço de log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou comandos do agente (ClsAgent. exe) e a coleção de logs</span><span class="sxs-lookup"><span data-stu-id="a0bc9-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="a0bc9-238">Resumo do firewall para Federação</span><span class="sxs-lookup"><span data-stu-id="a0bc9-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0bc9-239">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a0bc9-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a0bc9-240">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="a0bc9-240">Source IP address</span></span></th>
<th><span data-ttu-id="a0bc9-241">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="a0bc9-241">Destination IP address</span></span></th>
<th><span data-ttu-id="a0bc9-242">Notas</span><span class="sxs-lookup"><span data-stu-id="a0bc9-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-243">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-244">Endereço IP público do serviço de borda do Access</span><span class="sxs-lookup"><span data-stu-id="a0bc9-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-245">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-245">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-246">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="a0bc9-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="a0bc9-247">Resumo do Firewall – Conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="a0bc9-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0bc9-248">Função/protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a0bc9-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a0bc9-249">Endereço IP de Origem</span><span class="sxs-lookup"><span data-stu-id="a0bc9-249">Source IP address</span></span></th>
<th><span data-ttu-id="a0bc9-250">Endereço IP de Destino</span><span class="sxs-lookup"><span data-stu-id="a0bc9-250">Destination IP address</span></span></th>
<th><span data-ttu-id="a0bc9-251">Notas</span><span class="sxs-lookup"><span data-stu-id="a0bc9-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-252">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-253">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="a0bc9-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-254">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-255">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="a0bc9-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-256">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-257">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-258">Parceiros de conectividade de mensagens de chat públicas</span><span class="sxs-lookup"><span data-stu-id="a0bc9-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-259">Para conectividade de mensagens de chat públicas e federadas usando SIP</span><span class="sxs-lookup"><span data-stu-id="a0bc9-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-260">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-261">Clientes</span><span class="sxs-lookup"><span data-stu-id="a0bc9-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-262">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-263">Tráfego SIP de cliente para servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="a0bc9-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-264">A/V/RTP/TCP/50.000 A 59.999</span><span class="sxs-lookup"><span data-stu-id="a0bc9-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-265">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-266">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a0bc9-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-267">Usado para sessões de A/V com o Windows Live Messenger se a conectividade de mensagem de chat pública estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a0bc9-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-269">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-270">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a0bc9-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-271">Necessário para conectividade de IM pública com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a0bc9-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a0bc9-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-273">Clientes do Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a0bc9-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-274">Serviço Edge Server A/V Edge</span><span class="sxs-lookup"><span data-stu-id="a0bc9-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-275">Necessário para conectividade de IM pública com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a0bc9-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="a0bc9-276">Resumo de firewall para mensagens extensíveis e protocolo de presença</span><span class="sxs-lookup"><span data-stu-id="a0bc9-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0bc9-277">Protocolo/TCP ou UDP/porta</span><span class="sxs-lookup"><span data-stu-id="a0bc9-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a0bc9-278">Fonte (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="a0bc9-279">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="a0bc9-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="a0bc9-280">Comentários</span><span class="sxs-lookup"><span data-stu-id="a0bc9-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a0bc9-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-282">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-282">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-283">Endereço IP da interface do serviço de borda do acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-284">Porta de comunicação de servidor para servidor padrão para XMPP.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a0bc9-285">Permite a comunicação com o servidor de borda XMPP o proxy de parceiros de XMPP federado</span><span class="sxs-lookup"><span data-stu-id="a0bc9-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0bc9-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a0bc9-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-287">Endereço IP da interface do serviço de borda do acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a0bc9-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-288">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-288">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-289">Porta de comunicação de servidor para servidor padrão para XMPP.</span><span class="sxs-lookup"><span data-stu-id="a0bc9-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a0bc9-290">Permite a comunicação do proxy do servidor de borda XMPP com parceiros do XMPP federado</span><span class="sxs-lookup"><span data-stu-id="a0bc9-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0bc9-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a0bc9-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-292">Qualquer um</span><span class="sxs-lookup"><span data-stu-id="a0bc9-292">Any</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-293">Cada IP de interface do servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="a0bc9-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="a0bc9-294">Tráfego de XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-end para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de bordas</span><span class="sxs-lookup"><span data-stu-id="a0bc9-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

