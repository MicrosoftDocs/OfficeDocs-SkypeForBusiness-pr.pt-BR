---
title: Monitorar o uso do Serviço de Mobilidade e do UCWA no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumo: Gerencie o serviço de mobilidade (Mcx) e a API (UCWA) da Web das comunicações unificadas Skype para Business Server 2015.'
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a><span data-ttu-id="554c7-103">Monitorar o uso do Serviço de Mobilidade e do UCWA no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="554c7-103">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="554c7-104">**Resumo:** Gerencie o serviço de mobilidade (Mcx) e a API (UCWA) da Web das comunicações unificadas Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="554c7-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="554c7-105">Em uma base contínua, você deve monitorar a CPU e memória que é usada pelo Skype para serviço de mobilidade do Business Server (Mcx) e a API de Web de comunicações unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="554c7-105">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="554c7-106">Para monitorar o uso, você pode usar uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="554c7-106">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="554c7-107">**Para Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="554c7-107">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="554c7-108">O processo de trabalho **LyncUcwa** no Gerenciador de serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="554c7-108">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="554c7-109">No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.</span><span class="sxs-lookup"><span data-stu-id="554c7-109">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="554c7-110">Os contadores de desempenho da **CPU** e do **Processador**.</span><span class="sxs-lookup"><span data-stu-id="554c7-110">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="554c7-111">Na maioria das implantações, o uso da CPU do UWCA deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="554c7-111">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="554c7-112">Uso da memória deve ficam dentro dos limites descritos no [Monitor de limites de capacidade de memória do servidor no Skype para Business Server 2015](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="554c7-112">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="554c7-113">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="554c7-113">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="554c7-114">**LS:WEB - limitação e Authentication\WEB - Total de solicitações no processamento**, que indica o número de solicitações da web no servidor pendentes.</span><span class="sxs-lookup"><span data-stu-id="554c7-114">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="554c7-115">Quando esse contador chegar a 10.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="554c7-115">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="554c7-116">**ASP.NET \requests Queued** (deve ser sempre zero).</span><span class="sxs-lookup"><span data-stu-id="554c7-116">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="554c7-117">Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web.</span><span class="sxs-lookup"><span data-stu-id="554c7-117">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="554c7-118">**Para o Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="554c7-118">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="554c7-119">Os processos de trabalho do **CSIntMcxAppPool** e **CSExtMcxAppPool** no Gerenciador de serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="554c7-119">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="554c7-120">No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.</span><span class="sxs-lookup"><span data-stu-id="554c7-120">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="554c7-121">Os contadores de desempenho da **CPU** e do **Processador**.</span><span class="sxs-lookup"><span data-stu-id="554c7-121">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="554c7-122">Na maioria das implantações o uso da CPU do Mobility Service deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="554c7-122">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="554c7-123">Uso da memória deve ficam dentro dos limites descritos no [Monitor de limites de capacidade de memória do servidor no Skype para Business Server 2015](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="554c7-123">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server 2015](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="554c7-124">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="554c7-124">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="554c7-125">**ASP.NET v2.0.50727\Requests atual**, que indica o número de solicitações da web no servidor pendentes.</span><span class="sxs-lookup"><span data-stu-id="554c7-125">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="554c7-126">Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="554c7-126">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="554c7-127">**ASP.NET \requests Queued** (deve ser sempre zero).</span><span class="sxs-lookup"><span data-stu-id="554c7-127">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="554c7-128">Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web.</span><span class="sxs-lookup"><span data-stu-id="554c7-128">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="554c7-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="554c7-129">See also</span></span>

#### 

[<span data-ttu-id="554c7-130">Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="554c7-130">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)

