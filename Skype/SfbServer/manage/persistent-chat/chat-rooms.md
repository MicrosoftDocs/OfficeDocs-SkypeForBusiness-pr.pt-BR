---
title: Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumo: Saiba como gerenciar salas de chat Persistent Chat Server Skype para Business Server 2015.'
ms.openlocfilehash: 7febc9736f43f3168d7bc62b0ddf833fa6b5864b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569397"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="8cef7-103">Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8cef7-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8cef7-104">**Resumo:** Saiba como gerenciar salas de chat Persistent Chat Server Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="8cef7-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8cef7-105">Criar e gerenciar sala de chat é mais fácil com o uso correto de categorias.</span><span class="sxs-lookup"><span data-stu-id="8cef7-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="8cef7-106">Uma categoria define quem pode criar ou ingressar em salas de chat.</span><span class="sxs-lookup"><span data-stu-id="8cef7-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="8cef7-107">Antes de tentar gerenciar salas de bate-papo, não deixe de ler [as categorias de chat persistente, salas de bate-papo e funções de usuário no Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e [Gerenciar categorias no servidor de bate-papo persistente no Skype para Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="8cef7-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
<span data-ttu-id="8cef7-108">Você pode configurar e gerenciar salas de bate-papo por meio da interface de linha de comando do Windows PowerShell, ou usando o Skype para o cliente de negócios, se você é um membro da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="8cef7-108">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="8cef7-109">Esse tópico descreve como gerenciar salas de chat usando a interface de linha de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8cef7-109">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="8cef7-110">Se você deseja gerenciar salas de chat usando o Skype para cliente corporativos, consulte a Ajuda do cliente.</span><span class="sxs-lookup"><span data-stu-id="8cef7-110">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="8cef7-111">Salas de chat pode ser um dos dois tipos: Normal e auditório.</span><span class="sxs-lookup"><span data-stu-id="8cef7-111">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="8cef7-112">Uma sala Normal permite que todos os membros publiquem e leiam mensagens.</span><span class="sxs-lookup"><span data-stu-id="8cef7-112">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="8cef7-113">Uma sala Auditório permite que apenas Apresentadores publiquem, mas todos podem ler.</span><span class="sxs-lookup"><span data-stu-id="8cef7-113">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="8cef7-114">Quem pode acessar e gerenciar as salas de chat depende das funções de usuários, conforme o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8cef7-114">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="8cef7-115">Os usuários devem ser Membros de uma sala de chat para poderem publicar e ler mensagens.</span><span class="sxs-lookup"><span data-stu-id="8cef7-115">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="8cef7-116">Os Apresentadores podem publicar nas salas Auditório.</span><span class="sxs-lookup"><span data-stu-id="8cef7-116">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="8cef7-117">Os administradores podem excluir qualquer conteúdo (por exemplo, conteúdo publicado antes de determinada data) de qualquer sala de chat para impedir que o banco de dados assuma proporções muito grandes.</span><span class="sxs-lookup"><span data-stu-id="8cef7-117">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="8cef7-118">Eles também podem remover ou substituir mensagens consideradas impróprias para uma sala de chat específica.</span><span class="sxs-lookup"><span data-stu-id="8cef7-118">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="8cef7-119">Os usuários finais, inclusive os autores das mensagens, não podem excluir conteúdo de nenhuma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="8cef7-119">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="8cef7-120">Os Gerentes de sala de chat podem fazer alterações em todas as propriedades da sala de chat, incluindo desabilitar salas.</span><span class="sxs-lookup"><span data-stu-id="8cef7-120">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="8cef7-121">No entanto, eles não podem excluir uma sala nem alterar a categoria dela.</span><span class="sxs-lookup"><span data-stu-id="8cef7-121">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="8cef7-122">Somente os administradores podem excluir salas de chat após a criação.</span><span class="sxs-lookup"><span data-stu-id="8cef7-122">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="8cef7-123">Você pode configurar e gerenciar salas de chat usando os seguintes cmdlets do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8cef7-123">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="8cef7-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="8cef7-124">**Cmdlet**</span></span>|<span data-ttu-id="8cef7-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8cef7-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8cef7-126">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="8cef7-126">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8cef7-127">Cria uma nova sala de chat</span><span class="sxs-lookup"><span data-stu-id="8cef7-127">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="8cef7-128">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="8cef7-128">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8cef7-129">Definir configurações para salas existentes; atribuir usuários e grupos de usuários para a sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-129">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="8cef7-130">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="8cef7-130">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8cef7-131">Recuperar informações sobre salas</span><span class="sxs-lookup"><span data-stu-id="8cef7-131">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="8cef7-132">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="8cef7-132">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8cef7-133">Limpar uma sala ou as mensagens de uma sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-133">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="8cef7-134">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="8cef7-134">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="8cef7-135">Remover uma sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-135">Remove a room</span></span>  <br/> |
|<span data-ttu-id="8cef7-136">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="8cef7-136">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="8cef7-137">Remover mensagens de uma sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-137">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="8cef7-138">Use o cmdlet **New-CsPersistentChatRoom** para criar salas de chat e o cmdlet **Set-CsPersistentChatRoom** para configurar uma sala de chat existente, incluindo a adição de usuários à sala de chat.</span><span class="sxs-lookup"><span data-stu-id="8cef7-138">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="8cef7-139">Você pode configurar os seguintes parâmetros para as salas de chat:</span><span class="sxs-lookup"><span data-stu-id="8cef7-139">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="8cef7-140">Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="8cef7-140">Disabled.</span></span> <span data-ttu-id="8cef7-141">Permite desabilitar ou habilitar uma sala de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="8cef7-141">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="8cef7-142">Convites.</span><span class="sxs-lookup"><span data-stu-id="8cef7-142">Invitations.</span></span> <span data-ttu-id="8cef7-143">Permite que você habilite ou desabilite os convites da sala de chat, que são usados para notificar usuários quando eles forem adicionados como membros de uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="8cef7-143">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="8cef7-144">A configuração padrão para convites é herdada, o que faz com que a sala de chat adote a configuração de convite definida na categoria que ela pertence.</span><span class="sxs-lookup"><span data-stu-id="8cef7-144">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="8cef7-145">Definir as configurações de convite para falso no nível da sala de chat permite que a configuração da categoria seja substituída.</span><span class="sxs-lookup"><span data-stu-id="8cef7-145">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="8cef7-146">Privacidade.</span><span class="sxs-lookup"><span data-stu-id="8cef7-146">Privacy.</span></span> <span data-ttu-id="8cef7-147">Permite que você especifique se uma sala de chat é Aberta, Fechada ou Secreta.</span><span class="sxs-lookup"><span data-stu-id="8cef7-147">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="8cef7-148">Salas abertas podem ser pesquisadas e acessadas por qualquer pessoa.</span><span class="sxs-lookup"><span data-stu-id="8cef7-148">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="8cef7-149">Salas fechadas podem ser pesquisadas por qualquer pessoa, mas podem ser acessadas apenas por membros.</span><span class="sxs-lookup"><span data-stu-id="8cef7-149">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="8cef7-150">Salas secretas podem ser pesquisadas e acessadas apenas por membros da sala.</span><span class="sxs-lookup"><span data-stu-id="8cef7-150">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="8cef7-151">Por padrão, cada nova sala é configurada inicialmente como Fechada.</span><span class="sxs-lookup"><span data-stu-id="8cef7-151">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="8cef7-152">Tipo.</span><span class="sxs-lookup"><span data-stu-id="8cef7-152">Type.</span></span> <span data-ttu-id="8cef7-153">Permite especificar se uma sala de bate-papo é uma sala Normal, que aceita as mensagens postadas por qualquer membro ou uma sala de auditório, que aceita as mensagens postadas apenas por um apresentador.</span><span class="sxs-lookup"><span data-stu-id="8cef7-153">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="8cef7-154">Suplemento.</span><span class="sxs-lookup"><span data-stu-id="8cef7-154">Addin.</span></span> <span data-ttu-id="8cef7-155">Permite que você associe um suplemento configurado anteriormente à uma sala de chat, fazendo com que o conteúdo da URL seja visualizado por membros durante suas participações.</span><span class="sxs-lookup"><span data-stu-id="8cef7-155">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="8cef7-156">Além de parâmetros acima, o cmdlet **Set-CsPersistentChatRoom** permite atribuir usuários a sala de bate-papo da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="8cef7-156">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="8cef7-157">Membros.</span><span class="sxs-lookup"><span data-stu-id="8cef7-157">Members.</span></span> <span data-ttu-id="8cef7-158">Configura a associação para a sala de chat.</span><span class="sxs-lookup"><span data-stu-id="8cef7-158">Configures membership for the chat room.</span></span> <span data-ttu-id="8cef7-159">Você pode adicionar ou remover um ou vários membros usando um único cmdlet especificando o endereço SIP dos usuários.</span><span class="sxs-lookup"><span data-stu-id="8cef7-159">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="8cef7-160">Para permitir que os usuários sejam adicionados em massa, os grupos de distribuição ou as unidades organizacionais do Active Directory também podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="8cef7-160">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="8cef7-161">Gerentes.</span><span class="sxs-lookup"><span data-stu-id="8cef7-161">Managers.</span></span> <span data-ttu-id="8cef7-162">Permite que você atribua gerentes para a sala de chat.</span><span class="sxs-lookup"><span data-stu-id="8cef7-162">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="8cef7-163">Os gerentes têm permissões para definir a associação de uma sala de chat, além de outras configurações.</span><span class="sxs-lookup"><span data-stu-id="8cef7-163">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="8cef7-p114">Apresentadores. Permite que você atribua apresentadores para uma sala de chat tipo Auditório.</span><span class="sxs-lookup"><span data-stu-id="8cef7-p114">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="8cef7-166">Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros, consulte [Skype do Shell de gerenciamento do Business Server 2015](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="8cef7-166">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="8cef7-167">Criar uma nova sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-167">Create a new room</span></span>

<span data-ttu-id="8cef7-168">Você pode criar uma nova sala usando o cmdlet **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="8cef7-168">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="8cef7-169">Por exemplo, o comando a seguir cria uma nova sala de chat chamada ITChatRoom no pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8cef7-169">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="8cef7-170">Neste exemplo, a sala de chat é adicionada à categoria de TI:</span><span class="sxs-lookup"><span data-stu-id="8cef7-170">In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="8cef7-171">**Observação:** PersistentChatPoolFqdn não é necessário se uma das opções a seguir for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="8cef7-171">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="8cef7-172">Não há somente um pool do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="8cef7-172">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="8cef7-173">Você oferece um FQDN do pool para a categoria.</span><span class="sxs-lookup"><span data-stu-id="8cef7-173">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="8cef7-174">Você oferece um FQDN do pool para adicionar a sala.</span><span class="sxs-lookup"><span data-stu-id="8cef7-174">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="8cef7-175">Configurar uma sala existente</span><span class="sxs-lookup"><span data-stu-id="8cef7-175">Configure an existing room</span></span>

<span data-ttu-id="8cef7-176">Você pode configurar uma sala existente usando o cmdlet **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="8cef7-176">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="8cef7-177">Por exemplo, o comando a seguir atribui user1 como um membro e o apresentador e user2 como gerente, da sala de auditório testCat:</span><span class="sxs-lookup"><span data-stu-id="8cef7-177">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="8cef7-178">O próximo exemplo adiciona todos os usuários da UO NorthAmericaUsers no Active Directory à sala de chat NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="8cef7-178">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="8cef7-179">O próximo exemplo adiciona todos os membros do grupo de distribuição Finanças à mesma sala de chat:</span><span class="sxs-lookup"><span data-stu-id="8cef7-179">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="8cef7-180">Habilitar ou desabilitar uma sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-180">Disable or enable a room</span></span>

<span data-ttu-id="8cef7-181">Se o tópico de uma sala de bate-papo persistente não for mais relevante, você pode fazer a sala de bate-papo indisponível aos usuários por desabilitá-la.</span><span class="sxs-lookup"><span data-stu-id="8cef7-181">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="8cef7-182">Quando uma sala de chat está desabilitada, todos os membros são desconectados imediatamente da sala.</span><span class="sxs-lookup"><span data-stu-id="8cef7-182">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="8cef7-183">Após uma sala de chat ser desabilitada, os usuários não podem participar novamente ou encontrá-la nas pesquisas de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="8cef7-183">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="8cef7-184">Se o histórico da sala de chat persistir, o conteúdo é preservado quando a sala de chat estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="8cef7-184">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="8cef7-185">Entretanto, o conteúdo não será exibido nas pesquisas durante o tempo em que a sala de chat permanecer no estado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="8cef7-185">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="8cef7-186">Se você habilitá-la mais tarde, os usuários poderão pesquisar mensagens que foram publicadas antes da sala de chat ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="8cef7-186">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="8cef7-187">Para obter informações sobre como configurar o histórico da sala de bate-papo, consulte [Gerenciar categorias no servidor de bate-papo persistente no Skype para Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="8cef7-187">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="8cef7-188">Se uma sala de chat for desabilitada, sua lista de associação e outras configurações serão preservadas.</span><span class="sxs-lookup"><span data-stu-id="8cef7-188">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="8cef7-189">Como administrador, você poderá habilitar uma sala que está desabilitada, e não é necessário criar as configurações novamente de maneira manual.</span><span class="sxs-lookup"><span data-stu-id="8cef7-189">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="8cef7-190">Você pode desabilitar uma sala usando o cmdlet **Set-CsPersistentChatRoom** e definindo o parâmetro desabilitado como True:</span><span class="sxs-lookup"><span data-stu-id="8cef7-190">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="8cef7-191">Para habilitar uma sala de chat, defina o parâmetro Disabled para False:</span><span class="sxs-lookup"><span data-stu-id="8cef7-191">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="8cef7-192">Obtenha informações sobre salas</span><span class="sxs-lookup"><span data-stu-id="8cef7-192">Get information about rooms</span></span>

<span data-ttu-id="8cef7-193">Para obter informações sobre as salas configuradas para uso em sua organização, você pode usar o cmdlet **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="8cef7-193">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="8cef7-194">O comando a seguir retorna informações sobre todas as salas de chat configuradas para uso na organização:</span><span class="sxs-lookup"><span data-stu-id="8cef7-194">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="8cef7-195">Remover todo o conteúdo de uma sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-195">Remove all content from a room</span></span>

<span data-ttu-id="8cef7-p120">Você pode remover o conteúdo de uma sala usando o cmdlet **Clear-CsPersistentChatRoom**. Por exemplo, o comando a seguir remove todo o conteúdo da sala de Chat Persistente ITChatRoom, que foi adicionado à sala em ou antes de 1º de março de 2015:</span><span class="sxs-lookup"><span data-stu-id="8cef7-p120">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="8cef7-198">Remover uma mensagem de uma sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-198">Remove a message from a room</span></span>

<span data-ttu-id="8cef7-p121">Você pode remover uma ou mais mensagens no banco de dados de Chat Persistente e, como opção, substituir a mensagem com uma mensagem padrão ou com uma mensagem fornecida pelo administrador por meio do cmdlet **Remove-CsPersistentChatMessage**. Por exemplo, o comando a seguir remove todas as mensagens da sala de chat ITChatRoom que foram publicadas pelo usuário kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="8cef7-p121">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="8cef7-201">O próximo exemplo substitui as mensagens removidas pela observação de que a mensagem não está mais disponível:</span><span class="sxs-lookup"><span data-stu-id="8cef7-201">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="8cef7-202">Remover uma sala</span><span class="sxs-lookup"><span data-stu-id="8cef7-202">Remove a room</span></span>

<span data-ttu-id="8cef7-203">Você pode remover uma sala usando o cmdlet **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="8cef7-203">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="8cef7-204">Por exemplo, o comando a seguir remove a sala de chat RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="8cef7-204">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="8cef7-205">Mover uma sala de uma categoria para outra</span><span class="sxs-lookup"><span data-stu-id="8cef7-205">Move a room from one category to another</span></span>

<span data-ttu-id="8cef7-p122">Se um gerente de sala de chat tem privilégios de **Criador** em outra categoria, ele ou ela pode mover a sala de uma categoria para outra. A sala não é excluída nem recriada. É uma alteração de associação dentro do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8cef7-p122">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="8cef7-p123">Mudar a categoria de uma sala de chat deve ser feito raramente e com cuidado. Uma categoria determina a associação permitida para a sala de chat, por isso, quando uma sala de chat muda de categoria, todas as listas de controle de acesso do sistema (SACLs) não mais suportadas pela nova categoria são purgadas. Por exemplo, se um usuário for membro da sala e não mais um Membro permitido na nova categoria, a associação da sala será modificada e o usuário será removido da sala.</span><span class="sxs-lookup"><span data-stu-id="8cef7-p123">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

