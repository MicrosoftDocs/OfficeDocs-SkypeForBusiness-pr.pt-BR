---
title: Resumo de porta-borda consolidada única com endereços IP privados usando NAT
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a5aaa4628a92174aca39579c5f2e6a8e4f31987
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533998"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="940b3-102">Resumo de porta-borda consolidada única com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="940b3-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="940b3-103">_**Última modificação do tópico:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="940b3-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="940b3-104">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="940b3-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="940b3-105">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="940b3-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="940b3-106">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="940b3-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="940b3-107">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="940b3-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="940b3-108">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="940b3-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="940b3-109">**Perímetro de rede para um único servidor de borda consolidado com endereçamento IP privado usando NAT**</span><span class="sxs-lookup"><span data-stu-id="940b3-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="940b3-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="940b3-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="940b3-111">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="940b3-111">Port and Protocol Details</span></span>

<span data-ttu-id="940b3-112">Recomendamos abrir apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="940b3-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="940b3-113">Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída.</span><span class="sxs-lookup"><span data-stu-id="940b3-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="940b3-114">Declarado de outra maneira, as mensagens SIP para e a partir do serviço de borda de acesso estão envolvidas em mensagens instantâneas (IM), presença, webconferência, áudio/vídeo (A/V) e Federação.</span><span class="sxs-lookup"><span data-stu-id="940b3-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="940b3-115">Resumo do firewall para borda consolidada única com endereços IP privados usando NAT: interface externa</span><span class="sxs-lookup"><span data-stu-id="940b3-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="940b3-116">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="940b3-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="940b3-117">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="940b3-117">Source IP address</span></span></th>
<th><span data-ttu-id="940b3-118">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="940b3-118">Destination IP address</span></span></th>
<th><span data-ttu-id="940b3-119">Observações</span><span class="sxs-lookup"><span data-stu-id="940b3-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="940b3-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="940b3-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="940b3-121">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-121">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-122">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="940b3-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="940b3-123">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="940b3-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="940b3-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="940b3-125">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-126">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-126">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-127">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="940b3-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="940b3-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="940b3-129">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-130">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-130">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-131">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="940b3-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="940b3-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="940b3-133">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-134">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-134">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-135">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="940b3-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-136">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="940b3-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="940b3-137">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-137">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-138">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-139">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="940b3-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-140">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="940b3-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="940b3-141">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-141">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-142">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-143">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="940b3-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-144">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="940b3-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="940b3-145">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-146">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-146">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-147">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="940b3-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-148">Webconferência/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="940b3-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="940b3-149">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-149">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-150">Serviço de borda de Webconferência da servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-151">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="940b3-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="940b3-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="940b3-153">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-154">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-154">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-155">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="940b3-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="940b3-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="940b3-157">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-158">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-158">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-159">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="940b3-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="940b3-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="940b3-161">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-161">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-162">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-163">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="940b3-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="940b3-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="940b3-165">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-165">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-166">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-167">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="940b3-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="940b3-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="940b3-169">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-170">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-170">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-171">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="940b3-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="940b3-172">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="940b3-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="940b3-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="940b3-174">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-174">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-175">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-176">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="940b3-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="940b3-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="940b3-178">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-178">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-179">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-180">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="940b3-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="940b3-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="940b3-182">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-183">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-183">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-184">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="940b3-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="940b3-185">Resumo do firewall para borda consolidada única com endereços IP privados usando NAT: interface interna</span><span class="sxs-lookup"><span data-stu-id="940b3-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="940b3-186">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="940b3-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="940b3-187">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="940b3-187">Source IP address</span></span></th>
<th><span data-ttu-id="940b3-188">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="940b3-188">Destination IP address</span></span></th>
<th><span data-ttu-id="940b3-189">Comments</span><span class="sxs-lookup"><span data-stu-id="940b3-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="940b3-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="940b3-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="940b3-191">Qualquer um (pode ser definido como IP do servidor Standard Edition, endereço IP do servidor Standard Edition ou endereço IP do pool executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="940b3-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="940b3-192">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-193">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="940b3-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="940b3-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="940b3-195">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="940b3-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="940b3-196">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-197">Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="940b3-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="940b3-199">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-200">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="940b3-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="940b3-201">Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="940b3-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="940b3-203">Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="940b3-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="940b3-204">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-205">Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="940b3-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="940b3-207">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="940b3-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="940b3-208">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-209">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="940b3-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="940b3-211">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-211">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-212">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-213">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="940b3-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="940b3-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="940b3-215">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-215">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-216">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-217">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="940b3-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="940b3-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="940b3-219">Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="940b3-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="940b3-220">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-221">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="940b3-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="940b3-223">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-223">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-224">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-225">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="940b3-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="940b3-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="940b3-227">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-227">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-228">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-229">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="940b3-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="940b3-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="940b3-231">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-231">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-232">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="940b3-233">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="940b3-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="940b3-234">Resumo de firewall para federação</span><span class="sxs-lookup"><span data-stu-id="940b3-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="940b3-235">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="940b3-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="940b3-236">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="940b3-236">Source IP address</span></span></th>
<th><span data-ttu-id="940b3-237">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="940b3-237">Destination IP address</span></span></th>
<th><span data-ttu-id="940b3-238">Observações</span><span class="sxs-lookup"><span data-stu-id="940b3-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="940b3-239">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="940b3-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="940b3-240">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="940b3-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="940b3-241">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-241">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-242">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="940b3-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="940b3-243">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="940b3-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="940b3-244">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="940b3-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="940b3-245">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="940b3-245">Source IP address</span></span></th>
<th><span data-ttu-id="940b3-246">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="940b3-246">Destination IP address</span></span></th>
<th><span data-ttu-id="940b3-247">Observações</span><span class="sxs-lookup"><span data-stu-id="940b3-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="940b3-248">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="940b3-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="940b3-249">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="940b3-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="940b3-250">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-251">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="940b3-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-252">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="940b3-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="940b3-253">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-254">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="940b3-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="940b3-255">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="940b3-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-256">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="940b3-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="940b3-257">Clientes</span><span class="sxs-lookup"><span data-stu-id="940b3-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="940b3-258">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-259">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="940b3-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="940b3-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="940b3-261">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-262">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="940b3-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="940b3-263">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="940b3-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="940b3-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="940b3-265">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-266">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="940b3-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="940b3-267">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="940b3-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="940b3-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="940b3-269">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="940b3-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="940b3-270">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="940b3-271">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="940b3-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="940b3-272">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="940b3-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="940b3-273">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="940b3-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="940b3-274">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="940b3-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="940b3-275">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="940b3-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="940b3-276">Comments</span><span class="sxs-lookup"><span data-stu-id="940b3-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="940b3-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="940b3-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="940b3-278">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-278">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-279">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="940b3-280">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="940b3-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="940b3-281">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="940b3-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="940b3-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="940b3-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="940b3-283">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="940b3-284">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-284">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-285">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="940b3-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="940b3-286">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="940b3-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="940b3-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="940b3-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="940b3-288">Qualquer</span><span class="sxs-lookup"><span data-stu-id="940b3-288">Any</span></span></p></td>
<td><p><span data-ttu-id="940b3-289">Cada IP de interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="940b3-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="940b3-290">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</span><span class="sxs-lookup"><span data-stu-id="940b3-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

