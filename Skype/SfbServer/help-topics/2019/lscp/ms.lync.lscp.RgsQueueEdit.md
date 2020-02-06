---
title: Fila de grupos de resposta criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: As filas do grupo de resposta mantêm chamadas para um grupo de resposta até que um agente atenda a chamada.
ms.openlocfilehash: 9cf88e66886794ee016f1faa03c4ee773ea568b7
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793489"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="cf1bf-103">Fila de Grupos de Resposta: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="cf1bf-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="cf1bf-104">As filas do grupo de resposta mantêm chamadas para um grupo de resposta até que um agente atenda a chamada.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="cf1bf-105">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="cf1bf-105">UI Reference</span></span>

<span data-ttu-id="cf1bf-106">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="cf1bf-107">**Nome** Cada fila deve ter um nome.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="cf1bf-108">Digite um nome descritivo para a fila.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="cf1bf-109">**Descrição** Este campo é opcional.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-109">**Description** This field is optional.</span></span> <span data-ttu-id="cf1bf-110">Use-o para fornecer detalhes adicionais sobre a fila.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="cf1bf-111">**Grupos** de Selecione os grupos de agente que você deseja atribuir à fila.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="cf1bf-112">Clique em **Selecionar** para adicionar grupos de agente à lista.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="cf1bf-113">Clique em **Remover** para excluir o grupo de agentes selecionado da lista.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="cf1bf-114">As setas para cima e para baixo movem um grupo de agentes selecionado para cima e para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="cf1bf-115">A ordem dos grupos de agente afeta a ordem em que o Skype for Business Server procura por um agente disponível.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="cf1bf-116">Ou seja, o primeiro grupo na lista é pesquisado primeiro em busca de um agente disponível, seguindo pelo segundo grupo e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="cf1bf-117">**Habilitar o tempo limite da fila** Marque esta caixa de seleção para especificar um período de tempo máximo para que um chamador aguarde em espera antes que um agente atenda a chamada.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="cf1bf-118">Se você selecionar essa opção, também precisará especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf1bf-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="cf1bf-119">**Período de tempo limite (segundos)** Selecione ou digite o número máximo de segundos que um chamador pode aguardar antes que um agente atenda a chamada.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="cf1bf-120">**Ação da chamada** Selecione a ação que ocorre quando uma chamada atinge o tempo limite. Suas opções são:</span><span class="sxs-lookup"><span data-stu-id="cf1bf-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="cf1bf-121">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-121">**Disconnect**</span></span>

  - <span data-ttu-id="cf1bf-122">**Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP**, digite um endereço de correio de voz no formato SIP<username> @ <domainname> : (por exemplo, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cf1bf-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="cf1bf-123">**Encaminhar para número de telefone** Se você selecionar essa opção, em **endereço SIP** , digite o número de telefone no formato SIP<number> @ <domainname> : (por exemplo, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cf1bf-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="cf1bf-124">**Encaminhar para endereço SIP** Selecione esta opção para encaminhar a chamada para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="cf1bf-125">Em **endereço SIP**, digite o URI para o usuário no formato SIP:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="cf1bf-126">**Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila para receber chamadas quando o tempo limite das chamadas for atingido.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="cf1bf-127">**Habilitar o estouro de fila** Marque esta caixa de seleção para especificar um número máximo de chamadas que a fila pode conter.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="cf1bf-128">Se você selecionar essa opção, também precisará especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cf1bf-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="cf1bf-129">**Número máximo de chamadas** Selecione ou digite o número máximo de chamadas que a fila pode conter.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="cf1bf-130">**Encaminhar a chamada** Selecione qual chamada deve ser tomada quando o limite de estouro de fila for atingido.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="cf1bf-131">**Ação da chamada** Selecione a ação que ocorre quando o limite de estouro de fila é atingido.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="cf1bf-132">Suas opções são:</span><span class="sxs-lookup"><span data-stu-id="cf1bf-132">Your choices are:</span></span>

  - <span data-ttu-id="cf1bf-133">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="cf1bf-133">**Disconnect**</span></span>

  - <span data-ttu-id="cf1bf-134">**Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP**, digite um endereço de correio de voz no formato SIP<username> @ <domainname> : (por exemplo, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cf1bf-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="cf1bf-135">**Encaminhar para número de telefone** Se você selecionar essa opção, em **endereço SIP** , digite o número de telefone no formato SIP<number> @ <domainname> : (por exemplo, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="cf1bf-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="cf1bf-136">**Encaminhar para endereço SIP** Selecione esta opção para encaminhar a chamada para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="cf1bf-137">Em **endereço SIP**, digite o URI para o usuário no formato SIP:<username>@<domainname>.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="cf1bf-138">**Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila que receberá chamadas quando o limite de estouro da fila for atingido.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="cf1bf-139">Para obter detalhes sobre recursos e recursos do grupo de resposta, consulte [planejar o aplicativo do grupo de resposta no Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="cf1bf-140">Para obter detalhes sobre como trabalhar com filas, consulte  [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="cf1bf-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


