---
title: 'Lync Server 2013: Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT'
description: 'Lync Server 2013: Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT.'
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
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563937"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="a5b53-103">Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5b53-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5b53-104">_**Última modificação do tópico:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="a5b53-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="a5b53-105">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a5b53-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="a5b53-106">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="a5b53-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="a5b53-107">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="a5b53-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="a5b53-108">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="a5b53-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="a5b53-109">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="a5b53-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="a5b53-110">**Rede de perímetro corporativa para borda consolidada em escala com endereços IP privados usando NAT**</span><span class="sxs-lookup"><span data-stu-id="a5b53-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="a5b53-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="a5b53-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a5b53-112">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="a5b53-112">Port and Protocol Details</span></span>

<span data-ttu-id="a5b53-113">Recomendamos abrir somente as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="a5b53-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="a5b53-p103">Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída. Dito de outra forma, as mensagens SIP de e para o serviço de Borda de Acesso está envolvido em sistemas de mensagens instantâneas (IM), presença, webconferências, áudio/vídeo (A/V) e federação.</span><span class="sxs-lookup"><span data-stu-id="a5b53-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="a5b53-116">Resumo do firewall para borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT: interface externa – nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="a5b53-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5b53-117">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="a5b53-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a5b53-118">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="a5b53-118">Source IP address</span></span></th>
<th><span data-ttu-id="a5b53-119">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="a5b53-119">Destination IP address</span></span></th>
<th><span data-ttu-id="a5b53-120">Observações</span><span class="sxs-lookup"><span data-stu-id="a5b53-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a5b53-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a5b53-122">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-122">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-123">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="a5b53-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a5b53-124">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="a5b53-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a5b53-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a5b53-126">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="a5b53-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a5b53-127">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-127">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-128">O serviço de proxy XMPP envia o tráfego para os contatos do XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="a5b53-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-129">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a5b53-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a5b53-130">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-131">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-131">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-132">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="a5b53-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-133">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="a5b53-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="a5b53-134">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-135">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-135">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-136">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="a5b53-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-137">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="a5b53-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="a5b53-138">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-139">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-139">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-140">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="a5b53-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-141">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a5b53-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a5b53-142">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-142">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-143">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-144">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="a5b53-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-145">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a5b53-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a5b53-146">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-146">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-147">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-148">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="a5b53-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-149">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a5b53-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a5b53-150">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-151">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-151">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-152">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="a5b53-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-153">Webconferência/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a5b53-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a5b53-154">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-154">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-155">Serviço de borda de Webconferência da servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-156">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="a5b53-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-157">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a5b53-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a5b53-158">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-159">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-159">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-160">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5b53-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-161">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a5b53-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a5b53-162">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-163">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-163">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-164">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="a5b53-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-165">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a5b53-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a5b53-166">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-166">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-167">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-168">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a5b53-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-169">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a5b53-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a5b53-170">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-170">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-171">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-172">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a5b53-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a5b53-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a5b53-174">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-175">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-175">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-176">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="a5b53-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="a5b53-177">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="a5b53-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-178">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a5b53-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a5b53-179">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-179">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-180">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-181">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a5b53-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a5b53-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a5b53-183">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-183">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-184">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-185">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="a5b53-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-186">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a5b53-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a5b53-187">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-188">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-188">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-189">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="a5b53-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="a5b53-190">Resumo do firewall para borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT: interface interna – nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="a5b53-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5b53-191">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="a5b53-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a5b53-192">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="a5b53-192">Source IP address</span></span></th>
<th><span data-ttu-id="a5b53-193">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="a5b53-193">Destination IP address</span></span></th>
<th><span data-ttu-id="a5b53-194">Comments</span><span class="sxs-lookup"><span data-stu-id="a5b53-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a5b53-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a5b53-196">Qualquer um (pode ser definido como endereço de servidor front-end ou endereço IP do pool de front-ends executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="a5b53-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="a5b53-197">Endereço IP da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a5b53-198">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="a5b53-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a5b53-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a5b53-200">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="a5b53-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a5b53-201">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-202">Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a5b53-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a5b53-204">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-205">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="a5b53-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="a5b53-206">Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="a5b53-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="a5b53-208">Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="a5b53-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="a5b53-209">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-210">Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="a5b53-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="a5b53-212">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="a5b53-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="a5b53-213">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-214">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-215">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a5b53-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a5b53-216">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-216">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-217">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-218">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="a5b53-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-219">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a5b53-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a5b53-220">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-220">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-221">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-222">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="a5b53-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a5b53-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a5b53-224">Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="a5b53-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="a5b53-225">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-226">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a5b53-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a5b53-228">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-228">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-229">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-230">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="a5b53-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a5b53-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a5b53-232">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-232">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-233">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-234">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="a5b53-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a5b53-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a5b53-236">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-236">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-237">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a5b53-238">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="a5b53-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="a5b53-239">Resumo de firewall para federação</span><span class="sxs-lookup"><span data-stu-id="a5b53-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5b53-240">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="a5b53-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a5b53-241">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="a5b53-241">Source IP address</span></span></th>
<th><span data-ttu-id="a5b53-242">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="a5b53-242">Destination IP address</span></span></th>
<th><span data-ttu-id="a5b53-243">Observações</span><span class="sxs-lookup"><span data-stu-id="a5b53-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-244">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a5b53-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a5b53-245">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="a5b53-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a5b53-246">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-246">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-247">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="a5b53-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="a5b53-248">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="a5b53-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5b53-249">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="a5b53-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a5b53-250">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="a5b53-250">Source IP address</span></span></th>
<th><span data-ttu-id="a5b53-251">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="a5b53-251">Destination IP address</span></span></th>
<th><span data-ttu-id="a5b53-252">Observações</span><span class="sxs-lookup"><span data-stu-id="a5b53-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-253">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a5b53-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a5b53-254">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="a5b53-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a5b53-255">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-256">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="a5b53-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-257">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="a5b53-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a5b53-258">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-259">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="a5b53-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="a5b53-260">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="a5b53-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-261">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="a5b53-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a5b53-262">Clientes</span><span class="sxs-lookup"><span data-stu-id="a5b53-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="a5b53-263">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-264">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="a5b53-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-265">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="a5b53-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a5b53-266">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-267">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a5b53-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a5b53-268">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="a5b53-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a5b53-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a5b53-270">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-271">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a5b53-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a5b53-272">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a5b53-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-273">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a5b53-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a5b53-274">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a5b53-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="a5b53-275">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="a5b53-276">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="a5b53-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="a5b53-277">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="a5b53-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5b53-278">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="a5b53-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a5b53-279">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="a5b53-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="a5b53-280">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="a5b53-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="a5b53-281">Comments</span><span class="sxs-lookup"><span data-stu-id="a5b53-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a5b53-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a5b53-283">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-283">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-284">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a5b53-285">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="a5b53-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a5b53-286">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="a5b53-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5b53-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a5b53-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a5b53-288">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="a5b53-289">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-289">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-290">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="a5b53-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="a5b53-291">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="a5b53-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5b53-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a5b53-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a5b53-293">Qualquer</span><span class="sxs-lookup"><span data-stu-id="a5b53-293">Any</span></span></p></td>
<td><p><span data-ttu-id="a5b53-294">Cada IP de interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="a5b53-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="a5b53-295">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</span><span class="sxs-lookup"><span data-stu-id="a5b53-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

