---
title: Configuração de Versão de Cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: Além de especificar a versão dos clientes que você deseja suportar em seu ambiente, também é possível especificar uma ação padrão para clientes ainda não têm uma política de versão definida. Isso permite que você restrinja quais versões de cliente são usadas em seu ambiente, o que pode ajudá-lo a controlar os custos associados ao suporte de múltiplas versões de cliente.
ms.openlocfilehash: 31facafd00a25993aa16f5d89b1fad5a97e566a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095615"
---
# <a name="client-version-configuration"></a><span data-ttu-id="0f460-104">Configuração da Versão de Cliente</span><span class="sxs-lookup"><span data-stu-id="0f460-104">Client Version Configuration</span></span>

<span data-ttu-id="0f460-p102">Além de especificar a versão dos clientes que você deseja suportar em seu ambiente, também é possível especificar uma ação padrão para clientes ainda não têm uma política de versão definida. Isso permite que você restrinja quais versões de cliente são usadas em seu ambiente, o que pode ajudá-lo a controlar os custos associados ao suporte de múltiplas versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="0f460-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0f460-107">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="0f460-107">Tasks you can perform</span></span>

<span data-ttu-id="0f460-108">É possível executar as seguintes tarefas na página **Configuração da Versão do Cliente**:</span><span class="sxs-lookup"><span data-stu-id="0f460-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="0f460-109">Edite a configuração de versão do cliente padrão ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="0f460-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="0f460-110">Criar uma configuração de versão de cliente para um site específico.</span><span class="sxs-lookup"><span data-stu-id="0f460-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="0f460-111">Habilitar ou desabilitar configurações de versão de cliente existentes.</span><span class="sxs-lookup"><span data-stu-id="0f460-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="0f460-112">Como os usuários anônimos não são associados a um site, eles são afetados somente por políticas no nível global.</span><span class="sxs-lookup"><span data-stu-id="0f460-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0f460-113">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="0f460-113">UI Reference</span></span>

<span data-ttu-id="0f460-114">As listas a seguir descrevem os menus, comando, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="0f460-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="0f460-115">**Novo** Você pode criar uma configuração de versão do cliente para um site específico.</span><span class="sxs-lookup"><span data-stu-id="0f460-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="0f460-116">**Editar** Você pode alterar as opções de qualquer uma das políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f460-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="0f460-117">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f460-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="0f460-118">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções para uma configuração de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f460-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="0f460-119">**Selecionar Tudo** Essa opção seleciona todas as configurações de versão do cliente na lista.</span><span class="sxs-lookup"><span data-stu-id="0f460-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="0f460-120">**Excluir** Essa opção exclui todas as configurações de versão do cliente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="0f460-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="0f460-121">**Atualizar** Você pode atualizar a lista de configuração da versão do cliente para verificar o status das opções de todas as configurações de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0f460-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="0f460-122">Para obter detalhes sobre a interoperabilidade entre clientes e versões de clientes, consulte [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) na documentação Planejamento.</span><span class="sxs-lookup"><span data-stu-id="0f460-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="0f460-123">Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="0f460-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>