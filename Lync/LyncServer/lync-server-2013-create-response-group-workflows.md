---
title: 'Lync Server 2013: Criar fluxos de trabalho de Grupo de Resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba7d989d1733645c7055fb64d6b790212e15e16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="064c0-102">Criar fluxos de trabalho de Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="064c0-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="064c0-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="064c0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="064c0-104">Um fluxo de trabalho define o comportamento de uma chamada desde a hora que o telefone toca até a hora que alguém atende essa chamada.</span><span class="sxs-lookup"><span data-stu-id="064c0-104">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="064c0-105">O fluxo de trabalho especifica a fila a ser usada para manter a chamada e especifica o método de roteamento a ser usado para grupos de busca ou perguntas e respostas a serem usadas para grupos de resposta interativos.</span><span class="sxs-lookup"><span data-stu-id="064c0-105">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups.</span></span> <span data-ttu-id="064c0-106">Um fluxo de trabalho também define configurações, como a mensagem de boas-vindas, a música de espera, o horário comercial e os feriados.</span><span class="sxs-lookup"><span data-stu-id="064c0-106">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="064c0-107">Use a ferramenta de configuração de grupo de resposta para criar fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="064c0-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="064c0-108">Você pode acessar a ferramenta de configuração de grupo de resposta na página grupo de resposta do painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="064c0-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="064c0-109">Você deve criar grupos de agente e filas antes de criar um fluxo de trabalho que os utiliza.</span><span class="sxs-lookup"><span data-stu-id="064c0-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="064c0-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="064c0-110">In This Section</span></span>

  - [<span data-ttu-id="064c0-111">Criar ou modificar um fluxo de trabalho de grupo coletivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="064c0-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="064c0-112">Projetar fluxos de chamada de resposta interativa de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="064c0-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="064c0-113">Criar ou modificar um fluxo de trabalho interativo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="064c0-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="064c0-114">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="064c0-114">Related Sections</span></span>

  - [<span data-ttu-id="064c0-115">Criar grupos de agente do Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="064c0-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="064c0-116">Criar filas do Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="064c0-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

