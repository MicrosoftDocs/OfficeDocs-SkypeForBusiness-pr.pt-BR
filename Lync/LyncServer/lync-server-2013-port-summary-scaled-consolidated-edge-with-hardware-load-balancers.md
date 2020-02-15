---
title: Resumo de porta-borda consolidada em escala com balanceadores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cad84208df5129b3a10c1e80aa28442ebcbd44
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="1f034-102">Resumo de porta-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f034-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f034-103">_**Última modificação do tópico:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="1f034-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="1f034-104">O Lync Server 2013, a funcionalidade do servidor de borda descrito nesta arquitetura de cenário é muito semelhante ao que foi implementado no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1f034-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="1f034-105">O acréscimo mais notável é a entrada **5269 over TCP** de porta para XMPP (extensible messaging and presence protocol).</span><span class="sxs-lookup"><span data-stu-id="1f034-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="1f034-106">O Lync Server 2013 implanta opcionalmente um proxy do XMPP no servidor de borda ou no pool de borda e no servidor de gateway do XMPP no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1f034-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="1f034-107">Além do IPv4, o servidor de borda agora oferece suporte a IPv6.</span><span class="sxs-lookup"><span data-stu-id="1f034-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="1f034-108">Para não confundir, apenas o IPv4 é usado nos cenários.</span><span class="sxs-lookup"><span data-stu-id="1f034-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="1f034-109">**Borda consolidada dimensionada usando o balanceamento de carga de hardware**</span><span class="sxs-lookup"><span data-stu-id="1f034-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="1f034-110">![Portas e protocolos de rede de perímetro do servidor de borda](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Portas e protocolos de rede de perímetro do servidor de borda")</span><span class="sxs-lookup"><span data-stu-id="1f034-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="1f034-111">Detalhes de Porta e Protocolo</span><span class="sxs-lookup"><span data-stu-id="1f034-111">Port and Protocol Details</span></span>

<span data-ttu-id="1f034-112">Recomendamos abrir somente as portas necessárias para dar suporte à funcionalidade para a qual você está fornecendo acesso externo.</span><span class="sxs-lookup"><span data-stu-id="1f034-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="1f034-p103">Para que o acesso remoto funcione para qualquer serviço de borda, é imprescindível que o tráfego SIP seja permitido bi-direcionalmente, conforme mostra a figura do tráfego de borda de entrada/saída. Dito de outra forma, as mensagens SIP de e para o serviço de Borda de Acesso está envolvido em sistemas de mensagens instantâneas (IM), presença, webconferências, áudio/vídeo (A/V) e federação.</span><span class="sxs-lookup"><span data-stu-id="1f034-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="1f034-115">Resumo do firewall para borda consolidada em escala, balanceamento de carga de hardware: interface externa – nó 1 e nó 2 (exemplo)</span><span class="sxs-lookup"><span data-stu-id="1f034-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f034-116">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="1f034-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1f034-117">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="1f034-117">Source IP address</span></span></th>
<th><span data-ttu-id="1f034-118">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="1f034-118">Destination IP address</span></span></th>
<th><span data-ttu-id="1f034-119">Observações</span><span class="sxs-lookup"><span data-stu-id="1f034-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f034-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="1f034-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="1f034-121">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-122">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-122">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-123">Revogação de certificado/verificação e recuperação CRL</span><span class="sxs-lookup"><span data-stu-id="1f034-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="1f034-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="1f034-125">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-126">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-126">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-127">Consulta DNS sobre TCP</span><span class="sxs-lookup"><span data-stu-id="1f034-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="1f034-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="1f034-129">Endereço IP público do serviço de borda de acesso do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-130">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-130">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-131">Consulta DNS sobre UDP</span><span class="sxs-lookup"><span data-stu-id="1f034-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-132">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="1f034-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1f034-133">Endereço IP do serviço de borda de A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-134">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-134">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-135">Necessário para federação com parceiros que executam o Office Communications Server 2007, o Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f034-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-136">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="1f034-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1f034-137">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-138">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-138">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-139">Necessário somente para federação com parceiros que executam o Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="1f034-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-140">A/V/RTP/TCP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="1f034-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1f034-141">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-141">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-142">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-143">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="1f034-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-144">A/V/RTP/UDP/50000-59.999</span><span class="sxs-lookup"><span data-stu-id="1f034-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1f034-145">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-145">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-146">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-147">Necessário somente para federação com parceiros que executam o Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="1f034-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1f034-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1f034-149">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-150">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-150">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-151">3478 a saída é usada para determinar a versão do servidor de borda com a qual o Lync Server está se comunicando e também para o tráfego de mídia do servidor de borda servidor a borda.</span><span class="sxs-lookup"><span data-stu-id="1f034-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="1f034-152">Necessário para federação com o Lync Server 2010, o Windows Live Messenger e o Office Communications Server 2007 R2, e também se vários pools de borda estiverem implantados em uma empresa.</span><span class="sxs-lookup"><span data-stu-id="1f034-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1f034-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1f034-154">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-154">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-155">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-156">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1f034-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1f034-158">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-158">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-159">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-160">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1f034-162">Endereço IP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-163">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-163">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-164">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="1f034-165">Resumo do firewall para borda consolidada em escala, balanceamento de carga de hardware: nó de interface interna 1 e nó 2</span><span class="sxs-lookup"><span data-stu-id="1f034-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f034-166">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="1f034-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1f034-167">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="1f034-167">Source IP address</span></span></th>
<th><span data-ttu-id="1f034-168">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="1f034-168">Destination IP address</span></span></th>
<th><span data-ttu-id="1f034-169">Observações</span><span class="sxs-lookup"><span data-stu-id="1f034-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f034-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="1f034-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="1f034-171">Qualquer um (pode ser definido como endereço de servidor front-end ou endereço IP virtual do pool de front-ends executando o serviço de gateway do XMPP)</span><span class="sxs-lookup"><span data-stu-id="1f034-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="1f034-172">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-173">Tráfego XMPP de saída do serviço de Gateway XMPP executado no servidor front-end ou no pool de front-ends</span><span class="sxs-lookup"><span data-stu-id="1f034-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="1f034-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="1f034-175">Qualquer um (pode ser definido como o IP ou pool do servidor de front-end que mantém o repositório de gerenciamento central)</span><span class="sxs-lookup"><span data-stu-id="1f034-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="1f034-176">Interface Interna dos Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="1f034-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-177">Replicação de alterações do armazenamento do Gerenciamento Central para o servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="1f034-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="1f034-179">Qualquer um (pode ser definido como IP de diretor, IP do servidor front-end ou IP virtual do pool)</span><span class="sxs-lookup"><span data-stu-id="1f034-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="1f034-180">Interface Interna dos Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="1f034-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-181">Tráfego de Webconferência da implantação interna para interface de servidor de borda interno</span><span class="sxs-lookup"><span data-stu-id="1f034-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1f034-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1f034-183">Qualquer um (pode ser definido como IP de diretor, IP do servidor front-end ou IP virtual do pool)</span><span class="sxs-lookup"><span data-stu-id="1f034-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="1f034-184">Interface Interna dos Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="1f034-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-185">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="1f034-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1f034-187">Qualquer um (pode ser definido como IP de diretor, IP do servidor front-end ou IP virtual do pool)</span><span class="sxs-lookup"><span data-stu-id="1f034-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="1f034-188">Interface Interna dos Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="1f034-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-189">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, aparelho de filial persistente ou servidor de filial persistente se a comunicação UDP não puder ser estabelecida, o TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="1f034-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1f034-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1f034-191">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-191">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-192">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-193">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="1f034-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1f034-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1f034-195">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-195">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-196">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-197">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="1f034-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1f034-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1f034-199">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-199">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-200">Interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-201">Controle de log centralizado usando o Shell de gerenciamento do Lync Server e os cmdlets do serviço de registro em log centralizado, comandos de linha de comando do ClsController (ClsController. exe) ou de agente (ClsAgent. exe) e coleção de logs</span><span class="sxs-lookup"><span data-stu-id="1f034-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1f034-202">Os balanceadores de carga de hardware têm requisitos específicos quando implantados para fornecer disponibilidade e balanceamento de carga para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f034-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="1f034-203">Os requisitos são definidos na figura e tabelas a seguir.</span><span class="sxs-lookup"><span data-stu-id="1f034-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="1f034-204">Fornecedores terceirizados podem usar terminologia diferente para os requisitos definidos aqui.</span><span class="sxs-lookup"><span data-stu-id="1f034-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="1f034-205">Será necessário mapear os requisitos do Lync Server para os recursos e opções de configuração fornecidos pelo fornecedor do balanceador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="1f034-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="1f034-206">Ao configurar balanceadores de carga de hardware, considere os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="1f034-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="1f034-207">A conversão de endereço de rede de origem (SNAT) pode ser configurada no balanceador de carga de hardware (HLB) para serviço de borda de acesso e serviço de borda de Webconferência</span><span class="sxs-lookup"><span data-stu-id="1f034-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="1f034-208">O SNAT não pode ser configurado no serviço de borda A/V – o serviço de borda A/V deve responder com o endereço do servidor real, e não o VIP (IP virtual) do HLB, para a passagem simples de UDP sobre NAT (STUN)/Traversal usando o NAT de retransmissão (ativar)/Federation TURN (FTURN) para funcionar corretamente</span><span class="sxs-lookup"><span data-stu-id="1f034-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="1f034-209">Se o cliente envia uma solicitação para o HLB, a resposta deve retornar do VIP HLB</span><span class="sxs-lookup"><span data-stu-id="1f034-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="1f034-210">Se o cliente envia uma solicitação para a borda, a resposta deve retornar do IP de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="1f034-211">Os endereços IP públicos são usados em cada interface de servidor e nos VIPs do HLB, e seus requisitos de endereço IP público são N + 1, onde há um endereço IP público para cada interface de servidor real e um para cada VIP do HLB.</span><span class="sxs-lookup"><span data-stu-id="1f034-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="1f034-212">Onde você tem dois servidores de borda no pool, isso resulta em 9 endereços IP públicos, onde 3 são usados para os VIPs HLB e um para cada interface de servidor de borda (um total de seis para os servidores)</span><span class="sxs-lookup"><span data-stu-id="1f034-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="1f034-213">Para o serviço de borda de acesso e serviço de borda de webconferência, (e usando NAT no HLB) o cliente contata o VIP, o VIP altera o endereço IP de origem do cliente para seu próprio endereço IP.</span><span class="sxs-lookup"><span data-stu-id="1f034-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="1f034-214">A interface do servidor resolve o endereço de retorno para o VIP, o VIP altera o endereço de origem do endereço IP da interface do servidor e envia o pacote para o cliente</span><span class="sxs-lookup"><span data-stu-id="1f034-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="1f034-215">Para o serviço de borda A/V, o VIP não deve alterar o endereço IP de origem e o endereço do servidor real é retornado ao cliente diretamente – você não pode configurar o NAT no HLB para tráfego AV</span><span class="sxs-lookup"><span data-stu-id="1f034-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="1f034-216">Se o cliente envia uma solicitação para o VIP HLB, a resposta deve retornar do VIP HLB</span><span class="sxs-lookup"><span data-stu-id="1f034-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="1f034-217">Se o cliente envia uma solicitação para o IP de borda, a resposta deve retornar do IP de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="1f034-218">Para o AV, o firewall externo manterá o endereço IP público do real Server para todos os pacotes</span><span class="sxs-lookup"><span data-stu-id="1f034-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="1f034-219">Depois de estabelecida, o cliente para a comunicação do serviço de borda a/V é para o servidor real, não para o HLB</span><span class="sxs-lookup"><span data-stu-id="1f034-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="1f034-220">A borda interna para servidores internos e clientes devem ser roteadas, e as rotas persistentes são definidas para todas as redes internas que hospedam servidores ou clientes</span><span class="sxs-lookup"><span data-stu-id="1f034-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="1f034-221">O VIP do serviço de borda de acesso do HLB atuará como o gateway padrão para cada interface de servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1f034-222">Para obter mais informações sobre planejamento e funcionalidade de NAT, consulte <A href="lync-server-2013-hardware-load-balancer-requirements.md">requisitos do balanceador de carga de hardware para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1f034-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1f034-223">![Detalhes de portas e protocolos do servidor de borda](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Detalhes de portas e protocolos do servidor de borda")</span><span class="sxs-lookup"><span data-stu-id="1f034-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="1f034-224">Configurações de porta externa necessárias para borda consolidada em escala, balanceamento de carga de hardware: IPs virtuais de interface externa</span><span class="sxs-lookup"><span data-stu-id="1f034-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f034-225">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="1f034-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1f034-226">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="1f034-226">Source IP address</span></span></th>
<th><span data-ttu-id="1f034-227">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="1f034-227">Destination IP address</span></span></th>
<th><span data-ttu-id="1f034-228">Observações</span><span class="sxs-lookup"><span data-stu-id="1f034-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f034-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="1f034-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="1f034-230">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-230">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-231">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="1f034-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="1f034-232">O serviço de proxy XMPP aceita tráfego de contatos XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="1f034-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="1f034-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="1f034-234">Serviço de proxy XMPP (compartilha o endereço IP com o serviço de borda de acesso)</span><span class="sxs-lookup"><span data-stu-id="1f034-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="1f034-235">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-235">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-236">O serviço de proxy XMPP envia o tráfego para os contatos do XMPP em federações XMPP definidas</span><span class="sxs-lookup"><span data-stu-id="1f034-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-237">/TCP/443 de acesso/SIP (TLS)</span><span class="sxs-lookup"><span data-stu-id="1f034-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1f034-238">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-238">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-239">Endereço VIP público do serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="1f034-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-240">Tráfego SIP de cliente a servidor para acesso de usuário externo</span><span class="sxs-lookup"><span data-stu-id="1f034-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-241">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1f034-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1f034-242">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-242">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-243">Endereço VIP público do serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="1f034-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-244">Sinalização SIP, conectividade de IM pública e federada usando SIP</span><span class="sxs-lookup"><span data-stu-id="1f034-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-245">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1f034-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1f034-246">Endereço VIP público do serviço de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="1f034-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-247">Parceiro federado</span><span class="sxs-lookup"><span data-stu-id="1f034-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="1f034-248">Sinalização SIP, conectividade de IM pública e federada usando SIP</span><span class="sxs-lookup"><span data-stu-id="1f034-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-249">Webconferência/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1f034-250">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-250">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-251">Endereço VIP público do serviço de borda de Webconferência do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-252">Mídia de webconferência</span><span class="sxs-lookup"><span data-stu-id="1f034-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1f034-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1f034-254">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-254">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-255">Endereço VIP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-256">Negociação de candidatos STUN/TURN através de UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1f034-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1f034-258">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-258">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-259">Endereço VIP público do serviço de borda A/V do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="1f034-260">Negociação de candidatos STUN/TURN através de TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="1f034-261">Resumo do firewall para borda consolidada em escala, balanceamento de carga de hardware: IPs virtuais de interface interna</span><span class="sxs-lookup"><span data-stu-id="1f034-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f034-262">Função/Protocolo/TCP ou UDP/Porta</span><span class="sxs-lookup"><span data-stu-id="1f034-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1f034-263">Endereço IP de origem</span><span class="sxs-lookup"><span data-stu-id="1f034-263">Source IP address</span></span></th>
<th><span data-ttu-id="1f034-264">Endereço IP de destino</span><span class="sxs-lookup"><span data-stu-id="1f034-264">Destination IP address</span></span></th>
<th><span data-ttu-id="1f034-265">Observações</span><span class="sxs-lookup"><span data-stu-id="1f034-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f034-266">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1f034-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1f034-267">Qualquer um (pode ser definido como diretor, endereço IP virtual do pool de diretores, servidor front-end ou endereço IP virtual do pool de front-end)</span><span class="sxs-lookup"><span data-stu-id="1f034-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="1f034-268">Interface VIP interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-269">Tráfego SIP de saída (do diretor, endereço IP virtual do pool de diretores, servidor front-end ou endereço IP virtual do pool de front-ends) para VIP de borda interna</span><span class="sxs-lookup"><span data-stu-id="1f034-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-270">/TCP/5061 de acesso/SIP (MTLS)</span><span class="sxs-lookup"><span data-stu-id="1f034-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1f034-271">Interface VIP interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-272">Qualquer um (pode ser definido como diretor, endereço IP virtual do pool de diretores, servidor front-end ou endereço IP virtual do pool de front-end)</span><span class="sxs-lookup"><span data-stu-id="1f034-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="1f034-273">Tráfego SIP de entrada (para diretor, endereço IP virtual do pool de diretores, servidor front-end ou endereço IP virtual do pool de front-ends) da interface interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="1f034-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="1f034-275">Qualquer um (pode ser definido como endereço IP do servidor front-end ou endereço IP do pool de front-ends ou qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda)</span><span class="sxs-lookup"><span data-stu-id="1f034-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="1f034-276">Interface VIP interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-277">Autenticação de usuários A/V (serviço de autenticação A/V) do servidor front-end ou endereço IP do pool de front-end ou de qualquer aparelho de filial persistente ou servidor de filial persistente usando este servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1f034-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1f034-279">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-279">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-280">Interface VIP interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-281">Caminho preferencial para transferência de mídia A/V entre usuários internos e externos (UDP)</span><span class="sxs-lookup"><span data-stu-id="1f034-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f034-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1f034-283">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-283">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-284">Interface VIP interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-285">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, se a comunicação UDP não pode ser estabelecida, TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="1f034-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f034-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1f034-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1f034-287">Interface VIP interna do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="1f034-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="1f034-288">Qualquer tamanho</span><span class="sxs-lookup"><span data-stu-id="1f034-288">Any</span></span></p></td>
<td><p><span data-ttu-id="1f034-289">Caminho de fallback para transferência de mídia A/V entre usuários internos e externos, se a comunicação UDP não pode ser estabelecida, TCP é usado para transferência de arquivos e compartilhamento de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="1f034-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

