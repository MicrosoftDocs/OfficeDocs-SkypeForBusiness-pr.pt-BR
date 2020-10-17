---
title: Suporte de tronco SIP do Lync Server 2013
description: Suporte de tronco SIP do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 427e573d88584ac8beb3bbcd54e68b13c4c42f0f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559057"
---
# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="39e16-103">Suporte de tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39e16-103">SIP trunking support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39e16-104">_**Última modificação do tópico:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="39e16-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="39e16-105">Se você planeja usar o Enterprise Voice com tronco SIP, você deve implantar um servidor de mediação e certificar-se de que outros componentes e infraestrutura atendem aos requisitos de suporte apropriados ao seu modelo de implantação.</span><span class="sxs-lookup"><span data-stu-id="39e16-105">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="39e16-106">Para obter detalhes sobre como determinar se deve implementar o tronco SIP, consulte [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="39e16-106">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="39e16-107">Você pode usar o programa de interoperabilidade aberta do Microsoft Unified Communications para infraestrutura de telefonia corporativa para localizar gateways PSTN (rede telefônica pública comutada), IP-PBXs e serviços de tronco SIP, incluindo provedores de serviços de telefonia IP qualificados.</span><span class="sxs-lookup"><span data-stu-id="39e16-107">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="39e16-108">Para obter detalhes, consulte o site do programa de interoperabilidade aberta do Microsoft Unified Communications em [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .</span><span class="sxs-lookup"><span data-stu-id="39e16-108">For details, see the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="39e16-109">Suporte ao servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="39e16-109">Mediation Server Support</span></span>

