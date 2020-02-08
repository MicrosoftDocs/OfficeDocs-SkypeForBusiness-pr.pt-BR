---
title: Presença do usuário no Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informações para administradores sobre a presença no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863192"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="9f5f4-103">Presença do usuário no Teams</span><span class="sxs-lookup"><span data-stu-id="9f5f4-103">User presence in Teams</span></span>

<span data-ttu-id="9f5f4-104">A presença faz parte do perfil de um usuário no Microsoft Teams (e durante todo o Office 365) que indica a disponibilidade e o status atuais do usuário para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="9f5f4-105">Por padrão, qualquer pessoa em sua organização que use o Microsoft Teams poderá ver (em pouco tempo) se outros usuários estiverem disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f5f4-106">Se você desinstalar o cliente do Skype for Business depois de mover um usuários para o modo **Somente Microsoft Teams**, a presença deixará de funcionar no Outlook e em outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="9f5f4-107">A presença funciona bem no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-107">Presence works fine in Teams.</span></span> <span data-ttu-id="9f5f4-108">Solução alternativa: para ver a presença no Outlook (e em outros aplicativos do Office), o Skype for Business deve estar instalado, mesmo se você estiver executando o Microsoft Teams no modo **somente Teams** .</span><span class="sxs-lookup"><span data-stu-id="9f5f4-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="9f5f4-109">A Microsoft está ciente desse problema e trabalhando para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="9f5f4-110">A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="9f5f4-111">Estados de presença no Teams</span><span class="sxs-lookup"><span data-stu-id="9f5f4-111">Presence states in Teams</span></span>

