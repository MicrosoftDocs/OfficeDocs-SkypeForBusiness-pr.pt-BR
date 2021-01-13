---
title: Configurar o Serviço de Mobilidade para alto desempenho no Skype for Business Server
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumo: saiba mais sobre o Serviço de Mobilidade no Skype for Business Server.'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817031"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="6f5d3-103">Configurar o Serviço de Mobilidade para alto desempenho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6f5d3-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="6f5d3-104">**Resumo:** Saiba mais sobre o Serviço de Mobilidade no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6f5d3-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6f5d3-105">Este tópico se aplica somente ao Serviço de Mobilidade do Skype for Business Server (Mcx) e não se aplica à Unified Communications Web API (UCWA), conforme fornecido nas Atualizações Cumulativas do Lync Server 2013: fevereiro de 2013.</span><span class="sxs-lookup"><span data-stu-id="6f5d3-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="6f5d3-106">Quando você instala o Mobility Service (Mcx) no Internet Information Services (IIS) 7.5, o instalador do Mobility Service define algumas configurações de desempenho no Servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="6f5d3-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="6f5d3-107">Recomendamos o uso do IIS 7.5 para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="6f5d3-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="6f5d3-108">As configurações afetam o número máximo de solicitações de usuário simultâneas e o número máximo de segmentos permitidos para o Serviço de Mobilidade.</span><span class="sxs-lookup"><span data-stu-id="6f5d3-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="6f5d3-109">Aqui estão as configurações de desempenho:</span><span class="sxs-lookup"><span data-stu-id="6f5d3-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="6f5d3-110">Configurações para Mcx no IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="6f5d3-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="6f5d3-111">**maxConcurrentThreadsPerCPU** está definido como zero (0).</span><span class="sxs-lookup"><span data-stu-id="6f5d3-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="6f5d3-112">**maxConcurrentRequestsPerCPU** está definido como zero (0).</span><span class="sxs-lookup"><span data-stu-id="6f5d3-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="6f5d3-113">O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="6f5d3-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="6f5d3-114">O limite de fila HTTP.sys está definido como 1.000 (por padrão).</span><span class="sxs-lookup"><span data-stu-id="6f5d3-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

