---
title: Política de Versão de Cliente
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
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: É possível especificar a versão de clientes suportados em seu ambiente. Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente. Para fazer o maior uso dos recursos incluídos no Skype for Business Server 2015 e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente que são usadas em seu ambiente. Usando o filtro de versão do cliente, também é possível reduzir os custos associados ao suporte de várias versões de clientes.
ms.openlocfilehash: 0af11ac26a73452412c653c04233df7b932f2b49
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118640"
---
# <a name="client-version-policy"></a><span data-ttu-id="b79d0-106">Política da Versão de Cliente</span><span class="sxs-lookup"><span data-stu-id="b79d0-106">Client Version Policy</span></span>

<span data-ttu-id="b79d0-107">É possível especificar a versão de clientes suportados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b79d0-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="b79d0-108">Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.</span><span class="sxs-lookup"><span data-stu-id="b79d0-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="b79d0-109">Para fazer o maior uso dos recursos incluídos no Skype for Business Server 2015 e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente que são usadas em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b79d0-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="b79d0-110">Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de múltiplas versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="b79d0-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b79d0-111">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="b79d0-111">Tasks you can perform</span></span>

<span data-ttu-id="b79d0-112">É possível executar as seguintes tarefas na página **Política da Versão do Cliente**:</span><span class="sxs-lookup"><span data-stu-id="b79d0-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="b79d0-113">Edite a política de versão do cliente padrão ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="b79d0-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="b79d0-114">Criar políticas de versão do cliente para um site específico ou pool.</span><span class="sxs-lookup"><span data-stu-id="b79d0-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="b79d0-115">Criar políticas de versão do cliente que possam ser atribuídas a usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="b79d0-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="b79d0-116">Como os usuários anônimos não são associados a um usuário, site ou serviço, os usuários anônimos são afetados somente por políticas no nível global.</span><span class="sxs-lookup"><span data-stu-id="b79d0-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b79d0-117">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="b79d0-117">UI Reference</span></span>

<span data-ttu-id="b79d0-118">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="b79d0-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="b79d0-119">**Novo** Você pode criar uma ou mais das seguintes políticas de versão do cliente:</span><span class="sxs-lookup"><span data-stu-id="b79d0-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="b79d0-120">Política de site</span><span class="sxs-lookup"><span data-stu-id="b79d0-120">Site policy</span></span>

  - <span data-ttu-id="b79d0-121">Política de pool</span><span class="sxs-lookup"><span data-stu-id="b79d0-121">Pool policy</span></span>

  - <span data-ttu-id="b79d0-122">Política de usuário</span><span class="sxs-lookup"><span data-stu-id="b79d0-122">User policy</span></span>

- <span data-ttu-id="b79d0-123">**Editar** Você pode alterar as opções de qualquer uma das políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="b79d0-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="b79d0-124">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b79d0-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="b79d0-125">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="b79d0-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="b79d0-126">**Selecionar Tudo** Essa opção seleciona todas as políticas de versão do cliente na lista.</span><span class="sxs-lookup"><span data-stu-id="b79d0-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="b79d0-127">**Excluir** Essa opção exclui todas as políticas de versão do cliente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="b79d0-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="b79d0-128">**Atualizar** Você pode atualizar a lista de políticas de versão do cliente para verificar o status das opções de todas as políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="b79d0-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="b79d0-129">Para obter detalhes sobre a interoperabilidade entre clientes e versões de clientes, consulte [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="b79d0-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="b79d0-130">Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="b79d0-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>