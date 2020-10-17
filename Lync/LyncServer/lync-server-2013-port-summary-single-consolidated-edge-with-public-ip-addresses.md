---
title: Resumo de porta-borda consolidada única com endereços IP públicos
description: Resumo de porta-borda consolidada única com endereços IP públicos.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566397"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="ac041-103">Resumo de porta-borda consolidada única com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac041-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac041-104">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ac041-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ac041-105">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ac041-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="ac041-106">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="ac041-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="ac041-107">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="ac041-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="ac041-108">As informações de planejamento para o proxy reverso e a Federação são encontradas em [cenários para o proxy reverso no Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [planejamento para SIP, Federação XMPP e mensagens instantâneas públicas nas seções do Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ac041-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="ac041-109">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="ac041-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="ac041-110">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="ac041-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="ac041-111">**Rede de perímetro corporativa para única borda consolidada com endereçamento de IP público**</span><span class="sxs-lookup"><span data-stu-id="ac041-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="ac041-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="ac041-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ac041-113">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="ac041-113">Port and Protocol Details</span></span>

<span data-ttu-id="ac041-114">Recomendamos abrir apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="ac041-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="ac041-p103">Para que o acesso remoto funcione em qualquer serviço de borda, é obrigatório que o fluxo do tráfego SIP possa ser bidirecional, como mostra a figura de tráfego de borda de Entrada/Saída. Indicado de outra forma, a mensagem SIP de e para o serviço Borda de Acesso está envolvido em mensagens instantâneas, presença, Webconferência, A/V (áudio/vídeo) e federação.</span><span class="sxs-lookup"><span data-stu-id="ac041-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="ac041-117">Resumo de firewall para borda consolidada única com endereços IP públicos: Interface Externa</span><span class="sxs-lookup"><span data-stu-id="ac041-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac041-118">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="ac041-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ac041-119">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="ac041-119">Source IP address</span></span></th>
<th><span data-ttu-id="ac041-120">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="ac041-120">Destination IP address</span></span></th>
<th><span data-ttu-id="ac041-121">Observações</span><span class="sxs-lookup"><span data-stu-id="ac041-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac041-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ac041-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ac041-123">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-123">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-124">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="ac041-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ac041-125">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="ac041-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-126">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ac041-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ac041-127">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-128">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-128">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-129">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="ac041-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-130">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="ac041-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="ac041-131">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-132">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-132">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-133">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="ac041-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-134">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="ac041-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="ac041-135">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-136">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-136">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-137">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="ac041-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-138">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ac041-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ac041-139">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-139">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-140">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-141">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="ac041-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-142">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ac041-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ac041-143">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-143">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-144">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-145">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="ac041-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-146">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ac041-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ac041-147">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-148">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-148">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-149">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="ac041-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-150">Webconferência/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ac041-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ac041-151">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-151">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-152">Endereço IP público do serviço de borda de Webconferência do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-153">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="ac041-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-154">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ac041-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ac041-155">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-156">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-156">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-157">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac041-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-158">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ac041-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ac041-159">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-160">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-160">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-161">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="ac041-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-162">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ac041-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ac041-163">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-163">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-164">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-165">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="ac041-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-166">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ac041-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ac041-167">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-167">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-168">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-169">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="ac041-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-170">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ac041-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ac041-171">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-172">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-172">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-173">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="ac041-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="ac041-174">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="ac041-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-175">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ac041-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ac041-176">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-176">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-177">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-178">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ac041-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-179">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ac041-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ac041-180">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-180">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-181">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-182">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="ac041-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-183">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ac041-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ac041-184">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-185">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-185">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-186">Negociação de candidatos STUN/TURN por TCP/443</span><span class="sxs-lookup"><span data-stu-id="ac041-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="ac041-187">Resumo do firewall para borda única consolidada com endereços IP públicos: Interface Interna</span><span class="sxs-lookup"><span data-stu-id="ac041-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac041-188">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="ac041-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ac041-189">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="ac041-189">Source IP address</span></span></th>
<th><span data-ttu-id="ac041-190">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="ac041-190">Destination IP address</span></span></th>
<th><span data-ttu-id="ac041-191">Comments</span><span class="sxs-lookup"><span data-stu-id="ac041-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac041-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ac041-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ac041-193">Qualquer um (pode ser definido como IP do servidor Standard Edition, endereço IP do servidor Standard Edition ou endereço IP do pool executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="ac041-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="ac041-194">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-195">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="ac041-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ac041-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ac041-197">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="ac041-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="ac041-198">IP do servidor de borda ou pool que contém a interface interna</span><span class="sxs-lookup"><span data-stu-id="ac041-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-199">Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ac041-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ac041-201">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-202">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="ac041-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="ac041-203">Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="ac041-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="ac041-205">Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="ac041-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="ac041-206">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-207">Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="ac041-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="ac041-209">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="ac041-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="ac041-210">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-211">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ac041-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ac041-213">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-213">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-214">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-215">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="ac041-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ac041-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ac041-217">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-217">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-218">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-219">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="ac041-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ac041-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ac041-221">Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="ac041-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="ac041-222">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-223">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ac041-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ac041-225">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-225">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-226">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-227">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="ac041-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ac041-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ac041-229">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-229">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-230">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-231">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="ac041-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ac041-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ac041-233">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-233">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-234">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ac041-235">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController.exe) ou de agente (ClsAgent.exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="ac041-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="ac041-236">Resumo de firewall para federação</span><span class="sxs-lookup"><span data-stu-id="ac041-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac041-237">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="ac041-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ac041-238">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="ac041-238">Source IP address</span></span></th>
<th><span data-ttu-id="ac041-239">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="ac041-239">Destination IP address</span></span></th>
<th><span data-ttu-id="ac041-240">Observações</span><span class="sxs-lookup"><span data-stu-id="ac041-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac041-241">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ac041-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ac041-242">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="ac041-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-243">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-243">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-244">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="ac041-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="ac041-245">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="ac041-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac041-246">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="ac041-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ac041-247">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="ac041-247">Source IP address</span></span></th>
<th><span data-ttu-id="ac041-248">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="ac041-248">Destination IP address</span></span></th>
<th><span data-ttu-id="ac041-249">Observações</span><span class="sxs-lookup"><span data-stu-id="ac041-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac041-250">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ac041-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ac041-251">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="ac041-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ac041-252">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ac041-253">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="ac041-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-254">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="ac041-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ac041-255">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ac041-256">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="ac041-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="ac041-257">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="ac041-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-258">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="ac041-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ac041-259">Clientes</span><span class="sxs-lookup"><span data-stu-id="ac041-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="ac041-260">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="ac041-261">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="ac041-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-262">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="ac041-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ac041-263">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ac041-264">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ac041-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ac041-265">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="ac041-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-266">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ac041-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ac041-267">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ac041-268">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ac041-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ac041-269">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ac041-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-270">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ac041-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ac041-271">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ac041-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="ac041-272">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="ac041-273">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="ac041-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="ac041-274">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="ac041-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac041-275">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="ac041-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ac041-276">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="ac041-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="ac041-277">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="ac041-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="ac041-278">Comments</span><span class="sxs-lookup"><span data-stu-id="ac041-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac041-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ac041-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ac041-280">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-280">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-281">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-282">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="ac041-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ac041-283">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="ac041-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac041-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ac041-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ac041-285">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="ac041-286">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-286">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-287">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="ac041-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="ac041-288">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="ac041-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac041-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ac041-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ac041-290">Qualquer</span><span class="sxs-lookup"><span data-stu-id="ac041-290">Any</span></span></p></td>
<td><p><span data-ttu-id="ac041-291">Cada IP de interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="ac041-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="ac041-292">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</span><span class="sxs-lookup"><span data-stu-id="ac041-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

