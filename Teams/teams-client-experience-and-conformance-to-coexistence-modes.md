---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Saiba mais sobre a experiência do cliente do Teams e a conformidade com os modos de coexistência (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821021"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="0db3a-103">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="0db3a-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="0db3a-104">A finalidade dos modos de coexistência do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) é fornecer uma experiência simples e previsível para os usuários finais à medida que as organizações migram do Skype for Business para o Teams.</span><span class="sxs-lookup"><span data-stu-id="0db3a-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="0db3a-105">Para uma organização que  está mudando para o Teams, o modo Somente equipes é o destino final para cada usuário, embora nem todos os usuários precisem ter apenas o **Teams** (ou qualquer outro modo) ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="0db3a-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="0db3a-106">Antes de os usuários chegarem ao modo TeamsOnly, as organizações podem usar qualquer um dos modos de coexistência do Skype for Business para garantir uma comunicação previsível entre usuários somente do **Teams** e aqueles que ainda não estão.</span><span class="sxs-lookup"><span data-stu-id="0db3a-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="0db3a-107">Quando um usuário está em qualquer um dos modos do Skype for Business, todos os chats de entrada e chamadas são roteados para o cliente Skype for Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="0db3a-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="0db3a-108">Para evitar confusão do usuário final e garantir o roteamento adequado, a funcionalidade de chamadas e chat no cliente do Teams é desabilitada quando um usuário está em qualquer um dos modos do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0db3a-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="0db3a-109">Da mesma forma, o agendamento de reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab e explicitamente habilitados quando um usuário está no modo SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="0db3a-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="0db3a-110">Como a presença é uma indicação de acessibilidade por meio de chat e chamada, quando o chat e as chamada são desabilitados, a própria presença no Teams (ou seja, a exibição da própria presença no cliente do Teams na imagem do usuário) também fica oculta.</span><span class="sxs-lookup"><span data-stu-id="0db3a-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="0db3a-111">Como a funcionalidade disponível no cliente do Teams muda com base no modo</span><span class="sxs-lookup"><span data-stu-id="0db3a-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="0db3a-112">A funcionalidade disponível no Teams depende do modo de coexistência do usuário, conforme definido pelo TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="0db3a-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="0db3a-113">A tabela a seguir resume o comportamento:</span><span class="sxs-lookup"><span data-stu-id="0db3a-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="0db3a-114">Modo eficaz do usuário</span><span class="sxs-lookup"><span data-stu-id="0db3a-114">User's effective mode</span></span>|<span data-ttu-id="0db3a-115">Experiência no cliente do Teams</span><span class="sxs-lookup"><span data-stu-id="0db3a-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="0db3a-116">Qualquer modo do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0db3a-116">Any Skype for Business mode</span></span>|<span data-ttu-id="0db3a-117">As chamada, o chat e a autoexecução estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="0db3a-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="0db3a-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="0db3a-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="0db3a-119">O agendamento de reunião está disponível</span><span class="sxs-lookup"><span data-stu-id="0db3a-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="0db3a-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0db3a-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="0db3a-121">O agendamento de reunião não está disponível</span><span class="sxs-lookup"><span data-stu-id="0db3a-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="0db3a-122">As capturas de tela a seguir  ilustram a diferença entre o **modo Somente equipes** ou ilhas e todos os outros modos.</span><span class="sxs-lookup"><span data-stu-id="0db3a-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="0db3a-123">Observe que os ícones de chat e chamada  estão disponíveis por padrão com o modo Somente do **Teams** ou Ilhas (captura de tela à esquerda), mas não com os outros modos (captura de tela à direita):</span><span class="sxs-lookup"><span data-stu-id="0db3a-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Uma comparação lado a lado dos modos do Teams](media/teams-mode-comparison.png)

