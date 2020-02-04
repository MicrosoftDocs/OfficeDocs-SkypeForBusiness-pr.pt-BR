---
title: Configuração de Versão de Cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: Além de especificar a versão dos clientes para a qual você deseja dar suporte em seu ambiente, você também pode especificar uma ação padrão para clientes que ainda não têm uma política de versão definida. Isso permite que você restrinja quais versões do cliente são usadas em seu ambiente, o que pode ajudá-lo a controlar os custos associados ao suporte a várias versões de cliente.
ms.openlocfilehash: 46969857647a51dd092e3131dd3c24b71b810a2d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700436"
---
# <a name="client-version-configuration"></a><span data-ttu-id="f0b11-104">Configuração de Versão de Cliente</span><span class="sxs-lookup"><span data-stu-id="f0b11-104">Client Version Configuration</span></span>

<span data-ttu-id="f0b11-105">Além de especificar a versão dos clientes para a qual você deseja dar suporte em seu ambiente, você também pode especificar uma ação padrão para clientes que ainda não têm uma política de versão definida.</span><span class="sxs-lookup"><span data-stu-id="f0b11-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="f0b11-106">Isso permite que você restrinja quais versões do cliente são usadas em seu ambiente, o que pode ajudá-lo a controlar os custos associados ao suporte a várias versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="f0b11-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f0b11-107">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="f0b11-107">Tasks you can perform</span></span>

<span data-ttu-id="f0b11-108">Você pode executar as seguintes tarefas na página **configuração de versão do cliente** :</span><span class="sxs-lookup"><span data-stu-id="f0b11-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="f0b11-109">Edite a configuração de versão do cliente padrão ( **global**).</span><span class="sxs-lookup"><span data-stu-id="f0b11-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="f0b11-110">Criar a configuração de versão do cliente para um site específico.</span><span class="sxs-lookup"><span data-stu-id="f0b11-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="f0b11-111">Habilite e desabilite as configurações de versão do cliente existentes.</span><span class="sxs-lookup"><span data-stu-id="f0b11-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="f0b11-112">Como os usuários anônimos não estão associados a um site, os usuários anônimos são afetados apenas por políticas de nível global.</span><span class="sxs-lookup"><span data-stu-id="f0b11-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f0b11-113">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="f0b11-113">UI Reference</span></span>

<span data-ttu-id="f0b11-114">As listas a seguir descrevem os menus, comando, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="f0b11-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="f0b11-115">**Novo** Você pode criar uma configuração de versão do cliente para um site específico.</span><span class="sxs-lookup"><span data-stu-id="f0b11-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="f0b11-116">**Editar** Você pode alterar as opções de qualquer uma das políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="f0b11-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="f0b11-117">Com essa opção, é possível fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f0b11-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="f0b11-118">**Mostrar detalhes** Essa opção abre uma caixa de diálogo na qual você pode alterar as opções de uma configuração de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="f0b11-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="f0b11-119">**Selecionar tudo** Essa opção seleciona todas as configurações de versão do cliente na lista.</span><span class="sxs-lookup"><span data-stu-id="f0b11-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="f0b11-120">**Excluir** Esta opção exclui todas as configurações de versão do cliente selecionadas.</span><span class="sxs-lookup"><span data-stu-id="f0b11-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="f0b11-121">**Atualização** Você pode atualizar a lista de configuração de versão do cliente para verificar o status das opções de todas as configurações de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="f0b11-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="f0b11-p104">Para obter detalhes sobre a interoperabilidade entre clientes e versões de clientes, consulte [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) na documentação Planejamento. Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="f0b11-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

