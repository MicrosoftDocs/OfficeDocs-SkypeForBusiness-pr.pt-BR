---
title: Experiência de reunião somente para exibição
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
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
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237451"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="160fb-103">Experiência de reunião somente para exibição do Teams</span><span class="sxs-lookup"><span data-stu-id="160fb-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="160fb-104">A experiência de reunião somente para exibição estará disponível no início de março de 2021.</span><span class="sxs-lookup"><span data-stu-id="160fb-104">View-only meeting experience will be available in early March 2021.</span></span>

> [!Note]
> <span data-ttu-id="160fb-105">Aumentamos temporariamente a experiência somente para exibição para 20.000 participantes, mas reverteremos o suporte para 10.000 participantes em 30 de junho de 2021.</span><span class="sxs-lookup"><span data-stu-id="160fb-105">We've temporarily increased view-only experience for 20,000 attendees, but we'll revert support to 10,000 attendees on June 30, 2021.</span></span>

<span data-ttu-id="160fb-106">O Microsoft Teams permite que até 10.000 participantes participem de uma reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="160fb-106">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="160fb-107">Depois que a capacidade da reunião principal tiver sido atingida, os participantes adicionais ingressarão com uma experiência somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-107">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="160fb-108">Os participantes que ingressarem na reunião primeiro, até a capacidade da reunião, terão a experiência completa de reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="160fb-108">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="160fb-109">Eles podem compartilhar áudio e vídeo, ver vídeos compartilhados e participar do chat da reunião.</span><span class="sxs-lookup"><span data-stu-id="160fb-109">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="160fb-110">Os participantes que ingressarem depois que a capacidade principal da reunião tiver sido atingido terão uma experiência somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-110">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="160fb-111">Temos suporte móvel completo para Android e iOS para um participante ingressar.</span><span class="sxs-lookup"><span data-stu-id="160fb-111">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="160fb-112">O limite atual para o número de pessoas que podem conversar e ligar para uma reunião é 300 na WW e 250 no GCC, GCC High e DoD.</span><span class="sxs-lookup"><span data-stu-id="160fb-112">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="160fb-113">A experiência somente para exibição é habilitada por padrão para qualquer organizador que tenha SKU E3/E5/A3/A5.</span><span class="sxs-lookup"><span data-stu-id="160fb-113">The view-only experience is enabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="160fb-114">Nenhuma configuração ou configuração é necessária.</span><span class="sxs-lookup"><span data-stu-id="160fb-114">No further configuration or setup is required.</span></span>

### <a name="disable-teams-view-only-experience"></a><span data-ttu-id="160fb-115">Desabilitar a experiência somente para exibição do Teams</span><span class="sxs-lookup"><span data-stu-id="160fb-115">Disable Teams view-only experience</span></span>

<span data-ttu-id="160fb-116">Os administradores podem desabilitar a experiência somente para exibição usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="160fb-116">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="160fb-117">No futuro, também será possível que os administradores desabilitem a experiência somente para exibição no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="160fb-117">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="160fb-118">Impacto para os usuários</span><span class="sxs-lookup"><span data-stu-id="160fb-118">Impact to users</span></span>

<span data-ttu-id="160fb-119">A experiência de um usuário variará dependendo de vários fatores.</span><span class="sxs-lookup"><span data-stu-id="160fb-119">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="160fb-120">Quando a capacidade da reunião principal tiver sido atingida, um participante não poderá ingressar na reunião se qualquer um dos seguintes fatores for verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="160fb-120">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="160fb-121">Um administrador desabilitou a experiência somente para exibição do Teams.</span><span class="sxs-lookup"><span data-stu-id="160fb-121">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="160fb-122">O participante não tem permissão para ignorar o lobby.</span><span class="sxs-lookup"><span data-stu-id="160fb-122">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="160fb-123">Quando a capacidade da reunião principal for atingida, o organizador da reunião e os apresentadores verão uma faixa informando que a capacidade da reunião foi atingida e que novos participantes ingressarão em um participante somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-123">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![a confusão entre o cliente e a faixa do Teams para organizadores e apresentadores](media/chat-and-banner-message.png)

