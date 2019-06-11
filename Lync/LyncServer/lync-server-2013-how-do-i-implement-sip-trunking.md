---
title: 'Lync Server 2013: Como implementar tronco SIP?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c14375f9e0b7f3a7615c11ddaca2bc6c46ec72f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="f907f-102">Como implementar tronco SIP no Lync Server 2013?</span><span class="sxs-lookup"><span data-stu-id="f907f-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f907f-103">_**Tópico da última modificação:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="f907f-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="f907f-104">Para implementar o entroncamento SIP, você deve direcionar a conexão por meio de um servidor de mediação, que atua como um proxy para sessões de comunicação entre clientes do Lync Server 2013 e o provedor de serviço e transformações de mídia, quando necessário.</span><span class="sxs-lookup"><span data-stu-id="f907f-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="f907f-105">Cada servidor de mediação tem uma interface de rede interna e uma interface de rede externa.</span><span class="sxs-lookup"><span data-stu-id="f907f-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="f907f-106">A interface interna se conecta aos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f907f-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="f907f-107">A interface externa geralmente é chamada de interface do gateway porque tem sido usada tradicionalmente para conectar o servidor de mediação a um gateway PSTN (rede telefônica pública comutada) ou a um IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f907f-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="f907f-108">Para implementar um tronco SIP, conecte a interface externa do servidor de mediação ao componente Edge externo da ITSP.</span><span class="sxs-lookup"><span data-stu-id="f907f-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f907f-109">O componente de borda externa do ITSP pode ser um SBC (Controlador de Borda da Sessão), um roteador ou um gateway.</span><span class="sxs-lookup"><span data-stu-id="f907f-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="f907f-110">Para obter detalhes sobre os servidores de mediação, consulte [componente servidor de mediação no Lync server 2013](lync-server-2013-mediation-server-component.md).</span><span class="sxs-lookup"><span data-stu-id="f907f-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="f907f-111">Tronco SIP centralizado versus distribuído</span><span class="sxs-lookup"><span data-stu-id="f907f-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="f907f-112">*Centralizado* O entroncamento SIP roteia todo o tráfego do protocolo VoIP, incluindo o tráfego do site da filial, por meio de seu site central.</span><span class="sxs-lookup"><span data-stu-id="f907f-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="f907f-113">O modelo de implantação centralizado é simples, econômico e geralmente é a abordagem recomendada para a implementação de troncos SIP com o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f907f-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="f907f-114">*Distribuído* O entroncamento SIP é um modelo de implantação no qual você implementa um tronco SIP local em um ou mais sites de filiais.</span><span class="sxs-lookup"><span data-stu-id="f907f-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="f907f-115">O tráfego de VoIP é então encaminhado do site de filial diretamente para um provedor de serviços sem passar pelo site central.</span><span class="sxs-lookup"><span data-stu-id="f907f-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="f907f-116">O tronco SIP distribuído é necessário somente nos seguintes casos:</span><span class="sxs-lookup"><span data-stu-id="f907f-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="f907f-117">O site da filial requer conectividade de telefone para o telefone cofuncional (por exemplo, se a WAN ficar inoperante).</span><span class="sxs-lookup"><span data-stu-id="f907f-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="f907f-118">Esse requisito deve ser analisado para cada site de filiais; algumas das suas filiais podem exigir redundância e failover, enquanto outras não podem.</span><span class="sxs-lookup"><span data-stu-id="f907f-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="f907f-119">A resiliência é necessária entre dois sites centrais.</span><span class="sxs-lookup"><span data-stu-id="f907f-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="f907f-120">Você precisa ter certeza de que um tronco SIP termina em cada site central.</span><span class="sxs-lookup"><span data-stu-id="f907f-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="f907f-121">Por exemplo, se você tiver sites centrais de Dublin e Tukwila e ambos usarem apenas um tronco SIP do site, se o tronco ficar inativo, os usuários do outro site não poderão fazer chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="f907f-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="f907f-122">O site de ramificação e o site central estão em países/regiões diferentes.</span><span class="sxs-lookup"><span data-stu-id="f907f-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="f907f-123">Por motivos legais e de compatibilidade, você precisa de pelo menos um tronco SIP por país/região.</span><span class="sxs-lookup"><span data-stu-id="f907f-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="f907f-124">Por exemplo, na União Europeia, as comunicações não podem deixar um país/região sem terminarem localmente em um ponto centralizado.</span><span class="sxs-lookup"><span data-stu-id="f907f-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="f907f-125">Dependendo da localização geográfica dos sites e da quantidade de tráfego que você prevê na sua empresa, talvez você não queira direcionar todos os usuários por meio do tronco SIP central ou pode optar por direcionar alguns usuários por meio de um tronco SIP em seu site de filiais.</span><span class="sxs-lookup"><span data-stu-id="f907f-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="f907f-126">Para analisar suas necessidades, responda às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="f907f-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="f907f-127">Qual é o tamanho de cada site (ou seja, quantos usuários estão habilitados para o Enterprise Voice)?</span><span class="sxs-lookup"><span data-stu-id="f907f-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="f907f-128">Quais números DID (discagem direta interna) em cada local recebem a maioria das chamadas?</span><span class="sxs-lookup"><span data-stu-id="f907f-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="f907f-129">A decisão de implantar um tronco SIP centralizado ou distribuído exige uma análise de custo-benefício.</span><span class="sxs-lookup"><span data-stu-id="f907f-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="f907f-130">Em alguns casos, pode ser vantajoso optar pelo modelo de implantação distribuído mesmo se ele não for necessário.</span><span class="sxs-lookup"><span data-stu-id="f907f-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="f907f-131">Em uma implantação completamente centralizada, todo o tráfego do site da filial é roteado através de links WAN.</span><span class="sxs-lookup"><span data-stu-id="f907f-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="f907f-132">Em vez de pagar pela largura de banda necessária ao link de WAN, convém usar o tronco SIP distribuído.</span><span class="sxs-lookup"><span data-stu-id="f907f-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="f907f-133">Por exemplo, você pode querer implantar um servidor Standard Edition em um site de filial com Federação para o site central ou pode querer implantar um aparelho de ramificação sobreviventes ou um servidor de ramificação sobreviventes com um pequeno gateway.</span><span class="sxs-lookup"><span data-stu-id="f907f-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f907f-134">Para obter detalhes sobre o entroncamento SIP distribuído, consulte <A href="lync-server-2013-branch-site-sip-trunking.md">entroncamento do site de ramificação SIP no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f907f-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="f907f-135">Tipos de conexão de tronco SIP suportadas</span><span class="sxs-lookup"><span data-stu-id="f907f-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="f907f-136">O Lync Server oferece suporte aos seguintes tipos de conexão para entroncamento SIP:</span><span class="sxs-lookup"><span data-stu-id="f907f-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="f907f-p109">O MPLS é uma rede privada que direciona e transporta dados de um nó de rede para o próximo. A largura de banda em uma rede MPLS é compartilhada com outros assinantes e cada pacote de dados recebe um rótulo para diferenciar os dados de um assinante dos dados de outro assinante. Esse tipo de conexão não exige VPN (rede virtual privada). Uma possível desvantagem é que o tráfego IP excessivo pode interferir na operação de VoIP, a menos que o tráfego VoIP tenha prioridade.</span><span class="sxs-lookup"><span data-stu-id="f907f-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="f907f-p110">Uma conexão privada sem outro tráfego, por exemplo, uma conexão de fibra ótica concedida ou uma linha T1, é normalmente o tipo de conexão mais confiável e seguro. Esse tipo de conexão oferece a maior capacidade de realização de chamadas, mas é geralmente o mais caro. Não é necessário VPN. As conexões privadas são adequadas para organizações com alto volume de chamadas ou com requisitos de segurança e disponibilidade rígidos.</span><span class="sxs-lookup"><span data-stu-id="f907f-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="f907f-145">A Internet é o tipo de conexão menos caro, mas também o menos confiável.</span><span class="sxs-lookup"><span data-stu-id="f907f-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="f907f-146">Conexão à Internet é o único tipo de conexão de entroncamento do Lync Server SIP que requer VPN.</span><span class="sxs-lookup"><span data-stu-id="f907f-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="f907f-147">Selecionando um tipo de conexão</span><span class="sxs-lookup"><span data-stu-id="f907f-147">Selecting a Connection Type</span></span>

