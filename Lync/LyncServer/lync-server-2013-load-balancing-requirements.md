---
title: Requisitos de balanceamento de carga do Lync Server 2013
description: Lync Server 2013 requisitos de balanceamento de carga.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a768b2cbfe444e6915c932835d3cc2abaf6a98c3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550027"
---
# <a name="load-balancing-requirements-for-lync-server-2013"></a><span data-ttu-id="aa803-103">Requisitos de balanceamento de carga para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa803-103">Load balancing requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa803-104">_**Última modificação do tópico:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="aa803-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="aa803-105">Se você tiver pools de front-ends, pools de diretores ou servidores de borda, será necessário implantar o balanceamento de carga para esses pools.</span><span class="sxs-lookup"><span data-stu-id="aa803-105">If you have Front End pools, Director pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span> <span data-ttu-id="aa803-106">O balanceamento de carga distribui o tráfego entre os servidores em um pool.</span><span class="sxs-lookup"><span data-stu-id="aa803-106">Load balancing distributes the traffic among the servers in a pool.</span></span>

<span data-ttu-id="aa803-107">O Lync Server 2013 oferece suporte a dois tipos de soluções de balanceamento de carga para tráfego de cliente para servidor: balanceamento de carga DNS (sistema de nomes de domínio) e balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="aa803-107">Lync Server 2013 supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="aa803-108">O balanceamento de carga DNS oferece várias vantagens, incluindo administração mais simples, solução de problemas mais eficiente e a capacidade de isolar grande parte do tráfego do Lync Server de qualquer problema potencial de balanceador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="aa803-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Lync Server traffic from any potential hardware load balancer problems.</span></span>

<span data-ttu-id="aa803-109">Decida que solução de balanceamento de carga é apropriada para cada pool de sua implantação, considerando as seguintes restrições:</span><span class="sxs-lookup"><span data-stu-id="aa803-109">Decide which load balancing solution is appropriate for each pool in your deployment, keeping in mind the following restrictions:</span></span>

  - <span data-ttu-id="aa803-p103">A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS em uma interface e o balanceamento de carga de hardware em outra.</span><span class="sxs-lookup"><span data-stu-id="aa803-p103">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>

  - <span data-ttu-id="aa803-p104">Alguns tipos de tráfego exigem um balanceador de carga de hardware. Por exemplo, o tráfego HTTP requer um balanceador de carga de hardware em vez do balanceamento de carga DNS. O balanceamento de carga DNS não funciona com o tráfego web de cliente-servidor.</span><span class="sxs-lookup"><span data-stu-id="aa803-p104">Some types of traffic require a hardware load balancer. For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing. DNS load balancing does not work with client-to-server web traffic.</span></span>

<span data-ttu-id="aa803-115">Para obter mais detalhes sobre a escolha de uma solução de balanceador de carga de hardware, consulte [requisitos de balanceador de carga de hardware para o Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa803-115">For more details about choosing a hardware load balancer solution, see [Hardware load balancer requirements for Lync Server 2013](lync-server-2013-hardware-load-balancer-requirements.md).</span></span>

<span data-ttu-id="aa803-116">Se você optar por usar o balanceamento de carga DNS para um pool mas ainda precisa implementar balanceadores de carga de hardware para o tráfego, como o tráfego HTTP, a administração dos balanceadores de carga de hardware é bastante simplificada.</span><span class="sxs-lookup"><span data-stu-id="aa803-116">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="aa803-117">Por exemplo, a configuração do balanceador de carga de hardware será mais simples, pois só gerenciará o tráfego HTTP e HTTPS, enquanto todos os outros protocolos serão gerenciados pelo balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="aa803-117">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="aa803-118">Para obter detalhes, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="aa803-118">For details, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md).</span></span>

<span data-ttu-id="aa803-119">Para o tráfego de servidor para servidor, o Lync Server 2013 usa o balanceamento de carga com reconhecimento de topologia.</span><span class="sxs-lookup"><span data-stu-id="aa803-119">For server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="aa803-120">Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores.</span><span class="sxs-lookup"><span data-stu-id="aa803-120">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="aa803-121">Os administradores não precisam configurar ou gerenciar esse tipo de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="aa803-121">Administrators do not need to set up or manage this type of load balancing.</span></span>

<span data-ttu-id="aa803-122">Se você usar o balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas de endereço IP do FQDN do pool.</span><span class="sxs-lookup"><span data-stu-id="aa803-122">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="aa803-123">Você também deve remover a entrada DNS do computador.</span><span class="sxs-lookup"><span data-stu-id="aa803-123">You must remove the DNS entry for the computer as well.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

