---
title: Teams e Skype interoperabilidade
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: Saiba mais sobre os recursos de interoperabilidade entre Teams usuários em sua organização e Skype (consumidor).
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093951"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="8dc8b-103">Teams e Skype interoperabilidade</span><span class="sxs-lookup"><span data-stu-id="8dc8b-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="8dc8b-104">Este artigo fornece uma visão geral dos recursos de interoperabilidade entre Microsoft Teams e Skype (Consumidor).</span><span class="sxs-lookup"><span data-stu-id="8dc8b-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="8dc8b-105">Saiba como Teams usuários e usuários Skype podem se comunicar por meio de chats e chamadas e os controles de administrador que se aplicam.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="8dc8b-106">Teams usuários em sua organização podem conversar e chamar Skype usuários usando seu endereço de email e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="8dc8b-107">Teams usuários podem pesquisar e iniciar uma conversa somente texto ou uma chamada de áudio/vídeo com um Skype usuário.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="8dc8b-108">Skype usuários podem pesquisar e iniciar uma conversa somente texto ou uma chamada de áudio/vídeo com um Teams usuário.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="8dc8b-109">Esses recursos estão disponíveis nos clientes desktop, web e mobile (Android e iOS) para clientes Teams e Skype.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="8dc8b-110">Para uma experiência ideal, recomendamos Skype versão 8.58 e posterior.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="8dc8b-111">Os recursos de Teams e Skype de interop discutidos neste artigo não estão disponíveis em implantações do GCC, GCC High ou DOD ou em ambientes de nuvem particulares.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="8dc8b-112">Experiência de chat e chamada</span><span class="sxs-lookup"><span data-stu-id="8dc8b-112">Chat and calling experience</span></span>

<span data-ttu-id="8dc8b-113">Aqui está uma visão geral da experiência de chat e chamada.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="8dc8b-114">Teams usuário inicia um chat ou chamada com um Skype usuário</span><span class="sxs-lookup"><span data-stu-id="8dc8b-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="8dc8b-115">Teams os usuários podem pesquisar um usuário Skype digitando seu endereço de email em um novo chat ou na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="8dc8b-116">O Teams usuário pode selecionar o usuário Skype nos resultados da pesquisa para iniciar um chat ou chamada com ele.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="8dc8b-117">Um Skype usuário pode optar por não aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="8dc8b-118">Nesse caso, eles não aparecerão nos resultados da pesquisa no Teams e Teams os usuários não poderão encontrá-los.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="8dc8b-119">Skype usuário inicia um chat ou chamada com um Teams usuário</span><span class="sxs-lookup"><span data-stu-id="8dc8b-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="8dc8b-120">Skype os usuários podem pesquisar e iniciar um chat com um usuário Teams usando seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="8dc8b-121">O Teams usuário é notificado de que ele tem uma nova mensagem de um usuário Skype e precisa primeiro aceitar a mensagem antes de poder responder a ela.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="8dc8b-122">Se o Teams o usuário selecionar **Aceitar**, a conversa será aceita e ambos os usuários poderão conversar e chamar uns aos outros.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="8dc8b-123">Se o Teams o usuário selecionar **Bloquear**, a conversa será bloqueada e as mensagens e chamadas subsequentes desse Skype usuário serão bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="8dc8b-124">Se o Teams o usuário selecionar **Exibir** mensagens , a mensagem será exibida no Teams, o que ajuda o usuário a decidir se aceita ou bloqueia a conversa.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="8dc8b-125">Se você tiver atualizado do Skype for Business para o Teams e seus usuários estão no modo Somente Teams, chats e chamadas de usuários do Skype para Teams usuários são entregues Teams.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="8dc8b-126">Se os usuários estão no modo Ilhas, os chats e chamadas de Skype usuários para Teams usuários são entregues Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="8dc8b-127">Teams ou desbloqueia um usuário Skype usuário</span><span class="sxs-lookup"><span data-stu-id="8dc8b-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="8dc8b-128">Depois que um Teams aceita ou bloqueia a solicitação de conversa inicial de um usuário Skype, ele pode optar por bloquear ou desbloquear essa pessoa a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="8dc8b-129">Eles podem fazer isso na conversa ou em suas configurações de privacidade Teams.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="8dc8b-130">Skype os usuários não saberão que foram bloqueados.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="8dc8b-131">Os usuários Skype bloqueados, juntamente com outras pessoas e números de telefone PSTN (rede telefônica pública comutada) que um usuário Teams bloqueou, estão listados na lista de contatos bloqueados do usuário no Teams.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="8dc8b-132">Limitações</span><span class="sxs-lookup"><span data-stu-id="8dc8b-132">Limitations</span></span>

