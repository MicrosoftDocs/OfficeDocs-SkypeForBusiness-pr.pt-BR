---
title: Configuração de Reunião
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: Definições de configuração de reunião definem o tipo de conferências (também calledmeetings) que os usuários podem criar e controlar como (ou se) usuários anônimos e usuários de conferência discada podem participar dessas conferências. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam à reuniões ad-hoc criadas clicando na opção Reunir Agora no cliente.
ms.openlocfilehash: 1318f2eee75809e736ce04af01eb2f2563b86f0f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="meeting-configuration"></a><span data-ttu-id="47746-105">Configuração de Reunião</span><span class="sxs-lookup"><span data-stu-id="47746-105">Meeting Configuration</span></span>
 
<span data-ttu-id="47746-p102">As definições de configuração de reunião definem os tipos de conferências (também chamadas de "reuniões") criados pelos usuários e controlam como (ou se) os usuários anônimos e os usuários de conferência discada podem ingressar nessas conferências. Essas configurações se aplicam apenas às reuniões agendadas. Elas não se aplicam à reuniões ad-hoc criadas clicando na opção Reunir Agora no cliente.</span><span class="sxs-lookup"><span data-stu-id="47746-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span> 
  
<span data-ttu-id="47746-109">As configurações de reunião se aplicam no nível global, do site ou do pool:</span><span class="sxs-lookup"><span data-stu-id="47746-109">Meeting configurations apply on the global, site, or pool level:</span></span>
  
- <span data-ttu-id="47746-110">**Configuração de reunião global:** A configuração de reunião global criada por padrão.</span><span class="sxs-lookup"><span data-stu-id="47746-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="47746-111">É possível editar a configuração de reunião global, mas não é possível excluí-la.</span><span class="sxs-lookup"><span data-stu-id="47746-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="47746-112">Se você tentar remover a configuração de reunião global, todas as configurações serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="47746-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="47746-113">**Configuração de reunião de site (opcional):** Você pode criar um ou mais sites configurações de reunião, cada um deles se aplica a um site específico.</span><span class="sxs-lookup"><span data-stu-id="47746-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="47746-114">As configurações de site substituem a configuração global.</span><span class="sxs-lookup"><span data-stu-id="47746-114">Site configurations override the global configuration.</span></span>
    
- <span data-ttu-id="47746-115">**Configuração de reunião de pool (opcional):** Você pode criar um ou mais pool configurações de reunião, cada um deles se aplica a um pool específico.</span><span class="sxs-lookup"><span data-stu-id="47746-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="47746-116">As configurações de pool substituem a configuração global e as configurações de site.</span><span class="sxs-lookup"><span data-stu-id="47746-116">Pool configurations override the global configuration and site configurations.</span></span>
    
<span data-ttu-id="47746-117">A página  **Configuração de Reunião** exibe uma lista de todas as configurações de reunião definidas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="47746-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="47746-118">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="47746-118">Tasks you can perform</span></span>

<span data-ttu-id="47746-119">É possível executar as seguintes tarefas na página **Configuração de Reunião**:</span><span class="sxs-lookup"><span data-stu-id="47746-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>
  
- <span data-ttu-id="47746-120">Criar uma nova configuração de reunião de site ou configuração de reunião de pool</span><span class="sxs-lookup"><span data-stu-id="47746-120">Create a new site meeting configuration or pool meeting configuration</span></span>
    
- <span data-ttu-id="47746-121">Alterar a configuração global ou uma configuração de site ou de pool existente</span><span class="sxs-lookup"><span data-stu-id="47746-121">Change the global configuration or an existing site configuration or pool configuration</span></span>
    
- <span data-ttu-id="47746-122">Excluir uma configuração de site ou configuração de pool</span><span class="sxs-lookup"><span data-stu-id="47746-122">Delete a site configuration or pool configuration</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="47746-123">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="47746-123">UI Reference</span></span>

<span data-ttu-id="47746-124">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="47746-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="47746-125">**Novo** Inicia uma nova configuração de reunião de site ou configuração de reunião de pool.</span><span class="sxs-lookup"><span data-stu-id="47746-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>
    
- <span data-ttu-id="47746-126">**Editar** Abre a configuração de reunião selecionada para editá-la, seleciona todas as configurações de reunião na lista ou exclui a configuração de site selecionado ou configuração de pool.</span><span class="sxs-lookup"><span data-stu-id="47746-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47746-127">Para a configuração de reunião global,  **Excluir** redefine as configurações para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="47746-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="47746-128">**Atualizar** Atualiza a lista de configurações de reunião.</span><span class="sxs-lookup"><span data-stu-id="47746-128">**Refresh** Refreshes the list of meeting configurations.</span></span>
    
<span data-ttu-id="47746-129">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="47746-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="47746-130">**Nome** Identifica a configuração de reunião.</span><span class="sxs-lookup"><span data-stu-id="47746-130">**Name** Identifies the meeting configuration.</span></span>
    
- <span data-ttu-id="47746-131">**Escopo** Identifica o escopo da configuração de reunião: global, site ou pool.</span><span class="sxs-lookup"><span data-stu-id="47746-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>
    
<span data-ttu-id="47746-132">Para obter detalhes sobre como trabalhar com configurações de reunião, consulte [criar uma ou modificar um conjunto de definições de configuração do reunião](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="47746-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>
  

