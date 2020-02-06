---
title: Política da versão do cliente criar novo ou editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: É possível especificar a versão de clientes compatíveis com seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.
ms.openlocfilehash: 2a30a52ea69c1803b04313289310f223fd716b62
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794600"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="1a85e-104">Política de Versão do Cliente: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="1a85e-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="1a85e-105">É possível especificar a versão de clientes compatíveis com seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="1a85e-106">Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="1a85e-107">Para aproveitar ao máximo os recursos incluídos no Skype for Business Server e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente usadas em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="1a85e-108">Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de várias versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a85e-p103">Os filtros são listados em ordem de precedência. Por exemplo, se você tiver um filtro que permite a conexão de clientes que executam a versão 1.5 ou mais recente, seguido por um filtro que bloqueia os clientes executando uma versão anterior a 2.0, o primeiro filtro terá precedência e os clientes que executam a versão 1.5 terão permissão para se conectar.</span><span class="sxs-lookup"><span data-stu-id="1a85e-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="1a85e-111">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="1a85e-111">Tasks you can perform</span></span>

<span data-ttu-id="1a85e-112">É possível executar as seguintes tarefas na página **Criar uma nova Política de Versão de Cliente** ou  **Editar Política da Versão de Cliente**:</span><span class="sxs-lookup"><span data-stu-id="1a85e-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="1a85e-113">Adicionar ou modificar o nome ou descrição da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="1a85e-114">Adicionar ou modificar as regras de versão de cliente da política de versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="1a85e-115">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="1a85e-115">UI Reference</span></span>

<span data-ttu-id="1a85e-116">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="1a85e-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="1a85e-117">**Escopo** Identifica o escopo (site, pool ou usuário) da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="1a85e-118">**Nome** Você pode adicionar ou modificar o nome da política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="1a85e-119">**Descrição** Você pode adicionar uma descrição para ajudar a identificar a política na lista na página de política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="1a85e-120">**Novo** Você pode adicionar uma nova regra de versão do cliente à política.</span><span class="sxs-lookup"><span data-stu-id="1a85e-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="1a85e-121">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma regra de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="1a85e-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="1a85e-122">**Remover** o Esta opção remove a regra de versão do cliente selecionada da política.</span><span class="sxs-lookup"><span data-stu-id="1a85e-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="1a85e-123">**Setas para cima e para baixo** Esta opção move a regra de versão do cliente selecionada para cima ou para baixo em prioridade.</span><span class="sxs-lookup"><span data-stu-id="1a85e-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="1a85e-124">As regras são processadas na ordem listada.</span><span class="sxs-lookup"><span data-stu-id="1a85e-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="1a85e-125">Para obter detalhes sobre a interoperabilidade entre clientes e versões do cliente, consulte [interoperabilidade do cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span><span class="sxs-lookup"><span data-stu-id="1a85e-125">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span></span> <span data-ttu-id="1a85e-126">Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="1a85e-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

