---
title: Pool de diretores em escala-balanceamento de carga de DNS e balanceador de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d05e579d8c4a2c54342b926b34ff20bbd722524c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510968"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="657eb-102">Pool de diretores em escala-balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="657eb-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="657eb-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="657eb-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="657eb-104">Um pool de diretores em escala, onde há mais de um diretor implantado para lidar com capacidade adicional e para fornecer alta disponibilidade, requer o balanceamento de carga para distribuir a comunicação de cliente e servidor para todos os membros do pool.</span><span class="sxs-lookup"><span data-stu-id="657eb-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="657eb-105">Um diretor hospeda serviços Web da mesma forma que um pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="657eb-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="657eb-106">Para fornecer o balanceamento de carga, você pode usar o balanceamento de carga de hardware, ou balanceamento de carga do DNS (sistema de nomes de domínio) e balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="657eb-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="657eb-107">O balanceamento de carga de hardware é obrigatório para serviços web e o balanceamento de carga do DNS sozinho não fornece os recursos exigidos pelos serviços web.</span><span class="sxs-lookup"><span data-stu-id="657eb-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="657eb-108">Os tópicos a seguir descrevem as considerações de planejamento para a implantação de um pool de diretores usando o balanceamento de carga DNS em conjunto com o balanceamento de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="657eb-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="657eb-109">Se você pretende usar o balanceamento de carga de hardware, mas não o balanceamento de carga DNS para o pool diretor, consulte o tópico [pool de diretores em escala-hardware Load Balancer no Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) que descreve os requisitos de planejamento para essa topologia.</span><span class="sxs-lookup"><span data-stu-id="657eb-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="657eb-110">![Novo Pool de Diretor em Escala](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Novo Pool de Diretor em Escala")</span><span class="sxs-lookup"><span data-stu-id="657eb-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="657eb-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="657eb-111">In This Section</span></span>

  - [<span data-ttu-id="657eb-112">Resumo de certificado-carga de DNS e HLB balanceada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="657eb-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="657eb-113">Resumo de porta-carga de DNS e HLB balanceada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="657eb-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="657eb-114">Resumo de DNS-cargas de DNS e de HLB balanceadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="657eb-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

