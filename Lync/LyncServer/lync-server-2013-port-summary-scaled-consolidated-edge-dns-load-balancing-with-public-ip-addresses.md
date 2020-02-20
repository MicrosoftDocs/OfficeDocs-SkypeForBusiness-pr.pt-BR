---
title: 'Lync Server 2013: Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df1a650feb27a4f104ae4077d0bf7d541cc5d7d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="3fde1-102">Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fde1-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fde1-103">_**Última modificação do tópico:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="3fde1-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="3fde1-104">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="3fde1-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="3fde1-105">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="3fde1-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="3fde1-106">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="3fde1-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="3fde1-107">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="3fde1-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="3fde1-108">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="3fde1-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="3fde1-109">**Rede de perímetro empresarial para borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos**</span><span class="sxs-lookup"><span data-stu-id="3fde1-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="3fde1-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="3fde1-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="3fde1-111">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="3fde1-111">Port and Protocol Details</span></span>

<span data-ttu-id="3fde1-112">Recomendamos abrir somente as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="3fde1-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="3fde1-p103">Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída. Dito de outra forma, as mensagens SIP de e para o serviço de Borda de Acesso está envolvido em sistemas de mensagens instantâneas (IM), presença, webconferências, áudio/vídeo (A/V) e federação.</span><span class="sxs-lookup"><span data-stu-id="3fde1-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="3fde1-115">Resumo do firewall para borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos: interface externa – nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="3fde1-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fde1-116">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="3fde1-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3fde1-117">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="3fde1-117">Source IP address</span></span></th>
<th><span data-ttu-id="3fde1-118">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="3fde1-118">Destination IP address</span></span></th>
<th><span data-ttu-id="3fde1-119">Observações</span><span class="sxs-lookup"><span data-stu-id="3fde1-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3fde1-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3fde1-121">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-121">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-122">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="3fde1-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="3fde1-123">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="3fde1-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="3fde1-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="3fde1-125">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-126">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-126">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-127">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="3fde1-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="3fde1-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="3fde1-129">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-130">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-130">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-131">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="3fde1-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="3fde1-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="3fde1-133">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-134">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-134">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-135">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="3fde1-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-136">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3fde1-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3fde1-137">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-137">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-138">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-139">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="3fde1-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-140">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3fde1-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3fde1-141">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-141">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-142">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-143">Para conectividade pública e federada de mensagens instantâneas usando SIP</span><span class="sxs-lookup"><span data-stu-id="3fde1-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-144">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3fde1-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3fde1-145">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-146">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-146">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-147">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="3fde1-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-148">Webconferência/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="3fde1-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3fde1-149">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-149">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-150">Endereço IP público do serviço de borda de Webconferência do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-151">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="3fde1-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3fde1-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3fde1-153">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-154">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-154">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-155">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3fde1-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3fde1-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3fde1-157">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-158">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-158">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-159">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="3fde1-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3fde1-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3fde1-161">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-161">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-162">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-163">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3fde1-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3fde1-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3fde1-165">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-165">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-166">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-167">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="3fde1-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3fde1-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3fde1-169">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-170">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-170">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-171">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="3fde1-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="3fde1-172">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="3fde1-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3fde1-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3fde1-174">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-174">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-175">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-176">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3fde1-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3fde1-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3fde1-178">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-178">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-179">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-180">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="3fde1-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3fde1-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3fde1-182">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3fde1-183">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-183">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-184">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="3fde1-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="3fde1-185">Resumo do firewall para borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos: interface interna - nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="3fde1-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fde1-186">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="3fde1-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3fde1-187">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="3fde1-187">Source IP address</span></span></th>
<th><span data-ttu-id="3fde1-188">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="3fde1-188">Destination IP address</span></span></th>
<th><span data-ttu-id="3fde1-189">Comentários</span><span class="sxs-lookup"><span data-stu-id="3fde1-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3fde1-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3fde1-191">Qualquer um (pode ser definido como endereço de servidor front-end ou endereço IP do pool de front-ends executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="3fde1-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="3fde1-192">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-193">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="3fde1-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3fde1-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3fde1-195">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="3fde1-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3fde1-196">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-197">Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="3fde1-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3fde1-199">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-200">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="3fde1-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="3fde1-201">Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="3fde1-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="3fde1-203">Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="3fde1-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="3fde1-204">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-205">Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="3fde1-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="3fde1-207">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="3fde1-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="3fde1-208">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-209">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3fde1-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3fde1-211">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-211">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-212">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-213">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="3fde1-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3fde1-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3fde1-215">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-215">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-216">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-217">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="3fde1-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="3fde1-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="3fde1-219">Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="3fde1-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="3fde1-220">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-221">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="3fde1-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="3fde1-223">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-223">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-224">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-225">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="3fde1-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="3fde1-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="3fde1-227">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-227">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-228">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-229">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="3fde1-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="3fde1-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="3fde1-231">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-231">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-232">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="3fde1-233">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="3fde1-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="3fde1-234">Resumo de firewall para federação</span><span class="sxs-lookup"><span data-stu-id="3fde1-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fde1-235">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="3fde1-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3fde1-236">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="3fde1-236">Source IP address</span></span></th>
<th><span data-ttu-id="3fde1-237">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="3fde1-237">Destination IP address</span></span></th>
<th><span data-ttu-id="3fde1-238">Observações</span><span class="sxs-lookup"><span data-stu-id="3fde1-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-239">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3fde1-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3fde1-240">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="3fde1-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-241">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-241">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-242">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="3fde1-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="3fde1-243">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="3fde1-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fde1-244">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="3fde1-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3fde1-245">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="3fde1-245">Source IP address</span></span></th>
<th><span data-ttu-id="3fde1-246">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="3fde1-246">Destination IP address</span></span></th>
<th><span data-ttu-id="3fde1-247">Observações</span><span class="sxs-lookup"><span data-stu-id="3fde1-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-248">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3fde1-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3fde1-249">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="3fde1-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3fde1-250">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3fde1-251">Para conectividade pública e federada de mensagens instantâneas usando SIP</span><span class="sxs-lookup"><span data-stu-id="3fde1-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-252">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="3fde1-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="3fde1-253">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3fde1-254">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="3fde1-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="3fde1-255">Para conectividade de IM público e federado usando SIP</span><span class="sxs-lookup"><span data-stu-id="3fde1-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-256">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="3fde1-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3fde1-257">Clientes</span><span class="sxs-lookup"><span data-stu-id="3fde1-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="3fde1-258">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="3fde1-259">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="3fde1-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="3fde1-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="3fde1-261">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3fde1-262">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3fde1-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3fde1-263">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="3fde1-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3fde1-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3fde1-265">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3fde1-266">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3fde1-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3fde1-267">Necessário para conectividade de IM público com Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3fde1-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="3fde1-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="3fde1-269">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3fde1-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="3fde1-270">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="3fde1-271">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="3fde1-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="3fde1-272">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="3fde1-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3fde1-273">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="3fde1-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3fde1-274">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="3fde1-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="3fde1-275">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="3fde1-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="3fde1-276">Comentários</span><span class="sxs-lookup"><span data-stu-id="3fde1-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3fde1-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3fde1-278">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-278">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-279">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-280">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="3fde1-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3fde1-281">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="3fde1-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fde1-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="3fde1-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="3fde1-283">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="3fde1-284">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-284">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-285">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="3fde1-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="3fde1-286">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="3fde1-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fde1-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="3fde1-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="3fde1-288">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="3fde1-288">Any</span></span></p></td>
<td><p><span data-ttu-id="3fde1-289">Cada IP de interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="3fde1-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="3fde1-290">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</span><span class="sxs-lookup"><span data-stu-id="3fde1-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

