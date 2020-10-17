---
title: 'Lync Server 2013: suporte de alta disponibilidade e recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c78982552cfe85479f2f1551fc85e64c3f89cbea
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528228"
---
# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="a106f-102">Suporte de alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a106f-102">High availability and disaster recovery support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a106f-103">_**Última modificação do tópico:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="a106f-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="a106f-104">O Lync Server 2013 oferece alta disponibilidade por redundância de servidor por meio de Pooling.</span><span class="sxs-lookup"><span data-stu-id="a106f-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="a106f-105">Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.</span><span class="sxs-lookup"><span data-stu-id="a106f-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="a106f-106">Isso se aplica a servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.</span><span class="sxs-lookup"><span data-stu-id="a106f-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="a106f-107">Para obter detalhes sobre as funções de servidor, consulte [Server Roles in Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a106f-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="a106f-108">O Lync Server 2013 também fornece medidas de recuperação de desastres habilitando o emparelhamento do pool.</span><span class="sxs-lookup"><span data-stu-id="a106f-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="a106f-109">Sr você implantar tal topologia, pode designar pares para pools de Front End, com cada pool em um par localizado em um datacenter separado, e em uma área geográfica separada.</span><span class="sxs-lookup"><span data-stu-id="a106f-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="a106f-110">Se um pool ou site sair do ar, você pode redirecionar os usuários deste pool para outro pool no par, com o mínimo de interrupção de serviço.</span><span class="sxs-lookup"><span data-stu-id="a106f-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="a106f-111">O Lync Server 2013 também oferece suporte à alta disponibilidade do servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="a106f-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="a106f-112">Esta é uma topologia opcional na qual você implanta dois servidores back-end para um pool de front-ends e configura o espelhamento síncrono do SQL Server para todos os bancos de dados do Lync executados nos servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="a106f-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="a106f-113">Para obter detalhes sobre o emparelhamento de pool e o espelhamento de servidor back-end, consulte [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="a106f-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a106f-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="a106f-114">See Also</span></span>


[<span data-ttu-id="a106f-115">Funções de servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a106f-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="a106f-116">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a106f-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