<span data-ttu-id="f907f-148">O tipo de conexão de tronco SIP mais apropriado para sua empresa depende de suas necessidades e de seu orçamento.</span><span class="sxs-lookup"><span data-stu-id="f907f-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="f907f-p112">Para uma empresa de médio ou grande porte, uma rede MPLS normalmente fornece o maior valor. Ela pode fornecer a largura de banda necessária por uma taxa mais barata do que uma rede privada especializada.</span><span class="sxs-lookup"><span data-stu-id="f907f-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="f907f-151">Empresas de grande porte podem exigir uma conexão de fibra ótica, T1, T3 ou superior privada (E1, E3 ou superior na União Europeia).</span><span class="sxs-lookup"><span data-stu-id="f907f-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="f907f-152">Para uma pequena empresa ou site de filial com baixo volume de chamadas, o entroncamento SIP pela Internet pode ser a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="f907f-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="f907f-153">Esse tipo de conexão não é recomendado para locais de médio ou grande porte.</span><span class="sxs-lookup"><span data-stu-id="f907f-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="f907f-154">Requisitos de largura de banda</span><span class="sxs-lookup"><span data-stu-id="f907f-154">Bandwidth Requirements</span></span>

<span data-ttu-id="f907f-p114">A quantidade de largura de banda exigida pela sua implementação depende da capacidade da chamada (o número de chamadas simultâneas que você precisa suportar). A disponibilidade de largura de banda precisa ser levada em consideração para que você possa aproveitar ao máximo a capacidade de pico pela qual pagou. Use a fórmula a seguir para calcular o requisito de largura de banda de pico do tronco SIP:</span><span class="sxs-lookup"><span data-stu-id="f907f-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="f907f-158">Largura de banda de pico do tronco SIP = máximo de chamadas simultâneas x (64 kbps + tamanho do cabeçalho)</span><span class="sxs-lookup"><span data-stu-id="f907f-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f907f-159">O tamanho do cabeçalho é de 20 bytes no máximo.</span><span class="sxs-lookup"><span data-stu-id="f907f-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="f907f-160">Suporte ao codec</span><span class="sxs-lookup"><span data-stu-id="f907f-160">Codec Support</span></span>