<span data-ttu-id="39e16-110">Para implementar o tronco SIP, você deve encaminhar a conexão por meio de um servidor de mediação, que atua como um proxy para sessões de comunicação entre os clientes do Lync Server 2013 e o provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="39e16-110">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="39e16-111">O servidor de mediação decodifica o tráfego de mídia de clientes e servidores e o codifica novamente antes de enviá-lo ao provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="39e16-111">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="39e16-112">A recodificação é necessária porque os troncos SIP não dão suporte a alguns codecs usados, como o RTA (áudio em tempo real) ou a negociação de protocolo ICE (estabelecimento de conectividade interativa) para passagem de firewall.</span><span class="sxs-lookup"><span data-stu-id="39e16-112">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="39e16-113">Cada servidor de mediação pode ter dois adaptadores de rede, que fornecem uma interface de rede interna e externa.</span><span class="sxs-lookup"><span data-stu-id="39e16-113">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="39e16-114">A interface externa é normalmente chamada de interface de gateway porque, tradicionalmente, ela foi usada para se conectar a um gateway PSTN ou a um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="39e16-114">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="39e16-115">Para implementar um tronco SIP, conecte a interface externa a um controlador de borda de sessão (SBC) em um provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="39e16-115">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="39e16-116">Tronco SIP centralizado versus distribuído</span><span class="sxs-lookup"><span data-stu-id="39e16-116">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="39e16-117">*Centralizado* O tronco SIP roteia todo o tráfego do protocolo VoIP, incluindo o tráfego do site da filial, por meio do Data Center.</span><span class="sxs-lookup"><span data-stu-id="39e16-117">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="39e16-118">O modelo de implantação centralizado é simples, econômico e geralmente é a abordagem preferida para a implementação de troncos SIP com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="39e16-118">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="39e16-119">Dependendo dos padrões de uso em sua empresa, talvez você não queira rotear todos os usuários por meio do tronco SIP centralizado.</span><span class="sxs-lookup"><span data-stu-id="39e16-119">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="39e16-120">Para analisar suas necessidades, responda às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="39e16-120">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="39e16-121">Qual é o tamanho de cada site?</span><span class="sxs-lookup"><span data-stu-id="39e16-121">How big is each site?</span></span> <span data-ttu-id="39e16-122">Quantos usuários?</span><span class="sxs-lookup"><span data-stu-id="39e16-122">How many users?</span></span>

  - <span data-ttu-id="39e16-123">Quais números DID (discagem direta interna) em cada site recebem mais chamadas telefônicas?</span><span class="sxs-lookup"><span data-stu-id="39e16-123">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="39e16-124">*Distribuído* O tronco SIP é um modelo de implantação no qual você implementa um tronco SIP local em um ou mais sites de filial.</span><span class="sxs-lookup"><span data-stu-id="39e16-124">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="39e16-125">O tráfego VoIP é então roteado do site de filial diretamente para o provedor de serviços, sem passar pelo Data Center.</span><span class="sxs-lookup"><span data-stu-id="39e16-125">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="39e16-126">O tronco SIP distribuído é exigido somente nos seguintes casos:</span><span class="sxs-lookup"><span data-stu-id="39e16-126">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="39e16-127">O site de filial requer conectividade de telefone persistente (por exemplo, se a WAN for desativada).</span><span class="sxs-lookup"><span data-stu-id="39e16-127">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="39e16-128">Se a ramificação precisar de redundância e failover, o provedor de serviços cobrará mais e a configuração levará mais tempo.</span><span class="sxs-lookup"><span data-stu-id="39e16-128">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="39e16-129">Isso deve ser analisado para cada site de filial.</span><span class="sxs-lookup"><span data-stu-id="39e16-129">This should be analyzed for each branch site.</span></span> <span data-ttu-id="39e16-130">Algumas das suas filiais podem exigir redundância e failover, enquanto outras não.</span><span class="sxs-lookup"><span data-stu-id="39e16-130">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="39e16-131">O site de filial e o Data Center estão em países/regiões diferentes.</span><span class="sxs-lookup"><span data-stu-id="39e16-131">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="39e16-132">Por motivos legais e de compatibilidade, você precisa de pelo menos um tronco SIP por país/região.</span><span class="sxs-lookup"><span data-stu-id="39e16-132">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="39e16-133">Decidir se deve implantar o tronco SIP centralizado ou distribuído requer uma análise de custo-benefício.</span><span class="sxs-lookup"><span data-stu-id="39e16-133">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="39e16-134">Em alguns casos, talvez seja vantajoso optar pelo modo de implantação distribuída, mesmo se não for necessário.</span><span class="sxs-lookup"><span data-stu-id="39e16-134">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="39e16-135">Em uma implantação completamente centralizada, todo o tráfego do site da filial é roteado através de links WAN.</span><span class="sxs-lookup"><span data-stu-id="39e16-135">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="39e16-136">Em vez de pagar pela largura de banda exigida pelo link de WAN, convém usar o tronco SIP distribuído.</span><span class="sxs-lookup"><span data-stu-id="39e16-136">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="39e16-137">Para obter detalhes sobre por que e como você pode usar o tronco SIP distribuído, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="39e16-137">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="39e16-138">Tipos de conexão de tronco SIP suportadas</span><span class="sxs-lookup"><span data-stu-id="39e16-138">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="39e16-139">O Lync Server 2013 oferece suporte aos seguintes tipos de conexão para tronco SIP:</span><span class="sxs-lookup"><span data-stu-id="39e16-139">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="39e16-140">MPLS (Multiprotocol Label Switching) é uma rede privada que direciona e transporta dados de um nó de rede para o próximo.</span><span class="sxs-lookup"><span data-stu-id="39e16-140">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="39e16-141">A largura de banda em uma rede MPLS é compartilhada com outros assinantes e cada pacote de dados recebe um rótulo para diferenciar os dados de um assinante dos dados de outro assinante.</span><span class="sxs-lookup"><span data-stu-id="39e16-141">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="39e16-142">Esse tipo de conexão não requer VPN.</span><span class="sxs-lookup"><span data-stu-id="39e16-142">This connection type does not require VPN.</span></span> <span data-ttu-id="39e16-143">Uma possível desvantagem é que o tráfego IP excessivo pode interferir com a operação VoIP, a menos que o tráfego VoIP tenha prioridade.</span><span class="sxs-lookup"><span data-stu-id="39e16-143">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="39e16-144">Uma conexão privada sem outro tráfego é normalmente o tipo de conexão mais confiável e segura (por exemplo, uma conexão de fibra óptica dedicada ou uma linha T1).</span><span class="sxs-lookup"><span data-stu-id="39e16-144">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="39e16-145">Esse tipo de conexão fornece a maior capacidade de transporte de chamadas, mas geralmente é o mais caro.</span><span class="sxs-lookup"><span data-stu-id="39e16-145">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="39e16-146">VPN não é necessário.</span><span class="sxs-lookup"><span data-stu-id="39e16-146">VPN is not required.</span></span> <span data-ttu-id="39e16-147">Conexões privadas são adequadas para organizações com alto volume de chamadas ou com requisitos de segurança e disponibilidade rígidos.</span><span class="sxs-lookup"><span data-stu-id="39e16-147">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="39e16-148">A Internet pública é o tipo de conexão menos caro, mas também a menos confiável, e aquela com a menor capacidade de transporte de chamadas.</span><span class="sxs-lookup"><span data-stu-id="39e16-148">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="39e16-149">Seu provedor de serviços de telefonia da Internet (ITSP) pode ajudar a proteger esse tipo de conexão de tronco SIP se ele oferecer suporte à segurança da camada de transporte (TLS) Real-Time e ao protocolo SRTP para criptografar a sinalização e o tráfego de mídia.</span><span class="sxs-lookup"><span data-stu-id="39e16-149">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="39e16-150">Se você não puder configurar uma conexão de tronco SIP através da Internet para usar TLS e SRTP, recomendamos enfaticamente que você use um túnel VPN para fornecer uma conexão mais segura.</span><span class="sxs-lookup"><span data-stu-id="39e16-150">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="39e16-151">Entre em contato com seu ITSP para determinar se ele fornece suporte para TLS com SRTP.</span><span class="sxs-lookup"><span data-stu-id="39e16-151">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="39e16-152">Selecionando um tipo de conexão</span><span class="sxs-lookup"><span data-stu-id="39e16-152">Selecting a Connection Type</span></span>