<span data-ttu-id="9f5f4-112">Os Estados de presença do usuário disponíveis no Teams são:</span><span class="sxs-lookup"><span data-stu-id="9f5f4-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="9f5f4-113">Configurado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="9f5f4-113">User configured</span></span>|<span data-ttu-id="9f5f4-114">Aplicativo configurado</span><span class="sxs-lookup"><span data-stu-id="9f5f4-114">App configured</span></span>|
|:--- |:---|
| ![Marca de seleção verde estável, indica presença disponível](media/Presence_Available.png) <span data-ttu-id="9f5f4-116">Disponível</span><span class="sxs-lookup"><span data-stu-id="9f5f4-116">Available</span></span>|![Marca de seleção verde estável, indica presença disponível](media/Presence_Available.png) <span data-ttu-id="9f5f4-118">Disponível</span><span class="sxs-lookup"><span data-stu-id="9f5f4-118">Available</span></span>|
|| ![Abrir a marca de seleção verde, indica OOF disponível](media/Presence_Available_OOF.png) <span data-ttu-id="9f5f4-120">Disponível, fora do escritório</span><span class="sxs-lookup"><span data-stu-id="9f5f4-120">Available, Out of Office</span></span> |
|  ![Círculo vermelho sólido, indica ocupado](media/Presence_Busy.png) <span data-ttu-id="9f5f4-122">Executando</span><span class="sxs-lookup"><span data-stu-id="9f5f4-122">Busy</span></span> |  ![Círculo vermelho sólido, indica ocupado](media/Presence_Busy.png) <span data-ttu-id="9f5f4-124">Executando</span><span class="sxs-lookup"><span data-stu-id="9f5f4-124">Busy</span></span>  |
|| ![Círculo vermelho sólido, indica ocupado em uma chamada](media/Presence_Busy.png) <span data-ttu-id="9f5f4-126">Em uma chamada</span><span class="sxs-lookup"><span data-stu-id="9f5f4-126">On a call</span></span>|
|| ![Círculo vermelho sólido, indica ocupado em uma reunião](media/Presence_Busy.png) <span data-ttu-id="9f5f4-128">Em uma reunião</span><span class="sxs-lookup"><span data-stu-id="9f5f4-128">In a meeting</span></span> |
|| ![Abrir círculo vermelho, indica ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="9f5f4-130">Em uma chamada, fora do escritório</span><span class="sxs-lookup"><span data-stu-id="9f5f4-130">On a call, out of office</span></span>|
|  ![Círculo vermelho com linha branca, indica que não incomodar](media/Presence_DND.png) <span data-ttu-id="9f5f4-132">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="9f5f4-132">Do not disturb</span></span> ||
|| ![Círculo vermelho com linha branca, indica a apresentação](media/Presence_DND.png) <span data-ttu-id="9f5f4-134">Fazendo</span><span class="sxs-lookup"><span data-stu-id="9f5f4-134">Presenting</span></span>|
|| ![Círculo vermelho com linha branca, indica foco](media/Presence_DND.png) <span data-ttu-id="9f5f4-136">Foco</span><span class="sxs-lookup"><span data-stu-id="9f5f4-136">Focusing</span></span>|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="9f5f4-138">Aparece</span><span class="sxs-lookup"><span data-stu-id="9f5f4-138">Away</span></span>| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="9f5f4-140">Aparece</span><span class="sxs-lookup"><span data-stu-id="9f5f4-140">Away</span></span>|
|| <span data-ttu-id="9f5f4-141">![Ícone de relógio amarelo, indica](media/Presence_Away.png) o último *período* de vista ausente</span><span class="sxs-lookup"><span data-stu-id="9f5f4-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) <span data-ttu-id="9f5f4-143">Volto logo</span><span class="sxs-lookup"><span data-stu-id="9f5f4-143">Be right back</span></span>| |
|| ![Ícone de relógio amarelo, indica ausente, fora do trabalho](media/Presence_Away.png)  <span data-ttu-id="9f5f4-145">Longe do trabalho</span><span class="sxs-lookup"><span data-stu-id="9f5f4-145">Off Work</span></span>|
|| ![Círculo cinza com x, indica offline](media/Presence_Offline.png) <span data-ttu-id="9f5f4-147">Modo</span><span class="sxs-lookup"><span data-stu-id="9f5f4-147">Offline</span></span> |
|| ![Abrir círculo cinza, indica o status desconhecido](media/Presence_Unknown.png) <span data-ttu-id="9f5f4-149">Status desconhecido</span><span class="sxs-lookup"><span data-stu-id="9f5f4-149">Status unknown</span></span>|
||![Abrir círculo vermelho com linha diagonal, indica bloqueado](media/Presence_Blocked.png) <span data-ttu-id="9f5f4-151">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="9f5f4-151">Blocked</span></span> |
|| ![Círculo roxo com seta, indica ausência temporária](media/Presence_OOF.png) <span data-ttu-id="9f5f4-153">Fora do escritório</span><span class="sxs-lookup"><span data-stu-id="9f5f4-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="9f5f4-154">Os usuários podem definir manualmente o estado de presença atual para algumas opções, e seu estado é refletido para todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="9f5f4-155">Mais detalhes de presença do usuário também são atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="9f5f4-156">As alterações são baseadas na atividade do usuário (disponível, ausente), os Estados do calendário do Outlook (em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação), para os Estados que são recuados na lista.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="9f5f4-157">Há um tempo limite de inatividade de 15 minutos, após o qual um estado de presença atual é redefinido para ausente.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="9f5f4-158">Os usuários recebem todas as mensagens de chat enviadas para eles no Teams independentemente do estado de presença deles.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="9f5f4-159">Se um usuário estiver offline quando alguém enviar uma mensagem, a mensagem de chat será exibida no Microsoft Teams na próxima vez que o usuário estiver online.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="9f5f4-160">Se um usuário estiver em um estado de não incomodar, o usuário ainda receberá mensagens de chat, mas uma notificação de banner não será exibida.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="9f5f4-161">Os usuários recebem chamadas em todos os Estados de presença, exceto para os Estados não incomodar, nos quais as chamadas recebidas são entregues ao correio de voz.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="9f5f4-162">Se o destinatário bloqueou o chamador, a chamada não será entregue e o chamador verá a presença do destinatário como offline.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="9f5f4-163">Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando a**privacidade** de **configurações** > no Teams.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="9f5f4-164">As pessoas com acesso prioritário podem entrar em contato com o usuário mesmo quando o usuário estiver em um estado não incomodar.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="9f5f4-165">Configurações de administrador no Teams em comparação com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9f5f4-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="9f5f4-166">As seguintes configurações de administração do Skype for Business são diferentes no Teams:</span><span class="sxs-lookup"><span data-stu-id="9f5f4-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="9f5f4-167">No Teams, o compartilhamento de presença sempre é habilitado para os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="9f5f4-168">Privacidade (onde você define quem pode ver a presença) não está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="9f5f4-169">O compartilhamento de presença com todos (incluindo serviços federados) sempre está habilitado para usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="9f5f4-170">Sua lista de contatos (se ela já tinha uma no Skype for Business) fica visível em **contatos de Chat >** ou em **chamadas > contatos**.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="9f5f4-171">Cliente não incomodar e recursos revolucionários sempre são habilitados para usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="9f5f4-172">Calendário (inclui ausência temporária e outras informações do calendário) a integração sempre é habilitada para os usuários quando o Microsoft Teams está integrado ao Outlook.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="9f5f4-173">O indicador mais *recente* ou *ausente já* está habilitado para usuários do teams se a organização também usa o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="9f5f4-174">Não há suporte para a capacidade de um administrador de equipe personalizar essas configurações no momento.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="9f5f4-175">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9f5f4-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="9f5f4-176">Veja a [coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como as funções de presença do teams quando sua organização também usam o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9f5f4-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
