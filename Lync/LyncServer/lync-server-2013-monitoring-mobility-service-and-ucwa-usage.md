---
title: 'Lync Server 2013: monitorar o serviço de mobilidade e o uso do UCWA'
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
ms.openlocfilehash: d4968c1a3b3dc30bdab2a3c19fd8e930da6122cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a><span data-ttu-id="df65c-102">Monitorar o serviço de mobilidade e o uso do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df65c-102">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df65c-103">_**Tópico da última modificação:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="df65c-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="df65c-104">Continuamente, você deve monitorar a CPU e a memória usadas pelo Lync Server Mobility Service (MCX) e pela API Web de comunicação unificada (UCWA).</span><span class="sxs-lookup"><span data-stu-id="df65c-104">On an ongoing basis, you should monitor the CPU and memory that is used by the Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="df65c-105">Para monitorar o uso, você pode usar uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="df65c-105">To monitor usage, you can use the following:</span></span>

<span data-ttu-id="df65c-106">**Para Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="df65c-106">**For Unified Communications Web API (UCWA):**</span></span>

  - <span data-ttu-id="df65c-107">O processo de trabalho do **LyncUcwa** no Gerenciador dos serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="df65c-107">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="df65c-108">No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.</span><span class="sxs-lookup"><span data-stu-id="df65c-108">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="df65c-109">Os contadores de desempenho da **CPU** e do **Processador**.</span><span class="sxs-lookup"><span data-stu-id="df65c-109">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="df65c-110">Na maioria das implantações, o uso da CPU do UWCA deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="df65c-110">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="df65c-111">O uso da memória deve ficar dentro dos limites descritos em [monitoramento para limites de capacidade de memória do servidor no Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="df65c-111">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="df65c-112">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="df65c-112">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="df65c-113">**Ls: Web – Web-throttling\\e autenticação – total de solicitações em processamento**, que indica o número de solicitações pendentes da Web no servidor.</span><span class="sxs-lookup"><span data-stu-id="df65c-113">**LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="df65c-114">Quando esse contador chegar a 10.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="df65c-114">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="df65c-115">**Solicitações\\ASP.NET Enfileiradas** (sempre devem ser zero).</span><span class="sxs-lookup"><span data-stu-id="df65c-115">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df65c-116">Se você atender ou ultrapassar esses valores, consulte novamente e recalcule o planejamento de capacidade para o dimensionamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="df65c-116">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the Web services.</span></span>



</div>

<span data-ttu-id="df65c-117">**Para o Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="df65c-117">**For the Mobility Service (Mcx):**</span></span>

  - <span data-ttu-id="df65c-118">Os processos de trabalho do **CSIntMcxAppPool** e do **CSExtMcxAppPool** no Gerenciador dos serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="df65c-118">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="df65c-119">No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.</span><span class="sxs-lookup"><span data-stu-id="df65c-119">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>

  - <span data-ttu-id="df65c-120">Os contadores de desempenho da **CPU** e do **Processador**.</span><span class="sxs-lookup"><span data-stu-id="df65c-120">The **CPU** and **Processor** performance counters.</span></span>

<span data-ttu-id="df65c-121">Na maioria das implantações o uso da CPU do Mobility Service deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="df65c-121">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="df65c-122">O uso da memória deve ficar dentro dos limites descritos em [monitoramento para limites de capacidade de memória do servidor no Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="df65c-122">Memory usage should fall within the limits described in [Monitoring for server memory capacity limits in Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).</span></span>

<span data-ttu-id="df65c-123">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="df65c-123">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>

  - <span data-ttu-id="df65c-124">O **ASP.NET v\\2.0.50727 requests Current**, que indica o número de solicitações pendentes da Web no servidor.</span><span class="sxs-lookup"><span data-stu-id="df65c-124">**ASP.NET v2.0.50727\\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="df65c-125">Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="df65c-125">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>

  - <span data-ttu-id="df65c-126">**Solicitações\\ASP.NET Enfileiradas** (sempre devem ser zero).</span><span class="sxs-lookup"><span data-stu-id="df65c-126">**ASP.NET\\Requests Queued** (should always be zero).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df65c-127">Se você satisfaz ou supera esses valores, deve revisitar e recalcular o planejamento da capacidade para o dimensionamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="df65c-127">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the Web services.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df65c-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="df65c-128">See Also</span></span>


[<span data-ttu-id="df65c-129">Monitorar os limites de capacidade de memória do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df65c-129">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

