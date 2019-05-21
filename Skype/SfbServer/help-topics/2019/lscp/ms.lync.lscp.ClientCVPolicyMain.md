---
title: Política de Versão do Cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: É possível especificar a versão de clientes compatíveis com seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.
ms.openlocfilehash: 42390f18bef702b5e7546d170aaa1a83e8394e0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300528"
---
# <a name="client-version-policy"></a><span data-ttu-id="313fa-104">Política de Versão do Cliente</span><span class="sxs-lookup"><span data-stu-id="313fa-104">Client Version Policy</span></span>

<span data-ttu-id="313fa-105">É possível especificar a versão de clientes compatíveis com seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="313fa-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="313fa-106">Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.</span><span class="sxs-lookup"><span data-stu-id="313fa-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="313fa-107">Para aproveitar ao máximo os recursos incluídos no Skype for Business Server e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente usadas em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="313fa-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="313fa-108">Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de várias versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="313fa-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="313fa-109">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="313fa-109">Tasks you can perform</span></span>

<span data-ttu-id="313fa-110">É possível executar as seguintes tarefas na página **Política da Versão do Cliente**:</span><span class="sxs-lookup"><span data-stu-id="313fa-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="313fa-111">Edite a política de versão do cliente padrão ( **global**).</span><span class="sxs-lookup"><span data-stu-id="313fa-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="313fa-112">Criar políticas de versão do cliente para um site específico ou pool.</span><span class="sxs-lookup"><span data-stu-id="313fa-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="313fa-113">Criar políticas de versão do cliente que possam ser atribuídas a usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="313fa-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="313fa-114">Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.</span><span class="sxs-lookup"><span data-stu-id="313fa-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="313fa-115">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="313fa-115">UI Reference</span></span>

<span data-ttu-id="313fa-116">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="313fa-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="313fa-117">**Novo** Você pode criar uma ou mais das seguintes políticas de versão do cliente:</span><span class="sxs-lookup"><span data-stu-id="313fa-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="313fa-118">Política de site</span><span class="sxs-lookup"><span data-stu-id="313fa-118">Site policy</span></span>

  - <span data-ttu-id="313fa-119">Política de pool</span><span class="sxs-lookup"><span data-stu-id="313fa-119">Pool policy</span></span>

  - <span data-ttu-id="313fa-120">Política de usuário</span><span class="sxs-lookup"><span data-stu-id="313fa-120">User policy</span></span>

- <span data-ttu-id="313fa-121">**Editar** Você pode alterar as opções de qualquer uma das políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="313fa-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="313fa-122">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="313fa-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="313fa-123">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="313fa-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="313fa-124">**Selecionar tudo** Essa opção seleciona todas as políticas de versão do cliente na lista.</span><span class="sxs-lookup"><span data-stu-id="313fa-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="313fa-125">**Excluir** Esta opção exclui todas as políticas de versão de cliente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="313fa-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="313fa-126">**Atualização** Você pode atualizar a lista de política de versão do cliente para verificar o status das opções de todas as políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="313fa-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="313fa-127">Para obter detalhes sobre a interoperabilidade entre clientes e versões do cliente, consulte interoperabilidade do [cliente](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="313fa-127">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="313fa-128">Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="313fa-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

