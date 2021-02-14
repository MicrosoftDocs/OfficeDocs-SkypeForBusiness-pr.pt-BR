---
title: Monitorar o uso do Serviço de Mobilidade e do UCWA no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 'Resumo: Gerencie o Serviço de Mobilidade (Mcx) e a Unified Communications Web API (UCWA) no Skype for Business Server.'
ms.openlocfilehash: 76bcf8727d3abbb417595f033ce9a59ec00a39ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814241"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a><span data-ttu-id="c4eb0-103">Monitorar o uso do Serviço de Mobilidade e do UCWA no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c4eb0-103">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>
 
<span data-ttu-id="c4eb0-104">**Resumo:** Gerencie o Mobility Service (Mcx) e a Unified Communications Web API (UCWA) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-104">**Summary:** Manage the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="c4eb0-105">O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-105">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c4eb0-106">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-106">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c4eb0-107">Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-107">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="c4eb0-108">Você deve monitorar continuamente a CPU e a memória usada pelo Serviço de Mobilidade do Skype for Business Server (Mcx) e pela UNIFIED Communications Web API (UCWA).</span><span class="sxs-lookup"><span data-stu-id="c4eb0-108">On an ongoing basis, you should monitor the CPU and memory that is used by the Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="c4eb0-109">Para monitorar o uso, você pode usar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c4eb0-109">To monitor usage, you can use the following:</span></span>
  
 <span data-ttu-id="c4eb0-110">**Para Unified Communications Web API (UCWA):**</span><span class="sxs-lookup"><span data-stu-id="c4eb0-110">**For Unified Communications Web API (UCWA):**</span></span>
  
- <span data-ttu-id="c4eb0-111">O processo de trabalho do **LyncUcwa** no Gerenciador do Serviços de Informações da Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="c4eb0-111">The **LyncUcwa** worker process in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="c4eb0-112">No painel **Processos de** Trabalho, veja a % **da CPU** e as colunas **Bytes Particulares (KB)** (memória).</span><span class="sxs-lookup"><span data-stu-id="c4eb0-112">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="c4eb0-113">Os **contadores de** desempenho **da** CPU e do processador.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-113">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="c4eb0-114">Para a maioria das implantações, o uso da CPU do UCWA deve estar abaixo de 15% em média.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-114">For most deployments, UCWA CPU usage should be below 15 percent on average.</span></span> <span data-ttu-id="c4eb0-115">O uso de memória deve estar dentro dos limites descritos no Monitor para limites de capacidade de memória do [servidor no Skype for Business Server.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="c4eb0-115">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="c4eb0-116">Além dos contadores de uso da CPU e da memória, você pode usar os seguintes contadores de desempenho para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="c4eb0-116">In addition to CPU and memory usage counters, you can use the following performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="c4eb0-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, que indica o número de solicitações web pendentes no servidor.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-117">**LS:WEB - Throttling and Authentication\WEB - Total Requests in Processing**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="c4eb0-118">Quando esse contador atingir 10.000, as solicitações subsequentes falharão, com a mensagem de erro "503 - Serviço Indisponível".</span><span class="sxs-lookup"><span data-stu-id="c4eb0-118">When this counter reaches 10,000, subsequent requests will fail, with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="c4eb0-119">**ASP.NET\Solicitações na Fila** (sempre deve ser zero).</span><span class="sxs-lookup"><span data-stu-id="c4eb0-119">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c4eb0-120">Se você atender ou exceder esses valores, revisite e re compute seu planejamento de capacidade para o reavaliamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-120">If you meet or exceed these values, you should revisit and re-compute your capacity planning for the correct sizing of CPU, number of cores and memory for the computers hosting the web services.</span></span> 
  
 <span data-ttu-id="c4eb0-121">**Para o Mobility Service (Mcx):**</span><span class="sxs-lookup"><span data-stu-id="c4eb0-121">**For the Mobility Service (Mcx):**</span></span>
  
- <span data-ttu-id="c4eb0-122">Os **processos de trabalho CSIntMcxAppPool** e **CSExtMcxAppPool** no Gerenciador do IIS (Serviços de Informações da Internet).</span><span class="sxs-lookup"><span data-stu-id="c4eb0-122">The **CSIntMcxAppPool** and **CSExtMcxAppPool** worker processes in Internet Information Services (IIS) Manager.</span></span> <span data-ttu-id="c4eb0-123">No painel **Processos de** Trabalho, veja a % **da CPU** e as colunas **Bytes Particulares (KB)** (memória).</span><span class="sxs-lookup"><span data-stu-id="c4eb0-123">In the **Worker Processes** pane, look at the **CPU %** and **Private Bytes (KB)** (memory) columns.</span></span>
    
- <span data-ttu-id="c4eb0-124">Os **contadores de** desempenho **da** CPU e do processador.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-124">The **CPU** and **Processor** performance counters.</span></span>
    
<span data-ttu-id="c4eb0-125">Para a maioria das implantações, o uso da CPU do Mobility Service deve estar abaixo de 15%, em média.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-125">For most deployments, Mobility Service CPU usage should be below 15 percent, on average.</span></span> <span data-ttu-id="c4eb0-126">O uso de memória deve estar dentro dos limites descritos no Monitor para limites de capacidade de memória do [servidor no Skype for Business Server.](server-memory-capacity-limits.md)</span><span class="sxs-lookup"><span data-stu-id="c4eb0-126">Memory usage should fall within the limits described in [Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md).</span></span>
  
<span data-ttu-id="c4eb0-127">Além dos contadores de uso da CPU e da memória, você pode usar os seguintes contadores ASP.NET de desempenho para ajudar a determinar quando um servidor está sobrecarregado com solicitações:</span><span class="sxs-lookup"><span data-stu-id="c4eb0-127">In addition to CPU and memory usage counters, you can use the following ASP.NET performance counters to help determine when a server is overloaded with requests:</span></span>
  
- <span data-ttu-id="c4eb0-128">**ASP.NET v2.0.50727\Solicitações** Atuais , que indica o número de solicitações da Web pendentes no servidor.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-128">**ASP.NET v2.0.50727\Requests Current**, which indicates the number of pending web requests on the server.</span></span> <span data-ttu-id="c4eb0-129">Quando esse contador atingir 5.000, as solicitações subsequentes falharão com a mensagem de erro "503 - Serviço Indisponível".</span><span class="sxs-lookup"><span data-stu-id="c4eb0-129">When this counter reaches 5,000, subsequent requests will fail with the error message, "503 - Service Unavailable."</span></span>
    
- <span data-ttu-id="c4eb0-130">**ASP.NET\Solicitações na Fila** (sempre deve ser zero).</span><span class="sxs-lookup"><span data-stu-id="c4eb0-130">**ASP.NET\Requests Queued** (should always be zero).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c4eb0-131">Se você atender ou exceder esses valores, revisite e recompute seu planejamento de capacidade para o reavaliamento correto da CPU, número de núcleos e memória para os computadores que hospedam os serviços Web.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-131">If you meet or exceed these values, you should revisit and recompute your capacity planning for the correct sizing of CPU, number of cores, and memory for the computers hosting the web services.</span></span> 

> [!NOTE]
> <span data-ttu-id="c4eb0-132">O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-132">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c4eb0-133">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-133">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c4eb0-134">Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-134">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4eb0-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="c4eb0-135">See also</span></span>

[<span data-ttu-id="c4eb0-136">Monitorar os limites de capacidade de memória do servidor no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c4eb0-136">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
