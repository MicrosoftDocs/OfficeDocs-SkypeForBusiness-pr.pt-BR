---
title: 'Lync Server 2013: como gerenciar grupos de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c0d8ac0fbfa8464fd0cd078fc90784eb9fdd3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="052d0-102">Gerenciamento de grupos de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="052d0-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="052d0-103">_**Tópico da última modificação:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="052d0-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="052d0-104">Grupos de resposta são um recurso de gerenciamento de chamadas que permite que você enfileirar chamadas feitas a uma área específica, como um suporte técnico e, em seguida, encaminhar as chamadas para um grupo designado de pessoas, chamado *agentes*.</span><span class="sxs-lookup"><span data-stu-id="052d0-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="052d0-105">Para gerenciar grupos de resposta, você configura grupos de agente, filas e fluxos de trabalho, que definem o que acontece com uma chamada no momento em que ele é colocado até que um agente responda a ele.</span><span class="sxs-lookup"><span data-stu-id="052d0-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="052d0-106">Se você tiver mais de 300 fluxos de trabalho em um único pool em sua implantação de grupo de resposta, é melhor usar cmdlets do Shell de gerenciamento do Lync Server para criar os fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="052d0-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="052d0-107">Se você usar a ferramenta de configuração de grupo de resposta para criar fluxos de trabalho para um pool que tenha mais de 300 fluxos de trabalho, a página da Web levará muito tempo para ser carregada.</span><span class="sxs-lookup"><span data-stu-id="052d0-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="052d0-108">O número de agentes que estão indiretamente associados a fluxos de trabalho por meio das filas também tem um efeito proporcional na carga da página.</span><span class="sxs-lookup"><span data-stu-id="052d0-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="052d0-109">Os tópicos desta seção fornecem procedimentos passo a passo para tarefas que você pode executar para personalizar e manter o aplicativo de grupo de resposta em sua implantação</span><span class="sxs-lookup"><span data-stu-id="052d0-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="052d0-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="052d0-110">In This Section</span></span>

  - [<span data-ttu-id="052d0-111">Gerenciamento de grupos de agente de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="052d0-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="052d0-112">Gerenciamento de filas de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="052d0-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="052d0-113">Gerenciamento de fluxos de trabalho de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="052d0-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="052d0-114">Gerenciando configurações de grupo de resposta no nível do aplicativo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="052d0-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="052d0-115">Movendo grupos de resposta para um novo pool no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="052d0-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="052d0-116">Gerenciando grupos de resposta no Lync Server 2013 durante um desastre</span><span class="sxs-lookup"><span data-stu-id="052d0-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

