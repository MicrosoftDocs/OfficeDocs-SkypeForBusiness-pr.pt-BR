---
title: Presença do usuário no Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Informações para administradores sobre a Presença no Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea756b24a0292a35d4e47252383bfc954fcb8fa7
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096966"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="9e550-103">Presença do usuário no Teams</span><span class="sxs-lookup"><span data-stu-id="9e550-103">User presence in Teams</span></span>

<span data-ttu-id="9e550-104">A presença faz parte do perfil de um usuário no Microsoft Teams (e durante todo o Office 365) que indica a disponibilidade e o status atuais do usuário para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="9e550-104">Presence is part of a user's profile in Microsoft Teams (and throughout Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="9e550-105">Por padrão, todas as pessoas da sua organização que usam o Teams podem ver (quase em tempo real) se outros usuários estiverem disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="9e550-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e550-106">Se você desinstalar o cliente do Skype for Business depois de mover um usuários para o modo **Somente Microsoft Teams**, a presença deixará de funcionar no Outlook e em outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="9e550-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="9e550-107">A presença funciona bem no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9e550-107">Presence works fine in Teams.</span></span> <span data-ttu-id="9e550-108">Solução alternativa: para ver a presença no Outlook (e em outros aplicativos do Office), o Skype for Business deve ser instalado, mesmo que você esteja executando o Teams no modo **Somente Teams**.</span><span class="sxs-lookup"><span data-stu-id="9e550-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="9e550-109">A Microsoft está ciente desse problema e trabalhando para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="9e550-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="9e550-110">A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.</span><span class="sxs-lookup"><span data-stu-id="9e550-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="9e550-111">Estados de presença no Teams</span><span class="sxs-lookup"><span data-stu-id="9e550-111">Presence states in Teams</span></span>

