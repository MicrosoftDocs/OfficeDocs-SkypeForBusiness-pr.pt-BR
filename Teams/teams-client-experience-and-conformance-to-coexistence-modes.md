---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Saiba mais Teams experiência do cliente e conformidade com modos de coexistência (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119250"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="6768c-103">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="6768c-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="6768c-104">O objetivo dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais à medida que as organizações migram de Skype for Business para Teams.</span><span class="sxs-lookup"><span data-stu-id="6768c-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="6768c-105">Para uma organização mudar para Teams, o modo somente **Teams** é o destino final para cada usuário, embora nem todos os usuários precisem ser atribuídos somente Teams **(ou** qualquer outro modo) ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="6768c-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="6768c-106">Antes de os usuários chegarem ao modo TeamsOnly, as organizações podem usar qualquer um dos modos de coexistência do Skype for Business para garantir uma comunicação previsível entre os usuários que estão Teams **somente** e aqueles que ainda não estão.</span><span class="sxs-lookup"><span data-stu-id="6768c-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="6768c-107">Quando um usuário está em qualquer um dos modos Skype for Business, todos os chats de entrada e chamadas são roteados para o cliente Skype for Business usuário.</span><span class="sxs-lookup"><span data-stu-id="6768c-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="6768c-108">Para evitar confusão do usuário final e garantir o roteamento adequado, a funcionalidade de chamada e de chat no cliente Teams é desabilitada quando um usuário está em qualquer um dos modos Skype for Business de usuário.</span><span class="sxs-lookup"><span data-stu-id="6768c-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="6768c-109">Da mesma forma, o agendamento de reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e explicitamente habilitados quando um usuário está no modo SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="6768c-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="6768c-110">Como a presença é uma indicação de alcance por meio de chat e chamada, quando o chat e a chamada são desabilitados, a auto-presença no Teams (ou seja, a exibição da própria presença no cliente Teams na imagem do usuário) também fica oculta.</span><span class="sxs-lookup"><span data-stu-id="6768c-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="6768c-111">Como a funcionalidade disponível no Teams cliente muda com base no modo</span><span class="sxs-lookup"><span data-stu-id="6768c-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="6768c-112">A funcionalidade disponível no Teams depende do modo de coexistência do usuário, conforme definido por TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="6768c-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="6768c-113">A tabela a seguir resume o comportamento:</span><span class="sxs-lookup"><span data-stu-id="6768c-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="6768c-114">Modo efetivo do usuário</span><span class="sxs-lookup"><span data-stu-id="6768c-114">User's effective mode</span></span>|<span data-ttu-id="6768c-115">Experiência no Teams cliente</span><span class="sxs-lookup"><span data-stu-id="6768c-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="6768c-116">Qualquer Skype for Business modo</span><span class="sxs-lookup"><span data-stu-id="6768c-116">Any Skype for Business mode</span></span>|<span data-ttu-id="6768c-117">A chamada, o Chat e a auto-presença estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="6768c-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="6768c-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="6768c-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="6768c-119">Agendamento de reuniões está disponível</span><span class="sxs-lookup"><span data-stu-id="6768c-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="6768c-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6768c-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="6768c-121">O agendamento de reuniões não está disponível</span><span class="sxs-lookup"><span data-stu-id="6768c-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="6768c-122">As capturas de tela a seguir ilustram a diferença entre Teams **modo Somente** ou **Ilhas** e todos os outros modos.</span><span class="sxs-lookup"><span data-stu-id="6768c-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="6768c-123">Observe que os ícones de chat e  chamada estão disponíveis por padrão com o modo Somente Teams ou **Ilhas** (captura de tela à esquerda), mas não com os outros modos (captura de tela à direita):</span><span class="sxs-lookup"><span data-stu-id="6768c-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Uma comparação lado a lado de Teams modos](media/teams-mode-comparison.png)

<span data-ttu-id="6768c-125">Além disso, a auto-presença não está disponível nos outros modos, conforme mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="6768c-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Captura de tela de auto-presença em Reuniões Primeiro](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="6768c-127">**Observação:** 
 <sup>1</sup> Neste momento, SfBwithTeamsCollab e SfBOnly se comportam da mesma forma, mas a intenção é que o modo SfBOnly também desabilite a funcionalidade Canais e Arquivos no Teams.</span><span class="sxs-lookup"><span data-stu-id="6768c-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="6768c-128">Nesse ínterim, os canais podem ser ocultos usando a política permissões do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6768c-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="6768c-129">Impacto do modo em outras configurações de política</span><span class="sxs-lookup"><span data-stu-id="6768c-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="6768c-130">Conforme descrito acima, o impacto do modo de coexistência de um usuário é a funcionalidade disponível no cliente Teams usuário.</span><span class="sxs-lookup"><span data-stu-id="6768c-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="6768c-131">Isso significa que o valor do modo pode ter precedência sobre o valor de outras configurações de política, dependendo do modo.</span><span class="sxs-lookup"><span data-stu-id="6768c-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="6768c-132">Especificamente, o modo de coexistência afeta se as seguintes configurações de política são atendida:</span><span class="sxs-lookup"><span data-stu-id="6768c-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="6768c-133">**Modalidade (App)**</span><span class="sxs-lookup"><span data-stu-id="6768c-133">**Modality (App)**</span></span>|<span data-ttu-id="6768c-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="6768c-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="6768c-135">Chat</span><span class="sxs-lookup"><span data-stu-id="6768c-135">Chat</span></span>|<span data-ttu-id="6768c-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="6768c-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="6768c-137">Chamadas</span><span class="sxs-lookup"><span data-stu-id="6768c-137">Calling</span></span>|<span data-ttu-id="6768c-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="6768c-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="6768c-139">Agendamento de reuniões</span><span class="sxs-lookup"><span data-stu-id="6768c-139">Meeting scheduling</span></span>|<span data-ttu-id="6768c-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="6768c-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="6768c-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="6768c-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="6768c-142">Os *administradores* não precisam definir explicitamente essas configurações de política ao usar o modo de co-existência, mas é importante entender que essas configurações se comportam efetivamente da seguinte maneira para um determinado modo.</span><span class="sxs-lookup"><span data-stu-id="6768c-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="6768c-143">Modo</span><span class="sxs-lookup"><span data-stu-id="6768c-143">Mode</span></span>|<span data-ttu-id="6768c-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="6768c-144">AllowUserChat</span></span>|<span data-ttu-id="6768c-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="6768c-145">AllowPrivateCalling</span></span>|<span data-ttu-id="6768c-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="6768c-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="6768c-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="6768c-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="6768c-148">TeamsOnly ou Islands</span><span class="sxs-lookup"><span data-stu-id="6768c-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="6768c-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-149">Enabled</span></span>|<span data-ttu-id="6768c-150">Habilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-150">Enabled</span></span>|<span data-ttu-id="6768c-151">Habilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-151">Enabled</span></span>|<span data-ttu-id="6768c-152">Habilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-152">Enabled</span></span>|
|<span data-ttu-id="6768c-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="6768c-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="6768c-154">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-154">Disabled</span></span>|<span data-ttu-id="6768c-155">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-155">Disabled</span></span>|<span data-ttu-id="6768c-156">Habilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-156">Enabled</span></span>|<span data-ttu-id="6768c-157">Habilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-157">Enabled</span></span>|
|<span data-ttu-id="6768c-158">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="6768c-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="6768c-159">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-159">Disabled</span></span>|<span data-ttu-id="6768c-160">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-160">Disabled</span></span>|<span data-ttu-id="6768c-161">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-161">Disabled</span></span>|<span data-ttu-id="6768c-162">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="6768c-162">Disabled</span></span>|
||||||

<span data-ttu-id="6768c-163">Ao usar o PowerShell, o cmdlet verifica a configuração das configurações correspondentes em `Grant-CsTeamsUpgradePolicy` TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam substituídos pelo TeamsUpgradePolicy e, em caso afirmativo, uma mensagem informativa é fornecida no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6768c-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="6768c-164">Conforme mencionado acima, não é mais necessário definir essas outras configurações de política.</span><span class="sxs-lookup"><span data-stu-id="6768c-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="6768c-165">Veja a seguir um exemplo da aparência do aviso do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6768c-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="6768c-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6768c-166">Related topics</span></span>

[<span data-ttu-id="6768c-167">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6768c-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)