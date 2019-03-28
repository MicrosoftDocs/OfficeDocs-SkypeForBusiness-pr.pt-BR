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
ms.openlocfilehash: 4865d66d4d3ff1257d0fc4bd355a65c7c1330101
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934784"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="f8036-103">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="f8036-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="f8036-104">Esta página descreve alterações importantes, liberadas recentemente no comportamento do cliente de equipes, quando os usuários estiverem em qualquer uma do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="f8036-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="f8036-105">A finalidade dos modos de coexistência é fornecer uma experiência previsível simple para usuários finais como transição de organizações do Skype para negócios às equipes.</span><span class="sxs-lookup"><span data-stu-id="f8036-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="f8036-106">Para uma organização mudando para equipes, o modo TeamsOnly é o destino final para cada usuário, embora nem todos os usuários precisam ser atribuídas TeamsOnly (ou qualquer outro modo) ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="f8036-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="f8036-107">Antes de usuários está atingindo o modo TeamsOnly, as organizações podem usar qualquer um do Skype para modos de negócios (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir a comunicação entre os usuários que são TeamsOnly e aqueles que não são ainda previsível.</span><span class="sxs-lookup"><span data-stu-id="f8036-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="f8036-108">Quando um usuário estiver em qualquer um do Skype para modos de negócios, todas as chamadas e chats de entrada são roteadas para Skype do usuário para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="f8036-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="f8036-109">Para evitar a confusão do usuário final e garantir o roteamento apropriado, a funcionalidade de chamada e bate-papo no cliente equipes está desabilitada quando um usuário está em qualquer uma do Skype para modos de negócios.</span><span class="sxs-lookup"><span data-stu-id="f8036-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="f8036-110">Da mesma forma, o agendamento de reuniões em equipes é explicitamente desabilitado quando os usuários estiverem nos modos de SfBOnly ou SfBWithTeamsCollab e explicitamente habilitado quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="f8036-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="f8036-111">Como a funcionalidade disponível no cliente de equipes muda com base no modo</span><span class="sxs-lookup"><span data-stu-id="f8036-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="f8036-112">A funcionalidade disponível no equipes dependes no modo de coexistência do usuário, como definido pelo TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="f8036-112">The available functionality in Teams dependes on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="f8036-113">A tabela a seguir resume o comportamento:</span><span class="sxs-lookup"><span data-stu-id="f8036-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="f8036-114">Modo de usuário efetivo</span><span class="sxs-lookup"><span data-stu-id="f8036-114">User's effective mode</span></span>|<span data-ttu-id="f8036-115">Experiência com o cliente de equipes</span><span class="sxs-lookup"><span data-stu-id="f8036-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="f8036-116">Qualquer Skype para o modo de negócios</span><span class="sxs-lookup"><span data-stu-id="f8036-116">Any Skype for Business mode</span></span>|<span data-ttu-id="f8036-117">Chamada e bate-papo<sup>1</sup> estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="f8036-117">Calling and Chat<sup>1</sup> are disabled.</span></span>|
|<span data-ttu-id="f8036-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="f8036-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="f8036-119">Agendamento de reunião está disponível</span><span class="sxs-lookup"><span data-stu-id="f8036-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="f8036-120">SfBWithTeamsCollab ou SfBOnly<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f8036-120">SfBWithTeamsCollab or SfBOnly<sup>2</sup></span></span>|<span data-ttu-id="f8036-121">Agendamento de reunião não está disponível</span><span class="sxs-lookup"><span data-stu-id="f8036-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="f8036-122">As capturas de tela a seguintes ilustram a diferença entre modo TeamsOnly ou Ilhas e todos os outros modos.</span><span class="sxs-lookup"><span data-stu-id="f8036-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="f8036-123">Observe que os ícones de bate-papo e chamadas estão disponíveis com TeamsOnly ou Ilhas modo (captura de tela da esquerda), mas não com outros modos (captura de tela direita):</span><span class="sxs-lookup"><span data-stu-id="f8036-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Mostra as comparações de modo de equipes](media/teams-mode-comparison.png)


 
<span data-ttu-id="f8036-125">**Observações:**
<sup>1</sup> bate-papo de reunião ainda está disponível.</span><span class="sxs-lookup"><span data-stu-id="f8036-125">**Notes:**
<sup>1</sup> Meeting chat is still available.</span></span>

