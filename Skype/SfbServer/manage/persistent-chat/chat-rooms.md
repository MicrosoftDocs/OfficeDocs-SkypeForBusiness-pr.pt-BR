---
title: Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Resumo: Saiba como gerenciar salas de chat do Servidor de Chat Persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815101"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="af0dc-103">Gerenciar salas de chat no Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="af0dc-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="af0dc-104">**Resumo:** Saiba como gerenciar salas de chat do Servidor de Chat Persistente no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="af0dc-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="af0dc-105">Criar e gerenciar salas de chat é muito mais fácil com o uso correto de categorias.</span><span class="sxs-lookup"><span data-stu-id="af0dc-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="af0dc-106">Uma categoria define quem pode criar ou ingressar nas salas de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="af0dc-107">Antes de tentar gerenciar salas de chat, certifique-se de ler categorias de chat persistente, salas de chat e funções de usuário no [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e Gerenciar categorias no Servidor de Chat Persistente no Skype for Business Server [2015.](categories.md)</span><span class="sxs-lookup"><span data-stu-id="af0dc-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="af0dc-108">O chat persistente está disponível no Skype for Business Server 2015, mas não é mais suportado no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="af0dc-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="af0dc-109">A mesma funcionalidade está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="af0dc-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="af0dc-110">Para saber mais, confira [Como começar a atualizar o Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="af0dc-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="af0dc-111">Se você precisar usar o chat persistente, suas opções são migrar os usuários que exigem essa funcionalidade para o Teams ou continuar usando o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="af0dc-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="af0dc-112">Você pode configurar e gerenciar salas de chat usando a interface de linha de comando do Windows PowerShell ou usando o cliente Skype for Business se você for membro da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="af0dc-113">Este tópico descreve como gerenciar salas de chat usando a interface de linha de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af0dc-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="af0dc-114">Se você quiser gerenciar salas de chat usando o cliente Skype for Business, consulte a ajuda do cliente.</span><span class="sxs-lookup"><span data-stu-id="af0dc-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="af0dc-115">As salas de chat podem ser de dois tipos: Normal e Auditório.</span><span class="sxs-lookup"><span data-stu-id="af0dc-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="af0dc-116">Uma sala de chat Normal permite que todos os membros postem e leiam mensagens.</span><span class="sxs-lookup"><span data-stu-id="af0dc-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="af0dc-117">Um Auditório é um tipo de sala de chat onde apenas Apresentadores podem postar, mas todos podem ler.</span><span class="sxs-lookup"><span data-stu-id="af0dc-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="af0dc-118">Quem pode acessar e gerenciar salas de chat depende das funções de usuário da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="af0dc-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="af0dc-119">Os usuários devem ser membros de uma sala de chat para serem capazes de postar e ler mensagens.</span><span class="sxs-lookup"><span data-stu-id="af0dc-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="af0dc-120">Os apresentadores podem postar em salas auditórios.</span><span class="sxs-lookup"><span data-stu-id="af0dc-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="af0dc-121">Os administradores podem excluir qualquer conteúdo (por exemplo, conteúdo postado antes de determinada data) de qualquer sala de char para impedir que o banco de dados assuma proporções muito grandesm.</span><span class="sxs-lookup"><span data-stu-id="af0dc-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="af0dc-122">Os administradores também podem remover ou substituir mensagens consideradas inadequadas para uma sala de chat específica.</span><span class="sxs-lookup"><span data-stu-id="af0dc-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="af0dc-123">Os usuários finais, incluisive os autores das mensagens, não podem excluir conteúdo de nenhuma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="af0dc-124">Os Gerentes de sala de chat podem fazer alterações em todas as propriedades da sala de chat, incluindo desabilitar salas.</span><span class="sxs-lookup"><span data-stu-id="af0dc-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="af0dc-125">No entanto, os gerentes não podem excluir uma sala ou alterar a categoria de uma sala.</span><span class="sxs-lookup"><span data-stu-id="af0dc-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="af0dc-126">Somente administradores podem excluir uma sala de chat depois que ela tiver sido criada.</span><span class="sxs-lookup"><span data-stu-id="af0dc-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="af0dc-127">Você pode configurar e gerenciar salas de chat usando os seguintes cmdlets do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="af0dc-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="af0dc-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="af0dc-128">**Cmdlet**</span></span>|<span data-ttu-id="af0dc-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="af0dc-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af0dc-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="af0dc-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="af0dc-131">Criar uma nova sala de chat</span><span class="sxs-lookup"><span data-stu-id="af0dc-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="af0dc-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="af0dc-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="af0dc-133">Definir configurações para uma sala existente; atribuir usuários e grupos de usuários à sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="af0dc-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="af0dc-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="af0dc-135">Recuperar informações sobre salas</span><span class="sxs-lookup"><span data-stu-id="af0dc-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="af0dc-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="af0dc-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="af0dc-137">Limpar uma sala ou mensagens de uma sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="af0dc-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="af0dc-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="af0dc-139">Remover uma sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="af0dc-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="af0dc-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="af0dc-141">Remover mensagens de uma sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="af0dc-142">Use o cmdlet **New-CsPersistentChatRoom** para criar salas de chat e o cmdlet **Set-CsPersistentChatRoom** para configurar uma sala de chat existente, incluindo a adição de usuários à sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="af0dc-143">Você pode configurar os seguintes parâmetros para salas de chat:</span><span class="sxs-lookup"><span data-stu-id="af0dc-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="af0dc-144">Desabilitado.</span><span class="sxs-lookup"><span data-stu-id="af0dc-144">Disabled.</span></span> <span data-ttu-id="af0dc-145">Permite desabilitar ou habilitar uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="af0dc-146">Convites.</span><span class="sxs-lookup"><span data-stu-id="af0dc-146">Invitations.</span></span> <span data-ttu-id="af0dc-147">Permite habilitar ou desabilitar convites de sala de chat, que são usados para notificar os usuários quando eles foram adicionados como membros da sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="af0dc-148">A configuração padrão para convites é herdada, o que fez com que a sala de chat adotasse a configuração de convite configurada na categoria à qual ela pertence.</span><span class="sxs-lookup"><span data-stu-id="af0dc-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="af0dc-149">Definir a configuração de convites como false no nível da sala de chat permite que a configuração de categoria seja substituído.</span><span class="sxs-lookup"><span data-stu-id="af0dc-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="af0dc-150">Privacidade.</span><span class="sxs-lookup"><span data-stu-id="af0dc-150">Privacy.</span></span> <span data-ttu-id="af0dc-151">Permite especificar se uma sala de chat é Aberta, Fechada ou Secreta.</span><span class="sxs-lookup"><span data-stu-id="af0dc-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="af0dc-152">Salas abertas podem ser pesquisadas e acessadas por qualquer pessoa.</span><span class="sxs-lookup"><span data-stu-id="af0dc-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="af0dc-153">Salas fechadas podem ser pesquisadas por qualquer pessoa, mas só podem ser acessadas por membros.</span><span class="sxs-lookup"><span data-stu-id="af0dc-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="af0dc-154">Salas secretas podem ser pesquisadas e acessadas somente por membros da sala.</span><span class="sxs-lookup"><span data-stu-id="af0dc-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="af0dc-155">Por padrão, cada nova sala é inicialmente configurada como Fechada.</span><span class="sxs-lookup"><span data-stu-id="af0dc-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="af0dc-156">Tipo.</span><span class="sxs-lookup"><span data-stu-id="af0dc-156">Type.</span></span> <span data-ttu-id="af0dc-157">Permite que você especifique se uma sala de chat é Uma sala Normal, que aceita mensagens publicadas por qualquer membro, ou uma sala Auditório, que aceita mensagens publicadas apenas por um Apresentador.</span><span class="sxs-lookup"><span data-stu-id="af0dc-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="af0dc-158">Addin.</span><span class="sxs-lookup"><span data-stu-id="af0dc-158">Addin.</span></span> <span data-ttu-id="af0dc-159">Permite que você associe um complemento configurado anteriormente a uma sala de chat, o que permite que o conteúdo da URL seja visualizado pelos membros durante a participação.</span><span class="sxs-lookup"><span data-stu-id="af0dc-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="af0dc-160">Além dos parâmetros acima, o cmdlet **Set-CsPersistentChatRoom** permite atribuir usuários à sala de chat da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="af0dc-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="af0dc-161">Membros.</span><span class="sxs-lookup"><span data-stu-id="af0dc-161">Members.</span></span> <span data-ttu-id="af0dc-162">Configura a associação para a sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-162">Configures membership for the chat room.</span></span> <span data-ttu-id="af0dc-163">Você pode adicionar ou remover um ou vários membros usando um único cmdlet especificando o endereço SIP dos usuários.</span><span class="sxs-lookup"><span data-stu-id="af0dc-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="af0dc-164">Para permitir que os usuários sejam adicionados em massa, unidades organizacionais ou grupos de distribuição do Active Directory também podem ser especificados.</span><span class="sxs-lookup"><span data-stu-id="af0dc-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="af0dc-165">Gerentes.</span><span class="sxs-lookup"><span data-stu-id="af0dc-165">Managers.</span></span> <span data-ttu-id="af0dc-166">Permite atribuir gerentes à sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="af0dc-167">Os gerentes têm permissões para definir a associação de uma sala de chat junto com outras configurações.</span><span class="sxs-lookup"><span data-stu-id="af0dc-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="af0dc-168">Apresentadores.</span><span class="sxs-lookup"><span data-stu-id="af0dc-168">Presenters.</span></span> <span data-ttu-id="af0dc-169">Permite atribuir apresentadores a uma sala de bate-papo auditório.</span><span class="sxs-lookup"><span data-stu-id="af0dc-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="af0dc-170">Para obter detalhes sobre sintaxe, incluindo todos os parâmetros, consulte [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="af0dc-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="af0dc-171">Criar uma nova sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-171">Create a new room</span></span>

<span data-ttu-id="af0dc-172">Você pode criar uma nova sala usando o cmdlet **New-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="af0dc-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="af0dc-173">Por exemplo, o comando a seguir cria uma nova sala de chat chamada ITChatRoom no pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="af0dc-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="af0dc-174">Neste exemplo, a sala de chat é adicionada à categoria de IT:</span><span class="sxs-lookup"><span data-stu-id="af0dc-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="af0dc-175">**Observação:** PersistentChatPoolFqdn não será necessário se um dos seguintes for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="af0dc-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="af0dc-176">Há apenas um pool de Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="af0dc-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="af0dc-177">Você oferece um FQDN do pool para a categoria.</span><span class="sxs-lookup"><span data-stu-id="af0dc-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="af0dc-178">Você oferece um FQDN do pool para adicionar a sala.</span><span class="sxs-lookup"><span data-stu-id="af0dc-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="af0dc-179">Configurar uma sala existente</span><span class="sxs-lookup"><span data-stu-id="af0dc-179">Configure an existing room</span></span>

<span data-ttu-id="af0dc-180">Você pode configurar uma sala existente usando o cmdlet **Set-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="af0dc-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="af0dc-181">Por exemplo, o comando a seguir atribui usuário1 como Membro e Apresentador e user2 como Gerente da sala auditório testCat:</span><span class="sxs-lookup"><span data-stu-id="af0dc-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="af0dc-182">O próximo exemplo adiciona todos os usuários da UO NorthAmericaUsers no Active Directory à sala de bate-papo NorthAmerica:</span><span class="sxs-lookup"><span data-stu-id="af0dc-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="af0dc-183">O próximo exemplo adiciona todos os membros do grupo de distribuição Finanças à mesma sala de chat:</span><span class="sxs-lookup"><span data-stu-id="af0dc-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="af0dc-184">Desabilitar ou habilitar uma sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-184">Disable or enable a room</span></span>

<span data-ttu-id="af0dc-185">Se o tópico de uma sala de Chat Persistente não for mais relevante, você poderá tornar a sala de chat indisponível para os usuários desabilitando-a.</span><span class="sxs-lookup"><span data-stu-id="af0dc-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="af0dc-186">Quando uma sala de chat está desabilitada, todos os membros são desconectados imediatamente da sala.</span><span class="sxs-lookup"><span data-stu-id="af0dc-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="af0dc-187">Após uma sala de chat é desabilitada, os usuários não podem participar novamente ou encontrar nas pesquisas de sala de chat.</span><span class="sxs-lookup"><span data-stu-id="af0dc-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="af0dc-188">Se o histórico da sala de chat persistir, o conteúdo será preservado quando a sala de chat for desabilitada.</span><span class="sxs-lookup"><span data-stu-id="af0dc-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="af0dc-189">No entanto, este conteúdo não será exibido nas pesquisas durante o momento que a sala de chat permanece em um estado desabilitado.</span><span class="sxs-lookup"><span data-stu-id="af0dc-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="af0dc-190">Se você posteriormente habilitar a sala de chat, os usuários podem pesquisar por mensagens publicadas antes da sala de chat ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="af0dc-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="af0dc-191">Para obter informações sobre como configurar o histórico da sala de chat, consulte Gerenciar categorias no Servidor de [Chat Persistente no Skype for Business Server 2015.](categories.md)</span><span class="sxs-lookup"><span data-stu-id="af0dc-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="af0dc-192">Se uma sala de chat for desabilitada, sua lista de associações e outras configurações serão preservadas.</span><span class="sxs-lookup"><span data-stu-id="af0dc-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="af0dc-193">Como administrador, você pode habilitar uma sala que foi desabilitada e não precisa criar as configurações manualmente.</span><span class="sxs-lookup"><span data-stu-id="af0dc-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="af0dc-194">Você pode desabilitar uma sala usando o cmdlet **Set-CsPersistentChatRoom** e definindo o parâmetro Disabled como True:</span><span class="sxs-lookup"><span data-stu-id="af0dc-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="af0dc-195">Para habilitar uma sala de chat, de definir o parâmetro Disabled como False:</span><span class="sxs-lookup"><span data-stu-id="af0dc-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="af0dc-196">Obter informações sobre salas</span><span class="sxs-lookup"><span data-stu-id="af0dc-196">Get information about rooms</span></span>

<span data-ttu-id="af0dc-197">Para obter informações sobre as salas configuradas para uso na organização, você pode usar o cmdlet **Get-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="af0dc-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="af0dc-198">O comando a seguir retorna informações sobre todas as salas de chat configuradas para uso na organização:</span><span class="sxs-lookup"><span data-stu-id="af0dc-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="af0dc-199">Remover todo o conteúdo de uma sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-199">Remove all content from a room</span></span>

<span data-ttu-id="af0dc-200">Você pode remover o conteúdo de uma sala usando o cmdlet **Clear-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="af0dc-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="af0dc-201">Por exemplo, o comando a seguir remove todo o conteúdo da sala de Chat Persistente ITChatRoom que foi adicionada à sala em ou antes de 1º de março de 2015:</span><span class="sxs-lookup"><span data-stu-id="af0dc-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="af0dc-202">Remover uma mensagem de uma sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-202">Remove a message from a room</span></span>

<span data-ttu-id="af0dc-203">Você pode remover uma ou mais mensagens no banco de dados de Chat Persistente e, opcionalmente, substituir a mensagem por uma mensagem padrão ou por uma mensagem fornecida pelo administrador, usando o cmdlet **Remove-CsPersistentChatMessage.**</span><span class="sxs-lookup"><span data-stu-id="af0dc-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="af0dc-204">Por exemplo, o comando a seguir remove todas as mensagens da sala de bate-papo ITChatRoom que foram postadas pelo usuário kenmyer@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="af0dc-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="af0dc-205">O próximo exemplo substitui as mensagens removidas pela observação de que a mensagem não está mais disponível:</span><span class="sxs-lookup"><span data-stu-id="af0dc-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="af0dc-206">Remover uma sala</span><span class="sxs-lookup"><span data-stu-id="af0dc-206">Remove a room</span></span>

<span data-ttu-id="af0dc-207">Você pode remover uma sala usando o cmdlet **Remove-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="af0dc-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="af0dc-208">Por exemplo, o seguinte comando remove a sala de chat RedmondChatRoom:</span><span class="sxs-lookup"><span data-stu-id="af0dc-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="af0dc-209">Mover uma sala de uma categoria para outra</span><span class="sxs-lookup"><span data-stu-id="af0dc-209">Move a room from one category to another</span></span>

<span data-ttu-id="af0dc-210">Se um gerente de sala de chat tiver **privilégios** de Criador em outra categoria, ele poderá mover a sala de uma categoria para outra.</span><span class="sxs-lookup"><span data-stu-id="af0dc-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="af0dc-211">A sala não é excluída e recriada.</span><span class="sxs-lookup"><span data-stu-id="af0dc-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="af0dc-212">É uma mudança de associação no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="af0dc-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="af0dc-213">Alterar uma categoria de sala de chat deve ser feito raramente e com cuidado.</span><span class="sxs-lookup"><span data-stu-id="af0dc-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="af0dc-214">Uma categoria determina o membro permitido para a sala de chat, por isso, quando uma sala de chat muda de categoria, todas as listas de controle de acesso ao sistema (SACLs) não mais suportados pela nova categoria são purgadas.</span><span class="sxs-lookup"><span data-stu-id="af0dc-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="af0dc-215">Por exemplo, se um usuário era membro da sala e não é mais um membro permitido na nova categoria, a associação da sala será modificada e o usuário será removido da sala.</span><span class="sxs-lookup"><span data-stu-id="af0dc-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

