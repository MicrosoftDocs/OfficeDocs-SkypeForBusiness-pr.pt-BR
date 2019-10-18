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
description: Informações para administradores sobre a presença no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 054c3a639cc5857fb25a7e211a272868477dcb61
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573212"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="6a98b-103">Presença do usuário no Teams</span><span class="sxs-lookup"><span data-stu-id="6a98b-103">User presence in Teams</span></span>

<span data-ttu-id="6a98b-104">A presença faz parte do perfil de um usuário no Microsoft Teams (e durante todo o Office 365) que indica a disponibilidade e o status atuais do usuário para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="6a98b-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="6a98b-105">Por padrão, qualquer pessoa em sua organização que use o Microsoft Teams poderá ver (em pouco tempo) se outros usuários estiverem disponíveis online.</span><span class="sxs-lookup"><span data-stu-id="6a98b-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a98b-106">Se você desinstalar o cliente do Skype for Business depois de mover um usuários para o modo **Somente Microsoft Teams**, a presença deixará de funcionar no Outlook e em outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="6a98b-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="6a98b-107">A presença funciona bem no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6a98b-107">Presence works fine in Teams.</span></span> <span data-ttu-id="6a98b-108">Solução alternativa: para ver a presença no Outlook (e em outros aplicativos do Office), o Skype for Business deve estar instalado, mesmo se você estiver executando o Microsoft Teams no modo **somente Teams** .</span><span class="sxs-lookup"><span data-stu-id="6a98b-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="6a98b-109">A Microsoft está ciente desse problema e trabalhando para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="6a98b-109">Microsoft is aware of this problem and is working on a fix.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="6a98b-110">Estados de presença no Teams</span><span class="sxs-lookup"><span data-stu-id="6a98b-110">Presence states in Teams</span></span>

<span data-ttu-id="6a98b-111">Os Estados de presença do usuário disponíveis no Teams são:</span><span class="sxs-lookup"><span data-stu-id="6a98b-111">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="6a98b-112">Configurado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="6a98b-112">User configured</span></span>|<span data-ttu-id="6a98b-113">Aplicativo configurado</span><span class="sxs-lookup"><span data-stu-id="6a98b-113">App configured</span></span>|
|:--- |:---|
| ![Marca de seleção verde estável, indica presença disponível](media/Presence_Available.png) <span data-ttu-id="6a98b-115">Disponível</span><span class="sxs-lookup"><span data-stu-id="6a98b-115">Available</span></span>|![Marca de seleção verde estável, indica presença disponível](media/Presence_Available.png) <span data-ttu-id="6a98b-117">Disponível</span><span class="sxs-lookup"><span data-stu-id="6a98b-117">Available</span></span>|
|| ![Abrir a marca de seleção verde, indica OOF disponível](media/Presence_Available_OOF.png) <span data-ttu-id="6a98b-119">Disponível, fora do escritório</span><span class="sxs-lookup"><span data-stu-id="6a98b-119">Available, Out of Office</span></span> |
|  ![Círculo vermelho sólido, indica ocupado](media/Presence_Busy.png) <span data-ttu-id="6a98b-121">Executando</span><span class="sxs-lookup"><span data-stu-id="6a98b-121">Busy</span></span> |  ![Círculo vermelho sólido, indica ocupado](media/Presence_Busy.png) <span data-ttu-id="6a98b-123">Executando</span><span class="sxs-lookup"><span data-stu-id="6a98b-123">Busy</span></span>  |
|| ![Círculo vermelho sólido, indica ocupado em uma chamada](media/Presence_Busy.png) <span data-ttu-id="6a98b-125">Em uma chamada</span><span class="sxs-lookup"><span data-stu-id="6a98b-125">In a call</span></span>|
|| ![Círculo vermelho sólido, indica ocupado em uma reunião](media/Presence_Busy.png) <span data-ttu-id="6a98b-127">Em uma reunião</span><span class="sxs-lookup"><span data-stu-id="6a98b-127">In a meeting</span></span> |
|| ![Abrir círculo vermelho, indica ocupado](media/Presence_Busy_OOF.png) <span data-ttu-id="6a98b-129">Em uma chamada, fora do escritório</span><span class="sxs-lookup"><span data-stu-id="6a98b-129">In a call, out of office</span></span>|
|  ![Círculo vermelho com linha branca, indica que não incomodar](media/Presence_DND.png) <span data-ttu-id="6a98b-131">Não incomodar</span><span class="sxs-lookup"><span data-stu-id="6a98b-131">Do not disturb</span></span> ||
|| ![Círculo vermelho com linha branca, indica a apresentação](media/Presence_DND.png) <span data-ttu-id="6a98b-133">Fazendo</span><span class="sxs-lookup"><span data-stu-id="6a98b-133">Presenting</span></span>|
|| ![Círculo vermelho com linha branca, indica foco](media/Presence_DND.png) <span data-ttu-id="6a98b-135">Foco</span><span class="sxs-lookup"><span data-stu-id="6a98b-135">Focusing</span></span>|
| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="6a98b-137">Aparece</span><span class="sxs-lookup"><span data-stu-id="6a98b-137">Away</span></span>| ![Ícone de relógio amarelo, indica ausente](media/Presence_Away.png) <span data-ttu-id="6a98b-139">Aparece</span><span class="sxs-lookup"><span data-stu-id="6a98b-139">Away</span></span>|
|| <span data-ttu-id="6a98b-140">![Ícone de relógio amarelo, indica](media/Presence_Away.png) o último *período* de vista ausente</span><span class="sxs-lookup"><span data-stu-id="6a98b-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![Ícone de relógio amarelo, indica ausente, volto logo](media/Presence_Away.png) <span data-ttu-id="6a98b-142">Volto logo</span><span class="sxs-lookup"><span data-stu-id="6a98b-142">Be right back</span></span>| |
|| ![Ícone de relógio amarelo, indica ausente, fora do trabalho](media/Presence_Away.png)  <span data-ttu-id="6a98b-144">Longe do trabalho</span><span class="sxs-lookup"><span data-stu-id="6a98b-144">Off Work</span></span>|
|| ![Círculo cinza com x, indica offline](media/Presence_Offline.png) <span data-ttu-id="6a98b-146">Modo</span><span class="sxs-lookup"><span data-stu-id="6a98b-146">Offline</span></span> |
|| ![Abrir círculo cinza, indica o status desconhecido](media/Presence_Unknown.png) <span data-ttu-id="6a98b-148">Status desconhecido</span><span class="sxs-lookup"><span data-stu-id="6a98b-148">Status unknown</span></span>|
||![Abrir círculo vermelho com linha diagonal, indica bloqueado](media/Presence_Blocked.png) <span data-ttu-id="6a98b-150">Bloqueado</span><span class="sxs-lookup"><span data-stu-id="6a98b-150">Blocked</span></span> |
|| ![Círculo roxo com seta, indica ausência temporária](media/Presence_OOF.png) <span data-ttu-id="6a98b-152">Fora do escritório</span><span class="sxs-lookup"><span data-stu-id="6a98b-152">Out of Office</span></span>|
|||
 
