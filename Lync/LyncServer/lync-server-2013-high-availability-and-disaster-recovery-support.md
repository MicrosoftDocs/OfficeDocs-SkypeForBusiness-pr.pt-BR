---
title: 'Lync Server 2013: Suporte à alta disponibilidade e recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: High availability and disaster recovery support
ms:assetid: 47e77e85-c7c3-4ade-8db7-a34c71aeafd7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204866(v=OCS.15)
ms:contentKeyID: 48184053
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa5ec2ad01372d593a4452c352c33dd8077e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="high-availability-and-disaster-recovery-support-in-lync-server-2013"></a><span data-ttu-id="c8905-102">Suporte à alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8905-102">High availability and disaster recovery support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8905-103">_**Tópico da última modificação:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="c8905-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="c8905-104">O Lync Server 2013 fornece alta disponibilidade por redundância de servidor via pool.</span><span class="sxs-lookup"><span data-stu-id="c8905-104">Lync Server 2013 provides high availability by server redundancy via pooling.</span></span> <span data-ttu-id="c8905-105">Se um servidor que executa determinada função falhar, os demais servidores do pool que executam a mesma função assumirão a carga desse servidor.</span><span class="sxs-lookup"><span data-stu-id="c8905-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="c8905-106">Isso se aplica a Servidores Front-End, Servidores de Borda, Servidores de Mediação e Diretores.</span><span class="sxs-lookup"><span data-stu-id="c8905-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span> <span data-ttu-id="c8905-107">Para obter detalhes sobre as funções de servidor, consulte [funções de servidor no Lync server 2013](lync-server-2013-server-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c8905-107">For details about server roles, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md).</span></span>

<span data-ttu-id="c8905-108">O Lync Server 2013 também fornece medidas de recuperação de desastres habilitando o emparelhamento de pool.</span><span class="sxs-lookup"><span data-stu-id="c8905-108">Lync Server 2013 also provides disaster recovery measures by enabling pool pairing.</span></span> <span data-ttu-id="c8905-109">Se implantar essa topologia, você designará pares de pools de Front-Ends, com cada pool de um par localizado em um datacenter e em uma área geográfica distinta.</span><span class="sxs-lookup"><span data-stu-id="c8905-109">If you deploy this topology, you will designate pairs of Front End pools, with each pool in a pair located in a separate data center, and in a separate geographical area.</span></span> <span data-ttu-id="c8905-110">Se um pool ou site ficar inativo, você poderá redirecionar os usuários desse pool para outro pool do par, com o mínimo de interrupção de serviço.</span><span class="sxs-lookup"><span data-stu-id="c8905-110">If one pool or site goes down, you can redirect the users of that pool to use the other pool in the pair, with minimal interruption of service.</span></span>

<span data-ttu-id="c8905-111">O Lync Server 2013 também oferece suporte à alta disponibilidade do servidor back-end.</span><span class="sxs-lookup"><span data-stu-id="c8905-111">Lync Server 2013 also supports Back End Server high availability.</span></span> <span data-ttu-id="c8905-112">Esta é uma topologia opcional na qual você implanta dois servidores back-end para um pool de front-end e configura o espelhamento do SQL Server síncrono para todos os bancos de dados do Lync em execução nos servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="c8905-112">This is an optional topology in which you deploy two Back End Servers for a Front End pool, and set up synchronous SQL Server mirroring for all the Lync databases running on the Back End Servers.</span></span>

<span data-ttu-id="c8905-113">Para obter detalhes sobre o emparelhamento de pool e o espelhamento do servidor back-end, consulte [planejando alta disponibilidade e recuperação de desastres no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="c8905-113">For details about pool pairing and Back End Server mirroring, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c8905-114">Confira também</span><span class="sxs-lookup"><span data-stu-id="c8905-114">See Also</span></span>


[<span data-ttu-id="c8905-115">Funções do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8905-115">Server roles in Lync Server 2013</span></span>](lync-server-2013-server-roles.md)  
[<span data-ttu-id="c8905-116">Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8905-116">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

