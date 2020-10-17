---
title: 'Lync Server 2013: monitorando a mobilidade para desempenho'
description: 'Lync Server 2013: monitorando a mobilidade para desempenho.'
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
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562897"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a><span data-ttu-id="47a4e-103">Monitorando a mobilidade para desempenho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a4e-103">Monitoring mobility for performance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47a4e-104">_**Última modificação do tópico:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="47a4e-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="47a4e-105">O Lync Server Mobility Service (MCX) e a API da Web de comunicações unificadas (UCWA) aumentam a carga em servidores front-end e pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="47a4e-105">The Lync Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="47a4e-106">Dispositivos móveis que mantêm uma conexão com o servidor, mesmo quando o aplicativo móvel é minimizado, como dispositivos Android e Nokia que executam o Lync 2010 Mobile, bem como dispositivos Android e Apple que executam o Lync 2013 Mobile, impõem uma carga maior do que os dispositivos que encerram a conexão com o servidor quando o aplicativo móvel é minimizado.</span><span class="sxs-lookup"><span data-stu-id="47a4e-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="47a4e-107">À medida que o uso de mobilidade aumenta, você deve monitorar o desempenho da mobilidade para determinar quando precisa aumentar sua capacidade.</span><span class="sxs-lookup"><span data-stu-id="47a4e-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

<span data-ttu-id="47a4e-108">Vários limites influenciam o desempenho da mobilidade:</span><span class="sxs-lookup"><span data-stu-id="47a4e-108">Several limits influence mobility performance:</span></span>

  - <span data-ttu-id="47a4e-109">Memória disponível</span><span class="sxs-lookup"><span data-stu-id="47a4e-109">Available memory</span></span>

  - <span data-ttu-id="47a4e-110">Limite da fila de solicitações</span><span class="sxs-lookup"><span data-stu-id="47a4e-110">Request queue limit</span></span>

  - <span data-ttu-id="47a4e-111">Conexões concorrentes</span><span class="sxs-lookup"><span data-stu-id="47a4e-111">Concurrent connections</span></span>

  - <span data-ttu-id="47a4e-112">Tamanho da fila do IIS</span><span class="sxs-lookup"><span data-stu-id="47a4e-112">IIS queue length</span></span>

<span data-ttu-id="47a4e-113">Outros limites em servidores que podem influenciar o desempenho de mobilidade são um máximo de doze entradas, autenticações, renovações de sessão e encerramentos simultâneos.</span><span class="sxs-lookup"><span data-stu-id="47a4e-113">Other limits on servers that can influence mobility performance are a maximum of twelve concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="47a4e-114">Esses máximos não precisam ser modificados para a maioria das implantações.</span><span class="sxs-lookup"><span data-stu-id="47a4e-114">These maximums do not need to be modified for most deployments.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47a4e-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="47a4e-115">In This Section</span></span>

  - [<span data-ttu-id="47a4e-116">Monitoramento de limites de capacidade de memória do servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a4e-116">Monitoring for server memory capacity limits in Lync Server 2013</span></span>](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [<span data-ttu-id="47a4e-117">Monitorando o serviço de mobilidade e o uso do UCWA no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a4e-117">Monitoring Mobility Service and UCWA usage in Lync Server 2013</span></span>](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [<span data-ttu-id="47a4e-118">Configurando o serviço de mobilidade para alto desempenho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a4e-118">Configuring Mobility Service for high performance in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [<span data-ttu-id="47a4e-119">Monitorar arquivos de log de rastreamento de solicitação IIS no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a4e-119">Monitoring IIS request tracing log files in Lync Server 2013</span></span>](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [<span data-ttu-id="47a4e-120">Contadores de desempenho de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47a4e-120">Mobility performance counters in Lync Server 2013</span></span>](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

