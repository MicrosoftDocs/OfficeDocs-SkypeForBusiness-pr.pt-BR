---
title: 'Lync Server 2013: Considerações técnicas para Roteamento Baseado em Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29187cf1a5cf99ae5312f655c924565f6a38a706
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="dfb42-102">Considerações técnicas para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfb42-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfb42-103">_**Tópico da última modificação:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="dfb42-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="dfb42-104">Ao planejar o roteamento baseado em localização, considere o impacto para os cenários a seguir.</span><span class="sxs-lookup"><span data-stu-id="dfb42-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="dfb42-105">Recuperação de desastres</span><span class="sxs-lookup"><span data-stu-id="dfb42-105">Disaster Recovery</span></span>

<span data-ttu-id="dfb42-106">Durante um failover do pool primário para um pool de backup, bem como ao restaurar operações normais para o pool primário, o roteamento baseado em local permanecerá em vigor a qualquer momento durante um desastre e procedimento de recuperação.</span><span class="sxs-lookup"><span data-stu-id="dfb42-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="dfb42-107">Aparelho de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="dfb42-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="dfb42-108">Configurar o roteamento baseado em local impacta o planejamento de onde você implanta os gateways associados a seus aparelhos de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="dfb42-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="dfb42-109">O gateway associado a seu SBA deve estar localizado no mesmo site de rede que o seu aparelho de ramificação sobreviventes; caso contrário, os usuários hospedados em seu aparelho de ramificação sobreviventes não terão permissão para fazer chamadas de saída se o roteamento baseado em localização estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="dfb42-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="dfb42-110">Quando a conexão WAN entre seu aparelho de ramificação sobreviventes e o site central está inativa, as restrições de roteamento baseadas em local permanecem impostas.</span><span class="sxs-lookup"><span data-stu-id="dfb42-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfb42-111">Confira também</span><span class="sxs-lookup"><span data-stu-id="dfb42-111">See Also</span></span>


[<span data-ttu-id="dfb42-112">Planejamento de Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfb42-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

