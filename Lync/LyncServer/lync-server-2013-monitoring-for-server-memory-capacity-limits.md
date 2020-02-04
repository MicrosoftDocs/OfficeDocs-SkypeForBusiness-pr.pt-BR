---
title: 'Lync Server 2013: monitoramento de limites de capacidade de memória do servidor'
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
ms.openlocfilehash: e5c9746240335b1c66606da24edf6ffa2a0e7bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a><span data-ttu-id="38265-102">Monitorar os limites de capacidade de memória do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38265-102">Monitoring for server memory capacity limits in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38265-103">_**Tópico da última modificação:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="38265-103">_**Topic Last Modified:** 2016-12-08_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> <span data-ttu-id="38265-104">As informações neste tópico referem-se ao planejamento da capacidade refere-se somente aos clientes móveis do Lync 2010 e ao serviço de mobilidade (MCX).</span><span class="sxs-lookup"><span data-stu-id="38265-104">The information in this topic that refers to Capacity Planning pertains only to Lync 2010 Mobile clients and the Mobility Service (Mcx).</span></span> <span data-ttu-id="38265-105">O planejamento de capacidade para a API da Web de comunicação unificada (UCWA), usado pelos clientes móveis do Lync 2013, é fornecido pela ferramenta de planejamento 2013 do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38265-105">Capacity Planning for the Unified Communications Web API (UCWA), used by the Lync 2013 Mobile clients, is provided by the Lync Server 2013, Planning Tool.</span></span>



</div>

<span data-ttu-id="38265-106">Dois contadores de desempenho de mobilidade podem ajudar você a determinar o uso atual e a ajudá-lo a planejar a capacidade do serviço de mobilidade do Lync Server 2013 (MCX), bem como monitorar o uso da memória para UCWA.</span><span class="sxs-lookup"><span data-stu-id="38265-106">Two mobility performance counters can help you to determine your current usage and help you plan capacity for the Lync Server 2013 Mobility Service (Mcx), as well as to monitor memory usage for UCWA.</span></span> <span data-ttu-id="38265-107">No caso da UCWA, a categoria do contador é **LS:WEB – UCWA**.</span><span class="sxs-lookup"><span data-stu-id="38265-107">For UCWA, the counter category is **LS:WEB – UCWA**.</span></span> <span data-ttu-id="38265-108">Para o Serviço de mobilidade (Mcx), os contadores estão sob a categoria **LS:WEB - Mobile Communication Service**.</span><span class="sxs-lookup"><span data-stu-id="38265-108">For the Mobility Service (Mcx), the counters are under the category **LS:WEB - Mobile Communication Service**.</span></span> <span data-ttu-id="38265-109">Os contadores para monitoramento são:</span><span class="sxs-lookup"><span data-stu-id="38265-109">The counters to monitor are:</span></span>

  - <span data-ttu-id="38265-110">**Contagem atual da sessão ativa com as assinaturas de presença ativa**, que é o número atual de pontos de extremidade registrados através do Serviço de mobilidade ou UCWA que tem assinaturas de presença ativa (número de usuários móveis sempre conectados).</span><span class="sxs-lookup"><span data-stu-id="38265-110">**Currently Active Session Count with Active Presence Subscriptions**, which is the current number of endpoints registered through UCWA or the Mobility Service (Mcx) that have active presence subscriptions (number of always-connected mobile users)</span></span>

  - <span data-ttu-id="38265-111">**Contagem atual de sessão ativa**, que é o número atual de pontos de extremidade registrados através do Serviço de Mobilidade ou UCWA.</span><span class="sxs-lookup"><span data-stu-id="38265-111">**Currently Active Session Count**, which is the current number of endpoints registered through UCWA or the Mobility Service</span></span>

<span data-ttu-id="38265-112">Se a diferença entre **Contagem atual de sessão ativa com assinaturas de presença ativa** e **Contagem atual de sessão ativa** for pequena com o passar do tempo, isso significa que a maioria dos usuários de dispositivos móveis tem um dispositivo sempre conectado, como um dispositivo Android ou Nokia (somente para Mcx).</span><span class="sxs-lookup"><span data-stu-id="38265-112">If the difference between **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** is small over time, this means that most mobile device users have an always-connected device, such as an Android or Nokia mobile device (for Mcx only).</span></span> <span data-ttu-id="38265-113">Os dispositivos UCWA sempre conectados incluem dispositivos Apple e Android que executam clientes móveis do Lync 2013).</span><span class="sxs-lookup"><span data-stu-id="38265-113">UCWA always-connected devices include Apple and Android devices running Lync 2013 Mobile clients).</span></span> <span data-ttu-id="38265-114">Se **Contagem atual de sessão ativa** for muito maior que **Contagem atual de sessão ativa com assinaturas de presença ativa**, isso mostra que mais usuários estão usando um dispositivo de ponto de extremidade de plano de fundo, como um dispositivo Apple iOS ou um Windows Phone com Mcx.</span><span class="sxs-lookup"><span data-stu-id="38265-114">If **Currently Active Session Count** is much higher than **Currently Active Session Count with Active Presence Subscriptions**, this indicates that more users are using a background endpoint device, such as an Apple iOS device or Windows Phone under Mcx.</span></span> <span data-ttu-id="38265-115">(O Windows Phone é o único cliente móvel do Lync 2013 que será registrado como este).</span><span class="sxs-lookup"><span data-stu-id="38265-115">(Windows Phone is the only Lync 2013 Mobile client that will register as this).</span></span>

