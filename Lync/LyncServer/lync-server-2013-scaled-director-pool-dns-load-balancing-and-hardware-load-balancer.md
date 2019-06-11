---
title: Pool de diretores em escala - balanceamento de carga de DNS e balanceador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="3b5c9-102">Pool de diretores em escala - balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b5c9-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b5c9-103">_**Tópico da última modificação:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3b5c9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3b5c9-104">Um pool de directors em escala, onde há mais de um director implantado para lidar com capacidade adicional e para fornecer alta disponibilidade, requer balanceamento de carga para distribuir a comunicação do cliente e do servidor para todos os membros do pool.</span><span class="sxs-lookup"><span data-stu-id="3b5c9-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="3b5c9-105">Um diretor hospeda serviços Web muito como um pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="3b5c9-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="3b5c9-106">Para fornecer o balanceamento de carga, você pode usar o balanceamento de carga de hardware ou o balanceamento de carga do sistema de nome de domínio (DNS) e o balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="3b5c9-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="3b5c9-107">O balanceamento de carga de hardware é necessário para os serviços Web, e o balanceamento de carga de DNS sozinha não fornece as funcionalidades necessárias para os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="3b5c9-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="3b5c9-108">Os tópicos a seguir descrevem as considerações de planejamento para a implantação de um pool de directors usando o balanceamento de carga de DNS em conjunto com o balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="3b5c9-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="3b5c9-109">Se você pretende usar o balanceamento de carga de hardware, mas não o balanceamento de carga de DNS para o pool de diretor, consulte o tópico pool de diretor de dimensionamento-balanceamento de [carga de hardware no Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) que descreve os requisitos de planejamento para essa topologia.</span><span class="sxs-lookup"><span data-stu-id="3b5c9-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="3b5c9-110">![Pool] de directors dimensionados (images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool") de directors dimensionados</span><span class="sxs-lookup"><span data-stu-id="3b5c9-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3b5c9-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3b5c9-111">In This Section</span></span>

  - [<span data-ttu-id="3b5c9-112">Resumo de certificado - Cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b5c9-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="3b5c9-113">Resumo de porta - cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b5c9-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="3b5c9-114">Resumo de DNS - Cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b5c9-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

