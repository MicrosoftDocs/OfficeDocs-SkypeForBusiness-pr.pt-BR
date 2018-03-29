---
title: Monitorar desempenho de mobilidade no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 'Resumo: Saiba sobre o serviço de mobilidade (Mcx) e a API (UCWA) da Web das comunicações unificadas em Skype para Business Server 2015.'
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="96bb0-103">Monitorar desempenho de mobilidade no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96bb0-103">Monitor mobility for performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="96bb0-104">**Resumo:** Saiba mais sobre o serviço de mobilidade (Mcx) e a API (UCWA) da Web das comunicações unificadas no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96bb0-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="96bb0-105">O Skype para serviço de mobilidade do Business Server (Mcx) e a API de Web de comunicações unificadas (UCWA) aumentar a carga nos servidores Front-End, pools de Front-End.</span><span class="sxs-lookup"><span data-stu-id="96bb0-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="96bb0-106">Dispositivos móveis que mantêm uma conexão ao servidor, mesmo quando o aplicativo móvel estiver minimizado, como Android e Nokia dispositivos que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple executando o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que encerrar sua conexão ao servidor quando o aplicativo móvel estiver minimizado.</span><span class="sxs-lookup"><span data-stu-id="96bb0-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="96bb0-107">Conforme seu uso de mobilidade cresce, é necessário monitorar o desempenho da mobilidade para determinar quando é necessário aumentar a capacidade.</span><span class="sxs-lookup"><span data-stu-id="96bb0-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>
  
<span data-ttu-id="96bb0-108">Vários limites influenciam o desempenho da mobilidade:</span><span class="sxs-lookup"><span data-stu-id="96bb0-108">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="96bb0-109">Memória disponível</span><span class="sxs-lookup"><span data-stu-id="96bb0-109">Available memory</span></span>
    
- <span data-ttu-id="96bb0-110">Limite da fila de solicitações</span><span class="sxs-lookup"><span data-stu-id="96bb0-110">Request queue limit</span></span>
    
- <span data-ttu-id="96bb0-111">Conexões concorrentes</span><span class="sxs-lookup"><span data-stu-id="96bb0-111">Concurrent connections</span></span>
    
- <span data-ttu-id="96bb0-112">Tamanho da fila do IIS</span><span class="sxs-lookup"><span data-stu-id="96bb0-112">IIS queue length</span></span>
    
<span data-ttu-id="96bb0-p102">Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de doze conexões simultâneas, autenticações e renovações e encerramentos de sessão. Esses máximos não precisam ser modificados para a maioria das implantações.</span><span class="sxs-lookup"><span data-stu-id="96bb0-p102">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="96bb0-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="96bb0-115">In this section</span></span>

- [<span data-ttu-id="96bb0-116">Monitorar a existência de limites de capacidade de memória do servidor no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96bb0-116">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="96bb0-117">Monitorar o uso do serviço de mobilidade e UCWA no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96bb0-117">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="96bb0-118">Configurar o serviço de mobilidade para alto desempenho em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96bb0-118">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>](configure-service.md)
    
- [<span data-ttu-id="96bb0-119">Monitoramento do IIS solicitar os arquivos de log de rastreamento em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96bb0-119">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="96bb0-120">Contadores de desempenho de mobilidade no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96bb0-120">Mobility performance counters in Skype for Business Server 2015</span></span>](performance-counters.md)
    

