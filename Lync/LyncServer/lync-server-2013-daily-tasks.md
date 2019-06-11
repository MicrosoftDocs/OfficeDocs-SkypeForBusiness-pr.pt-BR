---
title: 'Lync Server 2013: Tarefas diárias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4375b11511d3b2c88222ea36575c18ca6fcc7dfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="b1899-102">Tarefas diárias no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1899-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1899-103">_**Tópico da última modificação:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="b1899-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="b1899-104">Para ajudar a garantir a disponibilidade e a confiabilidade da implantação do Lync Server 2013, você deve fazer parte do monitor de rotina diária e dos elementos de teste que são muito importantes para o funcionamento do sistema, que inclui a plataforma física, o sistema operacional e todos os serviços importantes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1899-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="b1899-105">A manutenção preventiva e o monitoramento proativo ajudarão você a identificar possíveis erros e problemas que podem afetar negativamente a implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b1899-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="b1899-106">Monitorar a implantação do Lync Server 2013 envolve a verificação de problemas com conexões, serviços, recursos do servidor e recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="b1899-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="b1899-107">Os sistemas operacionais Windows Server, juntos com o System Center Operations Manager e o Lync Server, dão a você muitas ferramentas e serviços de monitoramento para ajudar a garantir que a organização do Lync Server esteja funcionando tranqüilamente.</span><span class="sxs-lookup"><span data-stu-id="b1899-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="b1899-108">Quando essas tecnologias forem implementadas juntas, os administradores poderão receber alertas quando ou antes de os problemas ocorrerem.</span><span class="sxs-lookup"><span data-stu-id="b1899-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="b1899-109">As principais vantagens do monitoramento diário são:</span><span class="sxs-lookup"><span data-stu-id="b1899-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="b1899-110">Atender aos requisitos de desempenho e disponibilidade dos SLAs definidos.</span><span class="sxs-lookup"><span data-stu-id="b1899-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="b1899-111">Concluir com êxito tarefas administrativas específicas, como operações diárias de backup, e verificar a integridade do servidor.</span><span class="sxs-lookup"><span data-stu-id="b1899-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="b1899-112">Detectar e resolver problemas, como afunilamentos no desempenho do servidor, ou a necessidade de recursos adicionais antes que eles afetem a produtividade.</span><span class="sxs-lookup"><span data-stu-id="b1899-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="b1899-113">As tarefas diárias de manutenção ajudam a equipe administrativa a definir ou estabelecer critérios ou linha de base para operações normais dos sistemas dentro da organização e a detectar qualquer atividade anormal.</span><span class="sxs-lookup"><span data-stu-id="b1899-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="b1899-114">É importante implementar essas tarefas de manutenção diárias para que a equipe administrativa possa capturar e manter dados sobre a infraestrutura do Lync Server 2013, como níveis de uso, possíveis afunilamentos de desempenho e alterações administrativas.</span><span class="sxs-lookup"><span data-stu-id="b1899-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="b1899-115">Para ajudar a organizar o desempenho das tarefas diárias, use a [Lista de verificação de tarefas diárias](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="b1899-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b1899-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="b1899-116">See Also</span></span>


[<span data-ttu-id="b1899-117">Lista de verificação de tarefas diárias</span><span class="sxs-lookup"><span data-stu-id="b1899-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

