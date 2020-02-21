---
title: 'Lync Server 2013: Configurando o serviço de mobilidade para alto desempenho'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f35d45c1b437c04e96885f098df6026650d61768
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a><span data-ttu-id="89a08-102">Configurando o serviço de mobilidade para alto desempenho no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89a08-102">Configuring Mobility Service for high performance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89a08-103">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="89a08-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="89a08-104">Este tópico se aplica apenas ao Lync Server 2013 Mobility Service (MCX) e não se aplica à API Web de comunicações unificadas (UCWA), conforme fornecido nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="89a08-104">This topic applies only to the Lync Server 2013 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

<span data-ttu-id="89a08-105">Ao instalar o serviço de mobilidade (MCX) nos serviços de informações da Internet (IIS) 7,5, o instalador do serviço de mobilidade configura algumas configurações de desempenho no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="89a08-105">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="89a08-106">Recomendamos o uso do IIS 7.5 para mobilidade.</span><span class="sxs-lookup"><span data-stu-id="89a08-106">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="89a08-107">As configurações afetam o número máximo de solicitações de usuário simultâneas e o número máximo de segmentos permitidos para o Serviço de Mobilidade.</span><span class="sxs-lookup"><span data-stu-id="89a08-107">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>

<span data-ttu-id="89a08-108">Aqui estão as configurações de desempenho:</span><span class="sxs-lookup"><span data-stu-id="89a08-108">Here are the performance settings:</span></span>

<div>

## <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="89a08-109">Configurações para MCX no IIS 7,5</span><span class="sxs-lookup"><span data-stu-id="89a08-109">Settings for Mcx on IIS 7.5</span></span>

1.  <span data-ttu-id="89a08-110">**maxConcurrentThreadsPerCPU** está definido como zero (0).</span><span class="sxs-lookup"><span data-stu-id="89a08-110">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>

2.  <span data-ttu-id="89a08-111">**maxConcurrentRequestsPerCPU** está definido como zero (0).</span><span class="sxs-lookup"><span data-stu-id="89a08-111">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>

3.  <span data-ttu-id="89a08-112">O modelo de processo ASP.NET está definido como AutoConfig (somente para IIS 7.5).</span><span class="sxs-lookup"><span data-stu-id="89a08-112">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>

4.  <span data-ttu-id="89a08-113">O limite de fila HTTP.sys está definido como 1.000 (por padrão).</span><span class="sxs-lookup"><span data-stu-id="89a08-113">HTTP.sys queue limit is set to 1,000 (by default).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

