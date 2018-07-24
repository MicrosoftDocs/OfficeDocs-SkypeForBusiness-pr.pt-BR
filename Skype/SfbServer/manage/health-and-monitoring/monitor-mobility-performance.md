---
title: Monitorar a mobilidade de desempenho no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumo: Saiba mais sobre o serviço de mobilidade (Mcx) e a Web de comunicação unificada API (UCWA) no Skype para Business Server.'
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990634"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="8ccc5-103">Monitorar a mobilidade de desempenho no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8ccc5-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="8ccc5-104">**Resumo:** Saiba mais sobre o serviço de mobilidade (Mcx) e de comunicação unificada Web API (UCWA) no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="8ccc5-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="8ccc5-105">O Skype para serviço de mobilidade do Business Server (Mcx) e a API de Web de comunicações unificadas (UCWA) aumentar a carga nos servidores Front-End, pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="8ccc5-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="8ccc5-106">Dispositivos móveis que mantêm uma conexão ao servidor, mesmo quando o aplicativo móvel estiver minimizado, como Android e Nokia dispositivos que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple executando o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que encerrar sua conexão ao servidor quando o aplicativo móvel estiver minimizado.</span><span class="sxs-lookup"><span data-stu-id="8ccc5-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="8ccc5-107">Conforme seu uso de mobilidade cresce, é necessário monitorar o desempenho da mobilidade para determinar quando é necessário aumentar a capacidade.</span><span class="sxs-lookup"><span data-stu-id="8ccc5-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="8ccc5-108">Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8ccc5-108">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8ccc5-109">Os usuários precisarem de atualização para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="8ccc5-109">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="8ccc5-110">Vários limites influenciam o desempenho da mobilidade:</span><span class="sxs-lookup"><span data-stu-id="8ccc5-110">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="8ccc5-111">Memória disponível</span><span class="sxs-lookup"><span data-stu-id="8ccc5-111">Available memory</span></span>
    
- <span data-ttu-id="8ccc5-112">Limite da fila de solicitações</span><span class="sxs-lookup"><span data-stu-id="8ccc5-112">Request queue limit</span></span>
    
- <span data-ttu-id="8ccc5-113">Conexões concorrentes</span><span class="sxs-lookup"><span data-stu-id="8ccc5-113">Concurrent connections</span></span>
    
- <span data-ttu-id="8ccc5-114">Tamanho da fila do IIS</span><span class="sxs-lookup"><span data-stu-id="8ccc5-114">IIS queue length</span></span>
    
<span data-ttu-id="8ccc5-p103">Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de doze conexões simultâneas, autenticações e renovações e encerramentos de sessão. Esses máximos não precisam ser modificados para a maioria das implantações.</span><span class="sxs-lookup"><span data-stu-id="8ccc5-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8ccc5-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8ccc5-117">In this section</span></span>

- [<span data-ttu-id="8ccc5-118">Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8ccc5-118">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="8ccc5-119">Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8ccc5-119">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="8ccc5-120">Configurar o serviço de mobilidade para alto desempenho em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8ccc5-120">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="8ccc5-121">Monitoramento de arquivos de log do Skype de rastreamento para o Business Server de solicitação do IIS</span><span class="sxs-lookup"><span data-stu-id="8ccc5-121">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="8ccc5-122">Contadores de desempenho de mobilidade no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8ccc5-122">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

