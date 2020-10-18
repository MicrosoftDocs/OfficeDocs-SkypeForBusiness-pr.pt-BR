---
title: 'Lync Server 2013: pool de diretores em escala-balanceador de carga de hardware'
description: 'Lync Server 2013: pool de diretores em escala-balanceador de carga de hardware.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 022c5afb67687149f8ba24655be2a1461d4371f2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578697"
---
# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="2b8c1-103">Pool de diretores em escala-balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b8c1-103">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b8c1-104">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2b8c1-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2b8c1-105">Um pool de diretores em escala, onde há mais de um diretor implantado para lidar com capacidade adicional e para fornecer alta disponibilidade, requer o balanceamento de carga para distribuir a comunicação de cliente e servidor para todos os membros do pool.</span><span class="sxs-lookup"><span data-stu-id="2b8c1-105">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="2b8c1-106">Um diretor hospeda serviços Web da mesma forma que um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="2b8c1-106">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="2b8c1-107">O balanceamento de carga de hardware é necessário para os serviços da Web.</span><span class="sxs-lookup"><span data-stu-id="2b8c1-107">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="2b8c1-108">Os tópicos a seguir descrevem as considerações de planejamento para a implantação de um pool de diretores usando o balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="2b8c1-108">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="2b8c1-109">Se você pretende usar o balanceamento de carga de hardware e o balanceamento de carga DNS para o pool de diretores, consulte o tópico [pool de diretor em escala-balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) que descreve os requisitos de planejamento para essa topologia.</span><span class="sxs-lookup"><span data-stu-id="2b8c1-109">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="2b8c1-110">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="2b8c1-110">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2b8c1-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2b8c1-111">In This Section</span></span>

  - [<span data-ttu-id="2b8c1-112">Resumo de certificado-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b8c1-112">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="2b8c1-113">Resumo de porta-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b8c1-113">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="2b8c1-114">Resumo de DNS-pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b8c1-114">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

