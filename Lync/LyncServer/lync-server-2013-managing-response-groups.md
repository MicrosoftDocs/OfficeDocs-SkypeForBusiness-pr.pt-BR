---
title: 'Lync Server 2013: Gerenciando grupos de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00736a94cc383a362a3f952519acc603c5beefab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507188"
---
# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="87120-102">Gerenciando grupos de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87120-102">Managing response groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87120-103">_**Última modificação do tópico:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="87120-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="87120-104">Grupos de resposta são um recurso de gerenciamento de chamadas que permite enfileirar as chamadas feitas para uma área específica, como Suporte Técnico, e depois encaminhá-las para um grupo designado de pessoas, conhecidas como *agentes*.</span><span class="sxs-lookup"><span data-stu-id="87120-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="87120-105">Para gerenciar grupos de resposta, configure os grupos de agentes, as filas e os fluxos de trabalho, que definem o que acontece com uma chamada do momento em que ela é efetuada até o agente atendê-la.</span><span class="sxs-lookup"><span data-stu-id="87120-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="87120-106">Se você tiver mais de 300 fluxos de trabalho em um único pool em sua implantação de grupo de resposta, é melhor usar os cmdlets do Shell de gerenciamento do Lync Server para criar os fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="87120-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="87120-107">Se você usar a Ferramenta de Configuração do Grupo de Respostas para criar fluxos de trabalho para um pool que possui mais de 300 fluxos de trabalho, a página da Web levará mais tempo para ser carregada.</span><span class="sxs-lookup"><span data-stu-id="87120-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="87120-108">O número de agentes que estão indiretamente associados aos fluxos de trabalho por meio das filas também tem um efeito proporcional no carregamento da página.</span><span class="sxs-lookup"><span data-stu-id="87120-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="87120-109">Os tópicos desta seção fornecem procedimentos passo a passo para tarefas que você pode executar para personalizar e manter o aplicativo de grupo de resposta em sua implantação</span><span class="sxs-lookup"><span data-stu-id="87120-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="87120-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="87120-110">In This Section</span></span>

  - [<span data-ttu-id="87120-111">Gerenciar grupos de agente de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87120-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="87120-112">Gerenciando filas de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87120-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="87120-113">Gerenciando fluxos de trabalho de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87120-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="87120-114">Gerenciando as configurações do grupo de resposta no nível do aplicativo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87120-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="87120-115">Movendo grupos de resposta para um novo pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="87120-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="87120-116">Gerenciando grupos de resposta no Lync Server 2013 durante um desastre</span><span class="sxs-lookup"><span data-stu-id="87120-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

