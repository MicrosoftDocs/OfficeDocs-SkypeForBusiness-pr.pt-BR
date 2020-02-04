---
title: 'Lync Server 2013: monitorando a mobilidade para desempenho'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="13ac2-102">Monitorando a mobilidade para o desempenho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ac2-102">Monitoring mobility for performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13ac2-103">_**Tópico da última modificação:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="13ac2-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="13ac2-104">O serviço de mobilidade do Lync Server (MCX) e a API da Web de comunicação unificada (UCWA) aumentam a carga em servidores front-end e em pools front-end.</span><span class="sxs-lookup"><span data-stu-id="13ac2-104">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="13ac2-105">Dispositivos móveis que mantêm uma conexão com o servidor, mesmo quando o aplicativo móvel é minimizado, como dispositivos Android e Nokia que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple que executam o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que Termine a conexão com o servidor quando o aplicativo móvel estiver minimizado.</span><span class="sxs-lookup"><span data-stu-id="13ac2-105">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="13ac2-106">Conforme seu uso de mobilidade cresce, é necessário monitorar o desempenho da mobilidade para determinar quando é necessário aumentar a capacidade.</span><span class="sxs-lookup"><span data-stu-id="13ac2-106">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="13ac2-107">Vários limites influenciam o desempenho da mobilidade:</span><span class="sxs-lookup"><span data-stu-id="13ac2-107">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="13ac2-108">Memória disponível</span><span class="sxs-lookup"><span data-stu-id="13ac2-108">Available memory</span></span>

  - <span data-ttu-id="13ac2-109">Limite da fila de solicitações</span><span class="sxs-lookup"><span data-stu-id="13ac2-109">Request queue limit</span></span>

  - <span data-ttu-id="13ac2-110">Conexões concorrentes</span><span class="sxs-lookup"><span data-stu-id="13ac2-110">Concurrent connections</span></span>

  - <span data-ttu-id="13ac2-111">Tamanho da fila do IIS</span><span class="sxs-lookup"><span data-stu-id="13ac2-111">IIS queue length</span></span>

<span data-ttu-id="13ac2-112">Outros limites em servidores que podem influenciar o desempenho da mobilidade são um máximo de doze entradas simultâneas, autenticações, renovações de sessão e resterminações.</span><span class="sxs-lookup"><span data-stu-id="13ac2-112">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="13ac2-113">Esses máximos não precisam ser modificados para a maioria das implantações.</span><span class="sxs-lookup"><span data-stu-id="13ac2-113">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13ac2-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="13ac2-114">In This Section</span></span>

  - [<span data-ttu-id="13ac2-115">Monitorar os limites de capacidade de memória do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ac2-115">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="13ac2-116">Monitorar o serviço de mobilidade e o uso do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ac2-116">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="13ac2-117">Configurando o serviço de mobilidade para alto desempenho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ac2-117">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="13ac2-118">Monitorar arquivos de log de rastreamento de solicitação do IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ac2-118">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="13ac2-119">Contadores de desempenho de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13ac2-119">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

