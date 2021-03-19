---
title: Experiência de reunião somente exibição
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre a experiência de reunião somente para exibição do Teams para administradores, apresentadores e participantes
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875051"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="4b948-103">Experiência de reunião somente para exibição do Teams</span><span class="sxs-lookup"><span data-stu-id="4b948-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="4b948-104">As transmissões somente para exibição estão disponíveis no Microsoft 365 E3/E5 e no Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="4b948-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="4b948-105">Esse recurso será habilitado em 1º de março de 2021 como off padrão.</span><span class="sxs-lookup"><span data-stu-id="4b948-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="4b948-106">O recurso no Microsoft 365 Government Community Cloud (GCC) começará a ser apresentado no final de março de 2021.</span><span class="sxs-lookup"><span data-stu-id="4b948-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="4b948-107">O Government Community Cloud High (GCCH) e o Departamento de Defesa (DoD) serão divulgados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="4b948-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="4b948-108">Você deve alterar a política padrão após essa data se quiser que o recurso seja on padrão.</span><span class="sxs-lookup"><span data-stu-id="4b948-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="4b948-109">Use o PowerShell para habilitar a política `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` .</span><span class="sxs-lookup"><span data-stu-id="4b948-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="4b948-110">Se sua reunião ou webinar atingir a capacidade, o Teams será dimensionado perfeitamente para acomodar uma experiência de transmissão somente para exibição de 10.000 pessoas.</span><span class="sxs-lookup"><span data-stu-id="4b948-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="4b948-111">Além disso, durante esse período de maior trabalho remoto, aproveite as transmissões ainda maiores de 20.000 pessoas até o final deste ano.</span><span class="sxs-lookup"><span data-stu-id="4b948-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="4b948-112">O Microsoft Teams permite que até 10.000 participantes participem de uma reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="4b948-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="4b948-113">Depois que a capacidade da reunião principal tiver sido atingida, participantes adicionais ingressarão com uma experiência somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="4b948-114">Os participantes que ingressarem na reunião primeiro, até a capacidade da reunião, terão a experiência de reunião completa do Teams.</span><span class="sxs-lookup"><span data-stu-id="4b948-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="4b948-115">Eles podem compartilhar áudio e vídeo, ver vídeos compartilhados e participar do chat de reunião.</span><span class="sxs-lookup"><span data-stu-id="4b948-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="4b948-116">Os participantes que ingressarem depois que a capacidade de reunião principal tiver sido atingida terão uma experiência somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="4b948-117">Temos suporte completo para android e iOS para um participante participar.</span><span class="sxs-lookup"><span data-stu-id="4b948-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="4b948-118">O limite atual para o número de pessoas que podem conversar e ligar para uma reunião é 300 na WW e 250 no GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="4b948-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="4b948-119">A experiência somente para exibição é desabilitada por padrão para qualquer organizador que tenha SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="4b948-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="4b948-120">Nenhuma configuração ou configuração posterior é necessária.</span><span class="sxs-lookup"><span data-stu-id="4b948-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="4b948-121">Desabilitar a experiência somente para exibição do Teams</span><span class="sxs-lookup"><span data-stu-id="4b948-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="4b948-122">Os administradores podem desabilitar a experiência somente para exibição usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b948-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="4b948-123">No futuro, também será possível que os administradores desabilitem a experiência somente para exibição no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="4b948-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="4b948-124">Impacto para os usuários</span><span class="sxs-lookup"><span data-stu-id="4b948-124">Impact to users</span></span>

<span data-ttu-id="4b948-125">A experiência de um usuário variará dependendo de vários fatores.</span><span class="sxs-lookup"><span data-stu-id="4b948-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="4b948-126">Quando a capacidade da reunião principal for atingida, um participante não poderá participar da reunião se qualquer um dos seguintes eventos for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="4b948-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="4b948-127">Um administrador desabilitou a experiência somente de exibição do Teams.</span><span class="sxs-lookup"><span data-stu-id="4b948-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="4b948-128">O participante não tem permissão para ignorar o lobby.</span><span class="sxs-lookup"><span data-stu-id="4b948-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="4b948-129">Quando a capacidade da reunião principal for atingida, o organizador da reunião e os apresentadores verão uma faixa informando que a capacidade de reunião foi atingida e que os novos participantes ingressarão em um participante somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![a mensagem de cliente e faixa do Teams para organizadores e apresentadores](media/chat-and-banner-message.png)

<span data-ttu-id="4b948-131">Quando a capacidade da reunião principal for atingida, os participantes da reunião serão informados na tela de pré-entrada de que eles estão in joining no modo somente exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![a tela de pré-participação do Teams e a mensagem para os participantes dizendo que eles ingressarão no modo somente exibição](media/view-only-pre-join-screen.png)

