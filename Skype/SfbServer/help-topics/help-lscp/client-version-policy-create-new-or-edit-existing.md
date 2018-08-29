---
title: Política de versão cliente criar novo ou editar existente
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: É possível especificar a versão de clientes aceitos em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente. Para fazer um uso maior dos recursos incluídos no Skype para Business Server 2015 e melhorar a experiência geral do usuário, você pode usar o filtro de versão de cliente para restringir as versões do cliente que são usadas em seu ambiente. Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de várias versões de cliente.
ms.openlocfilehash: 9b69b3dd52665c01e42d12f7aed2790064cb6688
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23261144"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="97074-106">Política de Versão do Cliente: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="97074-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="97074-107">É possível especificar a versão de clientes aceitos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="97074-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="97074-108">Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.</span><span class="sxs-lookup"><span data-stu-id="97074-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="97074-109">Para fazer um uso maior dos recursos incluídos no Skype para Business Server 2015 e melhorar a experiência geral do usuário, você pode usar o filtro de versão de cliente para restringir as versões do cliente que são usadas em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="97074-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="97074-110">Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de várias versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="97074-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97074-p103">Os filtros são listados em ordem de precedência. Por exemplo, se você tiver um filtro que permite a conexão de clientes que executam a versão 1.5 ou mais recente, seguido por um filtro que bloqueia os clientes executando uma versão anterior a 2.0, o primeiro filtro terá precedência e os clientes que executam a versão 1.5 terão permissão para se conectar.</span><span class="sxs-lookup"><span data-stu-id="97074-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="97074-113">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="97074-113">Tasks you can perform</span></span>

<span data-ttu-id="97074-114">É possível executar as seguintes tarefas na página **Criar uma nova Política de Versão de Cliente** ou  **Editar Política da Versão de Cliente**:</span><span class="sxs-lookup"><span data-stu-id="97074-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="97074-115">Adicionar ou modificar o nome ou descrição da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="97074-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="97074-116">Adicionar ou modificar as regras de versão de cliente da política de versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="97074-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="97074-117">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="97074-117">UI Reference</span></span>

<span data-ttu-id="97074-118">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="97074-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="97074-119">**Escopo** Identifica o escopo (Site, Pool ou usuário) da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="97074-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="97074-120">**Nome** É possível adicionar ou modificar o nome da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="97074-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="97074-121">**Descrição** Você pode adicionar uma descrição para ajudar a identificar a política na lista na página política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="97074-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="97074-122">**Novo** Você pode adicionar uma nova regra de versão de cliente à política.</span><span class="sxs-lookup"><span data-stu-id="97074-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="97074-123">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções para uma regra de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="97074-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="97074-124">**Remover** Essa opção remove a política a regra de versão de cliente selecionada.</span><span class="sxs-lookup"><span data-stu-id="97074-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="97074-125">**Acima e abaixo setas** Essa opção move a regra de versão de cliente selecionada para cima ou para baixo na ordem de prioridade.</span><span class="sxs-lookup"><span data-stu-id="97074-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="97074-126">As regras são processadas na ordem listada.</span><span class="sxs-lookup"><span data-stu-id="97074-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="97074-127">Para obter detalhes sobre a interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="97074-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="97074-128">Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="97074-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

