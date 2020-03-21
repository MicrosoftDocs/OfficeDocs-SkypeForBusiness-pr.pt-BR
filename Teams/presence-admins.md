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
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863192"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="391f3-103">Presença do usuário no Teams</span><span class="sxs-lookup"><span data-stu-id="391f3-103">User presence in Teams</span></span>

<span data-ttu-id="391f3-104">A presença faz parte do perfil de usuário do Microsoft Teams (e em todo o Office 365) que indica a disponibilidade atual do usuário e o status para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="391f3-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="391f3-105">Por padrão, todas as pessoas da sua organização que usam o Teams podem ver (quase em tempo real) se outros usuários estiverem disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="391f3-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="391f3-106">Se você desinstalar o cliente do Skype for Business depois de mover um usuários para o modo **Somente Microsoft Teams**, a presença deixará de funcionar no Outlook e em outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="391f3-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="391f3-107">A presença funciona bem no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="391f3-107">Presence works fine in Teams.</span></span> <span data-ttu-id="391f3-108">Solução alternativa: para ver a presença no Outlook (e em outros aplicativos do Office), o Skype for Business deve ser instalado, mesmo que você esteja executando o Teams no modo **Somente Teams**.</span><span class="sxs-lookup"><span data-stu-id="391f3-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="391f3-109">A Microsoft está ciente desse problema e trabalhando para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="391f3-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="391f3-110">A presença do Teams no Outlook é compatível com o aplicativo de área de trabalho do Outlook 2013 e posterior.</span><span class="sxs-lookup"><span data-stu-id="391f3-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="391f3-111">Estados de presença no Teams</span><span class="sxs-lookup"><span data-stu-id="391f3-111">Presence states in Teams</span></span>

