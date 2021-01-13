---
title: Política de Versão de Cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.
ms.openlocfilehash: c52921df4e68b8273a4e87af0cfe54105e8a10ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812391"
---
# <a name="client-version-policy"></a><span data-ttu-id="c8643-104">Política da Versão de Cliente</span><span class="sxs-lookup"><span data-stu-id="c8643-104">Client Version Policy</span></span>

<span data-ttu-id="c8643-105">É possível especificar a versão de clientes suportados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c8643-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="c8643-106">Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.</span><span class="sxs-lookup"><span data-stu-id="c8643-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="c8643-107">Para fazer o máximo uso dos recursos incluídos no Skype for Business Server e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões de cliente que são usadas em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c8643-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="c8643-108">Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de múltiplas versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="c8643-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c8643-109">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="c8643-109">Tasks you can perform</span></span>

<span data-ttu-id="c8643-110">É possível executar as seguintes tarefas na página **Política da Versão do Cliente**:</span><span class="sxs-lookup"><span data-stu-id="c8643-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="c8643-111">Edite a política de versão do cliente padrão **(Global).**</span><span class="sxs-lookup"><span data-stu-id="c8643-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="c8643-112">Criar políticas de versão do cliente para um site específico ou pool.</span><span class="sxs-lookup"><span data-stu-id="c8643-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="c8643-113">Criar políticas de versão do cliente que possam ser atribuídas a usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="c8643-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="c8643-114">Como os usuários anônimos não são associados a um usuário, site ou serviço, os usuários anônimos são afetados somente por políticas no nível global.</span><span class="sxs-lookup"><span data-stu-id="c8643-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c8643-115">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="c8643-115">UI Reference</span></span>

<span data-ttu-id="c8643-116">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="c8643-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="c8643-117">**Novo** Você pode criar uma ou mais de cada uma das seguintes políticas de versão do cliente:</span><span class="sxs-lookup"><span data-stu-id="c8643-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="c8643-118">Política de site</span><span class="sxs-lookup"><span data-stu-id="c8643-118">Site policy</span></span>

  - <span data-ttu-id="c8643-119">Política de pool</span><span class="sxs-lookup"><span data-stu-id="c8643-119">Pool policy</span></span>

  - <span data-ttu-id="c8643-120">Política de usuário</span><span class="sxs-lookup"><span data-stu-id="c8643-120">User policy</span></span>

- <span data-ttu-id="c8643-121">**Editar** Você pode alterar as opções de qualquer uma das políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="c8643-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="c8643-122">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c8643-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="c8643-123">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="c8643-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="c8643-124">**Selecionar Tudo** Essa opção seleciona todas as políticas de versão do cliente na lista.</span><span class="sxs-lookup"><span data-stu-id="c8643-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="c8643-125">**Excluir** Essa opção exclui todas as políticas de versão do cliente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="c8643-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="c8643-126">**Atualizar** Você pode atualizar a lista de políticas de versão do cliente para verificar o status das opções de todas as políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="c8643-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="c8643-127">Para obter detalhes sobre interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="c8643-127">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="c8643-128">Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="c8643-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