<span data-ttu-id="0db3a-125">Além disso, a autoexecução não está disponível nos outros modos, conforme mostrado aqui.</span><span class="sxs-lookup"><span data-stu-id="0db3a-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![Captura de tela de autoexecução em Reuniões Primeiro](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="0db3a-127">**Observação:** 
 <sup>1</sup> Neste momento, o SfBwithTeamsCollab e o SfBOnly se comportam da mesma forma, mas a intenção é que o modo SfBOnly também desabilite a funcionalidade Canais e Arquivos no Teams.</span><span class="sxs-lookup"><span data-stu-id="0db3a-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="0db3a-128">Na medida provisória, os Canais podem ser ocultos usando a política permissões do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0db3a-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="0db3a-129">Impacto do Modo em outras configurações de política</span><span class="sxs-lookup"><span data-stu-id="0db3a-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="0db3a-130">Conforme descrito acima, o modo de coexistência de um usuário afeta qual funcionalidade está disponível no cliente do Teams do usuário.</span><span class="sxs-lookup"><span data-stu-id="0db3a-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="0db3a-131">Isso significa que o valor do modo pode ter precedência sobre o valor de outras configurações de política, dependendo do modo.</span><span class="sxs-lookup"><span data-stu-id="0db3a-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="0db3a-132">Especificamente, o modo de coexistência afeta se as seguintes configurações de política são atendida:</span><span class="sxs-lookup"><span data-stu-id="0db3a-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="0db3a-133">**Modalidade (Aplicativo)**</span><span class="sxs-lookup"><span data-stu-id="0db3a-133">**Modality (App)**</span></span>|<span data-ttu-id="0db3a-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="0db3a-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="0db3a-135">Chat</span><span class="sxs-lookup"><span data-stu-id="0db3a-135">Chat</span></span>|<span data-ttu-id="0db3a-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="0db3a-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="0db3a-137">Chamadas</span><span class="sxs-lookup"><span data-stu-id="0db3a-137">Calling</span></span>|<span data-ttu-id="0db3a-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="0db3a-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="0db3a-139">Agendamento de reunião</span><span class="sxs-lookup"><span data-stu-id="0db3a-139">Meeting scheduling</span></span>|<span data-ttu-id="0db3a-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0db3a-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="0db3a-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0db3a-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="0db3a-142">Os *administradores* não precisam definir explicitamente essas configurações de política ao usar o modo de co-existência, mas é importante compreender que essas configurações se comportam efetivamente da seguinte maneira para um determinado modo.</span><span class="sxs-lookup"><span data-stu-id="0db3a-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="0db3a-143">Modo</span><span class="sxs-lookup"><span data-stu-id="0db3a-143">Mode</span></span>|<span data-ttu-id="0db3a-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="0db3a-144">AllowUserChat</span></span>|<span data-ttu-id="0db3a-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="0db3a-145">AllowPrivateCalling</span></span>|<span data-ttu-id="0db3a-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0db3a-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="0db3a-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="0db3a-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="0db3a-148">TeamsOnly ou Islands</span><span class="sxs-lookup"><span data-stu-id="0db3a-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="0db3a-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-149">Enabled</span></span>|<span data-ttu-id="0db3a-150">Habilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-150">Enabled</span></span>|<span data-ttu-id="0db3a-151">Habilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-151">Enabled</span></span>|<span data-ttu-id="0db3a-152">Habilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-152">Enabled</span></span>|
|<span data-ttu-id="0db3a-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="0db3a-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="0db3a-154">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-154">Disabled</span></span>|<span data-ttu-id="0db3a-155">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-155">Disabled</span></span>|<span data-ttu-id="0db3a-156">Habilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-156">Enabled</span></span>|<span data-ttu-id="0db3a-157">Habilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-157">Enabled</span></span>|
|<span data-ttu-id="0db3a-158">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="0db3a-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="0db3a-159">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-159">Disabled</span></span>|<span data-ttu-id="0db3a-160">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-160">Disabled</span></span>|<span data-ttu-id="0db3a-161">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-161">Disabled</span></span>|<span data-ttu-id="0db3a-162">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="0db3a-162">Disabled</span></span>|
||||||

<span data-ttu-id="0db3a-163">Ao usar o PowerShell, o cmdlet verifica a configuração das configurações correspondentes em `Grant-CsTeamsUpgradePolicy` TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam superadas pelo TeamsUpgradePolicy e, em caso afirmativo, uma mensagem informativa é fornecida no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0db3a-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="0db3a-164">Conforme mencionado acima, não é mais necessário definir essas outras configurações de política.</span><span class="sxs-lookup"><span data-stu-id="0db3a-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="0db3a-165">Veja a seguir um exemplo da aparência do aviso do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0db3a-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="0db3a-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0db3a-166">Related topics</span></span>

[<span data-ttu-id="0db3a-167">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0db3a-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




