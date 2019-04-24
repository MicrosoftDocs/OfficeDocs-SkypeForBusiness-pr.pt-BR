---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Experiência do cliente de equipes e conformidade aos modos de coexistência
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e62dd8a19e2207f6b40864cab19a3fda48d184fe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204648"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="8281d-103">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="8281d-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="8281d-104">Esta página descreve alterações importantes, liberadas recentemente no comportamento do cliente de equipes, quando os usuários estiverem em qualquer uma do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="8281d-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="8281d-105">A finalidade dos modos de coexistência é fornecer uma experiência previsível simple para usuários finais como transição de organizações do Skype para negócios às equipes.</span><span class="sxs-lookup"><span data-stu-id="8281d-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="8281d-106">Para uma organização mudando para equipes, o modo TeamsOnly é o destino final para cada usuário, embora nem todos os usuários precisam ser atribuídas TeamsOnly (ou qualquer outro modo) ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="8281d-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="8281d-107">Antes de usuários está atingindo o modo TeamsOnly, as organizações podem usar qualquer um do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir a comunicação entre os usuários que são TeamsOnly e aqueles que não são ainda previsível.</span><span class="sxs-lookup"><span data-stu-id="8281d-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="8281d-108">Quando um usuário estiver em qualquer um do Skype para modos de negócios, todas as chamadas e chats de entrada são roteadas para Skype do usuário para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="8281d-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="8281d-109">Para evitar a confusão do usuário final e garantir o roteamento apropriado, a funcionalidade de chamada e bate-papo no cliente equipes está desabilitada quando um usuário está em qualquer uma do Skype para modos de negócios.</span><span class="sxs-lookup"><span data-stu-id="8281d-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="8281d-110">Da mesma forma, o agendamento de reuniões em equipes é explicitamente desabilitado quando os usuários estiverem nos modos de SfBOnly ou SfBWithTeamsCollab e explicitamente habilitado quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="8281d-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="8281d-111">Como a funcionalidade disponível no cliente de equipes muda com base no modo</span><span class="sxs-lookup"><span data-stu-id="8281d-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="8281d-112">A funcionalidade disponível nas equipes depende do modo de coexistência do usuário, como definido pelo TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="8281d-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="8281d-113">A tabela a seguir resume o comportamento:</span><span class="sxs-lookup"><span data-stu-id="8281d-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="8281d-114">Modo de usuário efetivo</span><span class="sxs-lookup"><span data-stu-id="8281d-114">User's effective mode</span></span>|<span data-ttu-id="8281d-115">Experiência com o cliente de equipes</span><span class="sxs-lookup"><span data-stu-id="8281d-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="8281d-116">Qualquer Skype para o modo de negócios</span><span class="sxs-lookup"><span data-stu-id="8281d-116">Any Skype for Business mode</span></span>|<span data-ttu-id="8281d-117">Chamada e bate-papo estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="8281d-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="8281d-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="8281d-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="8281d-119">Agendamento de reunião está disponível</span><span class="sxs-lookup"><span data-stu-id="8281d-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="8281d-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8281d-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="8281d-121">Agendamento de reunião não está disponível</span><span class="sxs-lookup"><span data-stu-id="8281d-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="8281d-122">As capturas de tela a seguintes ilustram a diferença entre modo TeamsOnly ou Ilhas e todos os outros modos.</span><span class="sxs-lookup"><span data-stu-id="8281d-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="8281d-123">Observe que os ícones de bate-papo e chamadas estão disponíveis com TeamsOnly ou Ilhas modo (captura de tela da esquerda), mas não com outros modos (captura de tela direita):</span><span class="sxs-lookup"><span data-stu-id="8281d-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Mostra as comparações de modo de equipes](media/teams-mode-comparison.png)


 
<span data-ttu-id="8281d-125">**Observação:**
<sup>1</sup> no momento, SfBwithTeamsCollab e SfBOnly se comportam da mesma, mas a intenção é para o modo de SfBOnly também desativar a funcionalidade de arquivos e canais em equipes; No entanto, não há atualmente nenhuma configuração que permite essa funcionalidade em equipes a ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="8281d-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="8281d-126">Impacto do modo em outras configurações de política</span><span class="sxs-lookup"><span data-stu-id="8281d-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="8281d-127">Conforme descrito acima, do impacto de modo para a coexistência do usuário a funcionalidade para a qual está disponível no cliente de equipes do usuário.</span><span class="sxs-lookup"><span data-stu-id="8281d-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="8281d-128">Isso significa que o valor do modo pode têm precedência sobre o valor de outras configurações de política, dependendo do modo.</span><span class="sxs-lookup"><span data-stu-id="8281d-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="8281d-129">Especificamente, o modo de coexistência impacta se as seguintes configurações de diretiva são observadas:</span><span class="sxs-lookup"><span data-stu-id="8281d-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="8281d-130">**Modalidade (App)**</span><span class="sxs-lookup"><span data-stu-id="8281d-130">**Modality (App)**</span></span>|<span data-ttu-id="8281d-131">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="8281d-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="8281d-132">Chat</span><span class="sxs-lookup"><span data-stu-id="8281d-132">Chat</span></span>|<span data-ttu-id="8281d-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="8281d-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="8281d-134">Chamadas</span><span class="sxs-lookup"><span data-stu-id="8281d-134">Calling</span></span>|<span data-ttu-id="8281d-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="8281d-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="8281d-136">Agendamento de reuniões</span><span class="sxs-lookup"><span data-stu-id="8281d-136">Meeting scheduling</span></span>|<span data-ttu-id="8281d-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8281d-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="8281d-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8281d-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="8281d-139">Os administradores precisam *não* explicitamente definir essas configurações de diretiva quando usando o modo de coexistência, mas ele é importante entender que essas configurações efetivamente se comportam como a seguir para um determinado modo.</span><span class="sxs-lookup"><span data-stu-id="8281d-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="8281d-140">Modo</span><span class="sxs-lookup"><span data-stu-id="8281d-140">Mode</span></span>|<span data-ttu-id="8281d-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="8281d-141">AllowUserChat</span></span>|<span data-ttu-id="8281d-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="8281d-142">AllowPrivateCalling</span></span>|<span data-ttu-id="8281d-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8281d-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="8281d-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="8281d-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="8281d-145">TeamsOnly ou Ilhas</span><span class="sxs-lookup"><span data-stu-id="8281d-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="8281d-146">Habilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-146">Enabled</span></span>|<span data-ttu-id="8281d-147">Habilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-147">Enabled</span></span>|<span data-ttu-id="8281d-148">Habilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-148">Enabled</span></span>|<span data-ttu-id="8281d-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-149">Enabled</span></span>|
|<span data-ttu-id="8281d-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="8281d-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="8281d-151">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-151">Disabled</span></span>|<span data-ttu-id="8281d-152">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-152">Disabled</span></span>|<span data-ttu-id="8281d-153">Habilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-153">Enabled</span></span>|<span data-ttu-id="8281d-154">Habilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-154">Enabled</span></span>|
|<span data-ttu-id="8281d-155">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="8281d-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="8281d-156">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-156">Disabled</span></span>|<span data-ttu-id="8281d-157">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-157">Disabled</span></span>|<span data-ttu-id="8281d-158">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-158">Disabled</span></span>|<span data-ttu-id="8281d-159">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="8281d-159">Disabled</span></span>|
||||||

<span data-ttu-id="8281d-160">Ao usar o PowerShell, a `Grant-CsTeamsUpgradePolicy` cmdlet verifica a configuração das respectivas configurações na TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam ser substituídas pelos TeamsUpgradePolicy e em caso afirmativo, um mensagem informativa é fornecida no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8281d-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="8281d-161">Conforme observado anteriormente, não é necessário definir essas outras configurações de diretiva.</span><span class="sxs-lookup"><span data-stu-id="8281d-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="8281d-162">Abaixo é um exemplo de aviso PowerShell se parece com:</span><span class="sxs-lookup"><span data-stu-id="8281d-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="8281d-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8281d-163">Related topics</span></span>

[<span data-ttu-id="8281d-164">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8281d-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




