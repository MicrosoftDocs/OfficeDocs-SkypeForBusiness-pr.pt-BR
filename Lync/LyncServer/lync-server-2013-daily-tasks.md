---
title: 'Lync Server 2013: tarefas diárias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59204fab5a1df067668f73ca4752033b64326a2e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="dc8f2-102">Tarefas diárias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc8f2-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc8f2-103">_**Última modificação do tópico:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="dc8f2-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="dc8f2-104">Para ajudar a garantir a disponibilidade e a confiabilidade da implantação do Lync Server 2013, você deve fazer parte do monitoramento de rotina diária e dos elementos de teste que são muito importantes para o funcionamento do sistema, que inclui a plataforma física, o sistema operacional e todos os serviços importantes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="dc8f2-105">A manutenção preventiva e o monitoramento proativo ajudarão você a identificar possíveis erros e problemas que podem afetar adversamente a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="dc8f2-106">O monitoramento da implantação do Lync Server 2013 envolve a verificação de problemas com conexões, serviços, recursos do servidor e recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="dc8f2-107">Os sistemas operacionais Windows Server, juntamente com o System Center Operations Manager e o Lync Server, oferecem muitas ferramentas e serviços de monitoramento para ajudar a garantir que a organização do Lync Server esteja funcionando sem problemas.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="dc8f2-108">Quando essas tecnologias forem implementadas juntas, os administradores poderão receber alertas quando ou antes de ocorrerem problemas.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="dc8f2-109">As principais vantagens do monitoramento diário são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="dc8f2-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="dc8f2-110">Atender aos requisitos de desempenho e disponibilidade dos SLAs definidos.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="dc8f2-111">Conclusão bem-sucedida de tarefas administrativas específicas, como operações de backup diárias, e verificação da integridade do servidor.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="dc8f2-112">Detectar e resolver problemas, como afunilamentos no desempenho do servidor, ou necessidade de recursos adicionais antes que eles afetem a produtividade.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="dc8f2-113">Tarefas diárias de manutenção ajudam a equipe administrativa a definir ou estabelecer um critério ou linha de base para operações normais de sistemas dentro da organização e para detectar qualquer atividade anormal.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="dc8f2-114">É importante implementar essas tarefas diárias de manutenção para que a equipe administrativa possa capturar e manter dados sobre a infraestrutura do Lync Server 2013, como níveis de uso, possíveis afunilamentos de desempenho e alterações administrativas.</span><span class="sxs-lookup"><span data-stu-id="dc8f2-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="dc8f2-115">Para ajudar a organizar o desempenho de tarefas diárias, use a [lista de verificação de tarefas diárias](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="dc8f2-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dc8f2-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="dc8f2-116">See Also</span></span>


[<span data-ttu-id="dc8f2-117">Lista de verificação de tarefas diárias</span><span class="sxs-lookup"><span data-stu-id="dc8f2-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

