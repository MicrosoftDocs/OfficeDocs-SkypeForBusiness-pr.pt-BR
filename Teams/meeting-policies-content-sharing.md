---
title: Gerenciar políticas de reunião para compartilhamento de conteúdo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Aprenda a gerenciar configurações de política de reunião no Teams para compartilhamento de conteúdo.
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598697"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="62ef0-103">Configurações de política de reunião - Compartilhamento de conteúdo</span><span class="sxs-lookup"><span data-stu-id="62ef0-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="62ef0-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="62ef0-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="62ef0-105">Este artigo descreve as seguintes configurações de política de reunião relacionadas ao compartilhamento de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="62ef0-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="62ef0-106">Modo de compartilhamento de tela</span><span class="sxs-lookup"><span data-stu-id="62ef0-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="62ef0-107">Permitir que um participante conceda ou solicite o controle</span><span class="sxs-lookup"><span data-stu-id="62ef0-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="62ef0-108">Permitir que um participante externo conceda ou solicite o controle</span><span class="sxs-lookup"><span data-stu-id="62ef0-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="62ef0-109">Permitir o compartilhamento do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="62ef0-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="62ef0-110">Permitir quadro de comunicações</span><span class="sxs-lookup"><span data-stu-id="62ef0-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="62ef0-111">Permitir anotações compartilhadas</span><span class="sxs-lookup"><span data-stu-id="62ef0-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="62ef0-112">Modo de compartilhamento de tela</span><span class="sxs-lookup"><span data-stu-id="62ef0-112">Screen sharing mode</span></span>

<span data-ttu-id="62ef0-113">Essa configuração é uma combinação de políticas por organizador e por usuário.</span><span class="sxs-lookup"><span data-stu-id="62ef0-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="62ef0-114">Essa configuração controla se o compartilhamento de área de trabalho e janela é permitido na reunião do usuário.</span><span class="sxs-lookup"><span data-stu-id="62ef0-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="62ef0-115">Os participantes da reunião que não possuem políticas atribuídas (por exemplo, participantes anônimos e federados, convidado, B2B) herdam a política do organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="62ef0-116">Valor de configuração</span><span class="sxs-lookup"><span data-stu-id="62ef0-116">Setting value</span></span> |<span data-ttu-id="62ef0-117">Comportamento</span><span class="sxs-lookup"><span data-stu-id="62ef0-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="62ef0-118">**Tela inteira**</span><span class="sxs-lookup"><span data-stu-id="62ef0-118">**Entire screen**</span></span>    | <span data-ttu-id="62ef0-119">Compartilhamento completo de área de trabalho e compartilhamento de aplicativos são permitidos na reunião</span><span class="sxs-lookup"><span data-stu-id="62ef0-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="62ef0-120">**Único aplicativo**</span><span class="sxs-lookup"><span data-stu-id="62ef0-120">**Single application**</span></span>   | <span data-ttu-id="62ef0-121">O compartilhamento de aplicativos é permitido na reunião</span><span class="sxs-lookup"><span data-stu-id="62ef0-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="62ef0-122">**Desabilitado**</span><span class="sxs-lookup"><span data-stu-id="62ef0-122">**Disabled**</span></span>     |<span data-ttu-id="62ef0-123">Compartilhamento de tela e compartilhamento de aplicativos desativados na reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="62ef0-124">Observe o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="62ef0-124">Let's look at the following example.</span></span>

|<span data-ttu-id="62ef0-125">Usuário</span><span class="sxs-lookup"><span data-stu-id="62ef0-125">User</span></span> |<span data-ttu-id="62ef0-126">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="62ef0-126">Meeting policy</span></span> |<span data-ttu-id="62ef0-127">Modo de compartilhamento de tela</span><span class="sxs-lookup"><span data-stu-id="62ef0-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="62ef0-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="62ef0-128">Daniela</span></span>  | <span data-ttu-id="62ef0-129">Global</span><span class="sxs-lookup"><span data-stu-id="62ef0-129">Global</span></span>   | <span data-ttu-id="62ef0-130">Tela inteira</span><span class="sxs-lookup"><span data-stu-id="62ef0-130">Entire screen</span></span> |
|<span data-ttu-id="62ef0-131">Amanda</span><span class="sxs-lookup"><span data-stu-id="62ef0-131">Amanda</span></span>   | <span data-ttu-id="62ef0-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="62ef0-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="62ef0-133">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-133">Disabled</span></span> |

