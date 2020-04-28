---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Saiba mais sobre a experiência do cliente e a conformidade do teams nos modos de coexistência (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c67046128c79608f19a4a1f4474164a949f37ef
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903356"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="13b67-103">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="13b67-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="13b67-104">A finalidade dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais como as organizações migrando do Skype for Business para o Teams.</span><span class="sxs-lookup"><span data-stu-id="13b67-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="13b67-105">Para uma organização se movendo para o Microsoft Teams, o modo **somente Teams** é o destino final de cada usuário, mas nem todos os usuários precisam ter **somente equipes** atribuídas (ou qualquer outro modo) ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="13b67-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="13b67-106">Antes de os usuários alcançarem o modo TeamsOnly, as organizações podem usar qualquer um dos modos de coexistência do Skype for Business para garantir a comunicação previsível entre os usuários que são **somente equipes** e os que ainda não estão.</span><span class="sxs-lookup"><span data-stu-id="13b67-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="13b67-107">Quando um usuário está em qualquer um dos modos do Skype for Business, todos os chats e chamadas recebidos são roteados para o cliente Skype for Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="13b67-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="13b67-108">Para evitar a confusão do usuário final e garantir o roteamento adequado, a chamada e a funcionalidade de chat no cliente do teams são desabilitadas quando um usuário está em qualquer um dos modos do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="13b67-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="13b67-109">Da mesma forma, o agendamento da reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab, e explicitamente habilitados quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="13b67-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="13b67-110">Como a presença é uma indicação de acessibilidade por meio de chat e chamadas, quando o chat e as chamadas são desabilitados, a auto-instalação no Microsoft Teams (ou seja, a exibição da própria presença de uma no cliente do teams na imagem do usuário) também está oculta.</span><span class="sxs-lookup"><span data-stu-id="13b67-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="13b67-111">Como a funcionalidade disponível no cliente do teams muda com base no modo</span><span class="sxs-lookup"><span data-stu-id="13b67-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="13b67-112">A funcionalidade disponível no Teams depende do modo de coexistência do usuário, conforme definido pela TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="13b67-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="13b67-113">A tabela a seguir resume o comportamento:</span><span class="sxs-lookup"><span data-stu-id="13b67-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="13b67-114">Modo efetivo do usuário</span><span class="sxs-lookup"><span data-stu-id="13b67-114">User's effective mode</span></span>|<span data-ttu-id="13b67-115">Experiência no cliente da equipe</span><span class="sxs-lookup"><span data-stu-id="13b67-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="13b67-116">Qualquer modo do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="13b67-116">Any Skype for Business mode</span></span>|<span data-ttu-id="13b67-117">As chamadas, os chats e a presença automática são desabilitados.</span><span class="sxs-lookup"><span data-stu-id="13b67-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="13b67-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="13b67-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="13b67-119">O agendamento da reunião está disponível</span><span class="sxs-lookup"><span data-stu-id="13b67-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="13b67-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13b67-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="13b67-121">O agendamento da reunião não está disponível</span><span class="sxs-lookup"><span data-stu-id="13b67-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="13b67-122">As capturas de tela a seguir ilustram a diferença entre **somente as equipes** ou o modo de **ilhas** e todos os outros modos.</span><span class="sxs-lookup"><span data-stu-id="13b67-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="13b67-123">Observe que os ícones de chat e de chamada estão disponíveis por padrão com **apenas Teams** ou modo de **ilhas** (captura de tela à esquerda), mas não com os outros modos (captura de tela à direita):</span><span class="sxs-lookup"><span data-stu-id="13b67-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Uma comparação lado a lado dos modos de equipe](media/teams-mode-comparison.png)

<span data-ttu-id="13b67-125">Além disso, a própria presença não está disponível nos outros modos, conforme mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="13b67-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Captura de tela de presença automática em reuniões primeiro](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="13b67-127">**Observação:**
<sup>1</sup> no momento, SfBwithTeamsCollab e SfBOnly se comportam da mesma maneira, mas a intenção é para o modo de SfBOnly também desabilitar a funcionalidade de canais e arquivos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="13b67-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="13b67-128">No ínterim, os canais podem ser ocultos usando a política de permissões do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="13b67-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="13b67-129">Impacto do modo em outras configurações de política</span><span class="sxs-lookup"><span data-stu-id="13b67-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="13b67-130">Conforme descrito acima, o modo de coexistência de um usuário afeta a funcionalidade disponível no cliente do teams do usuário.</span><span class="sxs-lookup"><span data-stu-id="13b67-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="13b67-131">Isso significa que o valor de Mode pode prevalecer sobre o valor de outras configurações de política, dependendo do modo.</span><span class="sxs-lookup"><span data-stu-id="13b67-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="13b67-132">Especificamente, o modo de coexistência impacta se as seguintes configurações de política são atendidas:</span><span class="sxs-lookup"><span data-stu-id="13b67-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="13b67-133">**Modalidade (app)**</span><span class="sxs-lookup"><span data-stu-id="13b67-133">**Modality (App)**</span></span>|<span data-ttu-id="13b67-134">**Política. setting**</span><span class="sxs-lookup"><span data-stu-id="13b67-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="13b67-135">Chat</span><span class="sxs-lookup"><span data-stu-id="13b67-135">Chat</span></span>|<span data-ttu-id="13b67-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="13b67-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="13b67-137">Chamadas</span><span class="sxs-lookup"><span data-stu-id="13b67-137">Calling</span></span>|<span data-ttu-id="13b67-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="13b67-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="13b67-139">Agendamento de reunião</span><span class="sxs-lookup"><span data-stu-id="13b67-139">Meeting scheduling</span></span>|<span data-ttu-id="13b67-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="13b67-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="13b67-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="13b67-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="13b67-142">Os administradores *não* precisam definir explicitamente essas configurações de política ao usar o modo de coexistência, mas é importante entender que essas configurações se comportam de forma eficaz para um determinado modo.</span><span class="sxs-lookup"><span data-stu-id="13b67-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="13b67-143">Modo</span><span class="sxs-lookup"><span data-stu-id="13b67-143">Mode</span></span>|<span data-ttu-id="13b67-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="13b67-144">AllowUserChat</span></span>|<span data-ttu-id="13b67-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="13b67-145">AllowPrivateCalling</span></span>|<span data-ttu-id="13b67-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="13b67-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="13b67-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="13b67-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="13b67-148">TeamsOnly ou ilhas</span><span class="sxs-lookup"><span data-stu-id="13b67-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="13b67-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-149">Enabled</span></span>|<span data-ttu-id="13b67-150">Habilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-150">Enabled</span></span>|<span data-ttu-id="13b67-151">Habilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-151">Enabled</span></span>|<span data-ttu-id="13b67-152">Habilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-152">Enabled</span></span>|
|<span data-ttu-id="13b67-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="13b67-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="13b67-154">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-154">Disabled</span></span>|<span data-ttu-id="13b67-155">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-155">Disabled</span></span>|<span data-ttu-id="13b67-156">Habilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-156">Enabled</span></span>|<span data-ttu-id="13b67-157">Habilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-157">Enabled</span></span>|
|<span data-ttu-id="13b67-158">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="13b67-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="13b67-159">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-159">Disabled</span></span>|<span data-ttu-id="13b67-160">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-160">Disabled</span></span>|<span data-ttu-id="13b67-161">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-161">Disabled</span></span>|<span data-ttu-id="13b67-162">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="13b67-162">Disabled</span></span>|
||||||

<span data-ttu-id="13b67-163">Ao usar o PowerShell, `Grant-CsTeamsUpgradePolicy` o cmdlet verifica a configuração das configurações correspondentes em TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam substituídas por TeamsUpgradePolicy e, nesse caso, uma mensagem informativa é fornecida no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13b67-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="13b67-164">Conforme observado acima, não é mais necessário definir essas outras configurações de política.</span><span class="sxs-lookup"><span data-stu-id="13b67-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="13b67-165">Veja a seguir um exemplo de como é a aparência do aviso do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="13b67-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="13b67-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="13b67-166">Related topics</span></span>

[<span data-ttu-id="13b67-167">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="13b67-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