<span data-ttu-id="4b948-133">Se houver espaço, um usuário sempre ingressará na reunião principal.</span><span class="sxs-lookup"><span data-stu-id="4b948-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="4b948-134">Se a reunião principal atingir a capacidade e um ou mais participantes saírem da reunião principal, a reunião principal terá capacidade disponível.</span><span class="sxs-lookup"><span data-stu-id="4b948-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="4b948-135">Os participantes que ingressarem (ou ingressarem) na reunião participarão da reunião principal até que ela atinja a capacidade novamente.</span><span class="sxs-lookup"><span data-stu-id="4b948-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="4b948-136">Os participantes que estão na experiência somente exibição não serão promovidos automaticamente para a reunião principal e não poderão ser promovidos manualmente para a reunião principal.</span><span class="sxs-lookup"><span data-stu-id="4b948-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="4b948-137">Se as funções de apresentador/participante não foram definidas, os espaços na reunião principal serão preenchidos por primeira vez.</span><span class="sxs-lookup"><span data-stu-id="4b948-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="4b948-138">Depois que a capacidade de reunião tiver sido atingida, todos os outros usuários ingressarão com uma experiência somente de exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="4b948-139">Impacto para apresentadores de reunião</span><span class="sxs-lookup"><span data-stu-id="4b948-139">Impact to meeting presenters</span></span>

<span data-ttu-id="4b948-140">As limitações para apresentadores de reunião incluem:</span><span class="sxs-lookup"><span data-stu-id="4b948-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="4b948-141">Você não terá informações sobre o participante somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="4b948-142">Não há suporte à descoberta de E para participantes somente de exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="4b948-143">Os usuários não podem ver os participantes somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="4b948-144">Não é possível remover um participante somente para exibição da reunião.</span><span class="sxs-lookup"><span data-stu-id="4b948-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="4b948-145">A contagem de participantes refletirá apenas as pessoas na reunião e não as pessoas na sala somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="4b948-146">Portanto, os apresentadores não podem obter uma contagem exata de quem está na experiência somente de exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="4b948-147">Experiência para participantes somente exibição</span><span class="sxs-lookup"><span data-stu-id="4b948-147">Experience for view-only attendees</span></span>

<span data-ttu-id="4b948-148">A experiência somente de exibição do Teams permite que os participantes:</span><span class="sxs-lookup"><span data-stu-id="4b948-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="4b948-149">Ouça os participantes da reunião principal do Teams.</span><span class="sxs-lookup"><span data-stu-id="4b948-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="4b948-150">Consulte o feed de vídeo do alto-falante ativo (se o alto-falante ativo estiver compartilhando vídeo).</span><span class="sxs-lookup"><span data-stu-id="4b948-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="4b948-151">Consulte o conteúdo que está sendo compartilhado usando a funcionalidade da área de trabalho de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="4b948-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="4b948-152">O participante somente para exibição não poderá experimentar as seguintes opções em reuniões:</span><span class="sxs-lookup"><span data-stu-id="4b948-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="4b948-153">Participe da reunião se o participante não tiver permissão para ignorar o lobby com base em políticas ou opções de lobby definidas.</span><span class="sxs-lookup"><span data-stu-id="4b948-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="4b948-154">Participe da sala somente exibição usando Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="4b948-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="4b948-155">Participe da sala somente exibição usando o sistema da Sala do Microsoft Teams ou usando serviços CVI (Cloud Video Interop).</span><span class="sxs-lookup"><span data-stu-id="4b948-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="4b948-156">Compartilhe seu áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="4b948-156">Share their audio or video.</span></span>
- <span data-ttu-id="4b948-157">Consulte ou participe do chat da reunião.</span><span class="sxs-lookup"><span data-stu-id="4b948-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="4b948-158">Consulte o feed de vídeo dos participantes da reunião, a menos que o participante seja o orador ativo.</span><span class="sxs-lookup"><span data-stu-id="4b948-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="4b948-159">Consulte Arquivos do PowerPoint compartilhados usando a funcionalidade nativa do PowerPoint ou compartilhamentos de aplicativos individuais (diferente do compartilhamento de área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="4b948-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="4b948-160">Limitações de recursos somente exibição</span><span class="sxs-lookup"><span data-stu-id="4b948-160">View-only feature limitations</span></span>

- <span data-ttu-id="4b948-161">Os participantes somente exibição sempre verão legendas ao vivo, independentemente da configuração de legendas ao vivo para essa reunião.</span><span class="sxs-lookup"><span data-stu-id="4b948-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="4b948-162">Somente legendas em inglês são suportadas no momento.</span><span class="sxs-lookup"><span data-stu-id="4b948-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="4b948-163">Os participantes somente para exibição terão suporte da tecnologia de streaming.</span><span class="sxs-lookup"><span data-stu-id="4b948-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="4b948-164">Os participantes somente exibição não serão incluídos no relatório de presença.</span><span class="sxs-lookup"><span data-stu-id="4b948-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="4b948-165">Os participantes somente para exibição terão uma única experiência em vídeo.</span><span class="sxs-lookup"><span data-stu-id="4b948-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="4b948-166">Eles podem ver o alto-falante ativo ou o conteúdo sendo compartilhado, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="4b948-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="4b948-167">No momento, não há suporte a  Layouts de modo **Galeria,** **Galeria** Grande ou Modo Juntos para participantes somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="4b948-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="4b948-168">Os participantes somente exibição não terão a mesma latência que um participante regular.</span><span class="sxs-lookup"><span data-stu-id="4b948-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="4b948-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b948-169"><sup>1</sup></span></span>

  <span data-ttu-id="4b948-170"><sup>1</sup> Os participantes somente exibição estarão com um atraso de vídeo e áudio de 30 segundos na reunião.</span><span class="sxs-lookup"><span data-stu-id="4b948-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
