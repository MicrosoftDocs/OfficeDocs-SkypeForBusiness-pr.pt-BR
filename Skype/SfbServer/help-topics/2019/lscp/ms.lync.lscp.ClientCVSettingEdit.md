---
title: Configuração de Versão de Cliente Criar Nova ou Editar Existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão do cliente global é instalada com o Skype for Business Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor. Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon. É possível desabilitar a configuração da versão do cliente Global se não quiser que qualquer controle de versão de cliente ocorra.
ms.openlocfilehash: e42d2c9e6d06bc72cd64de148454d28aab41483d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812361"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a><span data-ttu-id="94d25-106">Configuração da Versão de Cliente: Criar Nova ou Editar Existente</span><span class="sxs-lookup"><span data-stu-id="94d25-106">Client Version Configuration: Create New or Edit Existing</span></span>

<span data-ttu-id="94d25-107">As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="94d25-107">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="94d25-108">A configuração de versão do cliente global é instalada com o Skype for Business Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor.</span><span class="sxs-lookup"><span data-stu-id="94d25-108">The Global client version configuration installs with Skype for Business Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="94d25-109">Quando a configuração Global é habilitada, quaisquer políticas de versão do cliente existentes entrarão em vigor quando os usuários tentarem fazer logon.</span><span class="sxs-lookup"><span data-stu-id="94d25-109">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="94d25-110">É possível desabilitar a configuração da versão do cliente Global se não quiser que qualquer controle de versão de cliente ocorra.</span><span class="sxs-lookup"><span data-stu-id="94d25-110">You can disable the Global client version configuration if you do not want any client version control to occur.</span></span>

<span data-ttu-id="94d25-p103">Também é possível criar configurações de versão do cliente específicas do site, permitindo a habilitação ou desabilitação do controle de versão do cliente por site. A configuração específica do site tem precedência sobre a configuração Global.</span><span class="sxs-lookup"><span data-stu-id="94d25-p103">You can also create site-specific client version configurations, allowing you to enable or disable client version control by site. Site-specific configurations take precedence over the Global configuration.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="94d25-113">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="94d25-113">Tasks you can perform</span></span>

<span data-ttu-id="94d25-114">É possível executar as seguintes tarefas na página **Criar uma nova Configuração de Versão de Cliente** ou **Editar Configuração da Versão de Cliente**:</span><span class="sxs-lookup"><span data-stu-id="94d25-114">You can perform the following tasks on the **New Client Version Configuration** or **Edit Client Version Configuration** page:</span></span>

- <span data-ttu-id="94d25-115">Adicionar ou modificar o nome da configuração de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="94d25-115">Add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="94d25-116">Habilitar ou desabilitar o controle de versão do cliente globalmente ou para o site específico.</span><span class="sxs-lookup"><span data-stu-id="94d25-116">Enable or disable client version control globally or for the specific site.</span></span>

- <span data-ttu-id="94d25-117">Adicionar ou modificar a ação padrão da configuração de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="94d25-117">Add or modify the default action for the client version configuration.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="94d25-118">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="94d25-118">UI Reference</span></span>

<span data-ttu-id="94d25-119">As listas a seguir descrevem os menus, comando, campos e propriedades na página.</span><span class="sxs-lookup"><span data-stu-id="94d25-119">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="94d25-120">**Escopo** Identifica o escopo (Global ou Site) da configuração de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="94d25-120">**Scope** Identifies the scope (Global or Site) of the client version configuration.</span></span>

- <span data-ttu-id="94d25-121">**Nome** Você pode adicionar ou modificar o nome da configuração de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="94d25-121">**Name** You can add or modify the name of the client version configuration.</span></span>

- <span data-ttu-id="94d25-122">**Habilitar controle de versão** Você pode habilitar ou desabilitar o controle de versão do cliente globalmente ou para o site, dependendo do escopo da configuração.</span><span class="sxs-lookup"><span data-stu-id="94d25-122">**Enable version control** You can enable or disable client version control globally or for the site, depending on the scope of the configuration.</span></span>

- <span data-ttu-id="94d25-123">**Ação padrão** Você pode selecionar a ação padrão que será aplicada quando um usuário tentar fazer logoff usando um aplicativo cliente para o qual não há política de versão de cliente específica.</span><span class="sxs-lookup"><span data-stu-id="94d25-123">**Default action** You can select the default action that will be applied when a user attempts to log on using a client application for which there is no specific client version policy.</span></span> <span data-ttu-id="94d25-124">Você tem as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="94d25-124">You have the following options:</span></span>

  - <span data-ttu-id="94d25-125">**Permitir** Permite que o cliente faça logoff se a versão do cliente não corresponder a qualquer filtro na lista de políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="94d25-125">**Allow** Allows the client to log on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="94d25-126">**Bloquear** Impede que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de políticas de versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="94d25-126">**Block** Prevents the client from logging on if the client version does not match any filter in the client version policies list.</span></span>

  - <span data-ttu-id="94d25-127">**Bloquear com URL** Impede que o cliente faça logon se a versão do cliente não corresponder a qualquer filtro na lista de políticas de versão do cliente e inclui uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.</span><span class="sxs-lookup"><span data-stu-id="94d25-127">**Block with URL** Prevents the client from logging on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="94d25-128">**Permitir com URL** Permite que o cliente faça logoff se a versão do cliente não corresponder a qualquer filtro na lista de políticas de versão do cliente e inclui uma mensagem de erro contendo uma URL onde um cliente mais recente pode ser baixado.</span><span class="sxs-lookup"><span data-stu-id="94d25-128">**Allow with URL** Allows the client to log on if the client version does not match any filter in the client version policies list, and includes an error message containing a URL where a newer client can be downloaded.</span></span>

  - <span data-ttu-id="94d25-129">**URL** Se você **selecionou Bloquear com URL** ou Permitir com **URL,** poderá especificar a URL de download do cliente para incluir na mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="94d25-129">**URL** If you selected **Block with URL** or **Allow with URL**, you can specify the client download URL to include in the error message.</span></span>

<span data-ttu-id="94d25-130">Para obter detalhes sobre interoperabilidade entre clientes e versões de cliente, consulte [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="94d25-130">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="94d25-131">Para obter detalhes sobre como trabalhar com configurações de versão de cliente, consulte [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="94d25-131">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

