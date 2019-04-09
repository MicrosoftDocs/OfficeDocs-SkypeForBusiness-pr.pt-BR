---
title: Presença do usuário no Microsoft Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rakayala
description: Os administradores de informações precisam entender sobre a presença em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cffa4e5eef3b5b120e38b103d04adbca08bef0e
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517083"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="9791f-103">Presença do usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9791f-103">User Presence in Teams</span></span>

<span data-ttu-id="9791f-104">Presença faz parte de um perfil de usuário no Microsoft Teams (e ao longo do Office 365) – e indica a disponibilidade atual do usuário e o status para outros usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="9791f-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="9791f-105">Por padrão, qualquer pessoa na sua organização usando equipes pode ver ou não a outros usuários estão disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="9791f-105">By default, anyone in your organization using Teams can see whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="9791f-106">Estados de presença em equipes</span><span class="sxs-lookup"><span data-stu-id="9791f-106">Presence states in Teams</span></span>

<span data-ttu-id="9791f-107">Os estados de presença do usuário disponíveis em equipes são:</span><span class="sxs-lookup"><span data-stu-id="9791f-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="9791f-108">Configurado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="9791f-108">User configured</span></span>|<span data-ttu-id="9791f-109">App configurada</span><span class="sxs-lookup"><span data-stu-id="9791f-109">App configured</span></span>|
|:--- |:---|
| ![Presença disponíveis](media/Presence_Available.png) <span data-ttu-id="9791f-111">Disponível</span><span class="sxs-lookup"><span data-stu-id="9791f-111">Available</span></span>|![Presença disponíveis](media/Presence_Available.png) <span data-ttu-id="9791f-113">Disponível</span><span class="sxs-lookup"><span data-stu-id="9791f-113">Available</span></span>|
|| ![oof disponível](media/Presence_Available_OOF.png) <span data-ttu-id="9791f-115">Disponível, ausência temporária</span><span class="sxs-lookup"><span data-stu-id="9791f-115">Available, Out of Office</span></span> |
|  ![Ocupado](media/Presence_Busy.png) <span data-ttu-id="9791f-117">Ocupado</span><span class="sxs-lookup"><span data-stu-id="9791f-117">Busy</span></span> |  ![Ocupado](media/Presence_Busy.png) <span data-ttu-id="9791f-119">Ocupado</span><span class="sxs-lookup"><span data-stu-id="9791f-119">Busy</span></span>  |
|| ![Ocupado](media/Presence_Busy.png) <span data-ttu-id="9791f-121">Em uma chamada</span><span class="sxs-lookup"><span data-stu-id="9791f-121">In a call</span></span>|
|| ![Ocupado](media/Presence_Busy.png) <span data-ttu-id="9791f-123">Em uma reunião</span><span class="sxs-lookup"><span data-stu-id="9791f-123">In a meeting</span></span> |
|| ![oof ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="9791f-125">Em uma chamada, ausência temporária</span><span class="sxs-lookup"><span data-stu-id="9791f-125">In a call, out of office</span></span>|
|  ![Não incomodar](media/Presence_DND.png) <span data-ttu-id="9791f-127">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="9791f-127">Do not disturb</span></span> ||
|| ![Não incomodar](media/Presence_DND.png) <span data-ttu-id="9791f-129">Apresentando</span><span class="sxs-lookup"><span data-stu-id="9791f-129">Presenting</span></span>|
| ![ausente](media/Presence_Away.png) <span data-ttu-id="9791f-131">Ausente</span><span class="sxs-lookup"><span data-stu-id="9791f-131">Away</span></span>| ![ausente](media/Presence_Away.png) <span data-ttu-id="9791f-133">Ausente</span><span class="sxs-lookup"><span data-stu-id="9791f-133">Away</span></span>|
|| <span data-ttu-id="9791f-134">![ausente](media/Presence_Away.png) vistas ausente última *hora*</span><span class="sxs-lookup"><span data-stu-id="9791f-134">![away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![ausente](media/Presence_Away.png) <span data-ttu-id="9791f-136">Volto logo</span><span class="sxs-lookup"><span data-stu-id="9791f-136">Be right back</span></span>| |
|| ![ausente](media/Presence_Away.png)  <span data-ttu-id="9791f-138">Ausente do trabalho</span><span class="sxs-lookup"><span data-stu-id="9791f-138">Off Work</span></span>|
|| ![Offline](media/Presence_Offline.png) <span data-ttu-id="9791f-140">Offline</span><span class="sxs-lookup"><span data-stu-id="9791f-140">Offline</span></span> |
|| ![desconhecido](media/Presence_Unknown.png) <span data-ttu-id="9791f-142">Status desconhecido</span><span class="sxs-lookup"><span data-stu-id="9791f-142">Status unknown</span></span>|
||![bloqueado](media/Presence_Blocked.png) <span data-ttu-id="9791f-144">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="9791f-144">Blocked</span></span> |
|| ![Ausência temporária](media/Presence_OOF.png) <span data-ttu-id="9791f-146">Ausência temporária</span><span class="sxs-lookup"><span data-stu-id="9791f-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="9791f-147">Os usuários podem definir manualmente seu estado de presença atual para algumas opções e seu estado obtém refletido para todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="9791f-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="9791f-148">Detalhes de presença do usuário adicionais são atualizados também automaticamente com base nos Estados do aplicativo de equipes, Outlook calendário estados (como em uma reunião) ou atividade do usuário (por exemplo, disponível ou ausente) (em uma chamada, apresentando), Estados recuados na lista.</span><span class="sxs-lookup"><span data-stu-id="9791f-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="9791f-149">Há um limite de inatividade de 15 minutos, após o qual o estado de presença atual dos usuários será redefinido para ausente.</span><span class="sxs-lookup"><span data-stu-id="9791f-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="9791f-150">Os usuários podem especificar que podem ser acessadas pelo (contatá-los substituindo uma configuração não incomodar).</span><span class="sxs-lookup"><span data-stu-id="9791f-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="9791f-151">Essas configurações estão disponíveis no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9791f-151">These settings are available in-app.</span></span>

## <a name="teams-is-not-skype-for-business"></a><span data-ttu-id="9791f-152">As equipes não for Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="9791f-152">Teams is not Skype for Business</span></span>

<span data-ttu-id="9791f-153">As seguintes configurações de administração no Skype para negócios são diferentes em equipes:</span><span class="sxs-lookup"><span data-stu-id="9791f-153">The following Admin settings in Skype for Business are different in Teams:</span></span>
- <span data-ttu-id="9791f-154">Compartilhamento de presença sempre está habilitada em equipes para usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="9791f-154">Presence sharing is always enabled in Teams for users in the organization.</span></span> <span data-ttu-id="9791f-155">Configuração de privacidade (decidir quem pode ver a presença) não está disponível em equipes.</span><span class="sxs-lookup"><span data-stu-id="9791f-155">Privacy (deciding who can see Presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="9791f-156">Presença compartilhamento com todos (inclusive serviços federados) está sempre habilitada para usuários de equipes.</span><span class="sxs-lookup"><span data-stu-id="9791f-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="9791f-157">Sua lista de contatos (se eles tinham um SfB) é visível em **gt _ contatos de Chat** ou em **chamadas gt _ contatos**.</span><span class="sxs-lookup"><span data-stu-id="9791f-157">Their contact list (if they had one in SfB) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="9791f-158">Recursos de cliente não incomodar e inovadora sempre estão habilitados para usuários de equipes.</span><span class="sxs-lookup"><span data-stu-id="9791f-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="9791f-159">Calendário (inclui OOF & outras informações de calendário) integração está sempre habilitada para usuários em equipes se integrado com o Outlook.</span><span class="sxs-lookup"><span data-stu-id="9791f-159">Calendar (includes OOF & other calendar info) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="9791f-160">O indicador *ausente desde* (se estiver em um ambiente de duplo com Skype for Business) ou *visto pela última vez* está sempre habilitada para usuários de equipes.</span><span class="sxs-lookup"><span data-stu-id="9791f-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="9791f-161">A capacidade de um administrador de equipes de personalizar essas configurações não é suportada no momento.</span><span class="sxs-lookup"><span data-stu-id="9791f-161">The ability of a Teams Admin to customize these settings is not currently supported.</span></span>


## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="9791f-162">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9791f-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="9791f-163">Consulte a [coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como a presença de equipes funciona quando coexistindo com o Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="9791f-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