<span data-ttu-id="6a98b-153">Os usuários podem definir manualmente o estado de presença atual para algumas opções, e seu estado é refletido para todos os outros usuários.</span><span class="sxs-lookup"><span data-stu-id="6a98b-153">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="6a98b-154">Mais detalhes de presença do usuário também são atualizados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6a98b-154">More user presence details are also automatically updated.</span></span> <span data-ttu-id="6a98b-155">As alterações são baseadas na atividade do usuário (disponível, ausente), os Estados do calendário do Outlook (em uma reunião) ou os Estados do aplicativo Teams (em uma chamada, apresentação), para os Estados que são recuados na lista.</span><span class="sxs-lookup"><span data-stu-id="6a98b-155">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="6a98b-156">Há um tempo limite de inatividade de 15 minutos, após o qual um estado de presença atual é redefinido para ausente.</span><span class="sxs-lookup"><span data-stu-id="6a98b-156">There is a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="6a98b-157">Os usuários podem especificar quem pode fazer uma pausa (ou seja, entre em contato com eles apesar do estado não incomodar).</span><span class="sxs-lookup"><span data-stu-id="6a98b-157">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="6a98b-158">Essas configurações estão disponíveis no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="6a98b-158">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="6a98b-159">Configurações de administrador no Teams em comparação com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6a98b-159">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="6a98b-160">As seguintes configurações de administração do Skype for Business são diferentes no Teams:</span><span class="sxs-lookup"><span data-stu-id="6a98b-160">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="6a98b-161">No Teams, o compartilhamento de presença sempre é habilitado para os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="6a98b-161">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="6a98b-162">Privacidade (onde você define quem pode ver a presença) não está disponível no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6a98b-162">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="6a98b-163">O compartilhamento de presença com todos (incluindo serviços federados) sempre está habilitado para usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="6a98b-163">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="6a98b-164">Sua lista de contatos (se ela já tinha uma no Skype for Business) fica visível em **contatos de Chat >** ou em **chamadas > contatos**.</span><span class="sxs-lookup"><span data-stu-id="6a98b-164">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="6a98b-165">Cliente não incomodar e recursos revolucionários sempre são habilitados para usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="6a98b-165">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="6a98b-166">Calendário (inclui ausência temporária e outras informações do calendário) a integração sempre é habilitada para os usuários quando o Microsoft Teams está integrado ao Outlook.</span><span class="sxs-lookup"><span data-stu-id="6a98b-166">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="6a98b-167">O indicador mais *recente* ou *ausente já* está habilitado para usuários do teams se a organização também usa o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6a98b-167">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="6a98b-168">Não há suporte para a capacidade de um administrador de equipe personalizar essas configurações no momento.</span><span class="sxs-lookup"><span data-stu-id="6a98b-168">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="6a98b-169">Coexistência com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6a98b-169">Coexistence with Skype for Business</span></span>

<span data-ttu-id="6a98b-170">Veja a [coexistência com o Skype for Business](coexistence-chat-calls-presence.md) para obter detalhes sobre como as funções de presença do teams quando sua organização também usam o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6a98b-170">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
