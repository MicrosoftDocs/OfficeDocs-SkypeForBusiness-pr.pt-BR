---
title: Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumo: saiba como gerenciar salas de chat do servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 91e8a2888a7c83e30f80160d8c2c1fbc2af542fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279344"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="e07f1-103">Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e07f1-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e07f1-104">**Resumo:** Saiba como gerenciar salas de chat do servidor de chat persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e07f1-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e07f1-105">Criar e gerenciar sala de chat é mais fácil com o uso correto de categorias.</span><span class="sxs-lookup"><span data-stu-id="e07f1-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="e07f1-106">Uma categoria define quem pode criar ou ingressar nas salas de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="e07f1-107">Antes de tentar gerenciar salas de chat, certifique-se de ler categorias de chat [persistente, salas de chat e funções de usuário no Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e [gerenciar categorias no servidor de chat persistente no Skype for Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="e07f1-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e07f1-108">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e07f1-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e07f1-109">A mesma funcionalidade está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e07f1-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="e07f1-110">Para obter mais informações, consulte [jornada do Skype for Business para o Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="e07f1-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="e07f1-111">Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e07f1-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="e07f1-112">Você pode configurar e gerenciar salas de chat usando a interface de linha de comando do Windows PowerShell ou usando o cliente Skype for Business se você for membro da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="e07f1-113">Esse tópico descreve como gerenciar salas de chat usando a interface de linha de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e07f1-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="e07f1-114">Se você quiser gerenciar salas de chat usando o cliente Skype for Business, consulte a ajuda do cliente.</span><span class="sxs-lookup"><span data-stu-id="e07f1-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="e07f1-115">As salas de chat podem ser um dos dois tipos: normal e Auditorium.</span><span class="sxs-lookup"><span data-stu-id="e07f1-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="e07f1-116">Uma sala Normal permite que todos os membros publiquem e leiam mensagens.</span><span class="sxs-lookup"><span data-stu-id="e07f1-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="e07f1-117">Uma sala Auditório permite que apenas Apresentadores publiquem, mas todos podem ler.</span><span class="sxs-lookup"><span data-stu-id="e07f1-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="e07f1-118">Quem pode acessar e gerenciar as salas de chat depende das funções de usuários, conforme o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e07f1-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="e07f1-119">Os usuários devem ser Membros de uma sala de chat para poderem publicar e ler mensagens.</span><span class="sxs-lookup"><span data-stu-id="e07f1-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="e07f1-120">Os Apresentadores podem publicar nas salas Auditório.</span><span class="sxs-lookup"><span data-stu-id="e07f1-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="e07f1-121">Os administradores podem excluir qualquer conteúdo (por exemplo, conteúdo publicado antes de determinada data) de qualquer sala de chat para impedir que o banco de dados assuma proporções muito grandes.</span><span class="sxs-lookup"><span data-stu-id="e07f1-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="e07f1-122">Eles também podem remover ou substituir mensagens consideradas impróprias para uma sala de chat específica.</span><span class="sxs-lookup"><span data-stu-id="e07f1-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="e07f1-123">Os usuários finais, inclusive os autores das mensagens, não podem excluir conteúdo de nenhuma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="e07f1-124">Os Gerentes de sala de chat podem fazer alterações em todas as propriedades da sala de chat, incluindo desabilitar salas.</span><span class="sxs-lookup"><span data-stu-id="e07f1-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="e07f1-125">No entanto, eles não podem excluir uma sala nem alterar a categoria dela.</span><span class="sxs-lookup"><span data-stu-id="e07f1-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="e07f1-126">Somente os administradores podem excluir salas de chat após a criação.</span><span class="sxs-lookup"><span data-stu-id="e07f1-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="e07f1-127">Você pode configurar e gerenciar salas de chat usando os seguintes cmdlets do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e07f1-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="e07f1-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e07f1-128">**Cmdlet**</span></span>|<span data-ttu-id="e07f1-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e07f1-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e07f1-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="e07f1-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e07f1-131">Cria uma nova sala de chat</span><span class="sxs-lookup"><span data-stu-id="e07f1-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="e07f1-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="e07f1-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e07f1-133">Definir configurações para salas existentes; atribuir usuários e grupos de usuários para a sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="e07f1-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="e07f1-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e07f1-135">Recuperar informações sobre salas</span><span class="sxs-lookup"><span data-stu-id="e07f1-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="e07f1-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="e07f1-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e07f1-137">Limpar uma sala ou as mensagens de uma sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="e07f1-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="e07f1-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="e07f1-139">Remover uma sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="e07f1-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="e07f1-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="e07f1-141">Remover mensagens de uma sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="e07f1-142">Use o cmdlet **New-CsPersistentChatRoom** para criar salas de chat e o cmdlet **Set-CsPersistentChatRoom** para configurar uma sala de chat existente, incluindo a adição de usuários à sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="e07f1-143">Você pode configurar os seguintes parâmetros para as salas de chat:</span><span class="sxs-lookup"><span data-stu-id="e07f1-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="e07f1-144">Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e07f1-144">Disabled.</span></span> <span data-ttu-id="e07f1-145">Permite que você desative ou ative uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="e07f1-146">Convites.</span><span class="sxs-lookup"><span data-stu-id="e07f1-146">Invitations.</span></span> <span data-ttu-id="e07f1-147">Permite que você habilite ou desabilite os convites da sala de chat, que são usados para notificar usuários quando eles forem adicionados como membros de uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="e07f1-148">A configuração padrão para convites é herdada, o que faz com que a sala de chat adote a configuração de convite definida na categoria que ela pertence.</span><span class="sxs-lookup"><span data-stu-id="e07f1-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="e07f1-149">Definir as configurações de convite para falso no nível da sala de chat permite que a configuração da categoria seja substituída.</span><span class="sxs-lookup"><span data-stu-id="e07f1-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="e07f1-150">Privacidade.</span><span class="sxs-lookup"><span data-stu-id="e07f1-150">Privacy.</span></span> <span data-ttu-id="e07f1-151">Permite que você especifique se uma sala de chat é Aberta, Fechada ou Secreta.</span><span class="sxs-lookup"><span data-stu-id="e07f1-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="e07f1-152">Salas abertas podem ser pesquisadas e acessadas por qualquer pessoa.</span><span class="sxs-lookup"><span data-stu-id="e07f1-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="e07f1-153">Salas fechadas podem ser pesquisadas por qualquer pessoa, mas podem ser acessadas apenas por membros.</span><span class="sxs-lookup"><span data-stu-id="e07f1-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="e07f1-154">Salas secretas podem ser pesquisadas e acessadas apenas por membros da sala.</span><span class="sxs-lookup"><span data-stu-id="e07f1-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="e07f1-155">Por padrão, cada nova sala é configurada inicialmente como Fechada.</span><span class="sxs-lookup"><span data-stu-id="e07f1-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="e07f1-156">Tipo.</span><span class="sxs-lookup"><span data-stu-id="e07f1-156">Type.</span></span> <span data-ttu-id="e07f1-157">Permite que você especifique se uma sala de chat é uma sala normal, que aceita mensagens publicadas por qualquer membro ou uma sala Auditorium, que aceita mensagens postadas apenas por um apresentador.</span><span class="sxs-lookup"><span data-stu-id="e07f1-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="e07f1-158">Suplemento.</span><span class="sxs-lookup"><span data-stu-id="e07f1-158">Addin.</span></span> <span data-ttu-id="e07f1-159">Permite que você associe um suplemento configurado anteriormente à uma sala de chat, fazendo com que o conteúdo da URL seja visualizado por membros durante suas participações.</span><span class="sxs-lookup"><span data-stu-id="e07f1-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="e07f1-160">Além dos parâmetros acima, o cmdlet **set-CsPersistentChatRoom** permite atribuir usuários à sala de chat da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e07f1-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="e07f1-161">Membros.</span><span class="sxs-lookup"><span data-stu-id="e07f1-161">Members.</span></span> <span data-ttu-id="e07f1-162">Configura a associação para a sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-162">Configures membership for the chat room.</span></span> <span data-ttu-id="e07f1-163">Você pode adicionar ou remover um ou vários membros usando um único cmdlet especificando o endereço SIP dos usuários.</span><span class="sxs-lookup"><span data-stu-id="e07f1-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="e07f1-164">Para permitir que os usuários sejam adicionados em massa, os grupos de distribuição ou as unidades organizacionais do Active Directory também podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="e07f1-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="e07f1-165">Gerentes.</span><span class="sxs-lookup"><span data-stu-id="e07f1-165">Managers.</span></span> <span data-ttu-id="e07f1-166">Permite que você atribua gerentes para a sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="e07f1-167">Os gerentes têm permissões para definir a associação de uma sala de chat, além de outras configurações.</span><span class="sxs-lookup"><span data-stu-id="e07f1-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="e07f1-p115">Apresentadores. Permite que você atribua apresentadores para uma sala de chat tipo Auditório.</span><span class="sxs-lookup"><span data-stu-id="e07f1-p115">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="e07f1-170">Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="e07f1-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="e07f1-171">Criar uma nova sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-171">Create a new room</span></span>

<span data-ttu-id="e07f1-172">Você pode criar uma nova sala usando o cmdlet **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="e07f1-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="e07f1-173">Por exemplo, o comando a seguir cria uma nova sala de chat chamada ITChatRoom no pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e07f1-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="e07f1-174">Neste exemplo, a sala de chat é adicionada à categoria de TI:</span><span class="sxs-lookup"><span data-stu-id="e07f1-174">In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="e07f1-175">**Observação:** O PersistentChatPoolFqdn não será necessário se uma das seguintes opções for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="e07f1-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="e07f1-176">Há apenas um pool de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e07f1-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="e07f1-177">Você oferece um FQDN do pool para a categoria.</span><span class="sxs-lookup"><span data-stu-id="e07f1-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="e07f1-178">Você oferece um FQDN do pool para adicionar a sala.</span><span class="sxs-lookup"><span data-stu-id="e07f1-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="e07f1-179">Configurar uma sala existente</span><span class="sxs-lookup"><span data-stu-id="e07f1-179">Configure an existing room</span></span>

<span data-ttu-id="e07f1-180">Você pode configurar uma sala existente usando o cmdlet **set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="e07f1-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="e07f1-181">Por exemplo, o comando a seguir atribui user1 como membro e apresentador, Usuário2 como gerente, da testCat Auditorium:</span><span class="sxs-lookup"><span data-stu-id="e07f1-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="e07f1-182">O próximo exemplo adiciona todos os usuários da UO NorthAmericaUsers no Active Directory à sala de chat NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="e07f1-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="e07f1-183">O próximo exemplo adiciona todos os membros do grupo de distribuição Finanças à mesma sala de chat:</span><span class="sxs-lookup"><span data-stu-id="e07f1-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="e07f1-184">Habilitar ou desabilitar uma sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-184">Disable or enable a room</span></span>

<span data-ttu-id="e07f1-185">Se o tópico de uma sala de chat persistente não for mais relevante, você poderá deixar a sala de chat indisponível para os usuários desabilitá-la.</span><span class="sxs-lookup"><span data-stu-id="e07f1-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="e07f1-186">Quando uma sala de chat está desabilitada, todos os membros são desconectados imediatamente da sala.</span><span class="sxs-lookup"><span data-stu-id="e07f1-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="e07f1-187">Após uma sala de chat ser desabilitada, os usuários não podem participar novamente ou encontrá-la nas pesquisas de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="e07f1-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="e07f1-188">Se o histórico da sala de chat persistir, o conteúdo será preservado quando a sala de chat estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e07f1-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="e07f1-189">Entretanto, o conteúdo não será exibido nas pesquisas durante o tempo em que a sala de chat permanecer no estado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e07f1-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="e07f1-190">Se você habilitá-la mais tarde, os usuários poderão pesquisar mensagens que foram publicadas antes da sala de chat ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e07f1-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="e07f1-191">Para obter informações sobre como configurar o histórico de salas de chat, consulte [gerenciar categorias no servidor de chat persistente no Skype for Business server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="e07f1-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="e07f1-192">Se uma sala de chat for desabilitada, sua lista de associação e outras configurações serão preservadas.</span><span class="sxs-lookup"><span data-stu-id="e07f1-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="e07f1-193">Como administrador, você poderá habilitar uma sala que está desabilitada, e não é necessário criar as configurações novamente de maneira manual.</span><span class="sxs-lookup"><span data-stu-id="e07f1-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="e07f1-194">Você pode desabilitar uma sala usando o cmdlet **set-CsPersistentChatRoom** e definindo o parâmetro Disabled como true:</span><span class="sxs-lookup"><span data-stu-id="e07f1-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="e07f1-195">Para habilitar uma sala de chat, defina o parâmetro Disabled para False:</span><span class="sxs-lookup"><span data-stu-id="e07f1-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="e07f1-196">Obter informações sobre salas</span><span class="sxs-lookup"><span data-stu-id="e07f1-196">Get information about rooms</span></span>

<span data-ttu-id="e07f1-197">Para obter informações sobre as salas configuradas para uso em sua organização, você pode usar o cmdlet **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="e07f1-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="e07f1-198">O comando a seguir retorna informações sobre todas as salas de chat configuradas para uso na organização:</span><span class="sxs-lookup"><span data-stu-id="e07f1-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="e07f1-199">Remover todo o conteúdo de uma sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-199">Remove all content from a room</span></span>

<span data-ttu-id="e07f1-p121">Você pode remover o conteúdo de uma sala usando o cmdlet **Clear-CsPersistentChatRoom**. Por exemplo, o comando a seguir remove todo o conteúdo da sala de Chat Persistente ITChatRoom, que foi adicionado à sala em ou antes de 1º de março de 2015:</span><span class="sxs-lookup"><span data-stu-id="e07f1-p121">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="e07f1-202">Remover uma mensagem de uma sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-202">Remove a message from a room</span></span>

<span data-ttu-id="e07f1-p122">Você pode remover uma ou mais mensagens no banco de dados de Chat Persistente e, como opção, substituir a mensagem com uma mensagem padrão ou com uma mensagem fornecida pelo administrador por meio do cmdlet **Remove-CsPersistentChatMessage**. Por exemplo, o comando a seguir remove todas as mensagens da sala de chat ITChatRoom que foram publicadas pelo usuário kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="e07f1-p122">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="e07f1-205">O próximo exemplo substitui as mensagens removidas pela observação de que a mensagem não está mais disponível:</span><span class="sxs-lookup"><span data-stu-id="e07f1-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="e07f1-206">Remover uma sala</span><span class="sxs-lookup"><span data-stu-id="e07f1-206">Remove a room</span></span>

<span data-ttu-id="e07f1-207">Você pode remover uma sala usando o cmdlet **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="e07f1-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="e07f1-208">Por exemplo, o comando a seguir remove a sala de chat RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="e07f1-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="e07f1-209">Mover uma sala de uma categoria para outra</span><span class="sxs-lookup"><span data-stu-id="e07f1-209">Move a room from one category to another</span></span>

<span data-ttu-id="e07f1-p123">Se um gerente de sala de chat tem privilégios de **Criador** em outra categoria, ele ou ela pode mover a sala de uma categoria para outra. A sala não é excluída nem recriada. É uma alteração de associação dentro do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e07f1-p123">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="e07f1-p124">Mudar a categoria de uma sala de chat deve ser feito raramente e com cuidado. Uma categoria determina a associação permitida para a sala de chat, por isso, quando uma sala de chat muda de categoria, todas as listas de controle de acesso do sistema (SACLs) não mais suportadas pela nova categoria são purgadas. Por exemplo, se um usuário for membro da sala e não mais um Membro permitido na nova categoria, a associação da sala será modificada e o usuário será removido da sala.</span><span class="sxs-lookup"><span data-stu-id="e07f1-p124">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