<span data-ttu-id="62ef0-134">As reuniões hospedadas pela Daniela permitem que os participantes da reunião compartilhem toda a tela ou um aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="62ef0-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="62ef0-135">Se a Amanda ingressar na reunião da Daniela, a Amanda não poderá compartilhar sua tela ou um determinado aplicativo, pois a configuração de política está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="62ef0-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="62ef0-136">Nas reuniões hospedadas por Amanda, ninguém tem permissão para compartilhar a tela ou um único aplicativo, independentemente da política de modo de compartilhamento de tela atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="62ef0-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="62ef0-137">Consequentemente, Daniela não pode compartilhar sua tela ou um único aplicativo nas reuniões de Amanda.</span><span class="sxs-lookup"><span data-stu-id="62ef0-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="62ef0-138">No momento, os usuários não podem reproduzir vídeo ou compartilhar a tela em uma reunião do Teams se estiverem usando o Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="62ef0-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="62ef0-139">Permitir que um participante conceda ou solicite o controle</span><span class="sxs-lookup"><span data-stu-id="62ef0-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="62ef0-140">Essa configuração é uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="62ef0-140">This setting is a per-user policy.</span></span> <span data-ttu-id="62ef0-141">Essa configuração controla se o usuário pode conceder o controle da área de trabalho ou da janela para outros participantes da reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="62ef0-142">Para dar controle, passe o mouse sobre a parte superior da tela.</span><span class="sxs-lookup"><span data-stu-id="62ef0-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="62ef0-143">Se essa configuração estiver ativada para o usuário, a opção **Atribuir controle** será exibida na barra superior de uma sessão de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="62ef0-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![Captura de tela mostrando a opção Conceder controle](media/meeting-policies-give-control.png)

<span data-ttu-id="62ef0-145">Se a configuração estiver desligada para o usuário, a **opção Dar Controle** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="62ef0-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![Captura de tela mostrando que a opção Conceder controle não está disponível](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="62ef0-147">Observe o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="62ef0-147">Let's look at the following example.</span></span>

|<span data-ttu-id="62ef0-148">Usuário</span><span class="sxs-lookup"><span data-stu-id="62ef0-148">User</span></span> |<span data-ttu-id="62ef0-149">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="62ef0-149">Meeting policy</span></span>  |<span data-ttu-id="62ef0-150">Permitir que o participante conceda ou solicite o controle</span><span class="sxs-lookup"><span data-stu-id="62ef0-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="62ef0-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="62ef0-151">Daniela</span></span>   | <span data-ttu-id="62ef0-152">Global</span><span class="sxs-lookup"><span data-stu-id="62ef0-152">Global</span></span>   | <span data-ttu-id="62ef0-153">Habilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-153">On</span></span>       |
|<span data-ttu-id="62ef0-154">Babek</span><span class="sxs-lookup"><span data-stu-id="62ef0-154">Babek</span></span>    | <span data-ttu-id="62ef0-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="62ef0-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="62ef0-156">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-156">Off</span></span>   |

