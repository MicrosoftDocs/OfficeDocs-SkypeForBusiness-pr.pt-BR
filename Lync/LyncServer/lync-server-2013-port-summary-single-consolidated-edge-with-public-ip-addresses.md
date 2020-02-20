---
title: Resumo de porta-borda consolidada única com endereços IP públicos
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
ms.openlocfilehash: 2c307ff7318a426610cf371a3d6f55591a7c6ed0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="86fa6-102">Resumo de porta-borda consolidada única com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86fa6-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86fa6-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="86fa6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="86fa6-104">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="86fa6-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="86fa6-105">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="86fa6-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="86fa6-106">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="86fa6-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="86fa6-107">As informações de planejamento para o proxy reverso e a Federação são encontradas em [cenários para o proxy reverso no Lync server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) e [planejamento para SIP, Federação XMPP e mensagens instantâneas públicas nas seções do Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="86fa6-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="86fa6-108">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="86fa6-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="86fa6-109">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="86fa6-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="86fa6-110">**Rede de perímetro corporativa para única borda consolidada com endereçamento de IP público**</span><span class="sxs-lookup"><span data-stu-id="86fa6-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="86fa6-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="86fa6-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="86fa6-112">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="86fa6-112">Port and Protocol Details</span></span>

<span data-ttu-id="86fa6-113">Recomendamos abrir apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="86fa6-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="86fa6-p103">Para que o acesso remoto funcione em qualquer serviço de borda, é obrigatório que o fluxo do tráfego SIP possa ser bidirecional, como mostra a figura de tráfego de borda de Entrada/Saída. Indicado de outra forma, a mensagem SIP de e para o serviço Borda de Acesso está envolvido em mensagens instantâneas, presença, Webconferência, A/V (áudio/vídeo) e federação.</span><span class="sxs-lookup"><span data-stu-id="86fa6-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="86fa6-116">Resumo de firewall para borda consolidada única com endereços IP públicos: Interface Externa</span><span class="sxs-lookup"><span data-stu-id="86fa6-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86fa6-117">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="86fa6-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="86fa6-118">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="86fa6-118">Source IP address</span></span></th>
<th><span data-ttu-id="86fa6-119">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="86fa6-119">Destination IP address</span></span></th>
<th><span data-ttu-id="86fa6-120">Observações</span><span class="sxs-lookup"><span data-stu-id="86fa6-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="86fa6-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="86fa6-122">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-122">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-123">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="86fa6-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="86fa6-124">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="86fa6-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="86fa6-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="86fa6-126">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-127">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-127">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-128">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="86fa6-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="86fa6-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="86fa6-130">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-131">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-131">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-132">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="86fa6-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="86fa6-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="86fa6-134">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-135">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-135">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-136">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="86fa6-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-137">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="86fa6-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="86fa6-138">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-138">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-139">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-140">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="86fa6-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-141">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="86fa6-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86fa6-142">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-142">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-143">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-144">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="86fa6-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-145">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="86fa6-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86fa6-146">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-147">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-147">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-148">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="86fa6-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-149">Webconferência/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="86fa6-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="86fa6-150">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-150">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-151">Endereço IP público do serviço de borda de Webconferência do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-152">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="86fa6-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-153">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="86fa6-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="86fa6-154">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-155">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-155">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-156">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="86fa6-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-157">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="86fa6-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="86fa6-158">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-159">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-159">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-160">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="86fa6-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-161">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="86fa6-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="86fa6-162">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-162">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-163">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-164">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="86fa6-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-165">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="86fa6-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="86fa6-166">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-166">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-167">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-168">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="86fa6-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="86fa6-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="86fa6-170">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-171">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-171">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-172">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="86fa6-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="86fa6-173">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="86fa6-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="86fa6-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="86fa6-175">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-175">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-176">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-177">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="86fa6-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="86fa6-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="86fa6-179">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-179">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-180">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-181">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="86fa6-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="86fa6-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="86fa6-183">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-184">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-184">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-185">Negociação de candidatos STUN/TURN por TCP/443</span><span class="sxs-lookup"><span data-stu-id="86fa6-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="86fa6-186">Resumo do firewall para borda única consolidada com endereços IP públicos: Interface Interna</span><span class="sxs-lookup"><span data-stu-id="86fa6-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86fa6-187">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="86fa6-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="86fa6-188">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="86fa6-188">Source IP address</span></span></th>
<th><span data-ttu-id="86fa6-189">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="86fa6-189">Destination IP address</span></span></th>
<th><span data-ttu-id="86fa6-190">Comentários</span><span class="sxs-lookup"><span data-stu-id="86fa6-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="86fa6-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="86fa6-192">Qualquer um (pode ser definido como IP do servidor Standard Edition, endereço IP do servidor Standard Edition ou endereço IP do pool executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="86fa6-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="86fa6-193">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-194">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="86fa6-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="86fa6-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86fa6-196">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="86fa6-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="86fa6-197">IP do servidor de borda ou pool que contém a interface interna</span><span class="sxs-lookup"><span data-stu-id="86fa6-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-198">Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="86fa6-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86fa6-200">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-201">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="86fa6-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="86fa6-202">Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="86fa6-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="86fa6-204">Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="86fa6-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="86fa6-205">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-206">Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="86fa6-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="86fa6-208">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="86fa6-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="86fa6-209">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-210">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="86fa6-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="86fa6-212">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-212">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-213">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-214">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="86fa6-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="86fa6-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="86fa6-216">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-216">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-217">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-218">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="86fa6-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="86fa6-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="86fa6-220">Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="86fa6-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="86fa6-221">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-222">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="86fa6-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="86fa6-224">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-224">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-225">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-226">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="86fa6-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="86fa6-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="86fa6-228">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-228">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-229">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-230">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="86fa6-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="86fa6-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="86fa6-232">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-232">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-233">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="86fa6-234">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="86fa6-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="86fa6-235">Resumo de firewall para federação</span><span class="sxs-lookup"><span data-stu-id="86fa6-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86fa6-236">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="86fa6-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="86fa6-237">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="86fa6-237">Source IP address</span></span></th>
<th><span data-ttu-id="86fa6-238">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="86fa6-238">Destination IP address</span></span></th>
<th><span data-ttu-id="86fa6-239">Observações</span><span class="sxs-lookup"><span data-stu-id="86fa6-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-240">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="86fa6-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86fa6-241">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="86fa6-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-242">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-242">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-243">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="86fa6-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="86fa6-244">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="86fa6-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86fa6-245">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="86fa6-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="86fa6-246">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="86fa6-246">Source IP address</span></span></th>
<th><span data-ttu-id="86fa6-247">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="86fa6-247">Destination IP address</span></span></th>
<th><span data-ttu-id="86fa6-248">Observações</span><span class="sxs-lookup"><span data-stu-id="86fa6-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-249">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="86fa6-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86fa6-250">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="86fa6-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="86fa6-251">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="86fa6-252">Para conectividade pública e federada de mensagens instantâneas usando SIP</span><span class="sxs-lookup"><span data-stu-id="86fa6-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-253">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="86fa6-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="86fa6-254">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="86fa6-255">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="86fa6-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="86fa6-256">Para conectividade de IM público e federado usando SIP</span><span class="sxs-lookup"><span data-stu-id="86fa6-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-257">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="86fa6-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="86fa6-258">Clientes</span><span class="sxs-lookup"><span data-stu-id="86fa6-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="86fa6-259">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="86fa6-260">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="86fa6-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-261">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="86fa6-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="86fa6-262">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="86fa6-263">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="86fa6-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="86fa6-264">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="86fa6-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="86fa6-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="86fa6-266">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="86fa6-267">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="86fa6-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="86fa6-268">Necessário para conectividade de IM público com Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="86fa6-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="86fa6-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="86fa6-270">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="86fa6-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="86fa6-271">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="86fa6-272">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="86fa6-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="86fa6-273">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="86fa6-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86fa6-274">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="86fa6-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="86fa6-275">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="86fa6-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="86fa6-276">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="86fa6-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="86fa6-277">Comentários</span><span class="sxs-lookup"><span data-stu-id="86fa6-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="86fa6-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="86fa6-279">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-279">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-280">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-281">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="86fa6-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="86fa6-282">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="86fa6-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86fa6-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="86fa6-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="86fa6-284">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="86fa6-285">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-285">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-286">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="86fa6-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="86fa6-287">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="86fa6-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86fa6-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="86fa6-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="86fa6-289">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="86fa6-289">Any</span></span></p></td>
<td><p><span data-ttu-id="86fa6-290">Cada IP de interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="86fa6-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="86fa6-291">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</span><span class="sxs-lookup"><span data-stu-id="86fa6-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