<span data-ttu-id="160fb-125">Quando a capacidade da reunião principal tiver sido atingida, os participantes da reunião serão informados na tela de pré-entrada de que estão in ingressar no modo somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-125">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![a tela de pré-participação do Teams e a mensagem para os participantes dizendo que eles ingressarão no modo somente exibição](media/view-only-pre-join-screen.png)

<span data-ttu-id="160fb-127">Se houver espaço, um usuário sempre ingressará na reunião principal.</span><span class="sxs-lookup"><span data-stu-id="160fb-127">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="160fb-128">Se a reunião principal atingir a capacidade e um ou mais participantes saírem da reunião principal, a reunião principal terá capacidade disponível.</span><span class="sxs-lookup"><span data-stu-id="160fb-128">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="160fb-129">Os participantes que ingressarem (ou reaparecer) na reunião ingressarão na reunião principal até que ela atinja a capacidade novamente.</span><span class="sxs-lookup"><span data-stu-id="160fb-129">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="160fb-130">Os participantes que estão na experiência somente para exibição não serão promovidos automaticamente para a reunião principal e não podem ser promovidos manualmente para a reunião principal.</span><span class="sxs-lookup"><span data-stu-id="160fb-130">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="160fb-131">Se as funções de apresentador/participante não foram definidas, os espaços na reunião principal serão preenchidos por primeira vez.</span><span class="sxs-lookup"><span data-stu-id="160fb-131">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="160fb-132">Depois que a capacidade de reunião tiver sido atingida, todos os outros usuários ingressarão com uma experiência somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-132">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="160fb-133">Impacto nos apresentadores da reunião</span><span class="sxs-lookup"><span data-stu-id="160fb-133">Impact to meeting presenters</span></span>

<span data-ttu-id="160fb-134">Reservaremos espaço na reunião normal para usuários explicitamente indicados como apresentadores nas opções da reunião.</span><span class="sxs-lookup"><span data-stu-id="160fb-134">We'll reserve space in the normal meeting for users explicitly indicated as presenters in the meeting options.</span></span> <span data-ttu-id="160fb-135">Se um apresentador sair e depois reapresentar a reunião, ele será deixado na reunião como apresentador.</span><span class="sxs-lookup"><span data-stu-id="160fb-135">If a presenter leaves and then later rejoins the meeting, they'll be let into the meeting as a presenter.</span></span>

<span data-ttu-id="160fb-136">As limitações para apresentadores de reunião incluem:</span><span class="sxs-lookup"><span data-stu-id="160fb-136">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="160fb-137">Você não terá nenhuma informação sobre o participante somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-137">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="160fb-138">Não há suporte para descoberta de E para participantes somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-138">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="160fb-139">Os usuários não podem ver os participantes somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-139">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="160fb-140">Não é possível remover um participante somente para exibição da reunião.</span><span class="sxs-lookup"><span data-stu-id="160fb-140">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="160fb-141">A contagem de participantes refletirá apenas as pessoas na reunião e não as pessoas na sala excedente.</span><span class="sxs-lookup"><span data-stu-id="160fb-141">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="160fb-142">Portanto, os apresentadores não conseguem obter uma contagem exata de quem está na experiência somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-142">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="160fb-143">Experiência para participantes somente para exibição</span><span class="sxs-lookup"><span data-stu-id="160fb-143">Experience for view-only attendees</span></span>