<span data-ttu-id="62ef0-157">Daniela pode dar controle da área de trabalho ou janela compartilhada a outros participantes em uma reunião organizada por Babek.</span><span class="sxs-lookup"><span data-stu-id="62ef0-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="62ef0-158">No entanto, o Babek não pode dar controle a outros participantes.</span><span class="sxs-lookup"><span data-stu-id="62ef0-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="62ef0-159">Para usar o PowerShell para controlar quem pode conceder controle ou aceitar solicitações de controle, use o cmdlet AllowParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="62ef0-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="62ef0-160">Para conceder e assumir o controle do conteúdo compartilhado durante o compartilhamento, as duas partes devem usar o cliente da área de trabalho do Teams.</span><span class="sxs-lookup"><span data-stu-id="62ef0-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="62ef0-161">Não há suporte para controle quando ambas as partes estiverem executando o Teams em um navegador.</span><span class="sxs-lookup"><span data-stu-id="62ef0-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="62ef0-162">Isso ocorre devido a uma limitação técnica de que estamos planejando corrigir.</span><span class="sxs-lookup"><span data-stu-id="62ef0-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="62ef0-163">Permitir que um participante externo conceda ou solicite o controle</span><span class="sxs-lookup"><span data-stu-id="62ef0-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="62ef0-164">Essa configuração é uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="62ef0-164">This setting is a per-user policy.</span></span> <span data-ttu-id="62ef0-165">Se uma organização definiu essa política para um usuário não controla o que os participantes externos podem fazer, independentemente do que o organizador da reunião definiu.</span><span class="sxs-lookup"><span data-stu-id="62ef0-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="62ef0-166">Esse parâmetro controla se os participantes externos podem receber ou solicitar controle da tela de compartilhamento do participante, dependendo do que o participante do compartilhamento definiu dentro das políticas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="62ef0-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="62ef0-167">Os participantes externos nas reuniões das Teams podem ser categorizados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="62ef0-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="62ef0-168">Usuário anônimo</span><span class="sxs-lookup"><span data-stu-id="62ef0-168">Anonymous user</span></span>
- <span data-ttu-id="62ef0-169">Usuários convidados</span><span class="sxs-lookup"><span data-stu-id="62ef0-169">Guest users</span></span>  
- <span data-ttu-id="62ef0-170">Usuário B2B</span><span class="sxs-lookup"><span data-stu-id="62ef0-170">B2B user</span></span>
- <span data-ttu-id="62ef0-171">Usuário federado</span><span class="sxs-lookup"><span data-stu-id="62ef0-171">Federated user</span></span>  

<span data-ttu-id="62ef0-172">Se os usuários federados podem conceder controle aos usuários externos enquanto o compartilhamento é controlado pela configuração **Permitir que um participante externo conceda ou solicite o controle** na organização.</span><span class="sxs-lookup"><span data-stu-id="62ef0-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="62ef0-173">Para usar o PowerShell para controlar se os participantes externos podem conceder controle ou aceitar solicitações de controle, use o cmdlet AllowExternalParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="62ef0-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="62ef0-174">Permitir compartilhamento do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="62ef0-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="62ef0-175">Essa é uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="62ef0-175">This is a per-user policy.</span></span> <span data-ttu-id="62ef0-176">Essa configuração controla se o usuário pode compartilhar os decks de slides do PowerPoint em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="62ef0-177">Os usuários externos, incluindo usuários anônimos, convidados e federados, herdam a política do organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="62ef0-178">Observe o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="62ef0-178">Let's look at the following example.</span></span>

|<span data-ttu-id="62ef0-179">Usuário</span><span class="sxs-lookup"><span data-stu-id="62ef0-179">User</span></span> |<span data-ttu-id="62ef0-180">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="62ef0-180">Meeting policy</span></span>  |<span data-ttu-id="62ef0-181">Permitir compartilhamento do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="62ef0-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="62ef0-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="62ef0-182">Daniela</span></span>   | <span data-ttu-id="62ef0-183">Global</span><span class="sxs-lookup"><span data-stu-id="62ef0-183">Global</span></span>   | <span data-ttu-id="62ef0-184">Habilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-184">On</span></span>       |
|<span data-ttu-id="62ef0-185">Amanda</span><span class="sxs-lookup"><span data-stu-id="62ef0-185">Amanda</span></span>   | <span data-ttu-id="62ef0-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="62ef0-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="62ef0-187">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-187">Off</span></span>   |

<span data-ttu-id="62ef0-188">Amanda não pode compartilhar os conjunto de slides do PowerPoint nas reuniões, mesmo que ela seja a organizadora da reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="62ef0-189">Daniela pode compartilhar os conjunto de slides do PowerPoint mesmo se a reunião for organizada pela Amanda.</span><span class="sxs-lookup"><span data-stu-id="62ef0-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="62ef0-190">Amanda pode exibir os conjunto de slides do PowerPoint compartilhados por outras pessoas na reunião, apesar de não poder compartilhar os conjunto de slides do PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="62ef0-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="62ef0-191">Permitir o quadro de comunicações</span><span class="sxs-lookup"><span data-stu-id="62ef0-191">Allow whiteboard</span></span>

