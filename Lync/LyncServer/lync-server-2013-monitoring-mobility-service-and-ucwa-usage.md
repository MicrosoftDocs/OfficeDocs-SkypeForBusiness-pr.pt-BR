---
title: 'Lync Server 2013: monitorando o serviço de mobilidade e o uso do UCWA'
description: 'Lync Server 2013: monitorando o serviço de mobilidade e o uso do UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6575941faf904e46cd1f66d7226a16c88e8cbaa3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548107"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="4db3f-103">Monitorando o serviço de mobilidade e o uso do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4db3f-103">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4db3f-104">_**Última modificação do tópico:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="4db3f-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="4db3f-105">Em uma base contínua, você deve monitorar a CPU e a memória que é usada pelo Lync Server Mobility Service (MCX) e pela API Web de comunicações unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="4db3f-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="4db3f-106">Para monitorar o uso, você pode usar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4db3f-106">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="4db3f-107">**Para a API Web de comunicações unificadas (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="4db3f-107">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="4db3f-108">O processo de trabalho do **LyncUcwa** no Gerenciador de serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="4db3f-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="4db3f-109">No painel **processos de trabalho** , examine as colunas **CPU%** e **bytes particulares (KB)** (memória).</span><span class="sxs-lookup"><span data-stu-id="4db3f-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="4db3f-110">Os contadores de desempenho **da CPU** e do **processador** .</span><span class="sxs-lookup"><span data-stu-id="4db3f-110">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="4db3f-111">Para a maioria das implantações, o uso da CPU do UCWA deve estar abaixo de 15% em média.</span><span class="sxs-lookup"><span data-stu-id="4db3f-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="4db3f-112">O uso de memória deve ficar dentro dos limites descritos em [Monitoring for Server Memory Capacity Limits in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="4db3f-112">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="4db3f-113">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="4db3f-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="4db3f-114">**Ls: Web – limitação e autenticação \\ WEB – total de solicitações em processamento**, que indica o número de solicitações da Web pendentes no servidor.</span><span class="sxs-lookup"><span data-stu-id="4db3f-114">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="4db3f-115">Quando esse contador chegar a 10.000, as solicitações subsequentes falharão, com a mensagem de erro "503-Serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="4db3f-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="4db3f-116">**ASP.NET \\ Solicitações enfileiradas** (devem sempre ser zero).</span><span class="sxs-lookup"><span data-stu-id="4db3f-116">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4db3f-117">Se você atender ou exceder esses valores, deverá revisitar e recalcular seu planejamento de capacidade para o dimensionamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="4db3f-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="4db3f-118">**Para o serviço de mobilidade (MCX):**</span><span class="sxs-lookup"><span data-stu-id="4db3f-118">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="4db3f-119">Os processos de trabalho do **CSIntMcxAppPool** e do **CSExtMcxAppPool** no Gerenciador de serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="4db3f-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="4db3f-120">No painel **processos de trabalho** , examine as colunas **CPU%** e **bytes particulares (KB)** (memória).</span><span class="sxs-lookup"><span data-stu-id="4db3f-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="4db3f-121">Os contadores de desempenho **da CPU** e do **processador** .</span><span class="sxs-lookup"><span data-stu-id="4db3f-121">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="4db3f-122">Para a maioria das implantações, o uso da CPU do serviço de mobilidade deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="4db3f-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="4db3f-123">O uso de memória deve ficar dentro dos limites descritos em [Monitoring for Server Memory Capacity Limits in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="4db3f-123">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="4db3f-124">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho do ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="4db3f-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="4db3f-125">**ASP.NET v 2.0.50727 \\ Solicitações atuais**, que indica o número de solicitações da Web pendentes no servidor.</span><span class="sxs-lookup"><span data-stu-id="4db3f-125">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="4db3f-126">Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com a mensagem de erro "503-Serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="4db3f-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="4db3f-127">**ASP.NET \\ Solicitações enfileiradas** (devem sempre ser zero).</span><span class="sxs-lookup"><span data-stu-id="4db3f-127">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4db3f-128">Se você atender ou exceder esses valores, deverá revisitar e recalcular seu planejamento de capacidade para o dimensionamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="4db3f-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4db3f-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="4db3f-129">See Also</span></span>


[<span data-ttu-id="4db3f-130">Monitoramento de limites de capacidade de memória do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4db3f-130">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

