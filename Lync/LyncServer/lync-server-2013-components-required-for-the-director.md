---
title: 'Lync Server 2013: componentes necessários para o diretor'
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
ms.openlocfilehash: 84a5765ce21ba955e4354c693171180a9d828210
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="a7ff6-102">Componentes necessários para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7ff6-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7ff6-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a7ff6-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a7ff6-104">O único componente necessário para criar e configurar um diretor é implantar a função de servidor diretor.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="a7ff6-105">Você faz isso usando o construtor de topologias e define um pool de computador único ou um pool de vários computadores no nó do pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="a7ff6-106">Após definir o diretor ou o pool de diretor, execute o assistente de implantação do Lync Server no computador que será um diretor.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="a7ff6-107">No caso de um pool de diretores, você executa o assistente de implantação do Lync Server em cada servidor que será membro do pool.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="a7ff6-108">Topologias</span><span class="sxs-lookup"><span data-stu-id="a7ff6-108">Topologies</span></span>

<span data-ttu-id="a7ff6-109">Você pode implementar um único servidor de diretor ou um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="a7ff6-110">O diretor é sempre um servidor ou pool separado, não colocado com qualquer outra função de servidor no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7ff6-111">Se você não implantar diretores, o servidor front-end ou o pool de front-ends assumirá a função diretor.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="a7ff6-112">Um pool de diretores deve ter o balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="a7ff6-113">Você pode:</span><span class="sxs-lookup"><span data-stu-id="a7ff6-113">You can do one of the following:</span></span>

  - <span data-ttu-id="a7ff6-114">Criar uma topologia que usa um balanceador de carga de hardware para serviços web e balanceamento de carga DNS (Domain Name System) para os outros tipos de tráfego.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="a7ff6-115">Pool de diretores em escala-balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7ff6-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="a7ff6-116">Criar uma topologia que usa um balanceador de carga de hardware para balanceamento de carga necessário para o pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="a7ff6-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="a7ff6-117">Pool de diretores em escala-balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7ff6-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