- <span data-ttu-id="8dc8b-133">As conversas são somente texto.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-133">Conversations are text-only.</span></span> <span data-ttu-id="8dc8b-134">Isso significa que não há formatação rica, @mentions, emojis ou outros recursos de chat que estão disponíveis em uma experiência de chat Teams [nativa.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="8dc8b-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="8dc8b-135">As conversas são somente um para um.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="8dc8b-136">Não há suporte para chats em grupo.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="8dc8b-137">Teams usuários e Skype usuários não podem ver a presença uns dos outros.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="8dc8b-138">A pesquisa Skype usuários usando sua Skype ID ou número de telefone não é suportado.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="8dc8b-139">Skype usuários não podem chamar Teams usuários que configurarem o encaminhamento de chamadas para o número de outro usuário, o número de um representante ou um número PSTN (Rede Telefônica Pública Comugada).</span><span class="sxs-lookup"><span data-stu-id="8dc8b-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="8dc8b-140">Somente a caixa postal é suportada.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="8dc8b-141">Não há suporte para escalonamento de interop, chamadas de grupo e reuniões.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="8dc8b-142">A capacidade de um representante chamar um Skype em nome de um usuário Teams não é suportada.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="8dc8b-143">Não há suporte para compartilhamento de tela com chat.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="8dc8b-144">Definir se Teams os usuários podem se comunicar com Skype usuários</span><span class="sxs-lookup"><span data-stu-id="8dc8b-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="8dc8b-145">Como administrador, você usa o centro de administração Microsoft Teams ou o PowerShell para definir configurações de acesso externo para controlar se Teams usuários em sua organização podem se comunicar com Skype usuários.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="8dc8b-146">Por padrão, esse recurso está ligado para novos locatários.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="8dc8b-147">No entanto, há um pré-requisito de que o seguinte registro DNS SRV precise ser configurado pelo Administrador de IT se ainda não estiver disponível para seu domínio, por exemplo _sipfederationtls.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="8dc8b-148">**Serviço**: sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8dc8b-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="8dc8b-149">**Protocolo**: TCP</span><span class="sxs-lookup"><span data-stu-id="8dc8b-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="8dc8b-150">**Prioridade**: 100</span><span class="sxs-lookup"><span data-stu-id="8dc8b-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="8dc8b-151">**Peso**: 1</span><span class="sxs-lookup"><span data-stu-id="8dc8b-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="8dc8b-152">**Porta**: 5061</span><span class="sxs-lookup"><span data-stu-id="8dc8b-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="8dc8b-153">**Target**: sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8dc8b-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="8dc8b-154">Se você tiver atualizado de Skype for Business para Teams, as configurações de comunicações externas configuradas no centro de administração Skype for Business serão migradas para Teams.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8dc8b-155">No Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8dc8b-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="8dc8b-156">No centro de Microsoft Teams de administração, vá para Configurações em toda a organização Acesso externo e, em seguida, ativar Usuários podem se comunicar com  >  Skype **usuários**.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="8dc8b-157">Para obter orientações passo a passo sobre como configurar essa e outras configurações de acesso externo, consulte Gerenciar acesso externo [em Teams](./manage-external-access.md#allow-or-block-domains).</span><span class="sxs-lookup"><span data-stu-id="8dc8b-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8dc8b-158">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8dc8b-158">Using PowerShell</span></span>

<span data-ttu-id="8dc8b-159">Siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="8dc8b-159">Do the following:</span></span> 
1. <span data-ttu-id="8dc8b-160">Use o cmdlet [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) juntamente com o parâmetro para controlar se os usuários Teams podem se comunicar com ```EnablePublicCloudAccess``` Skype usuários.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="8dc8b-161">Definir o parâmetro para ```true``` permitir que Teams usuários se comuniquem com Skype usuários.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="8dc8b-162">Você pode usar o ```EnablePublicCloudAudioVideoAccess``` parâmetro para habilitar/desabilitar chamadas de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="8dc8b-163">Use o cmdlet [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) juntamente com o parâmetro definido como para que Teams usuários possam se comunicar com ```Provider``` ```"WindowsLive"``` Skype usuários.</span><span class="sxs-lookup"><span data-stu-id="8dc8b-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8dc8b-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8dc8b-164">Related topics</span></span>

- [<span data-ttu-id="8dc8b-165">Gerenciar acesso externo em Teams</span><span class="sxs-lookup"><span data-stu-id="8dc8b-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="8dc8b-166">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="8dc8b-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)