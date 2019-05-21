---
title: Configurar o serviço de mobilidade para alto desempenho no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 'Resumo: Saiba mais sobre o serviço de mobilidade no Skype for Business Server.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305840"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="fac4c-103">Configurar o serviço de mobilidade para alto desempenho no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fac4c-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="fac4c-104">**Resumo:** Saiba mais sobre o serviço de mobilidade no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fac4c-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fac4c-105">Este tópico se aplica somente ao serviço Skype for Business Server Mobility (MCX) e não se aplica à API da Web de comunicação unificada (UCWA), conforme entregue nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="fac4c-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="fac4c-106">Quando você instala o serviço de mobilidade (MCX) em serviços de informações da Internet (IIS) 7,5, o instalador do serviço de mobilidade configura algumas configurações de desempenho no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fac4c-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="fac4c-107">Recomendamos usar IIS 7.5 para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="fac4c-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="fac4c-108">As configurações afetam o número máximo de solicitações concomitantes de usuários e o número máximo de threads permitidos para o Mobility Service.</span><span class="sxs-lookup"><span data-stu-id="fac4c-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="fac4c-109">Aqui estão as configurações de desempenho:</span><span class="sxs-lookup"><span data-stu-id="fac4c-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="fac4c-110">Configurações para Mcx no IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="fac4c-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="fac4c-111">**maxConcurrentThreadsPerCPU** está definido como zero (0).</span><span class="sxs-lookup"><span data-stu-id="fac4c-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="fac4c-112">**maxConcurrentRequestsPerCPU** está definido como zero (0).</span><span class="sxs-lookup"><span data-stu-id="fac4c-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="fac4c-113">O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="fac4c-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="fac4c-114">O limite de fila HTTP.sys está definido como 1.000 (por padrão).</span><span class="sxs-lookup"><span data-stu-id="fac4c-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

