---
title: 'Lync Server 2013: Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT'
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
ms.openlocfilehash: ff1cb9d559d3d6824882a87aaa4d45ad7254c276
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534138"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="12e46-102">Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e46-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12e46-103">_**Última modificação do tópico:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="12e46-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="12e46-104">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="12e46-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="12e46-105">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="12e46-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="12e46-106">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="12e46-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="12e46-107">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="12e46-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="12e46-108">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="12e46-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="12e46-109">**Rede de perímetro corporativa para borda consolidada em escala com endereços IP privados usando NAT**</span><span class="sxs-lookup"><span data-stu-id="12e46-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="12e46-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="12e46-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="12e46-111">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="12e46-111">Port and Protocol Details</span></span>

<span data-ttu-id="12e46-112">Recomendamos abrir somente as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="12e46-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="12e46-p103">Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída. Dito de outra forma, as mensagens SIP de e para o serviço de Borda de Acesso está envolvido em sistemas de mensagens instantâneas (IM), presença, webconferências, áudio/vídeo (A/V) e federação.</span><span class="sxs-lookup"><span data-stu-id="12e46-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="12e46-115">Resumo do firewall para borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT: interface externa – nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="12e46-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12e46-116">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="12e46-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="12e46-117">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="12e46-117">Source IP address</span></span></th>
<th><span data-ttu-id="12e46-118">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="12e46-118">Destination IP address</span></span></th>
<th><span data-ttu-id="12e46-119">Observações</span><span class="sxs-lookup"><span data-stu-id="12e46-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12e46-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="12e46-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="12e46-121">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-121">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-122">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="12e46-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="12e46-123">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="12e46-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="12e46-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="12e46-125">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="12e46-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="12e46-126">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-126">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-127">O serviço de proxy XMPP envia o tráfego para os contatos do XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="12e46-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="12e46-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="12e46-129">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-130">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-130">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-131">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="12e46-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="12e46-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="12e46-133">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-134">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-134">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-135">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="12e46-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="12e46-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="12e46-137">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-138">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-138">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-139">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="12e46-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-140">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="12e46-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="12e46-141">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-141">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-142">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-143">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="12e46-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-144">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="12e46-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12e46-145">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-145">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-146">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-147">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="12e46-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-148">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="12e46-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12e46-149">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-150">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-150">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-151">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="12e46-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-152">Webconferência/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="12e46-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="12e46-153">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-153">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-154">Serviço de borda de Webconferência da servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-155">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="12e46-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-156">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="12e46-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="12e46-157">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-158">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-158">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-159">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12e46-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-160">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="12e46-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="12e46-161">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-162">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-162">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-163">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="12e46-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-164">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="12e46-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="12e46-165">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-165">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-166">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-167">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="12e46-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-168">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="12e46-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="12e46-169">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-169">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-170">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-171">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="12e46-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="12e46-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="12e46-173">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-174">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-174">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-175">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="12e46-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="12e46-176">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="12e46-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="12e46-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="12e46-178">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-178">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-179">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-180">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="12e46-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="12e46-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="12e46-182">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-182">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-183">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-184">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="12e46-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="12e46-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="12e46-186">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-187">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-187">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-188">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="12e46-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="12e46-189">Resumo do firewall para borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT: interface interna – nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="12e46-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12e46-190">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="12e46-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="12e46-191">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="12e46-191">Source IP address</span></span></th>
<th><span data-ttu-id="12e46-192">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="12e46-192">Destination IP address</span></span></th>
<th><span data-ttu-id="12e46-193">Comments</span><span class="sxs-lookup"><span data-stu-id="12e46-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12e46-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="12e46-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="12e46-195">Qualquer um (pode ser definido como endereço de servidor front-end ou endereço IP do pool de front-ends executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="12e46-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="12e46-196">Endereço IP da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="12e46-197">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="12e46-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="12e46-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12e46-199">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="12e46-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="12e46-200">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-201">Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="12e46-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12e46-203">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-204">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="12e46-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="12e46-205">Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="12e46-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="12e46-207">Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="12e46-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="12e46-208">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-209">Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="12e46-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="12e46-211">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="12e46-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="12e46-212">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-213">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="12e46-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="12e46-215">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-215">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-216">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-217">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="12e46-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="12e46-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="12e46-219">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-219">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-220">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-221">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="12e46-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="12e46-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="12e46-223">Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="12e46-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="12e46-224">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-225">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="12e46-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="12e46-227">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-227">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-228">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-229">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="12e46-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="12e46-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="12e46-231">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-231">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-232">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-233">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="12e46-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="12e46-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="12e46-235">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-235">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-236">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="12e46-237">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="12e46-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="12e46-238">Resumo de firewall para federação</span><span class="sxs-lookup"><span data-stu-id="12e46-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12e46-239">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="12e46-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="12e46-240">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="12e46-240">Source IP address</span></span></th>
<th><span data-ttu-id="12e46-241">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="12e46-241">Destination IP address</span></span></th>
<th><span data-ttu-id="12e46-242">Observações</span><span class="sxs-lookup"><span data-stu-id="12e46-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12e46-243">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="12e46-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12e46-244">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="12e46-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="12e46-245">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-245">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-246">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="12e46-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="12e46-247">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="12e46-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12e46-248">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="12e46-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="12e46-249">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="12e46-249">Source IP address</span></span></th>
<th><span data-ttu-id="12e46-250">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="12e46-250">Destination IP address</span></span></th>
<th><span data-ttu-id="12e46-251">Observações</span><span class="sxs-lookup"><span data-stu-id="12e46-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12e46-252">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="12e46-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12e46-253">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="12e46-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="12e46-254">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-255">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="12e46-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-256">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="12e46-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="12e46-257">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-258">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="12e46-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="12e46-259">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="12e46-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-260">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="12e46-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="12e46-261">Clientes</span><span class="sxs-lookup"><span data-stu-id="12e46-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="12e46-262">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-263">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="12e46-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-264">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="12e46-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="12e46-265">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-266">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="12e46-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="12e46-267">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="12e46-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="12e46-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="12e46-269">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-270">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="12e46-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="12e46-271">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="12e46-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="12e46-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="12e46-273">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="12e46-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="12e46-274">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="12e46-275">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="12e46-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="12e46-276">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="12e46-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12e46-277">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="12e46-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="12e46-278">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="12e46-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="12e46-279">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="12e46-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="12e46-280">Comments</span><span class="sxs-lookup"><span data-stu-id="12e46-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12e46-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="12e46-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="12e46-282">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-282">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-283">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="12e46-284">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="12e46-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="12e46-285">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="12e46-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12e46-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="12e46-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="12e46-287">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="12e46-288">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-288">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-289">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="12e46-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="12e46-290">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="12e46-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12e46-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="12e46-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="12e46-292">Qualquer</span><span class="sxs-lookup"><span data-stu-id="12e46-292">Any</span></span></p></td>
<td><p><span data-ttu-id="12e46-293">Cada IP de interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="12e46-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="12e46-294">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</span><span class="sxs-lookup"><span data-stu-id="12e46-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

