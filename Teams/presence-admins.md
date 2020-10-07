---
title: Presença do usuário no Teams
author: msdmaguire
ms.author: dmaguire
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
ms.openlocfilehash: 9f14aeaf83862cbdd695eb6ec4646d8da81a0c5b
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369206"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="028b2-103">Presença do usuário no Teams</span><span class="sxs-lookup"><span data-stu-id="028b2-103">User presence in Teams</span></span>

<span data-ttu-id="028b2-104">A presença faz parte do perfil de um usuário no Microsoft Teams (e em todo o Microsoft 365 ou o Office 365) que indica a disponibilidade e o status atuais do usuário para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="028b2-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="028b2-105">Por padrão, todas as pessoas da sua organização que usam o Teams podem ver (quase em tempo real) se outros usuários estiverem disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="028b2-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="028b2-106">A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.</span><span class="sxs-lookup"><span data-stu-id="028b2-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

 > [!Note]
 > <span data-ttu-id="028b2-107">Para obter detalhes sobre os perfis de usuário do Team em diferentes plataformas, consulte [recursos do teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="028b2-107">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="028b2-108">Estados de presença no Teams</span><span class="sxs-lookup"><span data-stu-id="028b2-108">Presence states in Teams</span></span>

|<span data-ttu-id="028b2-109">Usuário configurado</span><span class="sxs-lookup"><span data-stu-id="028b2-109">User configured</span></span>|<span data-ttu-id="028b2-110">Aplicativo configurado</span><span class="sxs-lookup"><span data-stu-id="028b2-110">App configured</span></span>|
|:--- |:---|
| ![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) <span data-ttu-id="028b2-112">Disponível</span><span class="sxs-lookup"><span data-stu-id="028b2-112">Available</span></span>|![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) <span data-ttu-id="028b2-114">Disponível</span><span class="sxs-lookup"><span data-stu-id="028b2-114">Available</span></span>|
|| ![Marca de seleção verde aberta, indica at disponível](media/Presence_Available_OOF.png) <span data-ttu-id="028b2-116">Disponível, Ausência Temporária</span><span class="sxs-lookup"><span data-stu-id="028b2-116">Available, Out of Office</span></span> |
|  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="028b2-118">Ocupado</span><span class="sxs-lookup"><span data-stu-id="028b2-118">Busy</span></span> |  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="028b2-120">Ocupado</span><span class="sxs-lookup"><span data-stu-id="028b2-120">Busy</span></span>  |
|| ![Círculo vermelho, indica Ocupado em uma chamada](media/Presence_Busy.png) <span data-ttu-id="028b2-122">Em uma chamada</span><span class="sxs-lookup"><span data-stu-id="028b2-122">On a call</span></span>|
|| ![Círculo vermelho, indica Ocupado em uma reunião](media/Presence_Busy.png) <span data-ttu-id="028b2-124">Em uma reunião</span><span class="sxs-lookup"><span data-stu-id="028b2-124">In a meeting</span></span> |
|| ![Círculo vermelho aberto, indica ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="028b2-126">Em uma chamada, ausência temporária</span><span class="sxs-lookup"><span data-stu-id="028b2-126">On a call, out of office</span></span>|
|  ![Círculo vermelho com linha branca, indica Não Incomodar](media/Presence_DND.png) <span data-ttu-id="028b2-128">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="028b2-128">Do not disturb</span></span> ||
|| ![Círculo vermelho com linha branca, indica Em Apresentação](media/Presence_DND.png) <span data-ttu-id="028b2-130">Em Apresentação</span><span class="sxs-lookup"><span data-stu-id="028b2-130">Presenting</span></span>|
|| ![Círculo vermelho com linha branca, indica Focado](media/Presence_DND.png) <span data-ttu-id="028b2-132">Focado</span><span class="sxs-lookup"><span data-stu-id="028b2-132">Focusing</span></span>|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="028b2-134">Ausente</span><span class="sxs-lookup"><span data-stu-id="028b2-134">Away</span></span>| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="028b2-136">Ausente</span><span class="sxs-lookup"><span data-stu-id="028b2-136">Away</span></span>|
|| <span data-ttu-id="028b2-137">![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente Visto por Último *horário*</span><span class="sxs-lookup"><span data-stu-id="028b2-137">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) <span data-ttu-id="028b2-139">Volto Logo</span><span class="sxs-lookup"><span data-stu-id="028b2-139">Be right back</span></span>| |
|![Círculo cinza com x, indica Offline](media/Presence_Offline.png) <span data-ttu-id="028b2-141">Aparecer offline</span><span class="sxs-lookup"><span data-stu-id="028b2-141">Appear offline</span></span> | ![Círculo cinza com x, indica Offline](media/Presence_Offline.png) <span data-ttu-id="028b2-143">Offline</span><span class="sxs-lookup"><span data-stu-id="028b2-143">Offline</span></span>| |
|| ![Círculo cinza aberta, indica status desconhecido](media/Presence_Unknown.png) <span data-ttu-id="028b2-145">Status desconhecido</span><span class="sxs-lookup"><span data-stu-id="028b2-145">Status unknown</span></span>|
|| ![Círculo roxo com seta, indica Ausência temporária](media/Presence_OOF.png) <span data-ttu-id="028b2-147">Ausência Temporária</span><span class="sxs-lookup"><span data-stu-id="028b2-147">Out of Office</span></span>|
|||

<span data-ttu-id="028b2-148">Os Estados de presença configurados pelo aplicativo são baseados na atividade do usuário (disponível, ausente), os Estados do calendário do Outlook (em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação).</span><span class="sxs-lookup"><span data-stu-id="028b2-148">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="028b2-149">Observe que, quando você estiver no modo de foco com base em seu calendário, o foco será o estado que as pessoas veem no Teams, mas serão exibidas como não incomodar em outros produtos.</span><span class="sxs-lookup"><span data-stu-id="028b2-149">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teams, but it will display as Do not disturb in other products.</span></span>

<span data-ttu-id="028b2-150">Seu estado de presença atual muda para ausente quando você bloqueia seu computador ou quando o computador entra no modo ocioso ou adormecido.</span><span class="sxs-lookup"><span data-stu-id="028b2-150">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="028b2-151">Em um dispositivo móvel, seu status de presença muda para ausente sempre que o aplicativo Teams está em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="028b2-151">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="028b2-152">Os usuários recebem todas as mensagens de chat enviadas para eles no Teams, independentemente do seu estado de presença.</span><span class="sxs-lookup"><span data-stu-id="028b2-152">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="028b2-153">Se um usuário estiver offline quando alguém lhe enviar uma mensagem, a mensagem de chat será exibida no Teams da próxima vez que o usuário estiver online.</span><span class="sxs-lookup"><span data-stu-id="028b2-153">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="028b2-154">Se um estado do usuário estiver definido como não incomodar, o usuário ainda receberá mensagens de chat, mas as notificações de cabeçalho não serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="028b2-154">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="028b2-155">Os usuários recebem chamadas em todos os Estados de presença, exceto para não incomodar, no qual as chamadas recebidas vão para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="028b2-155">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="028b2-156">Se o destinatário bloqueou o chamador, a chamada não será completada e o chamador verá a presença do destinatário como Offline.</span><span class="sxs-lookup"><span data-stu-id="028b2-156">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="028b2-157">Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando **Configurações** > **Privacidade** no Teams.</span><span class="sxs-lookup"><span data-stu-id="028b2-157">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="028b2-158">As pessoas com acesso prioritário podem entrar em contato com o usuário mesmo quando o status do usuário estiver definido como não incomodar.</span><span class="sxs-lookup"><span data-stu-id="028b2-158">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="028b2-159">Expiração de Estados configurados pelo usuário</span><span class="sxs-lookup"><span data-stu-id="028b2-159">User configured states expiration</span></span>
<span data-ttu-id="028b2-160">Quando um usuário seleciona um estado de presença específico, ele tem precedência sobre qualquer atualização de atividade do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="028b2-160">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="028b2-161">Por exemplo, se um usuário define-se como não incomodar, sua presença permanecerá como não incomodar, mesmo que ela participe de uma reunião ou responda a uma chamada.</span><span class="sxs-lookup"><span data-stu-id="028b2-161">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="028b2-162">Os Estados configurados pelo usuário têm configurações de expiração padrão no Teams, para impedir que os usuários exibam um status que podem não ser relevantes após um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="028b2-162">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="028b2-163">Estado configurado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="028b2-163">User configured state</span></span>|<span data-ttu-id="028b2-164">Expiração padrão</span><span class="sxs-lookup"><span data-stu-id="028b2-164">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="028b2-165">Ocupado</span><span class="sxs-lookup"><span data-stu-id="028b2-165">Busy</span></span>|<span data-ttu-id="028b2-166">1 dia</span><span class="sxs-lookup"><span data-stu-id="028b2-166">1 day</span></span>|
| <span data-ttu-id="028b2-167">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="028b2-167">Do not disturb</span></span>|<span data-ttu-id="028b2-168">1 dia</span><span class="sxs-lookup"><span data-stu-id="028b2-168">1 day</span></span>|
| <span data-ttu-id="028b2-169">Computadores</span><span class="sxs-lookup"><span data-stu-id="028b2-169">Others</span></span>|<span data-ttu-id="028b2-170">7 dias</span><span class="sxs-lookup"><span data-stu-id="028b2-170">7 days</span></span>|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="028b2-171">Configurações de administrador no Teams em comparação com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="028b2-171">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="028b2-172">As seguintes configurações de administrador do Skype for Business são diferentes no Teams:</span><span class="sxs-lookup"><span data-stu-id="028b2-172">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="028b2-173">No Teams, o compartilhamento de presença fica sempre habilitado para os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="028b2-173">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="028b2-174">A configuração de privacidade (onde você define quem pode ver a presença) não está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="028b2-174">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="028b2-175">O compartilhamento de presença com todos (incluindo serviços federados) está sempre habilitado para usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="028b2-175">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="028b2-176">Sua lista de contatos (se tiverem uma no Skype for Business) é visível em **Chat > Contatos** ou em **Chamadas > Contatos**.</span><span class="sxs-lookup"><span data-stu-id="028b2-176">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="028b2-177">Os recursos de cliente Não Incomodar e Exceções estão sempre habilitados para usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="028b2-177">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="028b2-178">A integração do calendário (inclui ausência temporária e outras informações de calendário) está sempre habilitada para os usuários quando o Teams é integrado com o Outlook.</span><span class="sxs-lookup"><span data-stu-id="028b2-178">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="028b2-179">Os indicadores *Visto por último* ou *Ausente desde* estarão sempre habilitados para usuários no Teams se a organização também usa o Skype.</span><span class="sxs-lookup"><span data-stu-id="028b2-179">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="028b2-180">Atualmente, não há suporte para a capacidade de um administrador do Teams personalizar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="028b2-180">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="028b2-181">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="028b2-181">Coexistence with Skype for Business</span></span>

<span data-ttu-id="028b2-182">Confira [Coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como a presença no Teams funciona quando sua organização também usa o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="028b2-182">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
