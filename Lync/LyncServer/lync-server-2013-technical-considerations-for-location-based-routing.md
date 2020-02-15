---
title: 'Lync Server 2013: considerações técnicas para roteamento baseado em local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcdebdccd0584d31b27120709212be674e8d3c2a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="e0594-102">Considerações técnicas para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0594-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0594-103">_**Última modificação do tópico:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="e0594-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="e0594-104">Ao planejar o roteamento baseado em local, considere o impacto nos cenários a seguir.</span><span class="sxs-lookup"><span data-stu-id="e0594-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="e0594-105">Recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="e0594-105">Disaster Recovery</span></span>

<span data-ttu-id="e0594-106">Durante um failover do pool primário para um pool de backup, bem como durante a restauração de operações normais para o pool primário, o roteamento baseado em local permanecerá em vigor em todos os momentos durante um desastre e procedimento de recuperação.</span><span class="sxs-lookup"><span data-stu-id="e0594-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="e0594-107">Aplicativo de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="e0594-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="e0594-108">Configurar o roteamento baseado em local impacta o planejamento de onde você implanta os gateways associados aos seus aparelhos de filial persistentes.</span><span class="sxs-lookup"><span data-stu-id="e0594-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="e0594-109">O gateway associado ao seu SBA deve estar localizado no mesmo local de rede que seu aparelho de filial persistente; caso contrário, os usuários hospedados no seu aparelho de filial persistente não terão permissão para fazer chamadas de saída se o roteamento baseado em local estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="e0594-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="e0594-110">Quando a conexão WAN entre seu aparelho de filial persistente e o site central estiver inativa, as restrições de roteamento baseadas em local permanecerão impostas.</span><span class="sxs-lookup"><span data-stu-id="e0594-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0594-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="e0594-111">See Also</span></span>


[<span data-ttu-id="e0594-112">Planejamento de roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0594-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

