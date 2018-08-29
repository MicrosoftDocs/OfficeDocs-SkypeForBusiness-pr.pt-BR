---
title: Configuração de versão do cliente
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: Além de especificar a versão dos clientes que você deseja suportar em seu ambiente, você também pode especificar uma ação padrão para clientes que ainda não tenham uma política de versão definida. Isso permite restringir quais versões dos clientes são usados em seu ambiente, que pode ajudar a controlar os custos associados ao suporte de várias versões do cliente.
ms.openlocfilehash: f2b15966b135ffcaf8379a9ea2b1c3da377c3686
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23254473"
---
# <a name="client-version-configuration"></a><span data-ttu-id="0c72b-104">Configuração de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="0c72b-104">Client Version Configuration</span></span>

<span data-ttu-id="0c72b-105">Além de especificar a versão dos clientes que você deseja suportar em seu ambiente, você também pode especificar uma ação padrão para clientes que ainda não tenham uma política de versão definida.</span><span class="sxs-lookup"><span data-stu-id="0c72b-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="0c72b-106">Isso permite restringir quais versões dos clientes são usados em seu ambiente, que pode ajudar a controlar os custos associados ao suporte de várias versões do cliente.</span><span class="sxs-lookup"><span data-stu-id="0c72b-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0c72b-107">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="0c72b-107">Tasks you can perform</span></span>

<span data-ttu-id="0c72b-108">Você pode executar as seguintes tarefas na página **Configuração de versão de cliente** :</span><span class="sxs-lookup"><span data-stu-id="0c72b-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="0c72b-109">Edite a configuração de versão de cliente padrão ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="0c72b-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="0c72b-110">Crie configuração de versão de cliente para um site específico.</span><span class="sxs-lookup"><span data-stu-id="0c72b-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="0c72b-111">Ativar e desativar as configurações de versão de cliente existentes.</span><span class="sxs-lookup"><span data-stu-id="0c72b-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="0c72b-112">Como usuários anônimos não são associados um site, os usuários anônimos são afetados por políticas no nível global somente.</span><span class="sxs-lookup"><span data-stu-id="0c72b-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0c72b-113">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="0c72b-113">UI Reference</span></span>

<span data-ttu-id="0c72b-114">As listas a seguir descrevem os menus, comando, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="0c72b-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="0c72b-115">**Novo** Você pode criar uma configuração de versão de cliente para um site específico.</span><span class="sxs-lookup"><span data-stu-id="0c72b-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="0c72b-116">**Editar** Você pode alterar as opções de qualquer uma das diretivas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0c72b-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="0c72b-117">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0c72b-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="0c72b-118">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções para uma configuração de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0c72b-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="0c72b-119">**Selecionar tudo** Essa opção seleciona todas as configurações de versão do cliente na lista.</span><span class="sxs-lookup"><span data-stu-id="0c72b-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="0c72b-120">**Excluir** Essa opção exclui todas as configurações de versão de cliente selecionada.</span><span class="sxs-lookup"><span data-stu-id="0c72b-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="0c72b-121">**Atualizar** É possível atualizar a lista de configuração de versão do cliente para verificar o status das opções de todas as configurações de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="0c72b-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="0c72b-122">Para obter detalhes sobre a interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="0c72b-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0c72b-123">Para obter detalhes sobre como trabalhar com as configurações de versão de cliente, consulte [modificar a ação padrão para clientes não explicitamente suportados ou restritos](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="0c72b-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

