---
title: Política de Versão de Cliente Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente. Para fazer o máximo uso dos recursos incluídos no Skype for Business Server 2015 e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente que são usadas em seu ambiente. Usando o filtro de versão do cliente, também é possível reduzir os custos associados ao suporte de várias versões de clientes.
ms.openlocfilehash: db463896426d8919776ba21532bbac04415c526d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829511"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="d9a15-106">Política da Versão do Cliente: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="d9a15-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="d9a15-107">É possível especificar a versão de clientes suportados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="d9a15-108">Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="d9a15-109">Para fazer o máximo uso dos recursos incluídos no Skype for Business Server 2015 e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente que são usadas em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="d9a15-110">Usando o filtro de versão do cliente, também é possível reduzir os custos associados ao suporte de várias versões de clientes.</span><span class="sxs-lookup"><span data-stu-id="d9a15-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9a15-p103">Os filtros são listados em ordem de precedência. Por exemplo, se você tiver um filtro que permite a conexão de clientes que executam a versão 1.5 ou mais recente, seguido por um filtro que bloqueia os clientes executando uma versão anterior a 2.0, o primeiro filtro terá precedência e os clientes que executam a versão 1.5 terão permissão para se conectar.</span><span class="sxs-lookup"><span data-stu-id="d9a15-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d9a15-113">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="d9a15-113">Tasks you can perform</span></span>

<span data-ttu-id="d9a15-114">É possível executar as seguintes tarefas na página Nova **Política de Versão de Cliente** ou Editar Política de Versão **de** Cliente:</span><span class="sxs-lookup"><span data-stu-id="d9a15-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="d9a15-115">Adicione ou modifique o nome ou a descrição da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="d9a15-116">Adicionar ou modificar regras de versão do cliente para a política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d9a15-117">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="d9a15-117">UI Reference</span></span>

<span data-ttu-id="d9a15-118">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="d9a15-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d9a15-119">**Escopo** Identifica o escopo (Site, Pool ou Usuário) da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="d9a15-120">**Nome** Você pode adicionar ou modificar o nome da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="d9a15-121">**Descrição** Você pode adicionar uma descrição para ajudar a identificar a política na lista na página Política de Versão de Cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="d9a15-122">**Novo** Você pode adicionar uma nova regra de versão de cliente à política.</span><span class="sxs-lookup"><span data-stu-id="d9a15-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="d9a15-123">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma regra de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a15-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="d9a15-124">**Remover** Essa opção remove a regra de versão do cliente selecionada da política.</span><span class="sxs-lookup"><span data-stu-id="d9a15-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="d9a15-125">**Setas para cima e para baixo** Essa opção move a regra de versão do cliente selecionada para cima ou para baixo com prioridade.</span><span class="sxs-lookup"><span data-stu-id="d9a15-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="d9a15-126">As regras são processadas na ordem listada.</span><span class="sxs-lookup"><span data-stu-id="d9a15-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="d9a15-127">Para obter detalhes sobre a interoperabilidade entre clientes e versões de clientes, consulte [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="d9a15-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="d9a15-128">Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="d9a15-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

