---
title: 'Lync Server 2013: Criar grupos de agente do Grupo de Resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="80d5d-102">Criar grupos de agente do Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80d5d-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80d5d-103">_**Tópico da última modificação:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="80d5d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="80d5d-104">Ao criar um grupo de operadores, você seleciona os operadores atribuídos ao grupo e especifica configurações de grupo adicionais, como o método de roteamento e se um operador pode entrar e sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="80d5d-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="80d5d-105">Um agente que deve entrar e sair do grupo, que é diferente de entrar ou sair do Lync Server, é chamado de *agente formal*.</span><span class="sxs-lookup"><span data-stu-id="80d5d-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="80d5d-106">Os operadores formais precisam entrar no grupo para que possam receber as chamadas roteadas para o grupo.</span><span class="sxs-lookup"><span data-stu-id="80d5d-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="80d5d-107">Isso pode ser útil para os operadores que respondem às chamadas do grupo em tempo parcial.</span><span class="sxs-lookup"><span data-stu-id="80d5d-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="80d5d-108">Os agentes formais entram e saem de seus grupos clicando em um item de menu no Lync 2013 para abrir o navegador da Internet do Windows Internet Explorer e exibir um console de página da Web.</span><span class="sxs-lookup"><span data-stu-id="80d5d-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="80d5d-109">Um operador que não precisa entrar ou sair do grupo é denominado *operador informal*.</span><span class="sxs-lookup"><span data-stu-id="80d5d-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="80d5d-110">Agentes informais são automaticamente conectados ao grupo quando são conectados ao Lync Server, e não podem sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="80d5d-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="80d5d-111">Somente os usuários no local podem ser agentes.</span><span class="sxs-lookup"><span data-stu-id="80d5d-111">Only on-premises users can be agents.</span></span> <span data-ttu-id="80d5d-112">Se um agente for movido do local para o online, as chamadas em grupo de resposta não serão roteadas para esse agente.</span><span class="sxs-lookup"><span data-stu-id="80d5d-112">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="80d5d-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="80d5d-113">In This Section</span></span>

[<span data-ttu-id="80d5d-114">Criar ou modificar um grupo de agente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="80d5d-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

