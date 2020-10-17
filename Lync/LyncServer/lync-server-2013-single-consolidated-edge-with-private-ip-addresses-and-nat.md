---
title: 'Lync Server 2013: borda consolidada única com endereços IP privados e NAT'
description: 'Lync Server 2013: borda consolidada única com endereços IP privados e NAT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e716cd7cd07fdb4e4557cab83db7d8f3aecada2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555667"
---
# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a><span data-ttu-id="a26c0-103">Única borda consolidada com endereços IP privados e NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26c0-103">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a26c0-104">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a26c0-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a26c0-105">Se sua organização precisar de suporte para menos de 15.000 conexões de cliente de serviço de borda de acesso, 1.000 conexões de cliente do serviço de Webconferência do Lync Server, 500 e as sessões de borda de A/V simultâneas e a alta disponibilidade do servidor de borda não for importante, essa topologia oferecerá as vantagens de menor custo de hardware e implantação mais simples.</span><span class="sxs-lookup"><span data-stu-id="a26c0-105">If your organization requires support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="a26c0-106">Se você precisar de mais capacidade ou se precisar de alta disponibilidade, será necessário implantar uma topologia de servidor de borda consolidada em escala.</span><span class="sxs-lookup"><span data-stu-id="a26c0-106">If you need greater capacity or you require high availability, you need to deploy a scaled consolidated Edge Server topology.</span></span> <span data-ttu-id="a26c0-107">Para obter informações detalhadas, consulte um dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="a26c0-107">For details, see one of the following:</span></span>

  - <span></span>  
    [<span data-ttu-id="a26c0-108">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26c0-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="a26c0-109">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26c0-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="a26c0-110">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26c0-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<span data-ttu-id="a26c0-111">A figura não mostra diretores, uma função de servidor opcional implantada na rede interna entre os servidores de borda e seus pools de front-ends ou servidor.</span><span class="sxs-lookup"><span data-stu-id="a26c0-111">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="a26c0-112">Para obter detalhes sobre a topologia para diretores, consulte [os componentes necessários para o diretor no Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="a26c0-112">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="a26c0-113">A figura representa um único proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="a26c0-113">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a26c0-114">A figura mostrada é para orientações e endereço IP de exemplo, mas não pretende representar fluxos de comunicações reais com o tráfego de entrada e saída correto.</span><span class="sxs-lookup"><span data-stu-id="a26c0-114">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="a26c0-115">A figura representa uma exibição de alto nível do possível tráfego.</span><span class="sxs-lookup"><span data-stu-id="a26c0-115">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="a26c0-116">Detalhes para o fluxo de tráfego como eles pertencem para entrada (para portas de ouvinte) e saída (para servidores de destino ou clientes) é representado no diagrama Resumo da Porta em cada cenário.</span><span class="sxs-lookup"><span data-stu-id="a26c0-116">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="a26c0-117">Por exemplo, TCP 443 é a entrada (para a Borda ou proxy reverso) apenas e é apenas um fluxo de duas vias de uma perspectiva do protocolo (TCP).</span><span class="sxs-lookup"><span data-stu-id="a26c0-117">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="a26c0-118">Além disso, a figura mostra a natureza do tráfego conforme muda quando o NAT (conversão de endereço de rede) ocorre (endereço de destino é alterado na entrada, o endereço de origem é alterado na saída).</span><span class="sxs-lookup"><span data-stu-id="a26c0-118">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="a26c0-119">Exemplos de firewall externo e interno e interfaces do servidor são mostrados apenas para fins de referência.</span><span class="sxs-lookup"><span data-stu-id="a26c0-119">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="a26c0-120">Por fim, o exemplo de gateway padrão e relações de roteamento são mostrados, onde aplicável.</span><span class="sxs-lookup"><span data-stu-id="a26c0-120">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="a26c0-121">Observe também que o diagrama usa a zona DNS <EM>. com</EM> para representar a zona DNS externa para servidores de borda e proxy reverso e a zona DNS do <EM>.net</EM> refere-se à zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="a26c0-121">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="a26c0-122">Novo no Microsoft Lync Server 2013 é o suporte para o endereçamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="a26c0-122">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="a26c0-123">Parecido como o endereço IPv4, os endereços IPv6 devem ser atribuídos de tal forma que o endereço faz parte do seu espaço de endereço IPv6 atribuído.</span><span class="sxs-lookup"><span data-stu-id="a26c0-123">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="a26c0-124">Os endereços neste tópico são apenas para exemplo.</span><span class="sxs-lookup"><span data-stu-id="a26c0-124">The addresses in this topic are for example only.</span></span> <span data-ttu-id="a26c0-125">Você deve adquirir endereços IPv6 que funcionarão em sua implantação, oferecer o escopo correto e irá interoperar com o endereço interno e externo.</span><span class="sxs-lookup"><span data-stu-id="a26c0-125">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="a26c0-126">O Windows Server fornece um recurso importante para a operação de IPv6 de transição e a comunicação IPv4 para IPv6 chamada de *pilha Dual*.</span><span class="sxs-lookup"><span data-stu-id="a26c0-126">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="a26c0-127">A pilha dupla é uma pilha de rede distinta e separada para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="a26c0-127">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="a26c0-128">A pilha dupla é que permite atribuir endereços para IPv4 e IPv6 simultaneamente e permite o servidor comunicar com outros hosts e clientes com base em seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="a26c0-128">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="a26c0-129">Os tipos de endereços típicos que você usará para o endereçamento IPv6 serão os endereços globais IPv6 (semelhante aos endereços IPv4 públicos), endereços locais exclusivos IPv6 (semelhante aos intervalos de endereços IPv4 privados) e endereços de link local IPv6 (semelhante aos endereços IP privados automáticos no Windows Server para IPv4)</span><span class="sxs-lookup"><span data-stu-id="a26c0-129">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="a26c0-130">Tecnologias de conversação do endereço de rede (NAT) para IPv6 existem que permitirá o NAT IPv6 para IPv4 (geralmente chamado como NAT64) e de NAT IPv6 para IPv6 (geralmente chamado como NAT66).</span><span class="sxs-lookup"><span data-stu-id="a26c0-130">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="a26c0-131">A existência de tecnologias NAT significa que os cinco cenários apresentados para servidores de borda do Lync Server ainda são válidos.</span><span class="sxs-lookup"><span data-stu-id="a26c0-131">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a26c0-132">O IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para garantir que os endereços que você atribui no nível do Windows Server e no nível do Lync Server 2013 funcionem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="a26c0-132">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="a26c0-133">Consulte os links no final deste tópico para obter recursos adicionais sobre o endereço IPv6 e planejamento.</span><span class="sxs-lookup"><span data-stu-id="a26c0-133">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="a26c0-134">**Topologia de borda consolidada única**</span><span class="sxs-lookup"><span data-stu-id="a26c0-134">**Single consolidated edge topology**</span></span>

<span data-ttu-id="a26c0-135">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span><span class="sxs-lookup"><span data-stu-id="a26c0-135">![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a26c0-136">Se você estiver usando o CAC (controle de admissão de chamadas), ainda deverá atribuir endereços IPv4 à interface interna do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="a26c0-136">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="a26c0-137">O CAC usa endereços IPv4 e deve ter disponível para operar.</span><span class="sxs-lookup"><span data-stu-id="a26c0-137">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a26c0-138">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a26c0-138">In This Section</span></span>

  - [<span data-ttu-id="a26c0-139">Resumo de certificado-borda consolidada única com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26c0-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="a26c0-140">Resumo de porta-borda consolidada única com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26c0-140">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="a26c0-141">Resumo de DNS-borda consolidada única com endereços IP privados usando NAT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26c0-141">DNS summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a26c0-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="a26c0-142">See Also</span></span>


[<span data-ttu-id="a26c0-143">Arquitetura de endereçamento de IP versão 6</span><span class="sxs-lookup"><span data-stu-id="a26c0-143">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="a26c0-144">Formato de endereço de unicast global IPv6</span><span class="sxs-lookup"><span data-stu-id="a26c0-144">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="a26c0-145">Endereços exclusivos de unicast IPv6 locais</span><span class="sxs-lookup"><span data-stu-id="a26c0-145">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