<span data-ttu-id="f907f-161">O Lync Server 2013 só oferece suporte aos seguintes codecs:</span><span class="sxs-lookup"><span data-stu-id="f907f-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="f907f-162">G.711 a-law (usado principalmente fora da América do Norte)</span><span class="sxs-lookup"><span data-stu-id="f907f-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="f907f-163">G.711 µ-law (usado na América do Norte)</span><span class="sxs-lookup"><span data-stu-id="f907f-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="f907f-164">Provedor de Serviço de Telefonia pela Internet</span><span class="sxs-lookup"><span data-stu-id="f907f-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="f907f-165">O modo de implementação do lado do provedor de serviços de uma conexão de tronco SIP varia de um ITSP para outro.</span><span class="sxs-lookup"><span data-stu-id="f907f-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="f907f-166">Para obter informações de implantação, contate seu provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="f907f-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="f907f-167">Para obter uma lista de provedores de serviços de entroncamento SIP certificados, consulte [website Microsoft Unified Communication Open Interoperability Program](http://go.microsoft.com/fwlink/?linkid=287029).</span><span class="sxs-lookup"><span data-stu-id="f907f-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](http://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="f907f-168">Para obter detalhes sobre os provedores de tronco SIP certificado pela Microsoft, entre em contato com seu representante da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f907f-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f907f-p116">Você deve usar um provedor de serviço certificado pela Microsoft para garantir que seu ITSP suporte todas as funcionalidades que atravessam o tronco SIP (por exemplo, configurar e gerenciar sessões e suportar todos os serviços de VoIP estendido). O suporte técnico da Microsoft não estender as configurações que usam provedores não certificados. Se você atualmente usa um provedor de serviço Internet não certificado para tronco SIP, é possível optar por continuar usando este provedor como seu ISP e usar um provedor certificado pela Microsoft para tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="f907f-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

