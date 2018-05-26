---
title: Número de Telefone Não Atribuído
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.
ms.openlocfilehash: d145b3ed7e55404e3763e0bdf65ae467a000c180
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2018
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="66fae-104">Número de Telefone Não Atribuído</span><span class="sxs-lookup"><span data-stu-id="66fae-104">Unassigned Phone Number</span></span>
 
<span data-ttu-id="66fae-p102">Números não atribuídos são números de telefone válidos para sua organização, mas que não são atribuídos a um usuário ou telefone. A tabela de números não atribuídos identifica como você deseja lidar com chamadas para números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="66fae-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>
  
<span data-ttu-id="66fae-p103">Como configurar a tabela de números não atribuídos dependerá de como você deseja usá-la. Você pode configurar a tabela com todas as extensões válidas para a sua organização, somente com extensões não atribuídas ou com uma combinação de ambos os tipos de números. A tabela de números não atribuídos pode incluir ambos, números atribuídos e não atribuídos, mas será invocada somente quando um chamador discar um número que não esteja atribuído atualmente. Se você incluir todas as extensões válidas na tabela de números não atribuídos, pode especificar a ação que ocorre sempre que alguém sair da sua organização, sem a necessidade de reconfigurar a tabela. Se você incluir extensões não atribuídas na tabela, pode ajustar a ação que ocorre para números específicos. Por exemplo, se você alterar a extensão para seu serviço de atendimento ao cliente, poderá incluir o número do atendimento ao cliente antigo na tabela e atribuí-lo a um comunicado que fornece o novo número.</span><span class="sxs-lookup"><span data-stu-id="66fae-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="66fae-113">Antes de configurar a tabela de números atribuídos, você já precisa ter definido um ou mais anúncios ou configurado um Atendedor Automático do UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="66fae-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span> 
  
<span data-ttu-id="66fae-114">A página **Número Não Atribuído** exibe uma lista de números não atribuídos definidos para sua organização.</span><span class="sxs-lookup"><span data-stu-id="66fae-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="66fae-115">Tarefas que podem ser executadas</span><span class="sxs-lookup"><span data-stu-id="66fae-115">Tasks you can perform</span></span>

<span data-ttu-id="66fae-116">É possível executar as seguintes tarefas na página **Número Não Atribuído**:</span><span class="sxs-lookup"><span data-stu-id="66fae-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>
  
- <span data-ttu-id="66fae-117">Criar um novo intervalo de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="66fae-117">Create a new unassigned number range</span></span>
    
- <span data-ttu-id="66fae-118">Alterar um intervalo de números não atribuídos existente</span><span class="sxs-lookup"><span data-stu-id="66fae-118">Change an existing unassigned number range</span></span>
    
- <span data-ttu-id="66fae-119">Excluir um intervalo de números não atribuídos</span><span class="sxs-lookup"><span data-stu-id="66fae-119">Delete an unassigned number range</span></span>
    
- <span data-ttu-id="66fae-120">Alterar a ordem dos intervalos de números não atribuídos a fim de determinar qual ação deve ser aplicada primeiro a uma chamada de entrada que corresponde a um número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="66fae-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span> 
    
## <a name="ui-reference"></a><span data-ttu-id="66fae-121">Referência de UI</span><span class="sxs-lookup"><span data-stu-id="66fae-121">UI Reference</span></span>

<span data-ttu-id="66fae-122">A lista a seguir descreve os comandos na página.</span><span class="sxs-lookup"><span data-stu-id="66fae-122">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="66fae-123">**Novo** Inicia um novo intervalo de números não atribuído.</span><span class="sxs-lookup"><span data-stu-id="66fae-123">**New** Starts a new unassigned number range.</span></span>
    
- <span data-ttu-id="66fae-124">**Editar** Abre o intervalo de números não atribuído selecionado para edição, seleciona todos os intervalos de números não atribuídos na lista ou exclui o intervalo de números não atribuído selecionado.</span><span class="sxs-lookup"><span data-stu-id="66fae-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>
    
- <span data-ttu-id="66fae-125">**Mover para cima** Move o intervalo de números não atribuído selecionado para cima na lista, de forma que Skype para Business Server localiza-lo com antecedência e aplica-se a ação especificada antes de aplicar as ações especificadas para outros intervalos na lista.</span><span class="sxs-lookup"><span data-stu-id="66fae-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66fae-126">Skype para Business Server procura na tabela de número não atribuída de cima para baixo e usa o primeiro intervalo que corresponde ao número não atribuído.</span><span class="sxs-lookup"><span data-stu-id="66fae-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="66fae-127">Por exemplo, se você tiver um intervalo que especifica uma ação de última instância, certifique-se de que o intervalo esteja no final da lista.</span><span class="sxs-lookup"><span data-stu-id="66fae-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span> 
  
- <span data-ttu-id="66fae-128">**Mover para baixo** Move o intervalo de números não atribuído selecionado para baixo na lista.</span><span class="sxs-lookup"><span data-stu-id="66fae-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>
    
- <span data-ttu-id="66fae-129">**Confirmar tudo** Salva todas as alterações feitas a intervalos de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="66fae-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="66fae-130">Esse comando salva todas as alterações feitas na página  **Novo Número Não Atribuído** e na página **Editar Número Não Atribuído**.</span><span class="sxs-lookup"><span data-stu-id="66fae-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>
  
- <span data-ttu-id="66fae-131">**Atualizar** Atualiza a lista de intervalos de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="66fae-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>
    
<span data-ttu-id="66fae-132">A lista a seguir descreve os campos na página.</span><span class="sxs-lookup"><span data-stu-id="66fae-132">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="66fae-133">**Nome** O nome exclusivo que identifica o intervalo de números não atribuído.</span><span class="sxs-lookup"><span data-stu-id="66fae-133">**Name** The unique name that identifies the unassigned number range.</span></span>
    
- <span data-ttu-id="66fae-134">**Estado** Mostra quais intervalos de números foram salvos para o banco de dados e quais não foram.</span><span class="sxs-lookup"><span data-stu-id="66fae-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>
    
- <span data-ttu-id="66fae-135">**Intervalo inicial** O número inicial do intervalo de números não atribuído.</span><span class="sxs-lookup"><span data-stu-id="66fae-135">**Start range** The beginning number of the unassigned number range.</span></span>
    
- <span data-ttu-id="66fae-136">**Intervalo final** O número final do intervalo de números não atribuído.</span><span class="sxs-lookup"><span data-stu-id="66fae-136">**End range** The ending number of the unassigned number range.</span></span>
    
- <span data-ttu-id="66fae-137">**Destino** A ID de serviço do serviço aplicativo que hospeda o aplicativo de anúncio que lidará com as chamadas de entrada para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="66fae-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>
    
- <span data-ttu-id="66fae-138">**Comunicado** O comunicado que será reproduzido para esse intervalo de números não atribuídos.</span><span class="sxs-lookup"><span data-stu-id="66fae-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>
    
<span data-ttu-id="66fae-139">Para obter detalhes sobre o comunicado recursos e capacidades, consulte o [plano para o aplicativo de anúncio no Skype para negócios 2015](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="66fae-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="66fae-140">Para obter detalhes sobre como trabalhar com intervalos de números não atribuídos, consulte [Configurar o roteamento de números não atribuídos telefone](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="66fae-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>
  