<span data-ttu-id="62ef0-192">Essa configuração é uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="62ef0-192">This setting is a per-user policy.</span></span> <span data-ttu-id="62ef0-193">Essa configuração controla se um usuário pode compartilhar o quadro de comunicações em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="62ef0-194">Os usuários externos, incluindo usuários anônimos, B2B e federados, herdam a política do organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="62ef0-195">Observe o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="62ef0-195">Let's look at the following example.</span></span>

|<span data-ttu-id="62ef0-196">Usuário</span><span class="sxs-lookup"><span data-stu-id="62ef0-196">User</span></span> |<span data-ttu-id="62ef0-197">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="62ef0-197">Meeting policy</span></span>  |<span data-ttu-id="62ef0-198">Permitir o quadro de comunicações</span><span class="sxs-lookup"><span data-stu-id="62ef0-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="62ef0-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="62ef0-199">Daniela</span></span>   | <span data-ttu-id="62ef0-200">Global</span><span class="sxs-lookup"><span data-stu-id="62ef0-200">Global</span></span>   | <span data-ttu-id="62ef0-201">Habilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-201">On</span></span>       |
|<span data-ttu-id="62ef0-202">Amanda</span><span class="sxs-lookup"><span data-stu-id="62ef0-202">Amanda</span></span>   | <span data-ttu-id="62ef0-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="62ef0-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="62ef0-204">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-204">Off</span></span>   |

<span data-ttu-id="62ef0-205">Amanda não pode compartilhar o quadro de comunicações em uma reunião, mesmo que ela seja a organizadora da reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="62ef0-206">Daniela pode compartilhar o quadro de comunicações mesmo se uma reunião for organizada por Amanda.</span><span class="sxs-lookup"><span data-stu-id="62ef0-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="62ef0-207">Permitir notas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="62ef0-207">Allow shared notes</span></span>

<span data-ttu-id="62ef0-208">Essa configuração é uma política por usuário.</span><span class="sxs-lookup"><span data-stu-id="62ef0-208">This setting is a per-user policy.</span></span> <span data-ttu-id="62ef0-209">Essa configuração controla se um usuário pode criar e compartilhar anotações em uma reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="62ef0-210">Os usuários externos, incluindo usuários anônimos, B2B e federados, herdam a política do organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="62ef0-211">No momento, só há suporte para a guia **Anotações de reunião** com reuniões com menos de 20 participantes.</span><span class="sxs-lookup"><span data-stu-id="62ef0-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="62ef0-212">Observe o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="62ef0-212">Let's look at the following example.</span></span>

|<span data-ttu-id="62ef0-213">Usuário</span><span class="sxs-lookup"><span data-stu-id="62ef0-213">User</span></span> |<span data-ttu-id="62ef0-214">Políticas de reunião</span><span class="sxs-lookup"><span data-stu-id="62ef0-214">Meeting policy</span></span>  |<span data-ttu-id="62ef0-215">Permitir notas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="62ef0-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="62ef0-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="62ef0-216">Daniela</span></span>   | <span data-ttu-id="62ef0-217">Global</span><span class="sxs-lookup"><span data-stu-id="62ef0-217">Global</span></span>   | <span data-ttu-id="62ef0-218">Habilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-218">On</span></span>       |
|<span data-ttu-id="62ef0-219">Amanda</span><span class="sxs-lookup"><span data-stu-id="62ef0-219">Amanda</span></span>   | <span data-ttu-id="62ef0-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="62ef0-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="62ef0-221">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="62ef0-221">Off</span></span> |

<span data-ttu-id="62ef0-222">Daniela pode fazer anotações nas reuniões da Amanda e a Amanda não pode fazer anotações em qualquer reunião.</span><span class="sxs-lookup"><span data-stu-id="62ef0-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="62ef0-223">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="62ef0-223">Related topics</span></span>

- [<span data-ttu-id="62ef0-224">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="62ef0-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="62ef0-225">Atribuir políticas aos usuários no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="62ef0-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="62ef0-226">Remover a política de reunião do Teams RestrictedAnonymousAccess dos usuários</span><span class="sxs-lookup"><span data-stu-id="62ef0-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
