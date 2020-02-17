---
title: 'Lync Server 2013: borda consolidada dimensionada com balanceadores de carga de hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8942b7d88bf4e52139a62b9a2ee0777b3532cf10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="021f7-102">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="021f7-102">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="021f7-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="021f7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="021f7-104">Na topologia do pool de borda, dois ou mais servidores de borda são implantados como um pool com balanceamento de carga na rede de perímetro do Data Center.</span><span class="sxs-lookup"><span data-stu-id="021f7-104">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="021f7-105">O balanceamento de carga de hardware é usado para o tráfego para as interfaces de servidor de borda interna e externa.</span><span class="sxs-lookup"><span data-stu-id="021f7-105">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="021f7-106">Se sua organização precisar de suporte para mais de 15.000 conexões de cliente do serviço de borda de acesso, 1.000 conexões de cliente do serviço de borda de webconferências ativas 500 ou as sessões de serviço de borda A/V simultâneas e alta disponibilidade do servidor de borda for importante, essa topologia oferecerá as vantagens de escalabilidade e suporte a failover.</span><span class="sxs-lookup"><span data-stu-id="021f7-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="021f7-107">A figura não mostra diretores, uma função de servidor opcional implantada na rede interna entre os servidores de borda e seus pools de front-ends ou servidor.</span><span class="sxs-lookup"><span data-stu-id="021f7-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="021f7-108">.</span><span class="sxs-lookup"><span data-stu-id="021f7-108">.</span></span> <span data-ttu-id="021f7-109">Para obter detalhes sobre a topologia para diretores, consulte [os componentes necessários para o diretor no Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="021f7-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="021f7-110">A figura mostrada é para orientações e endereço IP de exemplo, mas não pretende representar fluxos de comunicações reais com o tráfego de entrada e saída correto.</span><span class="sxs-lookup"><span data-stu-id="021f7-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="021f7-111">A figura representa uma exibição de alto nível do possível tráfego.</span><span class="sxs-lookup"><span data-stu-id="021f7-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="021f7-112">Detalhes para o fluxo de tráfego como eles pertencem para entrada (para portas de ouvinte) e saída (para servidores de destino ou clientes) é representado no diagrama Resumo da Porta em cada cenário.</span><span class="sxs-lookup"><span data-stu-id="021f7-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="021f7-113">Por exemplo, o TCP 443 é realmente de entrada (apenas para o servidor de borda ou de proxy reverso) e é apenas um fluxo bidirecional de uma perspectiva de protocolo (TCP).</span><span class="sxs-lookup"><span data-stu-id="021f7-113">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="021f7-114">Além disso, a figura mostra a natureza do tráfego conforme muda quando o NAT (conversão de endereço de rede) ocorre (endereço de destino é alterado na entrada, o endereço de origem é alterado na saída).</span><span class="sxs-lookup"><span data-stu-id="021f7-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="021f7-115">Exemplos de firewall externo e interno e interfaces do servidor são mostrados apenas para fins de referência.</span><span class="sxs-lookup"><span data-stu-id="021f7-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="021f7-116">Por fim, o exemplo de gateway padrão e relações de roteamento são mostrados, onde aplicável.</span><span class="sxs-lookup"><span data-stu-id="021f7-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="021f7-117">Observe também que o diagrama usa a zona DNS <EM>. com</EM> para representar a zona DNS externa para servidores de borda e proxy reverso e a zona DNS do <EM>.net</EM> refere-se à zona DNS interna.</span><span class="sxs-lookup"><span data-stu-id="021f7-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="021f7-118">Novo no Microsoft Lync Server 2013 é o suporte para o endereçamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="021f7-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="021f7-119">Parecido como o endereço IPv4, os endereços IPv6 devem ser atribuídos de tal forma que o endereço faz parte do seu espaço de endereço IPv6 atribuído.</span><span class="sxs-lookup"><span data-stu-id="021f7-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="021f7-120">Os endereços neste tópico são apenas para exemplo.</span><span class="sxs-lookup"><span data-stu-id="021f7-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="021f7-121">Você deve adquirir endereços IPv6 que funcionarão em sua implantação, oferecer o escopo correto e irá interoperar com o endereço interno e externo.</span><span class="sxs-lookup"><span data-stu-id="021f7-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="021f7-122">O Windows Server fornece um recurso importante para a operação de IPv6 de transição e a comunicação IPv4 para IPv6 chamada de *pilha Dual*.</span><span class="sxs-lookup"><span data-stu-id="021f7-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="021f7-123">A pilha dupla é uma pilha de rede distinta e separada para IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="021f7-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="021f7-124">A pilha dupla é que permite atribuir endereços para IPv4 e IPv6 simultaneamente e permite o servidor comunicar com outros hosts e clientes com base em seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="021f7-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="021f7-125">Os tipos de endereços típicos que você usará para o endereçamento IPv6 serão os endereços globais IPv6 (semelhante aos endereços IPv4 públicos), endereços locais exclusivos IPv6 (semelhante aos intervalos de endereços IPv4 privados) e endereços de link local IPv6 (semelhante ao IP privado automático endereços no Windows Server para IPv4)</span><span class="sxs-lookup"><span data-stu-id="021f7-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="021f7-126">Tecnologias de conversação do endereço de rede (NAT) para IPv6 existem que permitirá o NAT IPv6 para IPv4 (geralmente chamado como NAT64) e de NAT IPv6 para IPv6 (geralmente chamado como NAT66).</span><span class="sxs-lookup"><span data-stu-id="021f7-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="021f7-127">A existência de tecnologias NAT significa que os cinco cenários apresentados para servidores de borda do Lync Server ainda são válidos.</span><span class="sxs-lookup"><span data-stu-id="021f7-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="021f7-128">O IPv6 é um tópico complexo e requer um planejamento cuidadoso com sua equipe de rede e seu provedor de Internet para garantir que os endereços que você atribui no nível do Windows Server e no nível do Lync Server 2013 funcionem conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="021f7-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="021f7-129">Consulte os links disponibilizados no final deste tópico para obter recursos adicionais sobre o planejamento e o endereçamento IPv6.</span><span class="sxs-lookup"><span data-stu-id="021f7-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="021f7-130">**Configuração do balanceador de carga de hardware**</span><span class="sxs-lookup"><span data-stu-id="021f7-130">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="021f7-131">Para obter detalhes, consulte a seção "requisitos do balanceador de carga de hardware para uma borda A/V" em [componentes necessários para acesso de usuário externo no Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="021f7-131">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="021f7-132">**Topologia de borda consolidada dimensionada (com balanceamento de carga de hardware)**</span><span class="sxs-lookup"><span data-stu-id="021f7-132">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="021f7-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="021f7-133">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="021f7-134">Se você estiver usando o CAC (controle de admissão de chamadas), ainda deverá atribuir endereços IPv4 à interface interna do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="021f7-134">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="021f7-135">O CAC usa endereços IPv4 e deve ter disponível para operar.</span><span class="sxs-lookup"><span data-stu-id="021f7-135">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="021f7-136">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="021f7-136">In This Section</span></span>

  - [<span data-ttu-id="021f7-137">Resumo de certificado-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="021f7-137">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="021f7-138">Resumo de porta-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="021f7-138">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="021f7-139">Resumo de DNS-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="021f7-139">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="021f7-140">Confira Também</span><span class="sxs-lookup"><span data-stu-id="021f7-140">See Also</span></span>


[<span data-ttu-id="021f7-141">Arquitetura de endereçamento de IP versão 6</span><span class="sxs-lookup"><span data-stu-id="021f7-141">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="021f7-142">Formato de endereço de unicast global IPv6</span><span class="sxs-lookup"><span data-stu-id="021f7-142">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="021f7-143">Endereços exclusivos de unicast IPv6 locais</span><span class="sxs-lookup"><span data-stu-id="021f7-143">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

