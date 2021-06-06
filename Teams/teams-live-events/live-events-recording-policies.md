---
title: Políticas de gravação de eventos ao vivo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Saiba mais sobre políticas de gravação de eventos ao vivo.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8d25f37f94a514b83bd37e44d1b022bac064a839
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739651"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="26bfe-103">Políticas de gravação de eventos ao vivo Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="26bfe-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="26bfe-104">Você tem várias opções para gravar um evento Microsoft Teams ao vivo.</span><span class="sxs-lookup"><span data-stu-id="26bfe-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="26bfe-105">As opções de gravação são definidas usando políticas de gravação.</span><span class="sxs-lookup"><span data-stu-id="26bfe-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="26bfe-106">Este artigo descreve as várias configurações.</span><span class="sxs-lookup"><span data-stu-id="26bfe-106">This article describes the various settings.</span></span>

<span data-ttu-id="26bfe-107">As opções de gravação são definidas usando o comando Do PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="26bfe-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="26bfe-108">Agendamento e comportamentos de opção</span><span class="sxs-lookup"><span data-stu-id="26bfe-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="26bfe-109">Há duas opções de organizador durante o agendamento de uma gravação de eventos ao vivo:</span><span class="sxs-lookup"><span data-stu-id="26bfe-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="26bfe-110">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="26bfe-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="26bfe-111">Arquivo de gravação: fornece um arquivo de gravação que os produtores e apresentadores podem baixar depois que o evento acabar.</span><span class="sxs-lookup"><span data-stu-id="26bfe-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="26bfe-112">Gravação disponível para participantes</span><span class="sxs-lookup"><span data-stu-id="26bfe-112">Recording available for attendees</span></span>

  - <span data-ttu-id="26bfe-113">DVR: um gravador de vídeo digital (DVR) permite que os participantes rebobinem e pausem durante o evento</span><span class="sxs-lookup"><span data-stu-id="26bfe-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="26bfe-114">VOD: um vídeo sob demanda (VOD) permite que os participantes assistam após o evento ter acabado</span><span class="sxs-lookup"><span data-stu-id="26bfe-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="26bfe-115">Configuração da política de gravação de transmissão</span><span class="sxs-lookup"><span data-stu-id="26bfe-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="26bfe-116">Como parte da política de transmissão, há uma configuração que você pode alternar para ativar ou desativar a gravação para um evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="26bfe-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="26bfe-117">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="26bfe-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="26bfe-118">Gravação disponível para participantes</span><span class="sxs-lookup"><span data-stu-id="26bfe-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="26bfe-119">Sempre gravar</span><span class="sxs-lookup"><span data-stu-id="26bfe-119">Always record</span></span>               | <span data-ttu-id="26bfe-120">Desabilitado e selecionado</span><span class="sxs-lookup"><span data-stu-id="26bfe-120">Disabled and selected</span></span>                                | <span data-ttu-id="26bfe-121">Habilitado e selecionado</span><span class="sxs-lookup"><span data-stu-id="26bfe-121">Enabled and selected</span></span>         |
| <span data-ttu-id="26bfe-122">O organizador pode gravar ou não</span><span class="sxs-lookup"><span data-stu-id="26bfe-122">Organizer can record or not</span></span> | <span data-ttu-id="26bfe-123">Habilitado e selecionado por padrão</span><span class="sxs-lookup"><span data-stu-id="26bfe-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="26bfe-124">Habilitado e selecionado por padrão</span><span class="sxs-lookup"><span data-stu-id="26bfe-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="26bfe-125">Nunca gravar</span><span class="sxs-lookup"><span data-stu-id="26bfe-125">Never record</span></span>               | <span data-ttu-id="26bfe-126">Desabilitado e não selecionado</span><span class="sxs-lookup"><span data-stu-id="26bfe-126">Disabled and not selected</span></span>                            | <span data-ttu-id="26bfe-127">Desabilitado e não selecionado</span><span class="sxs-lookup"><span data-stu-id="26bfe-127">Disabled and not selected</span></span>      |

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="26bfe-128">Armazenamento e comportamento de persistência</span><span class="sxs-lookup"><span data-stu-id="26bfe-128">Storage and persistence behavior</span></span>

| <span data-ttu-id="26bfe-129">Opção</span><span class="sxs-lookup"><span data-stu-id="26bfe-129">Option</span></span>                                       | <span data-ttu-id="26bfe-130">Estado</span><span class="sxs-lookup"><span data-stu-id="26bfe-130">State</span></span>   | <span data-ttu-id="26bfe-131">DVR</span><span class="sxs-lookup"><span data-stu-id="26bfe-131">DVR</span></span>                                                   | <span data-ttu-id="26bfe-132">VOD</span><span class="sxs-lookup"><span data-stu-id="26bfe-132">VOD</span></span>                                                     | <span data-ttu-id="26bfe-133">Gravando</span><span class="sxs-lookup"><span data-stu-id="26bfe-133">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="26bfe-134">Gravação disponível para participantes</span><span class="sxs-lookup"><span data-stu-id="26bfe-134">Recording available for attendees</span></span> | <span data-ttu-id="26bfe-135">Selecionado</span><span class="sxs-lookup"><span data-stu-id="26bfe-135">Selected</span></span>     | <span data-ttu-id="26bfe-136">O DVR está disponível e o ativo Serviços de Mídia do Azure (AMS) é armazenado por 180 dias</span><span class="sxs-lookup"><span data-stu-id="26bfe-136">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="26bfe-137">O participante pode acessar e assistir ao evento</span><span class="sxs-lookup"><span data-stu-id="26bfe-137">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="26bfe-138">Não Selecionado</span><span class="sxs-lookup"><span data-stu-id="26bfe-138">Not Selected</span></span> | <span data-ttu-id="26bfe-139">O DVR está disponível e o ativo AMS é armazenado por 180 dias</span><span class="sxs-lookup"><span data-stu-id="26bfe-139">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="26bfe-140">O participante não terá acesso ao evento após o fim</span><span class="sxs-lookup"><span data-stu-id="26bfe-140">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="26bfe-141">Desabilitado (Não selecionado)</span><span class="sxs-lookup"><span data-stu-id="26bfe-141">Disabled (Not selected)</span></span>|<span data-ttu-id="26bfe-142">DVR está disponível e o ativo AMS é excluído após o evento</span><span class="sxs-lookup"><span data-stu-id="26bfe-142">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="26bfe-143">O participante não terá acesso ao evento após o fim</span><span class="sxs-lookup"><span data-stu-id="26bfe-143">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="26bfe-144">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="26bfe-144">Recording available to producers and presenters</span></span> | <span data-ttu-id="26bfe-145">Selecionado</span><span class="sxs-lookup"><span data-stu-id="26bfe-145">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="26bfe-146">Um MP4 é criado e armazenado</span><span class="sxs-lookup"><span data-stu-id="26bfe-146">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="26bfe-147">Não Selecionado</span><span class="sxs-lookup"><span data-stu-id="26bfe-147">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="26bfe-148">Nenhum arquivo é criado</span><span class="sxs-lookup"><span data-stu-id="26bfe-148">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="26bfe-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="26bfe-149">Related topics</span></span>

- [<span data-ttu-id="26bfe-150">O que são eventos ao vivo de Teams?</span><span class="sxs-lookup"><span data-stu-id="26bfe-150">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="26bfe-151">Planejar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="26bfe-151">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="26bfe-152">Definir configurações de eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="26bfe-152">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="26bfe-153">Teams de reunião de nuvens</span><span class="sxs-lookup"><span data-stu-id="26bfe-153">Teams clouds meeting recording</span></span>](../cloud-recording.md)
