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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875051"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="b7dc7-103">Experiência de reunião somente para visualização de Teams</span><span class="sxs-lookup"><span data-stu-id="b7dc7-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="b7dc7-104">As transmissões somente para visualização estão disponíveis no Microsoft 365 E3/E5 e Microsoft 365 A3/A5.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="b7dc7-105">Este recurso será habilitado em 1º de março de 2021 como DESLIGADO padrão.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="b7dc7-106">O recurso no Microsoft 365 Government Community Cloud (GCC) começará a ser implementado no final de março de 2021.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="b7dc7-107">Government Community Cloud High (GCCH) e Department of Defense (DoD) serão implementados posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="b7dc7-108">Você deve alterar a política padrão após essa data se quiser que o recurso seja ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="b7dc7-109">Use o Windows PowerShell para habilitar a política `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="b7dc7-110">Se a sua reunião ou webinar atingir a capacidade máxima, o Teams será perfeitamente escalado para acomodar uma experiência de transmissão somente visualização para 10.000 pessoas.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="b7dc7-111">Além disso, durante este período de maior trabalho remoto, aproveite as transmissões ainda maiores para 20.000 pessoas até o final deste ano.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="b7dc7-112">O Microsoft Teams permite que até 10.000 participantes participem de uma reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="b7dc7-113">Depois que a capacidade da reunião principal for atingida, os participantes adicionais entrarão em uma experiência somente de visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="b7dc7-114">Os participantes que ingressarem primeiro na reunião, até a capacidade máxima da reunião, terão a experiência completa de reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="b7dc7-115">Eles podem compartilhar áudio e vídeo, ver vídeos compartilhados e participar do bate-papo da reunião.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="b7dc7-116">Os participantes que ingressarem depois que a capacidade da reunião principal for atingida terão uma experiência somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="b7dc7-117">Temos suporte móvel completo para Android e iOS para a adesão de um participante.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="b7dc7-118">O limite atual para o número de pessoas que podem bater papo e ligar para uma reunião é 300 na WW e 250 no GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="b7dc7-119">A experiência somente visualização é desabilitada por padrão para qualquer organizador que tenha E3/E5/A3/A5 SKU.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="b7dc7-120">Nenhuma configuração ou instalação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="b7dc7-121">Desativar experiência somente para visualização do Teams</span><span class="sxs-lookup"><span data-stu-id="b7dc7-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="b7dc7-122">Os administradores podem desabilitar a experiência somente visualização usando o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="b7dc7-123">No futuro, os administradores também poderão desativar a experiência somente visualização no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="b7dc7-124">Impacto nos usuários</span><span class="sxs-lookup"><span data-stu-id="b7dc7-124">Impact to users</span></span>

<span data-ttu-id="b7dc7-125">A experiência de um usuário varia de acordo com vários fatores.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="b7dc7-126">Quando a capacidade da reunião principal for atingida, um participante não poderá participar da reunião se alguma das seguintes condições for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="b7dc7-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="b7dc7-127">Um administrador desativou a experiência somente visualização do Teams.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="b7dc7-128">O participante não tem permissão para ignorar o saguão.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="b7dc7-129">Quando a capacidade da reunião principal for atingida, o organizador da reunião e os apresentadores verão um banner informando que a capacidade da reunião foi atingida e que os novos participantes ingressarão em um participante somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![o cliente do Teams e a mensagem do banner para organizadores e apresentadores](media/chat-and-banner-message.png)

<span data-ttu-id="b7dc7-131">Quando a capacidade da reunião principal for atingida, os participantes da reunião serão informados na tela de pré-entrada que eles estão entrando no modo somente visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![a tela de pré-adesão das equipes e a mensagem para os participantes informando que eles entrarão no modo somente visualização](media/view-only-pre-join-screen.png)

<span data-ttu-id="b7dc7-133">Se houver espaço, um usuário sempre participará da reunião principal.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="b7dc7-134">Se a reunião principal atingir a capacidade máxima e um ou mais participantes deixarem a reunião principal, a reunião principal terá capacidade disponível.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="b7dc7-135">Os participantes que ingressarem (ou reingressarem) na reunião entrarão na reunião principal até que ela atinja sua capacidade novamente.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="b7dc7-136">Os participantes que estão na experiência somente visualização não serão promovidos automaticamente para a reunião principal e não podem ser promovidos manualmente para a reunião principal no momento.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="b7dc7-137">Se as funções de apresentador / participante não tiverem sido definidas, os espaços na reunião principal serão preenchidos por ordem de chegada.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="b7dc7-138">Assim que a capacidade de reunião for atingida, todos os outros usuários ingressarão com uma experiência somente visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="b7dc7-139">Impacto para os apresentadores da reunião</span><span class="sxs-lookup"><span data-stu-id="b7dc7-139">Impact to meeting presenters</span></span>

<span data-ttu-id="b7dc7-140">As limitações para apresentadores de reuniões incluem:</span><span class="sxs-lookup"><span data-stu-id="b7dc7-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="b7dc7-141">Você não terá informações sobre o participante somente visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="b7dc7-142">Não oferecemos suporte ao E-discovery para participantes somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="b7dc7-143">Os usuários não podem ver os participantes somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="b7dc7-144">Você não pode remover um participante somente visualização da reunião.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="b7dc7-145">A contagem de participantes refletirá apenas as pessoas na reunião e não as pessoas na sala somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="b7dc7-146">Portanto, os apresentadores não podem obter uma contagem exata de quem está na experiência somente visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="b7dc7-147">Experiência para participantes somente visualização</span><span class="sxs-lookup"><span data-stu-id="b7dc7-147">Experience for view-only attendees</span></span>

<span data-ttu-id="b7dc7-148">A experiência do Teams apenas para visualização permite que os participantes:</span><span class="sxs-lookup"><span data-stu-id="b7dc7-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="b7dc7-149">Ouça os participantes da reunião das equipes principais.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="b7dc7-150">Veja o feed de vídeo do locutor ativo (se o locutor ativo estiver compartilhando vídeo).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="b7dc7-151">Veja o conteúdo sendo compartilhado usando a funcionalidade de compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="b7dc7-152">O participante somente visualização não poderá experimentar as seguintes opções nas reuniões:</span><span class="sxs-lookup"><span data-stu-id="b7dc7-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="b7dc7-153">Participe da reunião se o participante não tiver permissão para ignorar o lobby com base nas políticas ou opções de lobby definidas.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="b7dc7-154">Entre na sala somente para visualização usando a conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="b7dc7-155">Participe da sala somente para visualização usando o sistema Sala do Microsoft Teams ou os serviços Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="b7dc7-156">Compartilhe seu áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-156">Share their audio or video.</span></span>
- <span data-ttu-id="b7dc7-157">Veja ou participe do chat da reunião.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="b7dc7-158">Veja o feed de vídeo dos participantes da reunião, a menos que o participante seja o palestrante ativo.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="b7dc7-159">Consulte os arquivos do PowerPoint que são compartilhados usando a funcionalidade de compartilhamento nativo do PowerPoint ou compartilhamentos de aplicativos individuais (diferente do compartilhamento da área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="b7dc7-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="b7dc7-160">Limitações do recurso somente visualização</span><span class="sxs-lookup"><span data-stu-id="b7dc7-160">View-only feature limitations</span></span>

- <span data-ttu-id="b7dc7-161">Os participantes somente para visualização sempre verão as legendas ao vivo, independentemente da configuração das legendas ao vivo para aquela reunião.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="b7dc7-162">Apenas legendas em inglês são suportadas no momento.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="b7dc7-163">Os participantes somente para visualização terão o suporte da tecnologia de streaming.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="b7dc7-164">Os participantes somente para visualização não serão incluídos no relatório de presença.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="b7dc7-165">Os participantes somente para visualização terão uma única experiência de vídeo.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="b7dc7-166">Eles podem ver o locutor ativo ou o conteúdo que está sendo compartilhado, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="b7dc7-167">No momento, não oferecemos suporte para **Galeria**, **Galeria grande** ou **Modo conferência** layouts para participantes somente para visualização.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="b7dc7-168">Os participantes somente para visualização não terão a mesma latência de um participante normal.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="b7dc7-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b7dc7-169"><sup>1</sup></span></span>

  <span data-ttu-id="b7dc7-170"><sup>1</sup> Os participantes somente para visualização terão um atraso de 30 segundos de vídeo e áudio na reunião.</span><span class="sxs-lookup"><span data-stu-id="b7dc7-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
