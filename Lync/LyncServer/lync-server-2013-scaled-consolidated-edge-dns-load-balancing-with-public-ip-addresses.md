---
title: Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: 2b854f6d-3d3f-4961-a5f8-a03f47740df0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204761(v=OCS.15)
ms:contentKeyID: 48183698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7145ae98a57523293d9d7d0d872c81a5e33e847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="8e253-102">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e253-102">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e253-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8e253-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8e253-104">Na topologia de pool do servidor de borda, dois ou mais servidores Edge são implantados como um pool de balanceamento de carga na rede de perímetro do Data Center.</span><span class="sxs-lookup"><span data-stu-id="8e253-104">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="8e253-105">O balanceamento de carga de DNS (sistema de nomes de domínio) é usado para tráfego para as interfaces de borda externa e externa.</span><span class="sxs-lookup"><span data-stu-id="8e253-105">Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="8e253-106">Se a sua organização requer suporte para mais de 15.000 conexões de cliente de serviço de borda de acesso, 1.000 conexões de cliente de serviço de Webconferência ativas do Lync Server, 500 ou as sessões de borda A/V simultâneas, e/ou alta disponibilidade do servidor de borda é importante , essa topologia oferece as vantagens de escalabilidade e suporte de failover.</span><span class="sxs-lookup"><span data-stu-id="8e253-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="8e253-107">A figura não mostra diretores, uma função de servidor opcional implantada na rede interna entre os servidores de borda e seus pools ou servidores de front-end.</span><span class="sxs-lookup"><span data-stu-id="8e253-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="8e253-108">Para obter detalhes sobre a topologia para diretores, consulte [os componentes necessários para o diretor no Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="8e253-108">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="8e253-109">A figura representa um único proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="8e253-109">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8e253-110">A imagem mostrada é para orientação e exemplo de endereçamento IP, mas não pretende representar os fluxos de comunicação reais com o tráfego de entrada e saída correto.</span><span class="sxs-lookup"><span data-stu-id="8e253-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="8e253-111">A figura representa uma exibição de alto nível do possível tráfego.</span><span class="sxs-lookup"><span data-stu-id="8e253-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="8e253-112">Os detalhes do fluxo de tráfego que pertencem à entrada (em portas de escuta) e saída (para clientes ou servidores de destino) são representados no diagrama de Resumo de porta em cada cenário.</span><span class="sxs-lookup"><span data-stu-id="8e253-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="8e253-113">Por exemplo, o TCP 443 é realmente de entrada (apenas para a borda ou proxy reverso) e só é um fluxo bidirecional de uma perspectiva de protocolo (TCP).</span><span class="sxs-lookup"><span data-stu-id="8e253-113">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="8e253-114">Além disso, a figura mostra a natureza do tráfego à medida que ele muda quando o NAT (conversão de endereço de rede) ocorre (o endereço de destino é alterado em entrada, o endereço de origem é alterado na saída).</span><span class="sxs-lookup"><span data-stu-id="8e253-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="8e253-115">Exemplo de firewall externo e interno e interfaces do servidor são mostradas somente para fins de referência.</span><span class="sxs-lookup"><span data-stu-id="8e253-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="8e253-116">Por fim, o gateway padrão e as relações de rota são exibidos, quando aplicável.</span><span class="sxs-lookup"><span data-stu-id="8e253-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="8e253-117">Observe também que o diagrama usa a zona DNS <EM>. com</EM> para representar a zona DNS externa para servidores de proxy reverso e Edge e a zona DNS do <EM>.net</EM> refere-se à zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="8e253-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="8e253-118">O novo para o Microsoft Lync Server 2013 é compatível com endereçamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="8e253-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="8e253-119">Como endereçamento IPv4, os endereços IPv6 devem ser atribuídos de forma que os endereços sejam parte do espaço de endereço IPv6 atribuído.</span><span class="sxs-lookup"><span data-stu-id="8e253-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="8e253-120">Os endereços neste tópico são somente por exemplo.</span><span class="sxs-lookup"><span data-stu-id="8e253-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="8e253-121">Você deve adquirir endereços IPv6 que funcionarão na sua implantação, fornecer o escopo correto e interoperar com o endereçamento interno e externo.</span><span class="sxs-lookup"><span data-stu-id="8e253-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="8e253-122">O Windows Server fornece um recurso que é importante para a operação IPv6 de transição e comunicação IPv4 para IPv6 chamada de *pilha dupla*.</span><span class="sxs-lookup"><span data-stu-id="8e253-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="8e253-123">A pilha dupla é uma pilha de rede separada e distinta para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="8e253-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="8e253-124">A pilha dupla é o que permite atribuir endereçamento para IPv4 e IPv6 simultaneamente e permite que o servidor se comunique com outros hosts e clientes de acordo com suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="8e253-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="8e253-125">Os tipos de endereços típicos que você usará para endereçamento IPv6 serão os endereços globais IPv6 (semelhantes aos endereços IPv4 públicos), os endereços locais exclusivos do IPv6 (semelhantes aos intervalos de endereços IPv4 particulares) e os endereços locais de link IPv6 (semelhante ao IP particular automático endereços no Windows Server para IPv4)</span><span class="sxs-lookup"><span data-stu-id="8e253-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="8e253-126">Há tecnologias de conversão de endereços de rede (NAT) para IPv6 que permitirão o NAT IPv6 para IPv4 (comumente chamado de NAT64) e para IPv6 NAT para IPv6 (geralmente chamado de NAT66).</span><span class="sxs-lookup"><span data-stu-id="8e253-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="8e253-127">A existência de tecnologias NAT significa que os cinco cenários apresentados para servidores do Lync Server Edge ainda são válidos.</span><span class="sxs-lookup"><span data-stu-id="8e253-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="8e253-128">O IPv6 é um tópico complexo e requer planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para garantir que os endereços que você atribuir no nível do Windows Server e no nível do Lync Server 2013 funcionarão conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="8e253-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="8e253-129">Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.</span><span class="sxs-lookup"><span data-stu-id="8e253-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="8e253-130">![7c1e3e6b-9b1b-4ac6-B0E7-9c256dbc2537] (images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "7c1e3e6b-9b1b-4ac6-B0E7-9c256dbc2537")</span><span class="sxs-lookup"><span data-stu-id="8e253-130">![7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537")</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8e253-131">Se você estiver usando o controle de admissão de chamadas (CAC), ainda deverá atribuir endereços IPv4 à interface interna do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8e253-131">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="8e253-132">O CAC usa endereços IPv4 e deve tê-los disponíveis para operação.</span><span class="sxs-lookup"><span data-stu-id="8e253-132">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8e253-133">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8e253-133">In This Section</span></span>

  - [<span data-ttu-id="8e253-134">Resumo de certificado - Borda consolidade em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e253-134">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="8e253-135">Resumo de porta - Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e253-135">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="8e253-136">Resumo de DNS - Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e253-136">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e253-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e253-137">See Also</span></span>


[<span data-ttu-id="8e253-138">Arquitetura de endereçamento de IP versão 6</span><span class="sxs-lookup"><span data-stu-id="8e253-138">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="8e253-139">Formato de endereço de difusão ponto a ponto global IPv6</span><span class="sxs-lookup"><span data-stu-id="8e253-139">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="8e253-140">Endereços exclusivos de unicast IPv6 locais</span><span class="sxs-lookup"><span data-stu-id="8e253-140">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

