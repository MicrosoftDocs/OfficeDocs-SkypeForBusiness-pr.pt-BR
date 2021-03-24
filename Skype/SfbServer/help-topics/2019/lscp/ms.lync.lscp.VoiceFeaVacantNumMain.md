---
title: Número de Telefone Não Atribuído
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: 135072c7128ac14e4073e95297fa2b5e4e1a8e5a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097037"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="f04be-104">Número de Telefone Não Atribuído</span><span class="sxs-lookup"><span data-stu-id="f04be-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="f04be-105">A UM do Exchange permanece disponível no Skype for Business Server 2019 quando você integra o Skype for Business 2019 com o Exchange 2013 ou o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="f04be-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="f04be-106">Devido às alterações no suporte no Exchange 2019, a integração da UM do Exchange está sendo desalmada em favor dos recursos de Cloud Voicemail e Cloud Atendedor Automático.</span><span class="sxs-lookup"><span data-stu-id="f04be-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="f04be-p103">Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="f04be-p104">O modo como você configura a tabela de números não atribuídos depende de como você deseja usá-la. É possível configurar a tabela com todas as extensões válidas para sua organização, com apenas extensões não atribuídas ou com uma combinação dos dois tipos de números. A tabela de números não atribuídos pode incluir números atribuídos e não atribuídos, mas é invocada somente quando um chamador disca um número que não está atribuído no momento. Se você incluir todas as extensões válidas na tabela de números não atribuídos, será possível especificar a ação que ocorre quando alguém deixa sua organização, sem precisar reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, poderá personalizar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu serviço de atendimento ao consumidor, poderá incluir o número antigo do serviço de atendimento ao consumidor na tabela e atribuí-lo a um anúncio que fornece o novo número.</span><span class="sxs-lookup"><span data-stu-id="f04be-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f04be-115">Antes de configurar a tabela de números atribuídos, você já precisa ter definido um ou mais anúncios ou configurar um Atendedor Automático do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f04be-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="f04be-116">A página **Número Não Atribuído** exibe uma lista de números não atribuídos definidos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f04be-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f04be-117">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="f04be-117">Tasks you can perform</span></span>

<span data-ttu-id="f04be-118">É possível executar as seguintes tarefas na página **Número Não Atribuído**:</span><span class="sxs-lookup"><span data-stu-id="f04be-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="f04be-119">Criar um novo intervalo de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="f04be-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="f04be-120">Alterar um intervalo de números não atribuídos existente</span><span class="sxs-lookup"><span data-stu-id="f04be-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="f04be-121">Excluir um intervalo de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="f04be-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="f04be-122">Alterar a ordem dos intervalos de números não atribuídos a fim de determinar qual ação deve ser aplicada primeiro a uma chamada de entrada que corresponde a um número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="f04be-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f04be-123">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="f04be-123">UI Reference</span></span>

<span data-ttu-id="f04be-124">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="f04be-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="f04be-125">**Novo** Inicia um novo intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="f04be-126">**Editar** Abre o intervalo de números não atribuídos selecionado para edição, seleciona todos os intervalos de números não atribuídos na lista ou exclui o intervalo de números não atribuídos selecionado.</span><span class="sxs-lookup"><span data-stu-id="f04be-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="f04be-127">**Mover para cima** Move o intervalo de números não atribuídos selecionado para cima na lista para que o Skype for Business Server o encontre mais cedo e aplique a ação especificada antes de aplicar ações especificadas para outros intervalos na lista.</span><span class="sxs-lookup"><span data-stu-id="f04be-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f04be-128">O Skype for Business Server pesquisa a tabela de números não atribuídos de cima para baixo e usa o primeiro intervalo que corresponde ao número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="f04be-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="f04be-129">Por exemplo, se você tiver um intervalo que especifica uma ação de última instância, certifique-se de que o intervalo esteja no final da lista.</span><span class="sxs-lookup"><span data-stu-id="f04be-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="f04be-130">**Mover para baixo** Move o intervalo de números não atribuídos selecionado para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="f04be-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="f04be-131">**Commit all** Salva todas as alterações feitas em intervalos de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f04be-132">Esse comando salva todas as alterações feitas na página **Novo Número Não Atribuído** e na página **Editar Número Não Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="f04be-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="f04be-133">**Atualizar** Atualiza a lista de intervalos de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="f04be-134">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="f04be-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="f04be-135">**Nome** O nome exclusivo que identifica o intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="f04be-136">**Estado** Mostra quais intervalos de números foram salvos no banco de dados e quais não foram.</span><span class="sxs-lookup"><span data-stu-id="f04be-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="f04be-137">**Intervalo inicial** O número inicial do intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="f04be-138">**Intervalo final** O número final do intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="f04be-139">**Destination** A ID de serviço do serviço application que hospeda o aplicativo Comunicado que tratará de chamadas de entrada para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="f04be-140">**Comunicado** O comunicado que será tocado para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="f04be-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="f04be-141">Para obter detalhes sobre recursos e recursos do Comunicado, consulte [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação planejamento.</span><span class="sxs-lookup"><span data-stu-id="f04be-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="f04be-142">Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="f04be-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) in the Operations documentation.</span></span>