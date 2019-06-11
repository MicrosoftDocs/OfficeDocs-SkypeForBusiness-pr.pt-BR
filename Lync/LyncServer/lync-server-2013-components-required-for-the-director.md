---
title: 'Lync Server 2013: Componentes necessários para o diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c80002d0c91853be1523f6ce1bedfdccef72a68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="523b1-102">Componentes necessários para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="523b1-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="523b1-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="523b1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="523b1-104">O único componente necessário para criar e configurar um diretor é implantar a função de servidor diretor.</span><span class="sxs-lookup"><span data-stu-id="523b1-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="523b1-105">Isso é feito usando o construtor de topologias e define um único pool de computadores ou um pool de vários computadores no nó do pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="523b1-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="523b1-106">Depois de definir o diretor ou o pool do diretor, execute o assistente de implantação do Lync Server no computador que será um diretor.</span><span class="sxs-lookup"><span data-stu-id="523b1-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="523b1-107">No caso de um pool de diretor, você executa o assistente de implantação do Lync Server em cada servidor que será membro do pool.</span><span class="sxs-lookup"><span data-stu-id="523b1-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="523b1-108">Topologia</span><span class="sxs-lookup"><span data-stu-id="523b1-108">Topologies</span></span>

<span data-ttu-id="523b1-109">Você pode implementar um único servidor de director ou um pool de directors.</span><span class="sxs-lookup"><span data-stu-id="523b1-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="523b1-110">O diretor é sempre um servidor ou pool separado, não posicionado com nenhuma outra função de servidor no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="523b1-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="523b1-111">Se você não implantar diretores, o servidor front-end ou o pool de front-end assumirá a função de diretor.</span><span class="sxs-lookup"><span data-stu-id="523b1-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="523b1-112">É necessário balancear A carga de um pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="523b1-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="523b1-113">Você pode executar uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="523b1-113">You can do one of the following:</span></span>

  - <span data-ttu-id="523b1-114">Crie uma topologia que use um balanceador de carga de hardware para serviços Web e balanceamento de carga DNS (Domain Name System) para os outros tipos de tráfego.</span><span class="sxs-lookup"><span data-stu-id="523b1-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="523b1-115">Pool de diretores em escala - balanceamento de carga de DNS e balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="523b1-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="523b1-116">Crie uma topologia que use um balanceador de carga de hardware para o balanceamento de carga necessário para o pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="523b1-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="523b1-117">Pool de diretores em escala - balanceador de carga de hardware no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="523b1-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