<span data-ttu-id="39e16-153">O tipo de conexão de tronco SIP mais apropriado para sua empresa depende de suas necessidades e de seu orçamento.</span><span class="sxs-lookup"><span data-stu-id="39e16-153">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="39e16-154">Para uma empresa de médio ou grande porte, uma rede MPLS geralmente fornece o maior valor.</span><span class="sxs-lookup"><span data-stu-id="39e16-154">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="39e16-155">Ela pode fornecer a largura de banda necessária por uma taxa mais barata do que uma rede privada especializada.</span><span class="sxs-lookup"><span data-stu-id="39e16-155">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="39e16-156">Grandes empresas podem exigir uma conexão privada óptica de fibra ou T1.</span><span class="sxs-lookup"><span data-stu-id="39e16-156">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="39e16-157">Para uma pequena empresa ou um site de filial com baixo volume de chamadas, o tronco SIP através da Internet pode ser a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="39e16-157">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="39e16-158">No entanto, esse tipo de conexão não é recomendado para sites de tamanho médio ou maior.</span><span class="sxs-lookup"><span data-stu-id="39e16-158">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="39e16-159">Suporte ao codec</span><span class="sxs-lookup"><span data-stu-id="39e16-159">Codec Support</span></span>

<span data-ttu-id="39e16-160">O proxy do provedor de serviços deve suportar os seguintes codecs:</span><span class="sxs-lookup"><span data-stu-id="39e16-160">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="39e16-161">G.711 a-law (usado principalmente fora da América do Norte)</span><span class="sxs-lookup"><span data-stu-id="39e16-161">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="39e16-162">G.711 µ-law (usado na América do Norte)</span><span class="sxs-lookup"><span data-stu-id="39e16-162">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

