---
title: 'Lync Server 2013: criar fluxos de trabalho de grupo de resposta'
description: 'Lync Server 2013: criar fluxos de trabalho de grupo de resposta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7082295eeca45c4dac76d68ef54b5c32fafb25d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548647"
---
# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="2be2c-103">Criar fluxos de trabalho de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be2c-103">Create Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2be2c-104">_**Última modificação do tópico:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2be2c-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2be2c-p101">Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada. O fluxo de trabalho especifica a fila que deve ser usada para colocar a chamada em espera, o método de roteamento a ser usado para grupos de busca e as perguntas e respostas a serem usadas com grupos de resposta interativa. Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.</span><span class="sxs-lookup"><span data-stu-id="2be2c-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="2be2c-108">Use a ferramenta de configuração de grupo de resposta para criar fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2be2c-108">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="2be2c-109">Você pode acessar a ferramenta de configuração do grupo de resposta na página grupo de resposta do painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2be2c-109">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2be2c-110">É necessário criar grupos de agentes e filas antes de criar um fluxo de trabalho que os use.</span><span class="sxs-lookup"><span data-stu-id="2be2c-110">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2be2c-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2be2c-111">In This Section</span></span>

  - [<span data-ttu-id="2be2c-112">Criar ou modificar um fluxo de trabalho de grupo de busca no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be2c-112">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="2be2c-113">Projetar fluxos de chamada de resposta interativa de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be2c-113">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="2be2c-114">Criar ou modificar um fluxo de trabalho interativo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be2c-114">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="2be2c-115">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="2be2c-115">Related Sections</span></span>

  - [<span data-ttu-id="2be2c-116">Criar grupos de agente de grupo de resposta Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be2c-116">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="2be2c-117">Criar filas de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be2c-117">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

