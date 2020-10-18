---
title: 'Lync Server 2013: borda consolidada dimensionada, balanceamento de carga de DNS com endereços IP privados usando NAT'
description: 'Lync Server 2013: borda consolidada dimensionada, balanceamento de carga de DNS com endereços IP privados usando NAT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a1b668902059ef2680525b884d8b2c5e8486260
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577697"
---
# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="e2e5a-103">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e5a-103">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2e5a-104">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e2e5a-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e2e5a-p101">Na topologia do pool do Servidor de Borda, dois ou mais Servidores de Borda são implantados como um pool com carga balanceada na rede de perímetro do centro de dados. O balanceamento de carga DNS é usado para tráfego de interfaces de Borda externa e interna.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-p101">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center. Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="e2e5a-107">Se sua organização precisar de suporte para mais de 15.000 conexões de cliente do serviço de borda de acesso, 1.000 conexões de cliente do serviço de Webconferência do Lync Server, 500 ou as sessões de borda A/V simultâneas, e/ou alta disponibilidade do servidor de borda for importante, essa topologia oferecerá as vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-107">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="e2e5a-108">A figura não mostra diretores, uma função de servidor opcional implantada na rede interna entre os servidores de borda e seus pools de front-ends ou servidor.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-108">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="e2e5a-109">Para obter detalhes sobre a topologia para diretores, consulte [os componentes necessários para o diretor no Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="e2e5a-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="e2e5a-110">A figura representa um único proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-110">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2e5a-111">A figura mostrada é para orientações e endereço IP de exemplo, mas não pretende representar fluxos de comunicações reais com o tráfego de entrada e saída correto.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-111">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="e2e5a-112">A figura representa uma exibição de alto nível do possível tráfego.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-112">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="e2e5a-113">Detalhes para o fluxo de tráfego como eles pertencem para entrada (para portas de ouvinte) e saída (para servidores de destino ou clientes) é representado no diagrama Resumo da Porta em cada cenário.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-113">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="e2e5a-114">Por exemplo, TCP 443 é a entrada (para a Borda ou proxy reverso) apenas e é apenas um fluxo de duas vias de uma perspectiva do protocolo (TCP).</span><span class="sxs-lookup"><span data-stu-id="e2e5a-114">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="e2e5a-115">Além disso, a figura mostra a natureza do tráfego conforme muda quando o NAT (conversão de endereço de rede) ocorre (endereço de destino é alterado na entrada, o endereço de origem é alterado na saída).</span><span class="sxs-lookup"><span data-stu-id="e2e5a-115">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="e2e5a-116">Exemplos de firewall externo e interno e interfaces do servidor são mostrados apenas para fins de referência.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-116">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="e2e5a-117">Por fim, o exemplo de gateway padrão e relações de roteamento são mostrados, onde aplicável.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-117">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="e2e5a-118">Observe também que o diagrama usa a zona DNS <EM>. com</EM> para representar a zona DNS externa para servidores de borda e proxy reverso e a zona DNS do <EM>.net</EM> refere-se à zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-118">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="e2e5a-119">Novo no Microsoft Lync Server 2013 é o suporte para o endereçamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-119">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="e2e5a-120">Parecido como o endereço IPv4, os endereços IPv6 devem ser atribuídos de tal forma que o endereço faz parte do seu espaço de endereço IPv6 atribuído.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-120">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="e2e5a-121">Os endereços neste tópico são apenas para exemplo.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-121">The addresses in this topic are for example only.</span></span> <span data-ttu-id="e2e5a-122">Você deve adquirir endereços IPv6 que funcionarão em sua implantação, oferecer o escopo correto e irá interoperar com o endereço interno e externo.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-122">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="e2e5a-123">O Windows Server fornece um recurso importante para a operação de IPv6 de transição e a comunicação IPv4 para IPv6 chamada de *pilha Dual*.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-123">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="e2e5a-124">A pilha dupla é uma pilha de rede distinta e separada para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-124">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="e2e5a-125">A pilha dupla é que permite atribuir endereços para IPv4 e IPv6 simultaneamente e permite o servidor comunicar com outros hosts e clientes com base em seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-125">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="e2e5a-126">Os tipos de endereços típicos que você usará para o endereçamento IPv6 serão os endereços globais IPv6 (semelhante aos endereços IPv4 públicos), endereços locais exclusivos IPv6 (semelhante aos intervalos de endereços IPv4 privados) e endereços de link local IPv6 (semelhante aos endereços IP privados automáticos no Windows Server para IPv4)</span><span class="sxs-lookup"><span data-stu-id="e2e5a-126">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="e2e5a-127">Tecnologias de conversação do endereço de rede (NAT) para IPv6 existem que permitirá o NAT IPv6 para IPv4 (geralmente chamado como NAT64) e de NAT IPv6 para IPv6 (geralmente chamado como NAT66).</span><span class="sxs-lookup"><span data-stu-id="e2e5a-127">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="e2e5a-128">A existência de tecnologias NAT significa que os cinco cenários apresentados para servidores de borda do Lync Server ainda são válidos.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-128">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e2e5a-129">O IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para garantir que os endereços que você atribui no nível do Windows Server e no nível do Lync Server 2013 funcionem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-129">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="e2e5a-130">Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-130">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="e2e5a-131">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span><span class="sxs-lookup"><span data-stu-id="e2e5a-131">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e2e5a-132">Se você estiver usando o CAC (controle de admissão de chamadas), ainda deverá atribuir endereços IPv4 à interface interna do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-132">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="e2e5a-133">O CAC usa endereços IPv4 e deve ter disponível para operar.</span><span class="sxs-lookup"><span data-stu-id="e2e5a-133">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e2e5a-134">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e2e5a-134">In This Section</span></span>

  - [<span data-ttu-id="e2e5a-135">Resumo de certificado-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e5a-135">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)

  - [<span data-ttu-id="e2e5a-136">Resumo de porta-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e5a-136">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="e2e5a-137">Resumo de DNS-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e5a-137">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2e5a-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="e2e5a-138">See Also</span></span>


[<span data-ttu-id="e2e5a-139">Arquitetura de endereçamento de IP versão 6</span><span class="sxs-lookup"><span data-stu-id="e2e5a-139">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="e2e5a-140">Formato de endereço de unicast global IPv6</span><span class="sxs-lookup"><span data-stu-id="e2e5a-140">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="e2e5a-141">Endereços exclusivos de unicast IPv6 locais</span><span class="sxs-lookup"><span data-stu-id="e2e5a-141">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