<span data-ttu-id="f8036-126"><sup>2</sup> no momento, SfBwithTeamsCollab e SfBOnly se comportam da mesma, mas a intenção é para o modo de SfBOnly também desativar a funcionalidade de arquivos e canais em equipes; No entanto, não há atualmente nenhuma configuração que permite essa funcionalidade em equipes a ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="f8036-126"><sup>2</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="f8036-127">Impacto do modo em outras configurações de política</span><span class="sxs-lookup"><span data-stu-id="f8036-127">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="f8036-128">Conforme descrito acima, do impacto de modo para a coexistência do usuário a funcionalidade para a qual está disponível no cliente de equipes do usuário.</span><span class="sxs-lookup"><span data-stu-id="f8036-128">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="f8036-129">Isso significa que o valor do modo pode têm precedência sobre o valor de outras configurações de política, dependendo do modo.</span><span class="sxs-lookup"><span data-stu-id="f8036-129">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="f8036-130">Especificamente, o modo de coexistência impacta se as seguintes configurações de diretiva são observadas:</span><span class="sxs-lookup"><span data-stu-id="f8036-130">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="f8036-131">**Modalidade (App)**</span><span class="sxs-lookup"><span data-stu-id="f8036-131">**Modality (App)**</span></span>|<span data-ttu-id="f8036-132">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="f8036-132">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="f8036-133">Chat</span><span class="sxs-lookup"><span data-stu-id="f8036-133">Chat</span></span>|<span data-ttu-id="f8036-134">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="f8036-134">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="f8036-135">Chamadas</span><span class="sxs-lookup"><span data-stu-id="f8036-135">Calling</span></span>|<span data-ttu-id="f8036-136">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="f8036-136">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="f8036-137">Agendamento de reuniões</span><span class="sxs-lookup"><span data-stu-id="f8036-137">Meeting scheduling</span></span>|<span data-ttu-id="f8036-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f8036-138">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="f8036-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f8036-139">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="f8036-140">Os administradores precisam *não* explicitamente definir essas configurações de diretiva quando usando o modo de coexistência, mas ele é importante entender que essas configurações efetivamente se comportam como a seguir para um determinado modo.</span><span class="sxs-lookup"><span data-stu-id="f8036-140">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="f8036-141">Modo</span><span class="sxs-lookup"><span data-stu-id="f8036-141">Mode</span></span>|<span data-ttu-id="f8036-142">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="f8036-142">AllowUserChat</span></span>|<span data-ttu-id="f8036-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="f8036-143">AllowPrivateCalling</span></span>|<span data-ttu-id="f8036-144">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f8036-144">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="f8036-145">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="f8036-145">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="f8036-146">TeamsOnly ou Ilhas</span><span class="sxs-lookup"><span data-stu-id="f8036-146">TeamsOnly or Islands</span></span>|<span data-ttu-id="f8036-147">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-147">Enabled</span></span>|<span data-ttu-id="f8036-148">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-148">Enabled</span></span>|<span data-ttu-id="f8036-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-149">Enabled</span></span>|<span data-ttu-id="f8036-150">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-150">Enabled</span></span>|
|<span data-ttu-id="f8036-151">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="f8036-151">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="f8036-152">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-152">Disabled</span></span>|<span data-ttu-id="f8036-153">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-153">Disabled</span></span>|<span data-ttu-id="f8036-154">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-154">Enabled</span></span>|<span data-ttu-id="f8036-155">Habilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-155">Enabled</span></span>|
|<span data-ttu-id="f8036-156">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="f8036-156">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="f8036-157">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-157">Disabled</span></span>|<span data-ttu-id="f8036-158">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-158">Disabled</span></span>|<span data-ttu-id="f8036-159">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-159">Disabled</span></span>|<span data-ttu-id="f8036-160">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="f8036-160">Disabled</span></span>|
||||||

<span data-ttu-id="f8036-161">Em breve, o `Grant-CsTeamsUpgradePolicy` cmdlet irá verificar a configuração das respectivas configurações na TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações serão ser substituídas pelos TeamsUpgradePolicy e em caso afirmativo, um mensagem informativa é fornecida no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8036-161">In the near future, the `Grant-CsTeamsUpgradePolicy` cmdlet will check the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings will be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="f8036-162">Conforme observado anteriormente, não é necessário definir essas outras configurações de diretiva.</span><span class="sxs-lookup"><span data-stu-id="f8036-162">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="f8036-163">Abaixo é um exemplo de aviso PowerShell se parece com:</span><span class="sxs-lookup"><span data-stu-id="f8036-163">Below is an example of what the PowerShell warning  looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="f8036-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f8036-164">Related topics</span></span>

[<span data-ttu-id="f8036-165">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f8036-165">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