<span data-ttu-id="160fb-144">A experiência somente para exibição do Teams permite que os participantes:</span><span class="sxs-lookup"><span data-stu-id="160fb-144">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="160fb-145">Ouça os participantes da reunião principal do Teams.</span><span class="sxs-lookup"><span data-stu-id="160fb-145">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="160fb-146">Veja o feed de vídeo do alto-falante ativo (se o alto-falante ativo estiver compartilhando vídeo).</span><span class="sxs-lookup"><span data-stu-id="160fb-146">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="160fb-147">Veja o conteúdo sendo compartilhado usando a funcionalidade compartilhar da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="160fb-147">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="160fb-148">O participante somente para exibição não poderá experimentar as seguintes opções em reuniões:</span><span class="sxs-lookup"><span data-stu-id="160fb-148">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="160fb-149">In join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span><span class="sxs-lookup"><span data-stu-id="160fb-149">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="160fb-150">In join the Overflow Room via AudioConferência.</span><span class="sxs-lookup"><span data-stu-id="160fb-150">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="160fb-151">In join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI).</span><span class="sxs-lookup"><span data-stu-id="160fb-151">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="160fb-152">In join the Overflow Room via the Teams Android mobile app.</span><span class="sxs-lookup"><span data-stu-id="160fb-152">Join the Overflow Room via the Teams Android mobile app.</span></span>
- <span data-ttu-id="160fb-153">Compartilhe seu áudio ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="160fb-153">Share their audio or video.</span></span>
- <span data-ttu-id="160fb-154">Veja ou participe do chat da reunião.</span><span class="sxs-lookup"><span data-stu-id="160fb-154">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="160fb-155">Veja o feed de vídeo dos participantes da reunião, a menos que o participante seja o orador ativo.</span><span class="sxs-lookup"><span data-stu-id="160fb-155">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="160fb-156">Veja arquivos do PowerPoint que são compartilhados usando a funcionalidade nativa do PowerPoint ou compartilhamentos de aplicativos individuais (além do compartilhamento de área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="160fb-156">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="160fb-157">Limitações de recursos somente para exibição</span><span class="sxs-lookup"><span data-stu-id="160fb-157">View-only feature limitations</span></span>

- <span data-ttu-id="160fb-158">Os participantes somente para exibição sempre verão legendas ao vivo, independentemente da configuração de legendas ao vivo para essa reunião.</span><span class="sxs-lookup"><span data-stu-id="160fb-158">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="160fb-159">No momento, só há suporte para legendas em inglês.</span><span class="sxs-lookup"><span data-stu-id="160fb-159">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="160fb-160">Os participantes somente para exibição terão suporte de tecnologia de streaming.</span><span class="sxs-lookup"><span data-stu-id="160fb-160">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="160fb-161">Os participantes somente para exibição não serão incluídos no relatório de presença.</span><span class="sxs-lookup"><span data-stu-id="160fb-161">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="160fb-162">Os participantes somente para exibição terão uma única experiência com vídeo.</span><span class="sxs-lookup"><span data-stu-id="160fb-162">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="160fb-163">Eles podem ver o orador ativo ou o conteúdo que está sendo compartilhado, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="160fb-163">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="160fb-164">No momento, não há suporte para  layouts de **modo Galeria,** Galeria Grande ou Modo Juntos para participantes somente para exibição.</span><span class="sxs-lookup"><span data-stu-id="160fb-164">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="160fb-165">Os participantes somente para exibição não terão a mesma latência que um participante comum.</span><span class="sxs-lookup"><span data-stu-id="160fb-165">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="160fb-166"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="160fb-166"><sup>1</sup></span></span>

  <span data-ttu-id="160fb-167"><sup>1</sup> Os participantes somente para exibição terão um atraso de áudio e vídeo de 30 segundos na reunião.</span><span class="sxs-lookup"><span data-stu-id="160fb-167"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="160fb-168">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="160fb-168">Related topics</span></span>

- [<span data-ttu-id="160fb-169">Complemento de comunicações avançadas para o Teams</span><span class="sxs-lookup"><span data-stu-id="160fb-169">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="160fb-170">Especificações e limites do Teams</span><span class="sxs-lookup"><span data-stu-id="160fb-170">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
