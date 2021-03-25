---
title: Grupos de resposta criar novo ou editar grupo de agentes existentes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: Os grupos de agente definem quem podem responder às chamadas para um grupo de respostas (conhecido como agentes) e as configurações que se aplicam a todos os agentes no grupo.
ms.openlocfilehash: 944cd48745a2524ccfcd795d9edc60e806859301
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118960"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="0bffb-103">Grupos de Resposta: Criar Novo ou Editar Grupo de Agentes Existente</span><span class="sxs-lookup"><span data-stu-id="0bffb-103">Response Groups: Create New or Edit Existing Agent Group</span></span>

<span data-ttu-id="0bffb-104">Os grupos de agente definem quem podem responder às chamadas para um grupo de respostas (conhecido como agentes) e as configurações que se aplicam a todos os agentes no grupo.</span><span class="sxs-lookup"><span data-stu-id="0bffb-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0bffb-105">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="0bffb-105">UI Reference</span></span>

<span data-ttu-id="0bffb-106">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="0bffb-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0bffb-107">**Nome** Cada grupo de agentes requer um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="0bffb-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="0bffb-108">Use um nome descritivo que identifique a função do grupo.</span><span class="sxs-lookup"><span data-stu-id="0bffb-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="0bffb-109">Por exemplo, Suporte Técnico.</span><span class="sxs-lookup"><span data-stu-id="0bffb-109">For example, Help Desk.</span></span>

- <span data-ttu-id="0bffb-110">**Descrição** Este campo é opcional.</span><span class="sxs-lookup"><span data-stu-id="0bffb-110">**Description** This field is optional.</span></span> <span data-ttu-id="0bffb-111">Use-o para fornecer detalhes adicionais sobre o grupo.</span><span class="sxs-lookup"><span data-stu-id="0bffb-111">Use it to provide additional details about the group.</span></span>

- <span data-ttu-id="0bffb-112">**Política de participação** Especifique a maneira como os agentes devem entrar no grupo de resposta:</span><span class="sxs-lookup"><span data-stu-id="0bffb-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>

  - <span data-ttu-id="0bffb-113">Selecione **Informal** para especificar que os agentes no grupo não precisam entrar e sair. Os agentes informais são automaticamente assinados quando eles se inscredem.</span><span class="sxs-lookup"><span data-stu-id="0bffb-113">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in.</span></span> <span data-ttu-id="0bffb-114">O padrão é **Informal**.</span><span class="sxs-lookup"><span data-stu-id="0bffb-114">The default is **Informal**.</span></span>

  - <span data-ttu-id="0bffb-115">Selecione **Formal** para especificar que os agentes no grupo devem entrar e sair. Quando você seleciona essa opção, os agentes clicam em um item de menu no cliente para abrir um navegador e exibir um console de página da Web para entrar e sair.</span><span class="sxs-lookup"><span data-stu-id="0bffb-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>

- <span data-ttu-id="0bffb-116">**Tempo de alerta (segundos)** Especifique o número de segundos para tocar um agente antes de oferecer a chamada ao próximo agente disponível.</span><span class="sxs-lookup"><span data-stu-id="0bffb-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="0bffb-117">O valor precisa ser pelo menos 10 segundos e menos de 180 segundos.</span><span class="sxs-lookup"><span data-stu-id="0bffb-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="0bffb-118">O padrão é 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="0bffb-118">The default is 20 seconds.</span></span>

