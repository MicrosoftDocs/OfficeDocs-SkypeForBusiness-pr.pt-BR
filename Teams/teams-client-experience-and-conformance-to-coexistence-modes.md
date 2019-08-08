---
title: Experiência e conformidade do cliente do Teams a modos de coexistência
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Experiência do cliente do Teams e comformabilidade para modos de coexistência
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 85f74b63f465bd0004e8b9a2ef93c79b00196495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243900"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="9fa23-103">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="9fa23-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="9fa23-104">Esta página descreve alterações importantes e recentemente lançadas no comportamento do cliente do teams quando os usuários estão em qualquer um dos modos do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span><span class="sxs-lookup"><span data-stu-id="9fa23-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="9fa23-105">A finalidade dos modos de coexistência é fornecer uma experiência simples e previsível para os usuários finais como as organizações migrando do Skype for Business para o Teams.</span><span class="sxs-lookup"><span data-stu-id="9fa23-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="9fa23-106">Para uma organização se movendo para o Microsoft Teams, o modo de TeamsOnly é o destino final de cada usuário, mas nem todos os usuários precisam ser atribuídos TeamsOnly (ou qualquer outro modo) ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9fa23-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="9fa23-107">Antes de os usuários alcançarem o modo TeamsOnly, as organizações podem usar qualquer um dos modos do Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) para garantir a comunicação previsível entre os usuários que são TeamsOnly e aqueles que ainda não estão.</span><span class="sxs-lookup"><span data-stu-id="9fa23-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="9fa23-108">Quando um usuário está em qualquer um dos modos do Skype for Business, todos os chats e chamadas recebidos são roteados para o cliente Skype for Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="9fa23-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="9fa23-109">Para evitar a confusão do usuário final e garantir o roteamento adequado, a chamada e a funcionalidade de chat no cliente do teams são desabilitadas quando um usuário está em qualquer um dos modos do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9fa23-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="9fa23-110">Da mesma forma, o agendamento da reunião no Teams é explicitamente desabilitado quando os usuários estão nos modos SfBOnly ou SfBWithTeamsCollab, e explicitamente habilitados quando um usuário está no modo de SfBWithTeamsCollabAndMeetings.</span><span class="sxs-lookup"><span data-stu-id="9fa23-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="9fa23-111">Como a funcionalidade disponível no cliente do teams muda com base no modo</span><span class="sxs-lookup"><span data-stu-id="9fa23-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="9fa23-112">A funcionalidade disponível no Teams depende do modo de coexistência do usuário, conforme definido pela TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="9fa23-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="9fa23-113">A tabela a seguir resume o comportamento:</span><span class="sxs-lookup"><span data-stu-id="9fa23-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="9fa23-114">Modo efetivo do usuário</span><span class="sxs-lookup"><span data-stu-id="9fa23-114">User's effective mode</span></span>|<span data-ttu-id="9fa23-115">Experiência no cliente da equipe</span><span class="sxs-lookup"><span data-stu-id="9fa23-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="9fa23-116">Qualquer modo do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9fa23-116">Any Skype for Business mode</span></span>|<span data-ttu-id="9fa23-117">A chamada e o chat estão desativados.</span><span class="sxs-lookup"><span data-stu-id="9fa23-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="9fa23-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="9fa23-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="9fa23-119">O agendamento da reunião está disponível</span><span class="sxs-lookup"><span data-stu-id="9fa23-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="9fa23-120">SfBWithTeamsCollab ou SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9fa23-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="9fa23-121">O agendamento da reunião não está disponível</span><span class="sxs-lookup"><span data-stu-id="9fa23-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="9fa23-122">As capturas de tela a seguir ilustram a diferença entre o modo de TeamsOnly ou de ilhas e todos os outros modos.</span><span class="sxs-lookup"><span data-stu-id="9fa23-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="9fa23-123">Observe que os ícones de chat e de chamada estão disponíveis com TeamsOnly ou o modo de ilhas (captura de tela à esquerda), mas não com os outros modos (captura de tela à direita):</span><span class="sxs-lookup"><span data-stu-id="9fa23-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Uma comparação lado a lado dos modos de equipe](media/teams-mode-comparison.png)


 
<span data-ttu-id="9fa23-125">**Observação:**
<sup>1</sup> por enquanto, SfBwithTeamsCollab e SfBOnly comportam-se da mesma maneira, mas a intenção é para o modo de SfBOnly também desativar a funcionalidade de canais e arquivos no Microsoft Teams; Contudo, no momento, não há nenhuma configuração que permita que essa funcionalidade em equipes seja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="9fa23-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="9fa23-126">Impacto do modo em outras configurações de política</span><span class="sxs-lookup"><span data-stu-id="9fa23-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="9fa23-127">Conforme descrito acima, o modo de coexistência de um usuário afeta a funcionalidade disponível no cliente do teams do usuário.</span><span class="sxs-lookup"><span data-stu-id="9fa23-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="9fa23-128">Isso significa que o valor de Mode pode prevalecer sobre o valor de outras configurações de política, dependendo do modo.</span><span class="sxs-lookup"><span data-stu-id="9fa23-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="9fa23-129">Especificamente, o modo de coexistência impacta se as seguintes configurações de política são atendidas:</span><span class="sxs-lookup"><span data-stu-id="9fa23-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="9fa23-130">**Modalidade (app)**</span><span class="sxs-lookup"><span data-stu-id="9fa23-130">**Modality (App)**</span></span>|<span data-ttu-id="9fa23-131">**Política. setting**</span><span class="sxs-lookup"><span data-stu-id="9fa23-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="9fa23-132">Chat</span><span class="sxs-lookup"><span data-stu-id="9fa23-132">Chat</span></span>|<span data-ttu-id="9fa23-133">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="9fa23-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="9fa23-134">Chamadas</span><span class="sxs-lookup"><span data-stu-id="9fa23-134">Calling</span></span>|<span data-ttu-id="9fa23-135">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="9fa23-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="9fa23-136">Agendamento de reunião</span><span class="sxs-lookup"><span data-stu-id="9fa23-136">Meeting scheduling</span></span>|<span data-ttu-id="9fa23-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9fa23-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="9fa23-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9fa23-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="9fa23-139">Os administradores *não* precisam definir explicitamente essas configurações de política ao usar o modo de coexistência, mas é importante entender que essas configurações se comportam de forma eficaz para um determinado modo.</span><span class="sxs-lookup"><span data-stu-id="9fa23-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="9fa23-140">Modo</span><span class="sxs-lookup"><span data-stu-id="9fa23-140">Mode</span></span>|<span data-ttu-id="9fa23-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="9fa23-141">AllowUserChat</span></span>|<span data-ttu-id="9fa23-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="9fa23-142">AllowPrivateCalling</span></span>|<span data-ttu-id="9fa23-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9fa23-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="9fa23-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9fa23-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="9fa23-145">TeamsOnly ou ilhas</span><span class="sxs-lookup"><span data-stu-id="9fa23-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="9fa23-146">Habilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-146">Enabled</span></span>|<span data-ttu-id="9fa23-147">Habilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-147">Enabled</span></span>|<span data-ttu-id="9fa23-148">Habilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-148">Enabled</span></span>|<span data-ttu-id="9fa23-149">Habilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-149">Enabled</span></span>|
|<span data-ttu-id="9fa23-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="9fa23-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="9fa23-151">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-151">Disabled</span></span>|<span data-ttu-id="9fa23-152">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-152">Disabled</span></span>|<span data-ttu-id="9fa23-153">Habilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-153">Enabled</span></span>|<span data-ttu-id="9fa23-154">Habilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-154">Enabled</span></span>|
|<span data-ttu-id="9fa23-155">SfBWithTeamsCollab ou SfBOnly</span><span class="sxs-lookup"><span data-stu-id="9fa23-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="9fa23-156">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-156">Disabled</span></span>|<span data-ttu-id="9fa23-157">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-157">Disabled</span></span>|<span data-ttu-id="9fa23-158">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-158">Disabled</span></span>|<span data-ttu-id="9fa23-159">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="9fa23-159">Disabled</span></span>|
||||||

<span data-ttu-id="9fa23-160">Ao usar o PowerShell, `Grant-CsTeamsUpgradePolicy` o cmdlet verifica a configuração das configurações correspondentes em TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy para determinar se essas configurações seriam substituídas por TeamsUpgradePolicy e, nesse caso, uma a mensagem informativa é fornecida no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fa23-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="9fa23-161">Conforme observado acima, não é mais necessário definir essas outras configurações de política.</span><span class="sxs-lookup"><span data-stu-id="9fa23-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="9fa23-162">Veja a seguir um exemplo de como é a aparência do aviso do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9fa23-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="9fa23-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9fa23-163">Related topics</span></span>

[<span data-ttu-id="9fa23-164">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9fa23-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