|<span data-ttu-id="9e550-112">Usuário configurado</span><span class="sxs-lookup"><span data-stu-id="9e550-112">User configured</span></span>|<span data-ttu-id="9e550-113">Aplicativo configurado</span><span class="sxs-lookup"><span data-stu-id="9e550-113">App configured</span></span>|
|:--- |:---|
| ![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) <span data-ttu-id="9e550-115">Disponível</span><span class="sxs-lookup"><span data-stu-id="9e550-115">Available</span></span>|![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) <span data-ttu-id="9e550-117">Disponível</span><span class="sxs-lookup"><span data-stu-id="9e550-117">Available</span></span>|
|| ![Marca de seleção verde aberta, indica at disponível](media/Presence_Available_OOF.png) <span data-ttu-id="9e550-119">Disponível, Ausência Temporária</span><span class="sxs-lookup"><span data-stu-id="9e550-119">Available, Out of Office</span></span> |
|  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="9e550-121">Ocupado</span><span class="sxs-lookup"><span data-stu-id="9e550-121">Busy</span></span> |  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="9e550-123">Ocupado</span><span class="sxs-lookup"><span data-stu-id="9e550-123">Busy</span></span>  |
|| ![Círculo vermelho, indica Ocupado em uma chamada](media/Presence_Busy.png) <span data-ttu-id="9e550-125">Em uma chamada</span><span class="sxs-lookup"><span data-stu-id="9e550-125">On a call</span></span>|
|| ![Círculo vermelho, indica Ocupado em uma reunião](media/Presence_Busy.png) <span data-ttu-id="9e550-127">Em uma reunião</span><span class="sxs-lookup"><span data-stu-id="9e550-127">In a meeting</span></span> |
|| ![Círculo vermelho aberto, indica ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="9e550-129">Em uma chamada, ausência temporária</span><span class="sxs-lookup"><span data-stu-id="9e550-129">On a call, out of office</span></span>|
|  ![Círculo vermelho com linha branca, indica Não Incomodar](media/Presence_DND.png) <span data-ttu-id="9e550-131">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="9e550-131">Do not disturb</span></span> ||
|| ![Círculo vermelho com linha branca, indica Em Apresentação](media/Presence_DND.png) <span data-ttu-id="9e550-133">Em Apresentação</span><span class="sxs-lookup"><span data-stu-id="9e550-133">Presenting</span></span>|
|| ![Círculo vermelho com linha branca, indica Focado](media/Presence_DND.png) <span data-ttu-id="9e550-135">Focado</span><span class="sxs-lookup"><span data-stu-id="9e550-135">Focusing</span></span>|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="9e550-137">Ausente</span><span class="sxs-lookup"><span data-stu-id="9e550-137">Away</span></span>| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="9e550-139">Ausente</span><span class="sxs-lookup"><span data-stu-id="9e550-139">Away</span></span>|
|| <span data-ttu-id="9e550-140">![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente Visto por Último *horário*</span><span class="sxs-lookup"><span data-stu-id="9e550-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) <span data-ttu-id="9e550-142">Volto Logo</span><span class="sxs-lookup"><span data-stu-id="9e550-142">Be right back</span></span>| |
|| ![Ícone de relógio amarelo, indica ausente do trabalho](media/Presence_Away.png)  <span data-ttu-id="9e550-144">Ausente do Trabalho</span><span class="sxs-lookup"><span data-stu-id="9e550-144">Off Work</span></span>|
|| ![Círculo cinza com x, indica Offline](media/Presence_Offline.png) <span data-ttu-id="9e550-146">Offline</span><span class="sxs-lookup"><span data-stu-id="9e550-146">Offline</span></span> |
|| ![Círculo cinza aberta, indica status desconhecido](media/Presence_Unknown.png) <span data-ttu-id="9e550-148">Status desconhecido</span><span class="sxs-lookup"><span data-stu-id="9e550-148">Status unknown</span></span>|
||![Círculo vermelho aberto com linha diagonal, indica bloqueado](media/Presence_Blocked.png) <span data-ttu-id="9e550-150">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="9e550-150">Blocked</span></span> |
|| ![Círculo roxo com seta, indica Ausência temporária](media/Presence_OOF.png) <span data-ttu-id="9e550-152">Ausência Temporária</span><span class="sxs-lookup"><span data-stu-id="9e550-152">Out of Office</span></span>|
|||

<span data-ttu-id="9e550-153">Os Estados de presença configurados pelo aplicativo são baseados na atividade do usuário (disponível, ausente), os Estados do calendário do Outlook (em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação).</span><span class="sxs-lookup"><span data-stu-id="9e550-153">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="9e550-154">Seu estado de presença atual muda para ausente quando você bloqueia seu computador ou quando ele entra no modo ocioso ou adormecido.</span><span class="sxs-lookup"><span data-stu-id="9e550-154">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="9e550-155">No celular, seu status de presença muda para ausente sempre que o aplicativo Teams está em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9e550-155">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="9e550-156">Os usuários recebem todas as mensagens de chat enviadas para eles no Teams, independentemente do seu estado de presença.</span><span class="sxs-lookup"><span data-stu-id="9e550-156">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="9e550-157">Se um usuário estiver offline quando alguém lhe enviar uma mensagem, a mensagem de chat será exibida no Teams da próxima vez que o usuário estiver online.</span><span class="sxs-lookup"><span data-stu-id="9e550-157">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="9e550-158">Se um usuário estiver em não incomodar, o usuário ainda receberá mensagens de chat, mas as notificações de cabeçalho não serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="9e550-158">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="9e550-159">Os usuários recebem chamadas em todos os Estados de presença, exceto para não incomodar, no qual as chamadas recebidas vão para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="9e550-159">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="9e550-160">Se o destinatário bloqueou o chamador, a chamada não será completada e o chamador verá a presença do destinatário como Offline.</span><span class="sxs-lookup"><span data-stu-id="9e550-160">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="9e550-161">Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando **Configurações** > **Privacidade** no Teams.</span><span class="sxs-lookup"><span data-stu-id="9e550-161">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="9e550-162">As pessoas com acesso prioritário podem entrar em contato com o usuário mesmo quando o usuário estiver em não incomodar.</span><span class="sxs-lookup"><span data-stu-id="9e550-162">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="9e550-163">Configurações de administrador no Teams em comparação com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9e550-163">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="9e550-164">As seguintes configurações de administrador do Skype for Business são diferentes no Teams:</span><span class="sxs-lookup"><span data-stu-id="9e550-164">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="9e550-165">No Teams, o compartilhamento de presença fica sempre habilitado para os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="9e550-165">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="9e550-166">A configuração de privacidade (onde você define quem pode ver a presença) não está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="9e550-166">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="9e550-167">O compartilhamento de presença com todos (incluindo serviços federados) está sempre habilitado para usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="9e550-167">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="9e550-168">Sua lista de contatos (se tiverem uma no Skype for Business) é visível em **Chat > Contatos** ou em **Chamadas > Contatos**.</span><span class="sxs-lookup"><span data-stu-id="9e550-168">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="9e550-169">Os recursos de cliente Não Incomodar e Exceções estão sempre habilitados para usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="9e550-169">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="9e550-170">A integração do calendário (inclui ausência temporária e outras informações de calendário) está sempre habilitada para os usuários quando o Teams é integrado com o Outlook.</span><span class="sxs-lookup"><span data-stu-id="9e550-170">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="9e550-171">Os indicadores *Visto por último* ou *Ausente desde* estarão sempre habilitados para usuários no Teams se a organização também usa o Skype.</span><span class="sxs-lookup"><span data-stu-id="9e550-171">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="9e550-172">Atualmente, não há suporte para a capacidade de um administrador do Teams personalizar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="9e550-172">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="9e550-173">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9e550-173">Coexistence with Skype for Business</span></span>

<span data-ttu-id="9e550-174">Confira [Coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como a presença no Teams funciona quando sua organização também usa o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9e550-174">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
