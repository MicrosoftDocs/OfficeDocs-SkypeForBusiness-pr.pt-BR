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
ms.openlocfilehash: f9654c139433ffa764767e0a2140896eab52204b
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513844"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="77587-103">Políticas de gravação de eventos ao vivo Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77587-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="77587-104">Você tem várias opções para gravar um evento Microsoft Teams ao vivo.</span><span class="sxs-lookup"><span data-stu-id="77587-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="77587-105">As opções de gravação são definidas usando políticas de gravação.</span><span class="sxs-lookup"><span data-stu-id="77587-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="77587-106">Este artigo descreve as várias configurações.</span><span class="sxs-lookup"><span data-stu-id="77587-106">This article describes the various settings.</span></span>

<span data-ttu-id="77587-107">As opções de gravação são definidas usando o comando Do PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77587-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps).</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="77587-108">Agendamento e comportamentos de opção</span><span class="sxs-lookup"><span data-stu-id="77587-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="77587-109">Há duas opções de organizador durante o agendamento de uma gravação de eventos ao vivo:</span><span class="sxs-lookup"><span data-stu-id="77587-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="77587-110">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="77587-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="77587-111">Arquivo de gravação: fornece um arquivo de gravação que os produtores e apresentadores podem baixar depois que o evento acabar.</span><span class="sxs-lookup"><span data-stu-id="77587-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="77587-112">Gravação disponível para participantes</span><span class="sxs-lookup"><span data-stu-id="77587-112">Recording available for attendees</span></span>

  - <span data-ttu-id="77587-113">DVR: um gravador de vídeo digital (DVR) permite que os participantes rebobinem e pausem durante o evento</span><span class="sxs-lookup"><span data-stu-id="77587-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="77587-114">VOD: um vídeo sob demanda (VOD) permite que os participantes assistam após o evento ter acabado</span><span class="sxs-lookup"><span data-stu-id="77587-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="77587-115">Configuração da política de gravação de transmissão</span><span class="sxs-lookup"><span data-stu-id="77587-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="77587-116">Como parte da política de transmissão, há uma configuração que você pode alternar para ativar ou desativar a gravação para um evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="77587-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="77587-117">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="77587-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="77587-118">Gravação disponível para participantes</span><span class="sxs-lookup"><span data-stu-id="77587-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="77587-119">Sempre gravar</span><span class="sxs-lookup"><span data-stu-id="77587-119">Always record</span></span>               | <span data-ttu-id="77587-120">Desabilitado e selecionado</span><span class="sxs-lookup"><span data-stu-id="77587-120">Disabled and selected</span></span>                                | <span data-ttu-id="77587-121">Habilitado e selecionado</span><span class="sxs-lookup"><span data-stu-id="77587-121">Enabled and selected</span></span>         |
| <span data-ttu-id="77587-122">O organizador pode gravar ou não</span><span class="sxs-lookup"><span data-stu-id="77587-122">Organizer can record or not</span></span> | <span data-ttu-id="77587-123">Habilitado e selecionado por padrão</span><span class="sxs-lookup"><span data-stu-id="77587-123">Enabled and selected by default</span></span>                  | <span data-ttu-id="77587-124">Habilitado e selecionado por padrão</span><span class="sxs-lookup"><span data-stu-id="77587-124">Enabled and selected by default</span></span>   |
| <span data-ttu-id="77587-125">Nunca gravar</span><span class="sxs-lookup"><span data-stu-id="77587-125">Never record</span></span>               | <span data-ttu-id="77587-126">Desabilitado e não selecionado</span><span class="sxs-lookup"><span data-stu-id="77587-126">Disabled and not selected</span></span>                            | <span data-ttu-id="77587-127">Desabilitado e não selecionado</span><span class="sxs-lookup"><span data-stu-id="77587-127">Disabled and not selected</span></span>      |

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="77587-128">Armazenamento e comportamento de persistência</span><span class="sxs-lookup"><span data-stu-id="77587-128">Storage and persistence behavior</span></span>

| <span data-ttu-id="77587-129">Opção</span><span class="sxs-lookup"><span data-stu-id="77587-129">Option</span></span>                                       | <span data-ttu-id="77587-130">Estado</span><span class="sxs-lookup"><span data-stu-id="77587-130">State</span></span>   | <span data-ttu-id="77587-131">DVR</span><span class="sxs-lookup"><span data-stu-id="77587-131">DVR</span></span>                                                   | <span data-ttu-id="77587-132">VOD</span><span class="sxs-lookup"><span data-stu-id="77587-132">VOD</span></span>                                                     | <span data-ttu-id="77587-133">Gravando</span><span class="sxs-lookup"><span data-stu-id="77587-133">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="77587-134">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="77587-134">Recording available to producers and presenters</span></span> | <span data-ttu-id="77587-135">Selecionado</span><span class="sxs-lookup"><span data-stu-id="77587-135">Selected</span></span>     | <span data-ttu-id="77587-136">O DVR está disponível e o ativo Serviços de Mídia do Azure (AMS) é armazenado por 180 dias</span><span class="sxs-lookup"><span data-stu-id="77587-136">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="77587-137">O participante pode acessar e assistir ao evento</span><span class="sxs-lookup"><span data-stu-id="77587-137">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="77587-138">Não Selecionado</span><span class="sxs-lookup"><span data-stu-id="77587-138">Not Selected</span></span> | <span data-ttu-id="77587-139">O DVR está disponível e o ativo AMS é armazenado por 180 dias</span><span class="sxs-lookup"><span data-stu-id="77587-139">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="77587-140">O participante não terá acesso ao evento após o fim</span><span class="sxs-lookup"><span data-stu-id="77587-140">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="77587-141">Desabilitado (Não selecionado)</span><span class="sxs-lookup"><span data-stu-id="77587-141">Disabled (Not selected)</span></span>|<span data-ttu-id="77587-142">DVR está disponível e o ativo AMS é excluído após o evento</span><span class="sxs-lookup"><span data-stu-id="77587-142">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="77587-143">O participante não terá acesso ao evento após o fim</span><span class="sxs-lookup"><span data-stu-id="77587-143">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="77587-144">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="77587-144">Recording available to producers and presenters</span></span> | <span data-ttu-id="77587-145">Selecionado</span><span class="sxs-lookup"><span data-stu-id="77587-145">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="77587-146">Um MP4 é criado e armazenado</span><span class="sxs-lookup"><span data-stu-id="77587-146">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="77587-147">Não Selecionado</span><span class="sxs-lookup"><span data-stu-id="77587-147">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="77587-148">Nenhum arquivo é criado</span><span class="sxs-lookup"><span data-stu-id="77587-148">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="77587-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="77587-149">Related topics</span></span>

- [<span data-ttu-id="77587-150">O que são eventos ao vivo de Teams?</span><span class="sxs-lookup"><span data-stu-id="77587-150">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="77587-151">Planejar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="77587-151">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="77587-152">Definir configurações de eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="77587-152">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="77587-153">Teams de reunião de nuvens</span><span class="sxs-lookup"><span data-stu-id="77587-153">Teams clouds meeting recording</span></span>](../cloud-recording.md)
