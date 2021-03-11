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
ms.openlocfilehash: 9fd67ce67d31effdba0d152a3d5920bb17f23b25
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615161"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a><span data-ttu-id="81876-103">Políticas de gravação de eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81876-103">Live event recording policies in Microsoft Teams</span></span>

<span data-ttu-id="81876-104">Você tem várias opções para gravar um evento ao vivo do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81876-104">You have several options for recording a Microsoft Teams live event.</span></span> <span data-ttu-id="81876-105">As opções de gravação são definidas usando políticas de gravação.</span><span class="sxs-lookup"><span data-stu-id="81876-105">The recording options are set using recording policies.</span></span> <span data-ttu-id="81876-106">Este artigo descreve as várias configurações.</span><span class="sxs-lookup"><span data-stu-id="81876-106">This article describes the various settings.</span></span>

<span data-ttu-id="81876-107">As opções de gravação são definidas usando o comando [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps) de comando do PowerShell</span><span class="sxs-lookup"><span data-stu-id="81876-107">The recording options are set using the PowerShell command [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)</span></span>

## <a name="scheduling-and-option-behaviors"></a><span data-ttu-id="81876-108">Agendamento e comportamentos de opção</span><span class="sxs-lookup"><span data-stu-id="81876-108">Scheduling and option behaviors</span></span>

<span data-ttu-id="81876-109">Há duas opções de organizador durante o agendamento de uma gravação de eventos ao vivo:</span><span class="sxs-lookup"><span data-stu-id="81876-109">There are two organizer options while scheduling a live event recording:</span></span>

- <span data-ttu-id="81876-110">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="81876-110">Recording available for producers and presenters</span></span>

  - <span data-ttu-id="81876-111">Arquivo de gravação: fornece um arquivo de gravação que os produtores e apresentadores podem baixar depois que o evento acabar.</span><span class="sxs-lookup"><span data-stu-id="81876-111">Recording file: Provides a recording file that producers and presenters can download after the event is over.</span></span>

- <span data-ttu-id="81876-112">Gravação disponível para participantes</span><span class="sxs-lookup"><span data-stu-id="81876-112">Recording available for attendees</span></span>

  - <span data-ttu-id="81876-113">DVR: um gravador de vídeo digital (DVR) permite que os participantes rebobinem e pausem durante o evento</span><span class="sxs-lookup"><span data-stu-id="81876-113">DVR: A digital video recorder (DVR) allows attendees to rewind and pause during the event</span></span>

  - <span data-ttu-id="81876-114">VOD: um vídeo sob demanda (VOD) permite que os participantes assistam após o evento ter acabado</span><span class="sxs-lookup"><span data-stu-id="81876-114">VOD: A video on demand (VOD) allows attendees to watch after the event is over</span></span>

## <a name="broadcast-recording-policy-setting"></a><span data-ttu-id="81876-115">Configuração da política de gravação de transmissão</span><span class="sxs-lookup"><span data-stu-id="81876-115">Broadcast recording policy setting</span></span>

<span data-ttu-id="81876-116">Como parte da política de transmissão, há uma configuração que você pode alternar para ativar ou desativar a gravação para um evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="81876-116">As part of the broadcast policy, there's a setting that you can toggle to turn recording on or off for a live event.</span></span>

|                                 | <span data-ttu-id="81876-117">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="81876-117">Recording available for producers and presenters</span></span> | <span data-ttu-id="81876-118">Gravação disponível para participantes</span><span class="sxs-lookup"><span data-stu-id="81876-118">Recording available for attendees</span></span> |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| <span data-ttu-id="81876-119">Sempre gravar</span><span class="sxs-lookup"><span data-stu-id="81876-119">Always record</span></span>               | <span data-ttu-id="81876-120">Desabilitado e selecionado</span><span class="sxs-lookup"><span data-stu-id="81876-120">Disabled and selected</span></span>                                | <span data-ttu-id="81876-121">Desabilitado e selecionado</span><span class="sxs-lookup"><span data-stu-id="81876-121">Disabled and selected</span></span>         |
| <span data-ttu-id="81876-122">O organizador pode gravar ou não</span><span class="sxs-lookup"><span data-stu-id="81876-122">Organizer can record or not</span></span> | <span data-ttu-id="81876-123">Habilitado e não selecionado por padrão</span><span class="sxs-lookup"><span data-stu-id="81876-123">Enabled and not selected by default</span></span>                  | <span data-ttu-id="81876-124">Habilitado e não selecionado por padrão</span><span class="sxs-lookup"><span data-stu-id="81876-124">Enabled and not selected by default</span></span>   |
| <span data-ttu-id="81876-125">Nunca gravar</span><span class="sxs-lookup"><span data-stu-id="81876-125">Never record</span></span>               | <span data-ttu-id="81876-126">Desabilitado e não selecionado</span><span class="sxs-lookup"><span data-stu-id="81876-126">Disabled and not selected</span></span>                            | <span data-ttu-id="81876-127">Desabilitado e não selecionado</span><span class="sxs-lookup"><span data-stu-id="81876-127">Disabled and not selected</span></span>      |

