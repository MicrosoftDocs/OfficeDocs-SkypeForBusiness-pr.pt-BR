---
title: Resumo de porta-borda consolidada única com endereços IP privados usando NAT
description: Resumo de porta-borda consolidada única com endereços IP privados usando NAT.
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
ms.openlocfilehash: a3fc182b9fbbd24d589feb7f73e3c0086fa23152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564557"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="c45d2-103">Resumo de porta-borda consolidada única com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c45d2-103">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c45d2-104">_**Última modificação do tópico:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="c45d2-104">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="c45d2-105">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c45d2-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="c45d2-106">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="c45d2-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="c45d2-107">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="c45d2-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="c45d2-108">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="c45d2-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="c45d2-109">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="c45d2-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="c45d2-110">**Perímetro de rede para um único servidor de borda consolidado com endereçamento IP privado usando NAT**</span><span class="sxs-lookup"><span data-stu-id="c45d2-110">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="c45d2-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="c45d2-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="c45d2-112">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="c45d2-112">Port and Protocol Details</span></span>

<span data-ttu-id="c45d2-113">Recomendamos abrir apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="c45d2-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="c45d2-114">Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída.</span><span class="sxs-lookup"><span data-stu-id="c45d2-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="c45d2-115">Declarado de outra maneira, as mensagens SIP para e a partir do serviço de borda de acesso estão envolvidas em mensagens instantâneas (IM), presença, webconferência, áudio/vídeo (A/V) e Federação.</span><span class="sxs-lookup"><span data-stu-id="c45d2-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="c45d2-116">Resumo do firewall para borda consolidada única com endereços IP privados usando NAT: interface externa</span><span class="sxs-lookup"><span data-stu-id="c45d2-116">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c45d2-117">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="c45d2-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c45d2-118">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="c45d2-118">Source IP address</span></span></th>
<th><span data-ttu-id="c45d2-119">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="c45d2-119">Destination IP address</span></span></th>
<th><span data-ttu-id="c45d2-120">Observações</span><span class="sxs-lookup"><span data-stu-id="c45d2-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c45d2-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c45d2-122">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-122">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-123">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="c45d2-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="c45d2-124">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="c45d2-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="c45d2-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="c45d2-126">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-126">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-127">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-127">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-128">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="c45d2-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="c45d2-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="c45d2-130">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-131">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-131">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-132">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="c45d2-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="c45d2-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="c45d2-134">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-135">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-135">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-136">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="c45d2-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-137">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="c45d2-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c45d2-138">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-138">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-139">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-139">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-140">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="c45d2-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-141">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="c45d2-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c45d2-142">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-142">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-143">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-144">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="c45d2-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-145">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="c45d2-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c45d2-146">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-147">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-147">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-148">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="c45d2-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-149">Webconferência/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c45d2-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c45d2-150">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-150">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-151">Serviço de borda de Webconferência da servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-151">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-152">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="c45d2-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c45d2-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c45d2-154">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-154">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-155">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-155">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-156">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c45d2-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c45d2-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c45d2-158">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-159">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-159">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-160">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="c45d2-160">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c45d2-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c45d2-162">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-162">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-163">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-163">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-164">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c45d2-164">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c45d2-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c45d2-166">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-166">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-167">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-168">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="c45d2-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c45d2-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c45d2-170">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-171">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-171">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-172">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="c45d2-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="c45d2-173">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="c45d2-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c45d2-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c45d2-175">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-175">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-176">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-176">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-177">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c45d2-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c45d2-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c45d2-179">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-179">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-180">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-181">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="c45d2-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c45d2-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c45d2-183">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-184">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-184">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-185">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="c45d2-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="c45d2-186">Resumo do firewall para borda consolidada única com endereços IP privados usando NAT: interface interna</span><span class="sxs-lookup"><span data-stu-id="c45d2-186">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c45d2-187">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="c45d2-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c45d2-188">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="c45d2-188">Source IP address</span></span></th>
<th><span data-ttu-id="c45d2-189">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="c45d2-189">Destination IP address</span></span></th>
<th><span data-ttu-id="c45d2-190">Comments</span><span class="sxs-lookup"><span data-stu-id="c45d2-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c45d2-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c45d2-192">Qualquer um (pode ser definido como IP do servidor Standard Edition, endereço IP do servidor Standard Edition ou endereço IP do pool executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="c45d2-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="c45d2-193">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-194">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="c45d2-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c45d2-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c45d2-196">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="c45d2-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c45d2-197">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-198">Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="c45d2-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c45d2-200">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-201">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="c45d2-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="c45d2-202">Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="c45d2-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="c45d2-204">Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="c45d2-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="c45d2-205">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-206">Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="c45d2-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="c45d2-208">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="c45d2-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="c45d2-209">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-210">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c45d2-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c45d2-212">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-212">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-213">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-214">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="c45d2-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="c45d2-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c45d2-216">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-216">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-217">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-218">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="c45d2-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="c45d2-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="c45d2-220">Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="c45d2-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="c45d2-221">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-222">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="c45d2-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="c45d2-224">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-224">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-225">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-226">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="c45d2-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="c45d2-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="c45d2-228">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-228">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-229">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-230">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="c45d2-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="c45d2-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="c45d2-232">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-232">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-233">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="c45d2-234">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="c45d2-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="c45d2-235">Resumo de firewall para federação</span><span class="sxs-lookup"><span data-stu-id="c45d2-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c45d2-236">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="c45d2-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c45d2-237">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="c45d2-237">Source IP address</span></span></th>
<th><span data-ttu-id="c45d2-238">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="c45d2-238">Destination IP address</span></span></th>
<th><span data-ttu-id="c45d2-239">Observações</span><span class="sxs-lookup"><span data-stu-id="c45d2-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-240">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="c45d2-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c45d2-241">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="c45d2-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="c45d2-242">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-242">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-243">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="c45d2-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="c45d2-244">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="c45d2-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c45d2-245">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="c45d2-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c45d2-246">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="c45d2-246">Source IP address</span></span></th>
<th><span data-ttu-id="c45d2-247">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="c45d2-247">Destination IP address</span></span></th>
<th><span data-ttu-id="c45d2-248">Observações</span><span class="sxs-lookup"><span data-stu-id="c45d2-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-249">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="c45d2-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c45d2-250">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="c45d2-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c45d2-251">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-252">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="c45d2-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-253">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="c45d2-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="c45d2-254">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-255">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="c45d2-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="c45d2-256">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="c45d2-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-257">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="c45d2-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="c45d2-258">Clientes</span><span class="sxs-lookup"><span data-stu-id="c45d2-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="c45d2-259">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-260">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="c45d2-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="c45d2-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c45d2-262">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-263">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c45d2-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c45d2-264">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="c45d2-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c45d2-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c45d2-266">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-267">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c45d2-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c45d2-268">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c45d2-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="c45d2-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="c45d2-270">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c45d2-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="c45d2-271">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="c45d2-272">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c45d2-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="c45d2-273">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="c45d2-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c45d2-274">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="c45d2-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="c45d2-275">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="c45d2-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="c45d2-276">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="c45d2-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="c45d2-277">Comments</span><span class="sxs-lookup"><span data-stu-id="c45d2-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c45d2-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c45d2-279">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-279">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-280">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c45d2-281">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="c45d2-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c45d2-282">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="c45d2-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45d2-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="c45d2-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="c45d2-284">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="c45d2-285">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-285">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-286">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="c45d2-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="c45d2-287">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="c45d2-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45d2-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="c45d2-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="c45d2-289">Qualquer</span><span class="sxs-lookup"><span data-stu-id="c45d2-289">Any</span></span></p></td>
<td><p><span data-ttu-id="c45d2-290">Cada IP de interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="c45d2-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="c45d2-291">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</span><span class="sxs-lookup"><span data-stu-id="c45d2-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