- <span data-ttu-id="0bffb-119">**Método Routing** Selecione o método para determinar a ordem na qual os agentes recebem chamadas:</span><span class="sxs-lookup"><span data-stu-id="0bffb-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>

  - <span data-ttu-id="0bffb-120">Selecione **Ocioso por mais tempo** para oferecer uma nova chamada primeiro para o agente que está ocioso (com uma presença de **Disponível** ou **Inativo**) por mais tempo.</span><span class="sxs-lookup"><span data-stu-id="0bffb-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>

  - <span data-ttu-id="0bffb-p105">Selecione **Paralelo** para oferecer uma nova chamada a todos os agentes disponíveis ao mesmo tempo. A chamada é enviada ao primeiro agente que a aceita.</span><span class="sxs-lookup"><span data-stu-id="0bffb-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>

  - <span data-ttu-id="0bffb-123">Selecione **Round robin** para oferecer uma nova chamada a um agente de cada vez.</span><span class="sxs-lookup"><span data-stu-id="0bffb-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>

  - <span data-ttu-id="0bffb-124">Selecione **Serial** para sempre oferecer uma nova chamada aos agentes na ordem na qual eles estão relacionados na lista **Agente**.</span><span class="sxs-lookup"><span data-stu-id="0bffb-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>

  - <span data-ttu-id="0bffb-125">Selecione **Atendente** para oferecer uma nova chamada a todos os agentes que estão assinados e ao aplicativo grupo de resposta ao mesmo tempo, independentemente de sua presença atual.</span><span class="sxs-lookup"><span data-stu-id="0bffb-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="0bffb-126">Os atendedores e usuários clientes configurados como agentes podem ver todas as chamadas que estão aguardando e podem atender chamadas de espera em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="0bffb-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="0bffb-127">A chamada é enviada para o primeiro agente que a aceita, e os outros atendentes e usuários não veem mais a chamada.</span><span class="sxs-lookup"><span data-stu-id="0bffb-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>

- <span data-ttu-id="0bffb-128">**Agentes** Selecione os usuários que devem ser agentes do grupo de resposta de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="0bffb-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>

  - <span data-ttu-id="0bffb-129">Selecione **Usar uma lista de distribuição de email existente** para usar uma lista de distribuição do Exchange.</span><span class="sxs-lookup"><span data-stu-id="0bffb-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="0bffb-130">Digite o endereço de email da lista de distribuição em **Endereço da lista de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="0bffb-130">Type the email address of the distribution list in **Distribution list address**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0bffb-p108">É possível selecionar apenas uma lista de distribuição para um grupo de agentes. Se a lista de distribuição incluir listas de distribuição aninhadas, as listas de distribuição aninhadas não serão incluídas no grupo de agentes.</span><span class="sxs-lookup"><span data-stu-id="0bffb-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0bffb-133">A ordem na qual os agentes estão listados na lista de distribuição afeta a ordem na qual os agentes recebem chamadas para round robin e roteamento em série.</span><span class="sxs-lookup"><span data-stu-id="0bffb-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0bffb-134">Associações ocultas ou listas ocultas podem ficar visíveis para administradores ou usuários do Grupo de Resposta.</span><span class="sxs-lookup"><span data-stu-id="0bffb-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="0bffb-135">Para obter detalhes, [consulte Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span><span class="sxs-lookup"><span data-stu-id="0bffb-135">For details, see [Create or modify an agent group in Skype for Business](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span>

  - <span data-ttu-id="0bffb-p110">Selecione **Definir um grupo personalizado de operadores** para selecionar os usuários que você deseja atribuir como agentes para o grupo de respostas. Clique em **Selecionar** para adicionar um agente à lista. Clique em **Remover** para excluir um agente selecionado da lista.</span><span class="sxs-lookup"><span data-stu-id="0bffb-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>

    <span data-ttu-id="0bffb-p111">As setas para cima e para baixo movem um agente selecionado para cima e para baixo na lista de agentes. A ordem de agentes na lista afeta a ordem na qual os agentes recebem chamadas para roteamento round robin e serial.</span><span class="sxs-lookup"><span data-stu-id="0bffb-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>

<span data-ttu-id="0bffb-141">Para obter detalhes sobre recursos e recursos do Grupo de Resposta, consulte [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação planejamento.</span><span class="sxs-lookup"><span data-stu-id="0bffb-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="0bffb-142">Para obter detalhes sobre como trabalhar com grupos de agente, consulte [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="0bffb-142">For details about working with agent groups, see [Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups) in the Operations documentation.</span></span>