---
title: Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumo: Gerencie o serviço de mobilidade (Mcx) e a Web de comunicação unificada API (UCWA) no Skype para Business Server.'
ms.openlocfilehash: 780d8fca068a78ec08312551d03dbdb5327df90e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975946"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="5d19f-103">Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5d19f-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="5d19f-104">**Resumo:** Gerencie o serviço de mobilidade (Mcx) e a Web de comunicação unificada API (UCWA) no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5d19f-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="5d19f-105">Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5d19f-105">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5d19f-106">Os usuários precisarem de atualização para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="5d19f-106">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="5d19f-107">Em uma base contínua, você deve monitorar a CPU e memória que é usada pelo Skype para serviço de mobilidade do Business Server (Mcx) e a API de Web de comunicações unificadas (UCWA).</span><span class="sxs-lookup"><span data-stu-id="5d19f-107">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="5d19f-108">Para monitorar o uso, você pode usar uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="5d19f-108">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="5d19f-109">**Para Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="5d19f-109">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="5d19f-110">O processo de trabalho **LyncUcwa** no Gerenciador de serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="5d19f-110">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="5d19f-111">No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.</span><span class="sxs-lookup"><span data-stu-id="5d19f-111">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="5d19f-112">Os contadores de desempenho da **CPU** e do **Processador**.</span><span class="sxs-lookup"><span data-stu-id="5d19f-112">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="5d19f-113">Na maioria das implantações, o uso da CPU do UWCA deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="5d19f-113">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="5d19f-114">Uso da memória deve ficam dentro dos limites descritos no [Monitor de limites de capacidade de memória do servidor no Skype para Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="5d19f-114">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="5d19f-115">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="5d19f-115">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="5d19f-116">**LS:WEB - limitação e Authentication\WEB - Total de solicitações no processamento**, que indica o número de solicitações da web no servidor pendentes.</span><span class="sxs-lookup"><span data-stu-id="5d19f-116">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="5d19f-117">Quando esse contador chegar a 10.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="5d19f-117">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="5d19f-118">**ASP.NET \requests Queued** (deve ser sempre zero).</span><span class="sxs-lookup"><span data-stu-id="5d19f-118">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="5d19f-119">Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web.</span><span class="sxs-lookup"><span data-stu-id="5d19f-119">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="5d19f-120">**Para o Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="5d19f-120">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="5d19f-121">Os processos de trabalho do **CSIntMcxAppPool** e **CSExtMcxAppPool** no Gerenciador de serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="5d19f-121">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="5d19f-122">No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.</span><span class="sxs-lookup"><span data-stu-id="5d19f-122">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="5d19f-123">Os contadores de desempenho da **CPU** e do **Processador**.</span><span class="sxs-lookup"><span data-stu-id="5d19f-123">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="5d19f-124">Na maioria das implantações o uso da CPU do Mobility Service deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="5d19f-124">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="5d19f-125">Uso da memória deve ficam dentro dos limites descritos no [Monitor de limites de capacidade de memória do servidor no Skype para Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="5d19f-125">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="5d19f-126">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="5d19f-126">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="5d19f-127">**ASP.NET v2.0.50727\Requests atual**, que indica o número de solicitações da web no servidor pendentes.</span><span class="sxs-lookup"><span data-stu-id="5d19f-127">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="5d19f-128">Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="5d19f-128">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="5d19f-129">**ASP.NET \requests Queued** (deve ser sempre zero).</span><span class="sxs-lookup"><span data-stu-id="5d19f-129">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="5d19f-130">Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web.</span><span class="sxs-lookup"><span data-stu-id="5d19f-130">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="5d19f-131">Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5d19f-131">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5d19f-132">Os usuários precisarem de atualização para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="5d19f-132">Your users will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d19f-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5d19f-133">See also</span></span>

[<span data-ttu-id="5d19f-134">Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5d19f-134">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)