<span data-ttu-id="391f3-112">Os estados de presença de usuário disponíveis no Teams são:</span><span class="sxs-lookup"><span data-stu-id="391f3-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="391f3-113">Usuário configurado</span><span class="sxs-lookup"><span data-stu-id="391f3-113">User configured</span></span>|<span data-ttu-id="391f3-114">Aplicativo configurado</span><span class="sxs-lookup"><span data-stu-id="391f3-114">App configured</span></span>|
|:--- |:---|
| ![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) <span data-ttu-id="391f3-116">Disponível</span><span class="sxs-lookup"><span data-stu-id="391f3-116">Available</span></span>|![Marca de seleção verde, indica Presença Disponível](media/Presence_Available.png) <span data-ttu-id="391f3-118">Disponível</span><span class="sxs-lookup"><span data-stu-id="391f3-118">Available</span></span>|
|| ![Marca de seleção verde aberta, indica at disponível](media/Presence_Available_OOF.png) <span data-ttu-id="391f3-120">Disponível, Ausência Temporária</span><span class="sxs-lookup"><span data-stu-id="391f3-120">Available, Out of Office</span></span> |
|  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="391f3-122">Ocupado</span><span class="sxs-lookup"><span data-stu-id="391f3-122">Busy</span></span> |  ![Círculo vermelho, indica Ocupado](media/Presence_Busy.png) <span data-ttu-id="391f3-124">Ocupado</span><span class="sxs-lookup"><span data-stu-id="391f3-124">Busy</span></span>  |
|| ![Círculo vermelho, indica Ocupado em uma chamada](media/Presence_Busy.png) <span data-ttu-id="391f3-126">Em uma chamada</span><span class="sxs-lookup"><span data-stu-id="391f3-126">On a call</span></span>|
|| ![Círculo vermelho, indica Ocupado em uma reunião](media/Presence_Busy.png) <span data-ttu-id="391f3-128">Em uma reunião</span><span class="sxs-lookup"><span data-stu-id="391f3-128">In a meeting</span></span> |
|| ![Círculo vermelho aberto, indica ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="391f3-130">Em uma chamada, ausência temporária</span><span class="sxs-lookup"><span data-stu-id="391f3-130">On a call, out of office</span></span>|
|  ![Círculo vermelho com linha branca, indica Não Incomodar](media/Presence_DND.png) <span data-ttu-id="391f3-132">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="391f3-132">Do not disturb</span></span> ||
|| ![Círculo vermelho com linha branca, indica Em Apresentação](media/Presence_DND.png) <span data-ttu-id="391f3-134">Em Apresentação</span><span class="sxs-lookup"><span data-stu-id="391f3-134">Presenting</span></span>|
|| ![Círculo vermelho com linha branca, indica Focado](media/Presence_DND.png) <span data-ttu-id="391f3-136">Focado</span><span class="sxs-lookup"><span data-stu-id="391f3-136">Focusing</span></span>|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="391f3-138">Ausente</span><span class="sxs-lookup"><span data-stu-id="391f3-138">Away</span></span>| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="391f3-140">Ausente</span><span class="sxs-lookup"><span data-stu-id="391f3-140">Away</span></span>|
|| <span data-ttu-id="391f3-141">![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) Ausente Visto por Último *horário*</span><span class="sxs-lookup"><span data-stu-id="391f3-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) <span data-ttu-id="391f3-143">Volto Logo</span><span class="sxs-lookup"><span data-stu-id="391f3-143">Be right back</span></span>| |
|| ![Ícone de relógio amarelo, indica ausente do trabalho](media/Presence_Away.png)  <span data-ttu-id="391f3-145">Ausente do Trabalho</span><span class="sxs-lookup"><span data-stu-id="391f3-145">Off Work</span></span>|
|| ![Círculo cinza com x, indica Offline](media/Presence_Offline.png) <span data-ttu-id="391f3-147">Offline</span><span class="sxs-lookup"><span data-stu-id="391f3-147">Offline</span></span> |
|| ![Círculo cinza aberta, indica status desconhecido](media/Presence_Unknown.png) <span data-ttu-id="391f3-149">Status desconhecido</span><span class="sxs-lookup"><span data-stu-id="391f3-149">Status unknown</span></span>|
||![Círculo vermelho aberto com linha diagonal, indica bloqueado](media/Presence_Blocked.png) <span data-ttu-id="391f3-151">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="391f3-151">Blocked</span></span> |
|| ![Círculo roxo com seta, indica Ausência temporária](media/Presence_OOF.png) <span data-ttu-id="391f3-153">Ausência Temporária</span><span class="sxs-lookup"><span data-stu-id="391f3-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="391f3-154">Os usuários podem definir manualmente seu estado de presença atual para algumas opções e seu estado é refletido para todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="391f3-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="391f3-155">Mais detalhes de presença do usuário também são atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="391f3-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="391f3-156">As alterações se baseiam na atividade do usuário (Disponível, Ausente), estados de calendário do Outlook (Em uma reunião) ou estados do aplicativo Teams (Em uma chamada, Em apresentação) para estados que estão recuados na lista.</span><span class="sxs-lookup"><span data-stu-id="391f3-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="391f3-157">Há um limite de tempo de inatividade de 15 minutos, após o qual um estado de presença atual é redefinido para Ausente.</span><span class="sxs-lookup"><span data-stu-id="391f3-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="391f3-158">Os usuários recebem todas as mensagens de chat enviadas para eles no Teams, independentemente do seu estado de presença.</span><span class="sxs-lookup"><span data-stu-id="391f3-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="391f3-159">Se um usuário estiver offline quando alguém lhe enviar uma mensagem, a mensagem de chat será exibida no Teams da próxima vez que o usuário estiver online.</span><span class="sxs-lookup"><span data-stu-id="391f3-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="391f3-160">Se um usuário estiver no estado Não Incomodar, o usuário ainda receberá mensagens de chat, mas as notificações por faixa não serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="391f3-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="391f3-161">Os usuários recebem chamadas em todos os estados de presença, exceto nos estados Não Incomodar, nos quais as chamadas recebidas são encaminhadas para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="391f3-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="391f3-162">Se o destinatário bloqueou o chamador, a chamada não será completada e o chamador verá a presença do destinatário como Offline.</span><span class="sxs-lookup"><span data-stu-id="391f3-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="391f3-163">Os usuários podem adicionar pessoas à sua lista de acesso prioritário acessando **Configurações** > **Privacidade** no Teams.</span><span class="sxs-lookup"><span data-stu-id="391f3-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="391f3-164">As pessoas com acesso prioritário podem contatar o usuário mesmo quando ele estiver em um estado Não Incomodar.</span><span class="sxs-lookup"><span data-stu-id="391f3-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="391f3-165">Configurações de administrador no Teams em comparação com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="391f3-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="391f3-166">As seguintes configurações de administrador do Skype for Business são diferentes no Teams:</span><span class="sxs-lookup"><span data-stu-id="391f3-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="391f3-167">No Teams, o compartilhamento de presença fica sempre habilitado para os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="391f3-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="391f3-168">A configuração de privacidade (onde você define quem pode ver a presença) não está disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="391f3-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="391f3-169">O compartilhamento de presença com todos (incluindo serviços federados) está sempre habilitado para usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="391f3-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="391f3-170">Sua lista de contatos (se tiverem uma no Skype for Business) é visível em **Chat > Contatos** ou em **Chamadas > Contatos**.</span><span class="sxs-lookup"><span data-stu-id="391f3-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="391f3-171">Os recursos de cliente Não Incomodar e Exceções estão sempre habilitados para usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="391f3-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="391f3-172">A integração do calendário (inclui ausência temporária e outras informações de calendário) está sempre habilitada para os usuários quando o Teams é integrado com o Outlook.</span><span class="sxs-lookup"><span data-stu-id="391f3-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="391f3-173">Os indicadores *Visto por último* ou *Ausente desde* estarão sempre habilitados para usuários no Teams se a organização também usa o Skype.</span><span class="sxs-lookup"><span data-stu-id="391f3-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="391f3-174">Atualmente, não há suporte para a capacidade de um administrador do Teams personalizar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="391f3-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="391f3-175">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="391f3-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="391f3-176">Confira [Coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como a presença no Teams funciona quando sua organização também usa o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="391f3-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
