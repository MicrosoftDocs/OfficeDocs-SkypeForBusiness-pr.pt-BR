---
title: Presença do usuário no Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Os administradores de informações precisam compreender a presença no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b3c36f0f83937e72ae4477ad38c9bd3187c6577
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244822"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="3c761-103">Presença do usuário no Teams</span><span class="sxs-lookup"><span data-stu-id="3c761-103">User presence in Teams</span></span>

<span data-ttu-id="3c761-104">A presença faz parte do perfil de um usuário no Microsoft Teams (e durante todo o Office 365) – e indica a disponibilidade e o status atuais do usuário para outros usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="3c761-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="3c761-105">Por padrão, qualquer pessoa em sua organização que use o Microsoft Teams pode ver, em quase tempo, se outros usuários estão ou não disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="3c761-105">By default, anyone in your organization using Teams can see – in nearly real time – whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="3c761-106">Estados de presença no Teams</span><span class="sxs-lookup"><span data-stu-id="3c761-106">Presence states in Teams</span></span>

<span data-ttu-id="3c761-107">Os Estados de presença do usuário disponíveis no Teams são:</span><span class="sxs-lookup"><span data-stu-id="3c761-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="3c761-108">Configurado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="3c761-108">User configured</span></span>|<span data-ttu-id="3c761-109">Aplicativo configurado</span><span class="sxs-lookup"><span data-stu-id="3c761-109">App configured</span></span>|
|:--- |:---|
| ![Marca de Chek verde estável, indicando presença disponível](media/Presence_Available.png) <span data-ttu-id="3c761-111">Disponível</span><span class="sxs-lookup"><span data-stu-id="3c761-111">Available</span></span>|![Marca de Chek verde estável, indicando presença disponível](media/Presence_Available.png) <span data-ttu-id="3c761-113">Disponível</span><span class="sxs-lookup"><span data-stu-id="3c761-113">Available</span></span>|
|| ![Abrir marca Chek verde, indicando OOF disponível](media/Presence_Available_OOF.png) <span data-ttu-id="3c761-115">Disponível, fora do escritório</span><span class="sxs-lookup"><span data-stu-id="3c761-115">Available, Out of Office</span></span> |
|  ![Círculo vermelho sólido, indicando ocupado](media/Presence_Busy.png) <span data-ttu-id="3c761-117">Executando</span><span class="sxs-lookup"><span data-stu-id="3c761-117">Busy</span></span> |  ![Círculo vermelho sólido, indicando ocupado](media/Presence_Busy.png) <span data-ttu-id="3c761-119">Executando</span><span class="sxs-lookup"><span data-stu-id="3c761-119">Busy</span></span>  |
|| ![Círculo vermelho sólido, que indica ocupado em uma chamada](media/Presence_Busy.png) <span data-ttu-id="3c761-121">Em uma chamada</span><span class="sxs-lookup"><span data-stu-id="3c761-121">In a call</span></span>|
|| ![Círculo vermelho sólido, que indica ocupado em uma reunião](media/Presence_Busy.png) <span data-ttu-id="3c761-123">Em uma reunião</span><span class="sxs-lookup"><span data-stu-id="3c761-123">In a meeting</span></span> |
|| ![Abrir círculo vermelho, indicando OOF indisponível](media/Presence_Busy_OOF.png) <span data-ttu-id="3c761-125">Em uma chamada, fora do escritório</span><span class="sxs-lookup"><span data-stu-id="3c761-125">In a call, out of office</span></span>|
|  ![Círculo vermelho com linha branca, indicando não incomodar](media/Presence_DND.png) <span data-ttu-id="3c761-127">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="3c761-127">Do not disturb</span></span> ||
|| ![Círculo vermelho com linha branca, indicando a apresentação](media/Presence_DND.png) <span data-ttu-id="3c761-129">Fazendo</span><span class="sxs-lookup"><span data-stu-id="3c761-129">Presenting</span></span>|
| ![Ícone de relógio amarelo, indicando ausente](media/Presence_Away.png) <span data-ttu-id="3c761-131">Aparece</span><span class="sxs-lookup"><span data-stu-id="3c761-131">Away</span></span>| ![Ícone de relógio amarelo, indicando ausente](media/Presence_Away.png) <span data-ttu-id="3c761-133">Aparece</span><span class="sxs-lookup"><span data-stu-id="3c761-133">Away</span></span>|
|| <span data-ttu-id="3c761-134">![Ícone de relógio amarelo, que](media/Presence_Away.png) indica o último *horário* visto ausente</span><span class="sxs-lookup"><span data-stu-id="3c761-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Ícone de relógio amarelo, indicando ausente, volto logo](media/Presence_Away.png) <span data-ttu-id="3c761-136">Volto logo</span><span class="sxs-lookup"><span data-stu-id="3c761-136">Be right back</span></span>| |
|| ![Ícone de relógio amarelo, indicando ausente, fora do trabalho](media/Presence_Away.png)  <span data-ttu-id="3c761-138">Longe do trabalho</span><span class="sxs-lookup"><span data-stu-id="3c761-138">Off Work</span></span>|
|| ![Círculo cinza com x, indicando offline](media/Presence_Offline.png) <span data-ttu-id="3c761-140">Modo</span><span class="sxs-lookup"><span data-stu-id="3c761-140">Offline</span></span> |
|| ![Abrir círculo cinza, indicando o status desconhecido](media/Presence_Unknown.png) <span data-ttu-id="3c761-142">Status desconhecido</span><span class="sxs-lookup"><span data-stu-id="3c761-142">Status unknown</span></span>|
||![Abrir círculo vermelho com linha diagonal, indicando bloqueado](media/Presence_Blocked.png) <span data-ttu-id="3c761-144">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="3c761-144">Blocked</span></span> |
|| ![Círculo roxo com seta, indicando ausência temporária](media/Presence_OOF.png) <span data-ttu-id="3c761-146">Fora do escritório</span><span class="sxs-lookup"><span data-stu-id="3c761-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="3c761-147">Os usuários podem definir manualmente o estado de presença atual para algumas opções, e seu estado é refletido para todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="3c761-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="3c761-148">Detalhes adicionais de presença do usuário também são atualizados automaticamente com base na atividade do usuário (como disponível ou ausente), os Estados do calendário do Outlook (como em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação), para os Estados que são recuados na lista.</span><span class="sxs-lookup"><span data-stu-id="3c761-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="3c761-149">Há um tempo limite de inatividade de 15 minutos, após o qual o estado de presença atual dos seus usuários será redefinido para ausente.</span><span class="sxs-lookup"><span data-stu-id="3c761-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="3c761-150">Os usuários podem especificar quem pode interromper (entre em contato com eles substituindo uma configuração não incomodar).</span><span class="sxs-lookup"><span data-stu-id="3c761-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="3c761-151">Essas configurações estão disponíveis no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c761-151">These settings are available in-app.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="3c761-152">Configurações de administrador no Teams em comparação com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3c761-152">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="3c761-153">As seguintes configurações de administração do Skype for Business são diferentes no Teams:</span><span class="sxs-lookup"><span data-stu-id="3c761-153">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="3c761-154">No Teams, o compartilhamento de presença sempre é habilitado para os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="3c761-154">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="3c761-155">Privacidade (decidindo quem pode ver a presença) a configuração não está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3c761-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="3c761-156">O compartilhamento de presença com todos (incluindo serviços federados) sempre está habilitado para usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="3c761-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="3c761-157">Sua lista de contatos (se ela já tinha uma no Skype for Business) fica visível em **contatos de Chat >** ou em **chamadas > contatos**.</span><span class="sxs-lookup"><span data-stu-id="3c761-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="3c761-158">Cliente não incomodar e recursos revolucionários sempre são habilitados para usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="3c761-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="3c761-159">Calendário (inclui ausência temporária e outras informações do calendário) a integração sempre é habilitada para usuários do Teams, se integradas ao Outlook.</span><span class="sxs-lookup"><span data-stu-id="3c761-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="3c761-160">A *última vista* ou *ausente desde* (se em um ambiente duplo com o Skype for Business) indicador sempre é habilitado para usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="3c761-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="3c761-161">Não há suporte para a capacidade de um administrador de equipe personalizar essas configurações no momento.</span><span class="sxs-lookup"><span data-stu-id="3c761-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="3c761-162">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3c761-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="3c761-163">Veja a [coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como as funções de presença de equipes são coexistentes com o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3c761-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
