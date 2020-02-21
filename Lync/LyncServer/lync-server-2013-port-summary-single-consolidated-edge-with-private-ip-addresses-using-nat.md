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
ms.openlocfilehash: 870732df847d589ebb24751977babc8182d79a3f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="e6ab4-102">Resumo de porta-borda consolidada única com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6ab4-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6ab4-103">_**Última modificação do tópico:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="e6ab4-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="e6ab4-104">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="e6ab4-105">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="e6ab4-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="e6ab4-106">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="e6ab4-107">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="e6ab4-108">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="e6ab4-109">**Perímetro de rede para um único servidor de borda consolidado com endereçamento IP privado usando NAT**</span><span class="sxs-lookup"><span data-stu-id="e6ab4-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="e6ab4-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="e6ab4-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e6ab4-111">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="e6ab4-111">Port and Protocol Details</span></span>

<span data-ttu-id="e6ab4-112">Recomendamos abrir apenas as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="e6ab4-113">Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="e6ab4-114">Declarado de outra maneira, as mensagens SIP para e a partir do serviço de borda de acesso estão envolvidas em mensagens instantâneas (IM), presença, webconferência, áudio/vídeo (A/V) e Federação.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="e6ab4-115">Resumo do firewall para borda consolidada única com endereços IP privados usando NAT: interface externa</span><span class="sxs-lookup"><span data-stu-id="e6ab4-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6ab4-116">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e6ab4-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e6ab4-117">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="e6ab4-117">Source IP address</span></span></th>
<th><span data-ttu-id="e6ab4-118">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="e6ab4-118">Destination IP address</span></span></th>
<th><span data-ttu-id="e6ab4-119">Observações</span><span class="sxs-lookup"><span data-stu-id="e6ab4-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e6ab4-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-121">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-121">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-122">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-123">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="e6ab4-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="e6ab4-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-125">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-126">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-126">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-127">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="e6ab4-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="e6ab4-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-129">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-130">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-130">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-131">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="e6ab4-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-133">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-134">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-134">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-135">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-136">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-137">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-137">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-138">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-139">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="e6ab4-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-140">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-141">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-141">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-142">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-143">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-144">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-145">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-146">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-146">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-147">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-148">Webconferência/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e6ab4-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-149">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-149">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-150">Serviço de borda de Webconferência da servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-151">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="e6ab4-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-152">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e6ab4-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-153">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-154">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-154">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-155">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-156">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e6ab4-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-157">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-158">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-158">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-159">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-160">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e6ab4-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-161">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-161">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-162">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-163">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e6ab4-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-164">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e6ab4-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-165">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-165">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-166">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-167">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="e6ab4-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e6ab4-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-169">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-170">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-170">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-171">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="e6ab4-172">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e6ab4-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-174">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-174">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-175">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-176">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e6ab4-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e6ab4-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-178">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-178">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-179">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-180">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="e6ab4-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e6ab4-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-182">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-183">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-183">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-184">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="e6ab4-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="e6ab4-185">Resumo do firewall para borda consolidada única com endereços IP privados usando NAT: interface interna</span><span class="sxs-lookup"><span data-stu-id="e6ab4-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6ab4-186">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e6ab4-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e6ab4-187">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="e6ab4-187">Source IP address</span></span></th>
<th><span data-ttu-id="e6ab4-188">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="e6ab4-188">Destination IP address</span></span></th>
<th><span data-ttu-id="e6ab4-189">Comentários</span><span class="sxs-lookup"><span data-stu-id="e6ab4-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e6ab4-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-191">Qualquer um (pode ser definido como IP do servidor Standard Edition, endereço IP do servidor Standard Edition ou endereço IP do pool executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-192">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-193">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="e6ab4-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e6ab4-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-195">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-196">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-197">Tráfego SIP de saída (do diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e6ab4-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-199">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-200">Qualquer um (pode ser definido como diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-201">Tráfego SIP de entrada (para diretor, endereço IP do pool de diretores, servidor front-end ou endereço IP do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="e6ab4-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-203">Qualquer um (pode ser definido como endereço IP do servidor front-end ou cada endereço IP do servidor front-end em um pool de front-ends)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-204">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-205">Tráfego de Webconferência do servidor front-end ou de cada servidor de front-end, se estiver em um pool, para a interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="e6ab4-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-207">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-208">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-209">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e6ab4-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-211">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-211">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-212">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-213">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="e6ab4-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e6ab4-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-215">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-215">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-216">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-217">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="e6ab4-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-219">Qualquer um (pode ser definido como o endereço IP do servidor front-end ou o pool que contém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-220">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-221">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e6ab4-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-223">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-223">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-224">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-225">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="e6ab4-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e6ab4-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-227">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-227">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-228">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-229">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="e6ab4-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e6ab4-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-231">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-231">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-232">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-233">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="e6ab4-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="e6ab4-234">Resumo de firewall para federação</span><span class="sxs-lookup"><span data-stu-id="e6ab4-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6ab4-235">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e6ab4-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e6ab4-236">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="e6ab4-236">Source IP address</span></span></th>
<th><span data-ttu-id="e6ab4-237">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="e6ab4-237">Destination IP address</span></span></th>
<th><span data-ttu-id="e6ab4-238">Observações</span><span class="sxs-lookup"><span data-stu-id="e6ab4-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-239">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-240">Endereço IP público do serviço da Borda de Acesso</span><span class="sxs-lookup"><span data-stu-id="e6ab4-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-241">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-241">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-242">Para conectividade a redes públicas e federadas de IM usando SIP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="e6ab4-243">Resumo do firewall – Conectividade pública de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="e6ab4-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6ab4-244">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e6ab4-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e6ab4-245">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="e6ab4-245">Source IP address</span></span></th>
<th><span data-ttu-id="e6ab4-246">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="e6ab4-246">Destination IP address</span></span></th>
<th><span data-ttu-id="e6ab4-247">Observações</span><span class="sxs-lookup"><span data-stu-id="e6ab4-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-248">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-249">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="e6ab4-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-250">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-251">Para conectividade pública e federada de mensagens instantâneas usando SIP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-252">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-253">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-254">Parceiros de conectividade pública de IM</span><span class="sxs-lookup"><span data-stu-id="e6ab4-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-255">Para conectividade de IM público e federado usando SIP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-256">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-257">Clientes</span><span class="sxs-lookup"><span data-stu-id="e6ab4-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-258">Serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-259">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="e6ab4-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-260">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="e6ab4-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-261">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-262">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e6ab4-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-263">Usado para sessões A/V com o Windows Live Messenger se a conectividade pública de IM estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e6ab4-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-265">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-266">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e6ab4-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-267">Necessário para conectividade de IM público com Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e6ab4-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e6ab4-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-269">Clientes Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e6ab4-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-270">Serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-271">Obrigatório para conectividade pública de IM com o Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="e6ab4-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="e6ab4-272">Resumo de Firewall para protocolo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6ab4-273">Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="e6ab4-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e6ab4-274">Origem (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="e6ab4-275">Destino (endereço IP)</span><span class="sxs-lookup"><span data-stu-id="e6ab4-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="e6ab4-276">Comentários</span><span class="sxs-lookup"><span data-stu-id="e6ab4-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e6ab4-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-278">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-278">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-279">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-280">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e6ab4-281">Permite a comunicação com o servidor de borda XMPP proxy de parceiros federados do XMPP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6ab4-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e6ab4-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-283">Endereço IP da interface de serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-284">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-284">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-285">Porta padrão de comunicação entre servidores para XMPP.</span><span class="sxs-lookup"><span data-stu-id="e6ab4-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e6ab4-286">Permite a comunicação do proxy do servidor de borda XMPP com parceiros federados XMPP</span><span class="sxs-lookup"><span data-stu-id="e6ab4-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6ab4-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e6ab4-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-288">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="e6ab4-288">Any</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-289">Cada IP de interface de servidor de borda interna</span><span class="sxs-lookup"><span data-stu-id="e6ab4-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="e6ab4-290">Tráfego XMPP interno do Gateway XMPP no servidor front-end ou do pool de front-ends para o endereço IP interno do servidor de borda ou o endereço IP interno de cada membro do pool de borda</span><span class="sxs-lookup"><span data-stu-id="e6ab4-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

