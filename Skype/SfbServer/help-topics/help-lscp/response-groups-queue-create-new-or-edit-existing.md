---
title: Fila de Grupos de Resposta Criar Novo ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: As filas do Grupo de Resposta resitem chamadas para um grupo de resposta até que um agente responda à chamada.
ms.openlocfilehash: 4226c30ad560d4f5e5396b8af4ab657e55f087c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122552"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="08b75-103">Fila de Grupos de Resposta: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="08b75-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="08b75-104">As filas do Grupo de Resposta resitem chamadas para um grupo de resposta até que um agente responda à chamada.</span><span class="sxs-lookup"><span data-stu-id="08b75-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="08b75-105">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="08b75-105">UI Reference</span></span>

<span data-ttu-id="08b75-106">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="08b75-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="08b75-107">**Nome** Cada fila deve ter um nome.</span><span class="sxs-lookup"><span data-stu-id="08b75-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="08b75-108">Digite um nome descritivo para a fila.</span><span class="sxs-lookup"><span data-stu-id="08b75-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="08b75-109">**Descrição** Este campo é opcional.</span><span class="sxs-lookup"><span data-stu-id="08b75-109">**Description** This field is optional.</span></span> <span data-ttu-id="08b75-110">Use-o para fornecer detalhes adicionais sobre a fila.</span><span class="sxs-lookup"><span data-stu-id="08b75-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="08b75-111">**Grupos** Selecione os grupos de agentes que você deseja atribuir à fila.</span><span class="sxs-lookup"><span data-stu-id="08b75-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="08b75-112">Clique em **Selecionar** para adicionar grupos de agente à lista.</span><span class="sxs-lookup"><span data-stu-id="08b75-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="08b75-113">Clique em **Remover** para excluir o grupo de agentes selecionado da lista.</span><span class="sxs-lookup"><span data-stu-id="08b75-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="08b75-114">As setas para cima e para baixo movem um grupo de agentes selecionado para cima e para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="08b75-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="08b75-115">A ordem dos grupos de agentes afeta a ordem na qual o Skype for Business Server pesquisa um agente disponível.</span><span class="sxs-lookup"><span data-stu-id="08b75-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="08b75-116">Ou seja, o primeiro grupo na lista é pesquisado primeiro em busca de um agente disponível, seguindo pelo segundo grupo e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="08b75-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="08b75-117">**Habilitar o tempo de espera da fila** Marque essa caixa de seleção para especificar um período máximo de tempo para um chamador aguardar em espera antes que um agente responda à chamada.</span><span class="sxs-lookup"><span data-stu-id="08b75-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="08b75-118">Se você selecionar essa opção, também precisará especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08b75-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="08b75-119">**Período de tempo decoro (segundos)** Selecione ou digite o número máximo de segundos que um chamador pode esperar antes que um agente responda à chamada.</span><span class="sxs-lookup"><span data-stu-id="08b75-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="08b75-120">**Ação de chamada** Selecione a ação que ocorre quando uma chamada é o tempo de saída. Suas opções são:</span><span class="sxs-lookup"><span data-stu-id="08b75-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="08b75-121">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="08b75-121">**Disconnect**</span></span>

  - <span data-ttu-id="08b75-122">**Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP,** digite um endereço de caixa postal no formato sip: <username> @ <domainname> (por exemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="08b75-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="08b75-123">**Encaminhar para o número de telefone** Se você selecionar essa opção, no **endereço SIP** digite o número de telefone no formato sip: <number> @ <domainname> (por exemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="08b75-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="08b75-124">**Encaminhar para endereço SIP** Selecione essa opção para encaminhar a chamada para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="08b75-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="08b75-125">No **endereço SIP,** digite o URI do usuário no formato sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="08b75-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="08b75-126">**Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila para receber chamadas quando as chamadas se desem tempo de espera.</span><span class="sxs-lookup"><span data-stu-id="08b75-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="08b75-127">**Habilitar estouro de fila** Marque essa caixa de seleção para especificar um número máximo de chamadas que a fila pode realizar.</span><span class="sxs-lookup"><span data-stu-id="08b75-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="08b75-128">Se você selecionar essa opção, também precisará especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08b75-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="08b75-129">**Número máximo de chamadas** Selecione ou digite o número máximo de chamadas que a fila pode realizar.</span><span class="sxs-lookup"><span data-stu-id="08b75-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="08b75-130">**Encaminhar a chamada** Selecione qual chamada deve ser tomada quando o limite de estouro da fila for atendido.</span><span class="sxs-lookup"><span data-stu-id="08b75-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="08b75-131">**Ação de chamada** Selecione a ação que ocorre quando o limite de estouro de fila é atendido.</span><span class="sxs-lookup"><span data-stu-id="08b75-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="08b75-132">Suas opções são:</span><span class="sxs-lookup"><span data-stu-id="08b75-132">Your choices are:</span></span>

  - <span data-ttu-id="08b75-133">**Desconectar**</span><span class="sxs-lookup"><span data-stu-id="08b75-133">**Disconnect**</span></span>

  - <span data-ttu-id="08b75-134">**Encaminhar para caixa postal** Se você selecionar essa opção, no **endereço SIP,** digite um endereço de caixa postal no formato sip: <username> @ <domainname> (por exemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="08b75-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="08b75-135">**Encaminhar para o número de telefone** Se você selecionar essa opção, no **endereço SIP** digite o número de telefone no formato sip: <number> @ <domainname> (por exemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="08b75-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="08b75-136">**Encaminhar para endereço SIP** Selecione essa opção para encaminhar a chamada para outro usuário.</span><span class="sxs-lookup"><span data-stu-id="08b75-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="08b75-137">No **endereço SIP,** digite o URI do usuário no formato sip: <username> @ <domainname> .</span><span class="sxs-lookup"><span data-stu-id="08b75-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="08b75-138">**Encaminhar para outra fila** Se você selecionar essa opção, navegue até a fila que receberá chamadas quando o limite de estouro da fila for atendido.</span><span class="sxs-lookup"><span data-stu-id="08b75-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="08b75-139">Para obter detalhes sobre recursos e recursos do Grupo de Resposta, consulte [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação planejamento.</span><span class="sxs-lookup"><span data-stu-id="08b75-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="08b75-140">Para obter detalhes sobre como trabalhar com filas, consulte [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="08b75-140">For details about working with queues, see [Managing Response Group Queues](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-queues) in the Operations documentation.</span></span>