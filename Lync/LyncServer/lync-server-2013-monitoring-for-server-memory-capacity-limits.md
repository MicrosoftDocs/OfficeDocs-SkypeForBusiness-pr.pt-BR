---
title: 'Lync Server 2013: monitoramento de limites de capacidade de memória do servidor'
description: 'Lync Server 2013: monitoramento de limites de capacidade de memória do servidor.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6561908af2c8f2f7b5fb9e347cc6247f7ca6642e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562047"
---
# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="45a50-103">Monitoramento de limites de capacidade de memória do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45a50-103">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45a50-104">_**Última modificação do tópico:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="45a50-104">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="45a50-105">As informações neste tópico referem-se ao planejamento de capacidade referem-se apenas aos clientes móveis do Lync 2010 e ao serviço de mobilidade (MCX).</span><span class="sxs-lookup"><span data-stu-id="45a50-105">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="45a50-106">O planejamento de capacidade para a API da Web de comunicações unificadas (UCWA), usado pelos clientes móveis do Lync 2013, é fornecido pelo Lync Server 2013, ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="45a50-106">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="45a50-107">Dois contadores de desempenho de mobilidade podem ajudá-lo a determinar o uso atual e a ajudá-lo a planejar a capacidade do Lync Server 2013 Mobility Service (MCX), bem como monitorar o uso de memória para o UCWA.</span><span class="sxs-lookup"><span data-stu-id="45a50-107">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="45a50-108">Para o UCWA, a categoria de contador é **ls: Web – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="45a50-108">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="45a50-109">Para o serviço de mobilidade (MCX), os contadores estão sob a categoria **ls: Web-Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="45a50-109">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="45a50-110">Os contadores a serem monitorados são:</span><span class="sxs-lookup"><span data-stu-id="45a50-110">The counters to monitor are:</span></span>

  - <span data-ttu-id="45a50-111">**Contagem de sessão ativa no momento com assinaturas de presença ativa**, que é o número atual de pontos de extremidade registrados através do UCWA ou do serviço de mobilidade (MCX) que possuem assinaturas de presença ativa (número de usuários móveis sempre conectados)</span><span class="sxs-lookup"><span data-stu-id="45a50-111">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="45a50-112">**Contagem de sessão ativa no momento**, que é o número atual de pontos de extremidade registrados através do UCWA ou do serviço de mobilidade</span><span class="sxs-lookup"><span data-stu-id="45a50-112">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="45a50-113">Se a diferença entre a **contagem de sessão ativa no momento com assinaturas de presença ativas** e a **contagem de sessão ativa no momento** for pequena ao longo do tempo, isso significa que a maioria dos usuários de dispositivos móveis têm um dispositivo sempre conectado, como um dispositivo móvel Android ou Nokia (apenas para MCX).</span><span class="sxs-lookup"><span data-stu-id="45a50-113">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="45a50-114">Os dispositivos UCWA sempre conectados incluem dispositivos Apple e Android que executam clientes móveis do Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="45a50-114">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="45a50-115">Se a **contagem de sessão ativa no momento** for muito maior do que a contagem de sessões ativas **no momento com assinaturas de presença ativa**, isso indica que mais usuários estão usando um dispositivo de ponto de extremidade de segundo plano, como um dispositivo Apple Ios ou Windows Phone em MCX.</span><span class="sxs-lookup"><span data-stu-id="45a50-115">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="45a50-116">(O Windows Phone é o único cliente móvel do Lync 2013 que será registrado como este).</span><span class="sxs-lookup"><span data-stu-id="45a50-116">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="45a50-117">Você deve definir um limite na **contagem de sessão ativa no momento com assinaturas de presença ativas** e contadores de desempenho de **contagem de sessão ativos atualmente** com base no uso esperado, nos resultados de planejamento de capacidade e no monitoramento contínuo do serviço de mobilidade e de outros contadores de servidor de front-end.</span><span class="sxs-lookup"><span data-stu-id="45a50-117">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="45a50-118">Os limites definidos devem permitir que você avalie a capacidade do servidor e gere alertas quando a capacidade for excedida.</span><span class="sxs-lookup"><span data-stu-id="45a50-118">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="45a50-119">Para determinar os limites apropriados, você precisa primeiro determinar a quantidade de memória disponível no servidor front-end para o serviço de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="45a50-119">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="45a50-120">Monitore os contadores para determinar quando você precisa planejar capacidade extra, de acordo com a fórmula a seguir:</span><span class="sxs-lookup"><span data-stu-id="45a50-120">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="45a50-121">Memória total usada pelo serviço de mobilidade MCX (MB) = 164 + (400 + 134)/1024 \* **contagem de sessão ativa no momento com assinaturas de presença ativas** + 400/1024 \* (contagem de sessão ativa**no** momento – **contagem de sessão ativa no momento com assinaturas de presença ativas**)</span><span class="sxs-lookup"><span data-stu-id="45a50-121">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45a50-122">A calculadora de capacidade do Microsoft Lync Server 2010 é uma planilha preenchida previamente com todas as fórmulas que permitem que um planejador determine quais são os requisitos para os servidores, incluindo CPU, memória e disco rígido.</span><span class="sxs-lookup"><span data-stu-id="45a50-122">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="45a50-123">Você pode baixar a planilha e um documento associado em: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="45a50-123">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="45a50-124">O servidor front-end precisa de memória suficiente disponível para suportar o serviço de mobilidade em situações de failover.</span><span class="sxs-lookup"><span data-stu-id="45a50-124">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="45a50-125">Você pode monitorar a memória atual disponível no servidor front-end usando o contador **memória \\ disponível de Mbytes** ou usando a equação mencionada anteriormente para planejar a quantidade de memória que você espera que o serviço de mobilidade use.</span><span class="sxs-lookup"><span data-stu-id="45a50-125">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="45a50-126">Se a quantidade de memória disponível no servidor front-end for inferior a 1.500 MB quando você planejar o número esperado de usuários de mobilidade, você precisará adicionar mais hardware para dar suporte ao serviço de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="45a50-126">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="45a50-127">Para obter mais detalhes, consulte [Monitoring Mobility for Performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="45a50-127">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="45a50-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="45a50-128">See Also</span></span>


[<span data-ttu-id="45a50-129">Monitorando a mobilidade para desempenho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45a50-129">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

