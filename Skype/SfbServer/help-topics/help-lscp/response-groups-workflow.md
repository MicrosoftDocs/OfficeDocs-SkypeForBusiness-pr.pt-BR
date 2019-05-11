---
title: Fluxo de Trabalho de Grupos de Resposta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: Grupos de resposta consistem de grupos de operadores, filas e fluxos de trabalho. Fluxos de trabalho do grupo de resposta definem as ações que serão executadas quando o aplicativo grupo de resposta recebe uma chamada telefônica.
ms.openlocfilehash: 39660de6360a14a762325430e80df3207d07468e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924350"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="52d04-104">Fluxo de Trabalho de Grupos de Resposta</span><span class="sxs-lookup"><span data-stu-id="52d04-104">Response Groups Workflow</span></span>

<span data-ttu-id="52d04-105">Grupos de resposta consistem de grupos de operadores, filas e fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="52d04-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="52d04-106">Fluxos de trabalho do grupo de resposta definem as ações que serão executadas quando o aplicativo grupo de resposta recebe uma chamada telefônica.</span><span class="sxs-lookup"><span data-stu-id="52d04-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="52d04-107">Os **Grupos de resposta** - página**fluxo de trabalho** exibe uma lista de todos os grupo de resposta fluxos de trabalho que são definidas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="52d04-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="52d04-108">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="52d04-108">Tasks you can perform</span></span>

<span data-ttu-id="52d04-109">Você pode executar as seguintes tarefas dos **Grupos de resposta** - página**fluxo de trabalho** :</span><span class="sxs-lookup"><span data-stu-id="52d04-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="52d04-110">Criar ou alterar um fluxo de trabalho do grupo de busca</span><span class="sxs-lookup"><span data-stu-id="52d04-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="52d04-111">Criar ou alterar um fluxo de trabalho interativo</span><span class="sxs-lookup"><span data-stu-id="52d04-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="52d04-112">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="52d04-112">UI Reference</span></span>

<span data-ttu-id="52d04-113">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="52d04-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="52d04-114">**Criar ou editar um fluxo de trabalho** Abre a ferramenta de configuração do grupo de resposta para criação ou edição de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="52d04-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="52d04-115">**Atualizar** Atualiza a lista de fluxos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="52d04-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="52d04-116">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="52d04-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="52d04-117">**Nome** O nome exclusivo atribuído ao fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="52d04-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="52d04-118">**Serviço** O serviço **ApplicationServer** que hospeda o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="52d04-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="52d04-119">**Endereço SIP** O endereço SIP do grupo que atenderá chamadas no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="52d04-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="52d04-120">**Telefone** O número de telefone que é chamado para acessar este grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="52d04-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="52d04-121">**Idioma** O que é usado para reconhecimento de fala e conversão de texto em idioma.</span><span class="sxs-lookup"><span data-stu-id="52d04-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="52d04-122">**IVR** Indica se o fluxo de trabalho é um grupo de busca ou um fluxo de trabalho interativo.</span><span class="sxs-lookup"><span data-stu-id="52d04-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="52d04-123">**Habilitado** Indica se o fluxo de trabalho está ativado para receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="52d04-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="52d04-124">Para obter detalhes sobre os recursos de grupo de resposta, consulte o [plano para o aplicativo de grupo de resposta no Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="52d04-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="52d04-125">Para obter detalhes sobre como trabalhar com fluxos de trabalho do grupo de resposta, consulte [Gerenciando fluxos de grupo de resposta](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="52d04-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


