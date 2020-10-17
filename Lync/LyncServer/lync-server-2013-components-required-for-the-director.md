---
title: 'Lync Server 2013: componentes necessários para o diretor'
description: 'Lync Server 2013: componentes necessários para o diretor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f717b9ddb9557f212321cdab075713a4b85c2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549497"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="b1032-103">Componentes necessários para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1032-103">Components required for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1032-104">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b1032-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b1032-105">O único componente necessário para criar e configurar um diretor é implantar a função de servidor diretor.</span><span class="sxs-lookup"><span data-stu-id="b1032-105">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="b1032-106">Você faz isso usando o construtor de topologias e define um pool de computador único ou um pool de vários computadores no nó do pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="b1032-106">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="b1032-107">Após definir o diretor ou o pool de diretor, execute o assistente de implantação do Lync Server no computador que será um diretor.</span><span class="sxs-lookup"><span data-stu-id="b1032-107">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="b1032-108">No caso de um pool de diretores, você executa o assistente de implantação do Lync Server em cada servidor que será membro do pool.</span><span class="sxs-lookup"><span data-stu-id="b1032-108">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="b1032-109">Topologias</span><span class="sxs-lookup"><span data-stu-id="b1032-109">Topologies</span></span>

<span data-ttu-id="b1032-110">Você pode implementar um único servidor de diretor ou um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="b1032-110">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="b1032-111">O diretor é sempre um servidor ou pool separado, não colocado com qualquer outra função de servidor no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1032-111">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1032-112">Se você não implantar diretores, o servidor front-end ou o pool de front-ends assumirá a função diretor.</span><span class="sxs-lookup"><span data-stu-id="b1032-112">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="b1032-113">Um pool de diretores deve ter o balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="b1032-113">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="b1032-114">Você pode:</span><span class="sxs-lookup"><span data-stu-id="b1032-114">You can do one of the following:</span></span>

  - <span data-ttu-id="b1032-115">Criar uma topologia que usa um balanceador de carga de hardware para serviços web e balanceamento de carga DNS (Domain Name System) para os outros tipos de tráfego.</span><span class="sxs-lookup"><span data-stu-id="b1032-115">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="b1032-116">Pool de diretores em escala-balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1032-116">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="b1032-117">Criar uma topologia que usa um balanceador de carga de hardware para balanceamento de carga necessário para o pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="b1032-117">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="b1032-118">Pool de diretores em escala-balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1032-118">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

