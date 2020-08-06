---
title: Presença do usuário no Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Conheça os Estados de presença no Teams, bem como as configurações administrativas do recurso de presença.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c31439485f245b522a55c2e5e1134ca6cdddbdf7
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572346"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="02353-103">Presença do usuário no Teams</span><span class="sxs-lookup"><span data-stu-id="02353-103">User presence in Teams</span></span>

<span data-ttu-id="02353-104">A presença faz parte do perfil de um usuário no Microsoft Teams (e em todo o Microsoft 365 ou o Office 365) que indica a disponibilidade e o status atuais do usuário para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="02353-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="02353-105">Por padrão, todas as pessoas da sua organização que usam o Teams podem ver (quase em tempo real) se outros usuários estiverem disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="02353-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="02353-106">A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.</span><span class="sxs-lookup"><span data-stu-id="02353-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="02353-107">Estados de presença no Teams</span><span class="sxs-lookup"><span data-stu-id="02353-107">Presence states in Teams</span></span>

|<span data-ttu-id="02353-108">Usuário configurado</span><span class="sxs-lookup"><span data-stu-id="02353-108">User configured</span></span>|<span data-ttu-id="02353-109">Aplicativo configurado</span><span class="sxs-lookup"><span data-stu-id="02353-109">App configured</span></span>|
|:--- |:---|
| ![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) <span data-ttu-id="02353-111">Disponível</span><span class="sxs-lookup"><span data-stu-id="02353-111">Available</span></span>|![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) <span data-ttu-id="02353-113">Disponível</span><span class="sxs-lookup"><span data-stu-id="02353-113">Available</span></span>|
|| ![Marca de seleção verde aberta, indica at disponível](media/Presence_Available_OOF.png) <span data-ttu-id="02353-115">Disponível, Ausência Temporária</span><span class="sxs-lookup"><span data-stu-id="02353-115">Available, Out of Office</span></span> |
|  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="02353-117">Ocupado</span><span class="sxs-lookup"><span data-stu-id="02353-117">Busy</span></span> |  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="02353-119">Ocupado</span><span class="sxs-lookup"><span data-stu-id="02353-119">Busy</span></span>  |
|| ![Círculo vermelho, indica Ocupado em uma chamada](media/Presence_Busy.png) <span data-ttu-id="02353-121">Em uma chamada</span><span class="sxs-lookup"><span data-stu-id="02353-121">On a call</span></span>|
|| ![Círculo vermelho, indica Ocupado em uma reunião](media/Presence_Busy.png) <span data-ttu-id="02353-123">Em uma reunião</span><span class="sxs-lookup"><span data-stu-id="02353-123">In a meeting</span></span> |
|| ![Círculo vermelho aberto, indica ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="02353-125">Em uma chamada, ausência temporária</span><span class="sxs-lookup"><span data-stu-id="02353-125">On a call, out of office</span></span>|
|  ![Círculo vermelho com linha branca, indica Não Incomodar](media/Presence_DND.png) <span data-ttu-id="02353-127">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="02353-127">Do not disturb</span></span> ||
|| ![Círculo vermelho com linha branca, indica Em Apresentação](media/Presence_DND.png) <span data-ttu-id="02353-129">Em Apresentação</span><span class="sxs-lookup"><span data-stu-id="02353-129">Presenting</span></span>|
|| ![Círculo vermelho com linha branca, indica Focado](media/Presence_DND.png) <span data-ttu-id="02353-131">Focado</span><span class="sxs-lookup"><span data-stu-id="02353-131">Focusing</span></span>|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="02353-133">Ausente</span><span class="sxs-lookup"><span data-stu-id="02353-133">Away</span></span>| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="02353-135">Ausente</span><span class="sxs-lookup"><span data-stu-id="02353-135">Away</span></span>|
|| <span data-ttu-id="02353-136">![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente Visto por Último *horário*</span><span class="sxs-lookup"><span data-stu-id="02353-136">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) <span data-ttu-id="02353-138">Volto Logo</span><span class="sxs-lookup"><span data-stu-id="02353-138">Be right back</span></span>| |
|| ![Ícone de relógio amarelo, indica ausente do trabalho](media/Presence_Away.png)  <span data-ttu-id="02353-140">Ausente do Trabalho</span><span class="sxs-lookup"><span data-stu-id="02353-140">Off Work</span></span>|
|| ![Círculo cinza com x, indica Offline](media/Presence_Offline.png) <span data-ttu-id="02353-142">Offline</span><span class="sxs-lookup"><span data-stu-id="02353-142">Offline</span></span> |
|| ![Círculo cinza aberta, indica status desconhecido](media/Presence_Unknown.png) <span data-ttu-id="02353-144">Status desconhecido</span><span class="sxs-lookup"><span data-stu-id="02353-144">Status unknown</span></span>|
||![Círculo vermelho aberto com linha diagonal, indica bloqueado](media/Presence_Blocked.png) <span data-ttu-id="02353-146">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="02353-146">Blocked</span></span> |
|| ![Círculo roxo com seta, indica Ausência temporária](media/Presence_OOF.png) <span data-ttu-id="02353-148">Ausência Temporária</span><span class="sxs-lookup"><span data-stu-id="02353-148">Out of Office</span></span>|
|||

<span data-ttu-id="02353-149">Os Estados de presença configurados pelo aplicativo são baseados na atividade do usuário (disponível, ausente), os Estados do calendário do Outlook (em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação).</span><span class="sxs-lookup"><span data-stu-id="02353-149">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="02353-150">Observe que, quando você estiver no modo de foco com base em seu calendário, o foco será o estado que as pessoas veem no Teans, mas aparecerão como não incomodar em outros produtos.</span><span class="sxs-lookup"><span data-stu-id="02353-150">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teans but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="02353-151">Seu estado de presença atual muda para ausente quando você bloqueia seu computador ou quando ele entra no modo ocioso ou adormecido.</span><span class="sxs-lookup"><span data-stu-id="02353-151">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="02353-152">No celular, seu status de presença muda para ausente sempre que o aplicativo Teams está em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="02353-152">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="02353-153">Os usuários recebem todas as mensagens de chat enviadas para eles no Teams, independentemente do seu estado de presença.</span><span class="sxs-lookup"><span data-stu-id="02353-153">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="02353-154">Se um usuário estiver offline quando alguém lhe enviar uma mensagem, a mensagem de chat será exibida no Teams da próxima vez que o usuário estiver online.</span><span class="sxs-lookup"><span data-stu-id="02353-154">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="02353-155">Se um usuário estiver em não incomodar, o usuário ainda receberá mensagens de chat, mas as notificações de cabeçalho não serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="02353-155">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="02353-156">Os usuários recebem chamadas em todos os Estados de presença, exceto para não incomodar, no qual as chamadas recebidas vão para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="02353-156">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="02353-157">Se o destinatário bloqueou o chamador, a chamada não será completada e o chamador verá a presença do destinatário como Offline.</span><span class="sxs-lookup"><span data-stu-id="02353-157">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="02353-158">Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando **Configurações** > **Privacidade** no Teams.</span><span class="sxs-lookup"><span data-stu-id="02353-158">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="02353-159">As pessoas com acesso prioritário podem entrar em contato com o usuário mesmo quando o usuário estiver em não incomodar.</span><span class="sxs-lookup"><span data-stu-id="02353-159">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="02353-160">Configurações de administrador no Teams em comparação com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="02353-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="02353-161">As seguintes configurações de administrador do Skype for Business são diferentes no Teams:</span><span class="sxs-lookup"><span data-stu-id="02353-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="02353-162">No Teams, o compartilhamento de presença fica sempre habilitado para os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="02353-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="02353-163">A configuração de privacidade (onde você define quem pode ver a presença) não está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="02353-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="02353-164">O compartilhamento de presença com todos (incluindo serviços federados) está sempre habilitado para usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="02353-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="02353-165">Sua lista de contatos (se tiverem uma no Skype for Business) é visível em **Chat > Contatos** ou em **Chamadas > Contatos**.</span><span class="sxs-lookup"><span data-stu-id="02353-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="02353-166">Os recursos de cliente Não Incomodar e Exceções estão sempre habilitados para usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="02353-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="02353-167">A integração do calendário (inclui ausência temporária e outras informações de calendário) está sempre habilitada para os usuários quando o Teams é integrado com o Outlook.</span><span class="sxs-lookup"><span data-stu-id="02353-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="02353-168">Os indicadores *Visto por último* ou *Ausente desde* estarão sempre habilitados para usuários no Teams se a organização também usa o Skype.</span><span class="sxs-lookup"><span data-stu-id="02353-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="02353-169">Atualmente, não há suporte para a capacidade de um administrador do Teams personalizar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="02353-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="02353-170">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="02353-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="02353-171">Confira [Coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como a presença no Teams funciona quando sua organização também usa o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="02353-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
