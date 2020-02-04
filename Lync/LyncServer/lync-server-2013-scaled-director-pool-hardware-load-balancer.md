---
title: 'Lync Server 2013: Pool de diretores em escala - balanceador de carga de hardware'
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
ms.openlocfilehash: f3fc699a5d0904b3ed308928e5edec612b3af03c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="60791-102">Pool de diretores em escala - balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60791-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60791-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="60791-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="60791-104">Um pool de directors em escala, onde há mais de um director implantado para lidar com capacidade adicional e para fornecer alta disponibilidade, requer balanceamento de carga para distribuir a comunicação do cliente e do servidor para todos os membros do pool.</span><span class="sxs-lookup"><span data-stu-id="60791-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="60791-105">Um diretor hospeda serviços Web muito como um pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="60791-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="60791-106">O balanceamento de carga de hardware é necessário para os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="60791-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="60791-107">Os tópicos a seguir descrevem as considerações de planejamento para a implantação de um pool de directors usando o balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="60791-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="60791-108">Se você pretende usar o balanceamento de carga de hardware e o balanceamento de carga de DNS para o pool diretor, consulte o tópico [pool de directors em escala-balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) que descreve os requisitos de planejamento para essa topologia.</span><span class="sxs-lookup"><span data-stu-id="60791-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="60791-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="60791-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="60791-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="60791-110">In This Section</span></span>

  - [<span data-ttu-id="60791-111">Resumo de certificado - pool Certificate summary - pool de diretores em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60791-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="60791-112">Resumo de porta - Pool de Diretor em escala, balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60791-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="60791-113">Resumo de DNS - Pool de diretores em escala, balanceadores de carga do hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60791-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