<span data-ttu-id="81876-128">Quando a política é definida como **Sempre registrar**, a página de política tem as seguintes opções selecionadas:</span><span class="sxs-lookup"><span data-stu-id="81876-128">When the policy is set to **Always record**, the policy page has the following selected options:</span></span>

<span data-ttu-id="81876-129">![configurações de política de eventos ao vivo](../media/live-event-recording-policy.png "Captura de tela de configurações de política de eventos ao vivo no centro de administração do Microsoft Teams")</span><span class="sxs-lookup"><span data-stu-id="81876-129">![live events policy settings](../media/live-event-recording-policy.png "Screen shot of live events policy settings in the Microsoft Teams admin center")</span></span>

## <a name="storage-and-persistence-behavior"></a><span data-ttu-id="81876-130">Comportamento de armazenamento e persistência</span><span class="sxs-lookup"><span data-stu-id="81876-130">Storage and persistence behavior</span></span>

| <span data-ttu-id="81876-131">Opção</span><span class="sxs-lookup"><span data-stu-id="81876-131">Option</span></span>                                       | <span data-ttu-id="81876-132">Estado</span><span class="sxs-lookup"><span data-stu-id="81876-132">State</span></span>   | <span data-ttu-id="81876-133">DVR</span><span class="sxs-lookup"><span data-stu-id="81876-133">DVR</span></span>                                                   | <span data-ttu-id="81876-134">VOD</span><span class="sxs-lookup"><span data-stu-id="81876-134">VOD</span></span>                                                     | <span data-ttu-id="81876-135">Gravando</span><span class="sxs-lookup"><span data-stu-id="81876-135">Recording</span></span>                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| <span data-ttu-id="81876-136">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="81876-136">Recording available to producers and presenters</span></span> | <span data-ttu-id="81876-137">Selecionado</span><span class="sxs-lookup"><span data-stu-id="81876-137">Selected</span></span>     | <span data-ttu-id="81876-138">O DVR está disponível e o ativo do Azure Media Services (AMS) é armazenado por 180 dias</span><span class="sxs-lookup"><span data-stu-id="81876-138">DVR is available and the Azure Media Services (AMS) asset is stored for 180 days</span></span> | <span data-ttu-id="81876-139">O participante pode acessar e assistir ao evento</span><span class="sxs-lookup"><span data-stu-id="81876-139">Attendee can access and watch the event</span></span>                     |                              |
|                                                  | <span data-ttu-id="81876-140">Não Selecionado</span><span class="sxs-lookup"><span data-stu-id="81876-140">Not Selected</span></span> | <span data-ttu-id="81876-141">O DVR está disponível e o ativo AMS é armazenado por 180 dias</span><span class="sxs-lookup"><span data-stu-id="81876-141">DVR is available and the AMS asset is stored for 180 days</span></span> | <span data-ttu-id="81876-142">O participante não terá acesso ao evento após o fim</span><span class="sxs-lookup"><span data-stu-id="81876-142">Attendee won't get access into the event after it's over</span></span> |                              |
||<span data-ttu-id="81876-143">Desabilitado (Não selecionado)</span><span class="sxs-lookup"><span data-stu-id="81876-143">Disabled (Not selected)</span></span>|<span data-ttu-id="81876-144">DVR está disponível e o ativo AMS é excluído após o evento</span><span class="sxs-lookup"><span data-stu-id="81876-144">DVR is available and the AMS asset is deleted after the event</span></span>|<span data-ttu-id="81876-145">O participante não terá acesso ao evento após o fim</span><span class="sxs-lookup"><span data-stu-id="81876-145">Attendee won't get access into the event after it's over</span></span>||
| <span data-ttu-id="81876-146">Gravação disponível para produtores e apresentadores</span><span class="sxs-lookup"><span data-stu-id="81876-146">Recording available to producers and presenters</span></span> | <span data-ttu-id="81876-147">Selecionado</span><span class="sxs-lookup"><span data-stu-id="81876-147">Selected</span></span>     |                                                           |                                                             | <span data-ttu-id="81876-148">Um MP4 é criado e armazenado</span><span class="sxs-lookup"><span data-stu-id="81876-148">An MP4 is created and stored</span></span> |
|                                                  | <span data-ttu-id="81876-149">Não Selecionado</span><span class="sxs-lookup"><span data-stu-id="81876-149">Not Selected</span></span> |                                                           |                                                             | <span data-ttu-id="81876-150">Nenhum arquivo é criado</span><span class="sxs-lookup"><span data-stu-id="81876-150">No file is created</span></span>           |

### <a name="related-topics"></a><span data-ttu-id="81876-151">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="81876-151">Related topics</span></span>

- [<span data-ttu-id="81876-152">O que são eventos ao vivo do Teams?</span><span class="sxs-lookup"><span data-stu-id="81876-152">What is Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="81876-153">Planejar eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="81876-153">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="81876-154">Definir configurações de eventos ao vivo do Teams</span><span class="sxs-lookup"><span data-stu-id="81876-154">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
- [<span data-ttu-id="81876-155">Gravação de reunião de nuvens do Teams</span><span class="sxs-lookup"><span data-stu-id="81876-155">Teams clouds meeting recording</span></span>](../cloud-recording.md)
