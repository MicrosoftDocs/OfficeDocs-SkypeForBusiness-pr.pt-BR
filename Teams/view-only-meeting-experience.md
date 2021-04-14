---
title: Experiência de reunião somente para visualização
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba mais sobre a experiência de reunião somente visualização do Teams para administradores, apresentadores e participantes
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09fe424dc576b6b167eec49e7cd8edf2f61d6cce
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697796"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="e3226-103">Experiência de reunião somente para visualização de Teams</span><span class="sxs-lookup"><span data-stu-id="e3226-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="e3226-104">As transmissões somente para visualização estão disponíveis no Microsoft 365 E3/E5 e Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="e3226-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="e3226-105">Este recurso será habilitado em 1º de março de 2021 como DESLIGADO padrão.</span><span class="sxs-lookup"><span data-stu-id="e3226-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="e3226-106">O recurso no Microsoft 365 Government Community Cloud (GCC) começará a ser implementado no final de março de 2021.</span><span class="sxs-lookup"><span data-stu-id="e3226-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="e3226-107">Government Community Cloud High (GCCH) e Department of Defense (DoD) serão implementados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e3226-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="e3226-108">Você deve alterar a política padrão após essa data se quiser que o recurso seja ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="e3226-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="e3226-109">Use o Windows PowerShell para habilitar a política `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="e3226-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="e3226-110">Se a sua reunião ou webinar atingir a capacidade máxima, o Teams será perfeitamente escalado para acomodar uma experiência de transmissão somente visualização para 10.000 pessoas.</span><span class="sxs-lookup"><span data-stu-id="e3226-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="e3226-111">Além disso, durante este período de maior trabalho remoto, aproveite as transmissões ainda maiores para 20.000 pessoas até o final deste ano.</span><span class="sxs-lookup"><span data-stu-id="e3226-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="e3226-112">O Microsoft Teams permite que até 10.000 participantes participem de uma reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="e3226-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="e3226-113">Depois que a capacidade da reunião principal for atingida (que é quando 300 usuários ingressam em uma reunião), os participantes adicionais ingressarão com uma experiência somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="e3226-113">After the capacity of the main meeting has been reached (which is when 300 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="e3226-114">Os participantes que ingressarem na reunião primeiro, até a capacidade da reunião principal, terão a experiência de reunião completa do Teams.</span><span class="sxs-lookup"><span data-stu-id="e3226-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="e3226-115">Eles podem compartilhar áudio e vídeo, ver vídeos compartilhados e participar do bate-papo da reunião.</span><span class="sxs-lookup"><span data-stu-id="e3226-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="e3226-116">Os participantes que ingressarem depois que a capacidade da reunião principal for atingida terão uma experiência somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="e3226-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="e3226-117">Os participantes poderão ingressar na experiência somente para exibição por meio da área de trabalho, da Web e do Teams mobile (Android e iOS).</span><span class="sxs-lookup"><span data-stu-id="e3226-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="e3226-118">A capacidade de limite atual da "reunião principal", ou em outras palavras, o número de usuários totalmente interativos é 300 na WW e 250 em GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="e3226-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="e3226-119">Controles de experiência somente para exibição do Teams</span><span class="sxs-lookup"><span data-stu-id="e3226-119">Teams view-only experience controls</span></span>

<span data-ttu-id="e3226-120">Você habilita a experiência somente para exibição usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3226-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="e3226-121">Para desabilitar a experiência somente para exibição, você também pode usar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3226-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="e3226-122">No futuro, você poderá habilitar ou desabilitar a experiência somente para exibição no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="e3226-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="e3226-123">Impacto nos usuários</span><span class="sxs-lookup"><span data-stu-id="e3226-123">Impact to users</span></span>

<span data-ttu-id="e3226-124">A experiência de um usuário varia de acordo com vários fatores.</span><span class="sxs-lookup"><span data-stu-id="e3226-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="e3226-125">Quando a capacidade da reunião principal for atingida, um participante não poderá participar da reunião se alguma das seguintes condições for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="e3226-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="e3226-126">Um administrador desabilitou a experiência somente de exibição do Teams para o organizador ou para todo o locatário.</span><span class="sxs-lookup"><span data-stu-id="e3226-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="e3226-127">O participante somente para exibição não pode ignorar o lobby.</span><span class="sxs-lookup"><span data-stu-id="e3226-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="e3226-128">Por exemplo, se um organizador de uma  reunião optar por fazer com que apenas pessoas da minha organização ignorem o lobby e um participante que está fora da organização tentar ingressar como um participante somente para exibição, eles não poderão participar.</span><span class="sxs-lookup"><span data-stu-id="e3226-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="e3226-129">Quando a capacidade da reunião principal for atingida, o organizador da reunião e os apresentadores verão uma faixa informando que os novos participantes ingressarão como participantes somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="e3226-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![o cliente do Teams e a mensagem do banner para organizadores e apresentadores](media/chat-and-banner-message.png)

<span data-ttu-id="e3226-131">Quando a capacidade da reunião principal for atingida, os participantes da reunião serão informados na tela de pré-entrada que eles estão entrando no modo somente visualização.</span><span class="sxs-lookup"><span data-stu-id="e3226-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![a tela de pré-adesão das equipes e a mensagem para os participantes informando que eles entrarão no modo somente visualização](media/view-only-pre-join-screen.png)

<span data-ttu-id="e3226-133">Se houver espaço, um usuário sempre participará da reunião principal.</span><span class="sxs-lookup"><span data-stu-id="e3226-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="e3226-134">Se a reunião principal atingir a capacidade máxima e um ou mais participantes deixarem a reunião principal, a reunião principal terá capacidade disponível.</span><span class="sxs-lookup"><span data-stu-id="e3226-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="e3226-135">Os participantes que ingressarem (ou reingressarem) na reunião entrarão na reunião principal até que ela atinja sua capacidade novamente.</span><span class="sxs-lookup"><span data-stu-id="e3226-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="e3226-136">Os participantes que estão na experiência somente exibição não serão promovidos automaticamente para a reunião principal e não poderão ser promovidos manualmente para a reunião principal.</span><span class="sxs-lookup"><span data-stu-id="e3226-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="e3226-137">Se as funções de apresentador e participante foram definidas e um apresentador tenta ingressar em uma reunião depois que a reunião principal tiver atingido a capacidade, ele ingressará como um participante somente para exibição e terá as mesmas limitações que outros participantes somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="e3226-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="e3226-138">Suporte para garantir que todos os apresentadores participem da reunião principal serão colocados em uma data posterior.</span><span class="sxs-lookup"><span data-stu-id="e3226-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="e3226-139">O organizador sempre terá espaço garantido na reunião principal.</span><span class="sxs-lookup"><span data-stu-id="e3226-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="e3226-140">Impacto para apresentadores e organizadores de reuniões</span><span class="sxs-lookup"><span data-stu-id="e3226-140">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="e3226-141">As limitações para apresentadores de reunião e organizadores incluem:</span><span class="sxs-lookup"><span data-stu-id="e3226-141">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="e3226-142">Você não terá informações sobre o participante somente visualização.</span><span class="sxs-lookup"><span data-stu-id="e3226-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="e3226-143">Não oferecemos suporte ao E-discovery para participantes somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="e3226-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="e3226-144">Os usuários da reunião principal não podem ver os participantes somente de exibição.</span><span class="sxs-lookup"><span data-stu-id="e3226-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="e3226-145">Você não pode remover um participante somente visualização da reunião.</span><span class="sxs-lookup"><span data-stu-id="e3226-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="e3226-146">A contagem de participantes refletirá apenas as pessoas na reunião principal e não as pessoas na sala somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="e3226-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="e3226-147">Portanto, os apresentadores não podem obter uma contagem exata de quem está na experiência somente visualização.</span><span class="sxs-lookup"><span data-stu-id="e3226-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="e3226-148">Experiência para participantes somente visualização</span><span class="sxs-lookup"><span data-stu-id="e3226-148">Experience for view-only attendees</span></span>

<span data-ttu-id="e3226-149">A experiência do Teams apenas para visualização permite que os participantes:</span><span class="sxs-lookup"><span data-stu-id="e3226-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="e3226-150">Ouça os participantes da reunião das equipes principais.</span><span class="sxs-lookup"><span data-stu-id="e3226-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="e3226-151">Veja o feed de vídeo do locutor ativo (se o locutor ativo estiver compartilhando vídeo).</span><span class="sxs-lookup"><span data-stu-id="e3226-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="e3226-152">Consulte conteúdo compartilhado usando a funcionalidade de área de trabalho ou tela de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="e3226-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="e3226-153">O participante somente visualização não poderá experimentar as seguintes opções nas reuniões:</span><span class="sxs-lookup"><span data-stu-id="e3226-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="e3226-154">Participe da reunião se o participante não tiver permissão para ignorar o lobby com base nas políticas ou opções de lobby definidas.</span><span class="sxs-lookup"><span data-stu-id="e3226-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="e3226-155">Entre na sala somente para visualização usando a conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="e3226-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="e3226-156">Participe da sala somente exibição usando o sistema salas do Microsoft Teams ou usando serviços CVI (Cloud Video Interop).</span><span class="sxs-lookup"><span data-stu-id="e3226-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="e3226-157">Compartilhe seu áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3226-157">Share their audio or video.</span></span>
- <span data-ttu-id="e3226-158">Veja ou participe do chat da reunião.</span><span class="sxs-lookup"><span data-stu-id="e3226-158">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="e3226-159">Veja o feed de vídeo dos participantes da reunião, a menos que o participante seja o palestrante ativo.</span><span class="sxs-lookup"><span data-stu-id="e3226-159">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="e3226-160">Consulte Arquivos do PowerPoint compartilhados usando a funcionalidade do PowerPoint Live ou compartilhamentos de aplicativos individuais (diferente do compartilhamento de área de trabalho ou tela).</span><span class="sxs-lookup"><span data-stu-id="e3226-160">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="e3226-161">Levante a mão na reunião.</span><span class="sxs-lookup"><span data-stu-id="e3226-161">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="e3226-162">Enviar ou ver reações.</span><span class="sxs-lookup"><span data-stu-id="e3226-162">Send or see reactions.</span></span>
- <span data-ttu-id="e3226-163">Interaja com qualquer aplicativo 3P integrando-se à Reunião do Teams, incluindo As Votações.</span><span class="sxs-lookup"><span data-stu-id="e3226-163">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="e3226-164">Limitações do recurso somente visualização</span><span class="sxs-lookup"><span data-stu-id="e3226-164">View-only feature limitations</span></span>

- <span data-ttu-id="e3226-165">Os participantes somente para exibição poderão ver Live Captions na Área de Trabalho e na Web.</span><span class="sxs-lookup"><span data-stu-id="e3226-165">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="e3226-166">Apenas legendas em inglês são suportadas no momento.</span><span class="sxs-lookup"><span data-stu-id="e3226-166">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="e3226-167">Os participantes somente para visualização terão o suporte da tecnologia de streaming.</span><span class="sxs-lookup"><span data-stu-id="e3226-167">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="e3226-168">Os participantes somente para visualização não serão incluídos no relatório de presença.</span><span class="sxs-lookup"><span data-stu-id="e3226-168">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="e3226-169">Os participantes somente para visualização terão uma única experiência de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e3226-169">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="e3226-170">Eles podem ver o locutor ativo ou o conteúdo que está sendo compartilhado, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="e3226-170">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="e3226-171">No momento, não oferecemos suporte para **Galeria**, **Galeria grande** ou **Modo conferência** layouts para participantes somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="e3226-171">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="e3226-172">Os participantes somente para visualização não terão a mesma latência de um participante normal.</span><span class="sxs-lookup"><span data-stu-id="e3226-172">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="e3226-173"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e3226-173"><sup>1</sup></span></span>

  <span data-ttu-id="e3226-174"><sup>1</sup> Os participantes somente para visualização terão um atraso de 30 segundos de vídeo e áudio na reunião.</span><span class="sxs-lookup"><span data-stu-id="e3226-174"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
