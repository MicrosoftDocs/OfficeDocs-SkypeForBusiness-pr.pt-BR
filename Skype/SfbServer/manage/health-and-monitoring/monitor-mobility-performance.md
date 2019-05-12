---
title: Monitorar a mobilidade de desempenho no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumo: Saiba mais sobre o serviço de mobilidade (Mcx) e a Web de comunicação unificada API (UCWA) no Skype para Business Server.'
ms.openlocfilehash: e2da6f073dc14268442e3c49273189b002eaadc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902830"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="894c8-103">Monitorar a mobilidade de desempenho no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="894c8-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="894c8-104">**Resumo:** Saiba mais sobre o serviço de mobilidade (Mcx) e de comunicação unificada Web API (UCWA) no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="894c8-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="894c8-105">O Skype para serviço de mobilidade do Business Server (Mcx) e a API de Web de comunicações unificadas (UCWA) aumentar a carga nos servidores Front-End, pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="894c8-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="894c8-106">Dispositivos móveis que mantêm uma conexão ao servidor, mesmo quando o aplicativo móvel estiver minimizado, como Android e Nokia dispositivos que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple executando o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que encerrar sua conexão ao servidor quando o aplicativo móvel estiver minimizado.</span><span class="sxs-lookup"><span data-stu-id="894c8-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="894c8-107">Conforme seu uso de mobilidade cresce, é necessário monitorar o desempenho da mobilidade para determinar quando é necessário aumentar a capacidade.</span><span class="sxs-lookup"><span data-stu-id="894c8-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="894c8-108">Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="894c8-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="894c8-109">Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="894c8-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="894c8-110">Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="894c8-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="894c8-111">Vários limites influenciam o desempenho da mobilidade:</span><span class="sxs-lookup"><span data-stu-id="894c8-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="894c8-112">Memória disponível</span><span class="sxs-lookup"><span data-stu-id="894c8-112">Available memory</span></span>
    
- <span data-ttu-id="894c8-113">Limite da fila de solicitações</span><span class="sxs-lookup"><span data-stu-id="894c8-113">Request queue limit</span></span>
    
- <span data-ttu-id="894c8-114">Conexões concorrentes</span><span class="sxs-lookup"><span data-stu-id="894c8-114">Concurrent connections</span></span>
    
- <span data-ttu-id="894c8-115">Tamanho da fila do IIS</span><span class="sxs-lookup"><span data-stu-id="894c8-115">IIS queue length</span></span>
    
<span data-ttu-id="894c8-p103">Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de doze conexões simultâneas, autenticações e renovações e encerramentos de sessão. Esses máximos não precisam ser modificados para a maioria das implantações.</span><span class="sxs-lookup"><span data-stu-id="894c8-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="894c8-118">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="894c8-118">In this section</span></span>

- [<span data-ttu-id="894c8-119">Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="894c8-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="894c8-120">Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="894c8-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="894c8-121">Configurar o serviço de mobilidade para alto desempenho em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="894c8-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="894c8-122">Monitoramento de arquivos de log do Skype de rastreamento para o Business Server de solicitação do IIS</span><span class="sxs-lookup"><span data-stu-id="894c8-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="894c8-123">Contadores de desempenho de mobilidade no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="894c8-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

