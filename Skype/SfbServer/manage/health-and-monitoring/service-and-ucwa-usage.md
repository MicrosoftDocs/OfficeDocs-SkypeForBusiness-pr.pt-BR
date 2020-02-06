---
title: Monitorar o uso do serviço de mobilidade e do UCWA no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumo: gerenciar o serviço de mobilidade (MCX) e a API da Web de comunicação unificada (UCWA) no Skype for Business Server.'
ms.openlocfilehash: 7c41e92b144e1bd4d198c5e9d9f90913ce41400e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817680"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="0c6bf-103">Monitorar o uso do serviço de mobilidade e do UCWA no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0c6bf-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="0c6bf-104">**Resumo:** Gerenciar o serviço de mobilidade (MCX) e a API da Web de comunicação unificada (UCWA) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="0c6bf-105">O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0c6bf-106">Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0c6bf-107">Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="0c6bf-108">Continuamente, você deve monitorar a CPU e a memória usadas pelo serviço Skype for Business Server Mobility (MCX) e pela API da Web de comunicação unificada (UCWA).</span><span class="sxs-lookup"><span data-stu-id="0c6bf-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="0c6bf-109">Para monitorar o uso, você pode usar uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="0c6bf-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="0c6bf-110">**Para Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="0c6bf-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="0c6bf-111">O processo de trabalho do **LyncUcwa** no Gerenciador dos serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="0c6bf-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="0c6bf-112">No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="0c6bf-113">Os contadores de desempenho da **CPU** e do **Processador**.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="0c6bf-114">Na maioria das implantações, o uso da CPU do UWCA deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="0c6bf-115">O uso da memória deve ficar dentro dos limites descritos em [monitorar os limites de capacidade de memória do servidor no Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="0c6bf-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="0c6bf-116">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="0c6bf-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="0c6bf-117">**Ls: Web-throttling e Authentication\WEB-total de solicitações em processamento**, que indica o número de solicitações de Web pendentes no servidor.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="0c6bf-118">Quando esse contador chegar a 10.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="0c6bf-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="0c6bf-119">**ASP.NET\Requests Queued** (deve ser sempre zero).</span><span class="sxs-lookup"><span data-stu-id="0c6bf-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0c6bf-120">Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="0c6bf-121">**Para o Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="0c6bf-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="0c6bf-122">Os processos de trabalho do **CSIntMcxAppPool** e do **CSExtMcxAppPool** no Gerenciador dos serviços de informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="0c6bf-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="0c6bf-123">No painel **Processos de Trabalho**, examine as colunas (memória) **CPU %** e **Bytes Particulares (KB)**.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="0c6bf-124">Os contadores de desempenho da **CPU** e do **Processador**.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="0c6bf-125">Na maioria das implantações o uso da CPU do Mobility Service deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="0c6bf-126">O uso da memória deve ficar dentro dos limites descritos em [monitorar os limites de capacidade de memória do servidor no Skype for Business Server](server-memory-capacity-limits.md).</span><span class="sxs-lookup"><span data-stu-id="0c6bf-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="0c6bf-127">Além de contadores de uso de CPU e memória, você pode usar os contadores de desempenho ASP.NET a seguir para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="0c6bf-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="0c6bf-128">**ASP.NET v2.0.50727\Requests Current**, que indica o número de solicitações Web pendentes no servidor.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="0c6bf-129">Quando esse contador chegar a 5.000, as solicitações subsequentes falharão com o erro "503 - serviço indisponível".</span><span class="sxs-lookup"><span data-stu-id="0c6bf-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="0c6bf-130">**ASP.NET\Requests Queued** (deve ser sempre zero).</span><span class="sxs-lookup"><span data-stu-id="0c6bf-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="0c6bf-131">Se você atender ou exceder esses valores, reveja e recalcule seu planejamento de capacidade para o tamanho correto da CPU, número de núcleos e memória para os computadores hospedando os serviços web.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="0c6bf-132">O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0c6bf-133">Todos os clientes móveis atuais do Skype for Business já usam a API da Web de comunicação unificada (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0c6bf-134">Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="0c6bf-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c6bf-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="0c6bf-135">See also</span></span>

[<span data-ttu-id="0c6bf-136">Monitorar os limites de capacidade de memória do servidor no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0c6bf-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
