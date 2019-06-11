---
title: Requisitos de balanceamento de carga do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4848c78c755b95a15c28ab1f8e2555a180e22bfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="f2446-102">Requisitos de balanceamento de carga para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2446-102">Load balancing requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2446-103">_**Tópico da última modificação:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f2446-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f2446-104">Se você tiver pools de front-end, pools de diretor ou pools de servidores de borda, será necessário implantar o balanceamento de carga para esses pools.</span><span class="sxs-lookup"><span data-stu-id="f2446-104">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="f2446-105">O balanceamento de carga distribui o tráfego entre os servidores em um pool.</span><span class="sxs-lookup"><span data-stu-id="f2446-105">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="f2446-106">O Lync Server 2013 dá suporte a dois tipos de soluções de balanceamento de carga para tráfego de cliente para servidor: equilíbrio de carga do sistema de nomes de domínio (DNS) e balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="f2446-106">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="f2446-107">O balanceamento de carga de DNS oferece várias vantagens, incluindo administração mais simples, solução de problemas mais eficiente e a capacidade de isolar grande parte do tráfego do Lync Server de qualquer problema potencial de balanceador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="f2446-107">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="f2446-108">Decida que solução de balanceamento de carga é apropriada para cada pool de sua implantação, considerando as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="f2446-108">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="f2446-p103">A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS em uma interface e o balanceamento de carga de hardware em outra.</span><span class="sxs-lookup"><span data-stu-id="f2446-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="f2446-p104">Alguns tipos de tráfego exigem um balanceador de carga de hardware. Por exemplo, o tráfego HTTP requer um balanceador de carga de hardware em vez do balanceamento de carga DNS. O balanceamento de carga DNS não funciona com o tráfego web de cliente-servidor.</span><span class="sxs-lookup"><span data-stu-id="f2446-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="f2446-114">Para obter mais detalhes sobre como escolher uma solução de balanceador de carga de hardware, consulte [requisitos do balanceador de carga de hardware para o Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2446-114">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="f2446-115">Se optar por usar o balanceamento de carga DNS para um pool, mas ainda for necessário implementar balanceadores de carga de hardware para o tráfego, como o tráfego HTTP, a administração dos balanceadores de carga de hardware é bastante simplificada.</span><span class="sxs-lookup"><span data-stu-id="f2446-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="f2446-116">Por exemplo, a configuração do balanceador de carga de hardware será mais simples, pois gerenciará somente os tráfegos HTTP e HTTPS, enquanto os demais protocolos serão gerenciados pelo balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="f2446-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="f2446-117">Para obter detalhes, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="f2446-117">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="f2446-118">Para o tráfego de servidor para servidor, o Lync Server 2013 usa o balanceamento de carga compatível com topologia.</span><span class="sxs-lookup"><span data-stu-id="f2446-118">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="f2446-119">Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores.</span><span class="sxs-lookup"><span data-stu-id="f2446-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="f2446-120">Os administradores não precisam configurar nem gerenciar esse tipo de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="f2446-120">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="f2446-p107">Se você usar um balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas do endereço IP do Pool FQDN. Você deve remover a entrada DNS do computador.</span><span class="sxs-lookup"><span data-stu-id="f2446-p107">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN. You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