<span data-ttu-id="38265-116">Você deve definir um limite na **contagem de sessões ativas atualmente com assinaturas de presença ativas** e contadores de desempenho de **contagem de sessões ativas no momento** com base no uso esperado, nos resultados de planejamento de capacidade e na monitoração contínua do serviço de mobilidade e em outros contadores de servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="38265-116">You should set a limit on the **Currently Active Session Count with Active Presence Subscriptions** and **Currently Active Session Count** performance counters based on your expected usage, capacity planning results, and ongoing monitoring of Mobility Service and other Front End Server counters.</span></span> <span data-ttu-id="38265-117">Os limites que você definir devem permitir a avaliação da capacidade do servidor e emitir alertas quando a capacidade for excedida.</span><span class="sxs-lookup"><span data-stu-id="38265-117">The limits you set should enable you to evaluate server capacity and raise alerts when capacity is exceeded.</span></span>

<span data-ttu-id="38265-118">Para determinar os limites apropriados, você precisa primeiro determinar a quantidade de memória disponível no servidor front-end para o serviço de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="38265-118">To determine the appropriate limits, you need to first determine how much memory is available on the Front End Server for the Mobility Service.</span></span> <span data-ttu-id="38265-119">Monitore os contadores determinar quando você precisa planejar uma capacidade extra, de acordo com a fórmula a seguir:</span><span class="sxs-lookup"><span data-stu-id="38265-119">Monitor the counters to determine when you need to plan for extra capacity, according to the following formula:</span></span>

<span data-ttu-id="38265-120">Total de memória usada pelo serviço de mobilidade MCX (MB) = 164 + (400 + 134)/ \* **1024 contagem de sessões ativas atualmente com assinaturas de presença ativas** + \* 400/1024 (**contagem de sessões ativas** no momento – **contagem de sessões ativas atualmente com assinaturas de presença ativas**)</span><span class="sxs-lookup"><span data-stu-id="38265-120">Total memory used by the Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="38265-121">A calculadora de capacidade do Microsoft Lync Server 2010 é uma planilha preenchida previamente com todas as fórmulas que permitem ao Planner determinar quais são os requisitos para os servidores, incluindo CPU, memória e disco rígido.</span><span class="sxs-lookup"><span data-stu-id="38265-121">The Microsoft Lync Server 2010 Capacity Calculator is a spreadsheet that is prepopulated with all of the formulas that enable a planner to determine what the requirements will be for the servers, including CPU, memory, and hard drive.</span></span> <span data-ttu-id="38265-122">Você pode baixar a planilha e um documento associado em:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span><span class="sxs-lookup"><span data-stu-id="38265-122">You can download the spreadsheet and an associated document at: <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A></span></span>



</div>

<span data-ttu-id="38265-123">O servidor front-end precisa de memória suficiente disponível para dar suporte ao serviço de mobilidade em situações de failover.</span><span class="sxs-lookup"><span data-stu-id="38265-123">The Front End Server needs enough available memory to support the Mobility Service in failover situations.</span></span> <span data-ttu-id="38265-124">Você pode monitorar a memória atual disponível no servidor front-end usando o contador **memória\\disponível em Mbytes** ou usando a equação mencionada anteriormente, para planejar a quantidade de memória que você espera que o serviço de mobilidade use.</span><span class="sxs-lookup"><span data-stu-id="38265-124">You can monitor the current available memory on the Front End Server by using the **Memory\\Available Mbytes** counter, or by using the equation mentioned earlier, to plan for the amount of memory that you expect the Mobility Service to use.</span></span>

<span data-ttu-id="38265-125">Se a quantidade de memória disponível no servidor front-end for inferior a 1.500 MB ao planejar o número esperado de usuários da mobilidade, você precisará adicionar mais hardware para dar suporte ao serviço de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="38265-125">If the amount of memory available on the Front End Server is lower than 1,500 MB when you plan for the expected number of mobility users, you need to add more hardware to support the Mobility Service.</span></span> <span data-ttu-id="38265-126">Para obter mais detalhes, consulte [monitorando a mobilidade para desempenho no Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="38265-126">For more details, see [Monitoring mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) in the Operations documentation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="38265-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="38265-127">See Also</span></span>


[<span data-ttu-id="38265-128">Monitorando a mobilidade para o desempenho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38265-128">Monitoring mobility for performance in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

