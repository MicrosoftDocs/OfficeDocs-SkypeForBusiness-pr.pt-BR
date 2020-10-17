---
title: 'Lync Server 2013: Gerenciando grupos de agente de grupo de resposta'
description: 'Lync Server 2013: Gerenciando grupos de agente do grupo de resposta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23a4f430981689f9794c05aa1472ff61cd32cd5f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569387"
---
# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="07fd3-103">Gerenciar grupos de agente de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07fd3-103">Managing Response Group agent groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07fd3-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="07fd3-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="07fd3-p101">Um grupo de operadores consiste em um grupo de pessoas designadas para atender às chamadas de um grupo de resposta. Ao criar um grupo de operadores, selecione os operadores que serão atribuídos ao grupo e especifique configurações de grupo adicionais, como o método de roteamento e se um operador pode entrar no grupo e sair dele.</span><span class="sxs-lookup"><span data-stu-id="07fd3-p101">An agent group consists of a group of people who are designated to answer calls to a response group. When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07fd3-107">Os usuários devem estar habilitados para o Enterprise Voice para que você possa adicioná-los aos grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="07fd3-107">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="07fd3-108">Para obter detalhes sobre como habilitar um usuário para o Enterprise Voice, consulte <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="07fd3-108">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="07fd3-p103">Apenas os usuários locais podem ser operadores. Se um operador for movido de local para online, a chamada do grupo de resposta não será mais roteada para ele.</span><span class="sxs-lookup"><span data-stu-id="07fd3-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="07fd3-111">Um agente que deve entrar e sair do grupo, que é diferente de entrar ou sair do Lync Server, é chamado de um *agente formal*.</span><span class="sxs-lookup"><span data-stu-id="07fd3-111">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="07fd3-112">Os operadores formais precisam entrar no grupo para que possam receber as chamadas roteadas para o grupo.</span><span class="sxs-lookup"><span data-stu-id="07fd3-112">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="07fd3-113">Isso pode ser útil para os operadores que respondem às chamadas do grupo em tempo parcial.</span><span class="sxs-lookup"><span data-stu-id="07fd3-113">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="07fd3-114">Os agentes formais entram e saem de seus grupos clicando em um item de menu no Lync 2013 para abrir o navegador Internet Windows Internet Explorer e exibir um console de página da Web.</span><span class="sxs-lookup"><span data-stu-id="07fd3-114">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="07fd3-115">Um operador que não precisa entrar ou sair do grupo é denominado *operador informal*.</span><span class="sxs-lookup"><span data-stu-id="07fd3-115">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="07fd3-116">Os agentes informais são automaticamente conectados ao grupo quando entram no Lync Server e não podem sair do grupo.</span><span class="sxs-lookup"><span data-stu-id="07fd3-116">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07fd3-p106">Quando você atribuir os usuários como operadores do grupo de resposta, informe-os de que, se tiverem o modo de privacidade habilitado, precisarão pesquisar os contatos do "RGS Presence Watcher" e adicioná-los à sua lista de contatos. Os operadores com o modo de privacidade habilitado, mas que não têm o "RGS Presence Watcher" na lista de contatos, não podem receber chamadas para o grupo de resposta. Os operadores que não têm o modo de privacidade habilitado não são afetados.</span><span class="sxs-lookup"><span data-stu-id="07fd3-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="07fd3-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="07fd3-120">In This Section</span></span>

  - [<span data-ttu-id="07fd3-121">Criar ou modificar um grupo de agentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07fd3-121">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="07fd3-122">Excluir um grupo de agentes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07fd3-122">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

