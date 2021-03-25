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
ms.openlocfilehash: fd3abdae41b912e63391121c740912cde80e18c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120290"
---
# <a name="client-version-policy"></a><span data-ttu-id="99e8f-104">Política da Versão de Cliente</span><span class="sxs-lookup"><span data-stu-id="99e8f-104">Client Version Policy</span></span>

<span data-ttu-id="99e8f-105">É possível especificar a versão de clientes suportados em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="99e8f-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="99e8f-106">Quando dois clientes executando versões diferentes interagem, os recursos disponíveis para cada cliente podem ser limitados pelos recursos do outro cliente.</span><span class="sxs-lookup"><span data-stu-id="99e8f-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="99e8f-107">Para fazer o maior uso dos recursos incluídos no Skype for Business Server e melhorar a experiência geral do usuário, você pode usar o filtro de versão do cliente para restringir as versões do cliente que são usadas em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="99e8f-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="99e8f-108">Ao usar o filtro de versão do cliente, também é possível ajudar a reduzir os custos associados ao suporte de múltiplas versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="99e8f-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="99e8f-109">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="99e8f-109">Tasks you can perform</span></span>

<span data-ttu-id="99e8f-110">É possível executar as seguintes tarefas na página **Política da Versão do Cliente**:</span><span class="sxs-lookup"><span data-stu-id="99e8f-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="99e8f-111">Edite a política de versão do cliente padrão ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="99e8f-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="99e8f-112">Criar políticas de versão do cliente para um site específico ou pool.</span><span class="sxs-lookup"><span data-stu-id="99e8f-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="99e8f-113">Criar políticas de versão do cliente que possam ser atribuídas a usuários individuais.</span><span class="sxs-lookup"><span data-stu-id="99e8f-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="99e8f-114">Como os usuários anônimos não são associados a um usuário, site ou serviço, os usuários anônimos são afetados somente por políticas no nível global.</span><span class="sxs-lookup"><span data-stu-id="99e8f-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="99e8f-115">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="99e8f-115">UI Reference</span></span>

<span data-ttu-id="99e8f-116">As listas a seguir descrevem os menus, comandos, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="99e8f-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="99e8f-117">**Novo** Você pode criar uma ou mais das seguintes políticas de versão do cliente:</span><span class="sxs-lookup"><span data-stu-id="99e8f-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="99e8f-118">Política de site</span><span class="sxs-lookup"><span data-stu-id="99e8f-118">Site policy</span></span>

  - <span data-ttu-id="99e8f-119">Política de pool</span><span class="sxs-lookup"><span data-stu-id="99e8f-119">Pool policy</span></span>

  - <span data-ttu-id="99e8f-120">Política de usuário</span><span class="sxs-lookup"><span data-stu-id="99e8f-120">User policy</span></span>

- <span data-ttu-id="99e8f-121">**Editar** Você pode alterar as opções de qualquer uma das políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="99e8f-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="99e8f-122">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="99e8f-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="99e8f-123">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma política de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="99e8f-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="99e8f-124">**Selecionar Tudo** Essa opção seleciona todas as políticas de versão do cliente na lista.</span><span class="sxs-lookup"><span data-stu-id="99e8f-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="99e8f-125">**Excluir** Essa opção exclui todas as políticas de versão do cliente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="99e8f-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="99e8f-126">**Atualizar** Você pode atualizar a lista de políticas de versão do cliente para verificar o status das opções de todas as políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="99e8f-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="99e8f-127">Para obter detalhes sobre interoperabilidade entre clientes e versões do cliente, consulte [Interoperabilidade do](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) cliente na documentação planejamento.</span><span class="sxs-lookup"><span data-stu-id="99e8f-127">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="99e8f-128">Para obter detalhes sobre como trabalhar com políticas de versão do cliente, consulte [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="99e8f-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>